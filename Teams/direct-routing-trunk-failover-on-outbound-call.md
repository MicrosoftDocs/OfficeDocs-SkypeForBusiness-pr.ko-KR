---
title: 발신 전화에 대한 트렁크 장애 조치
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Teams에서 SBC(세션 테두리 컨트롤러)로의 아웃바운드 호출에서 트렁크 장애 조치(failover)를 처리하는 방법을 알아보려면 이 항목을 참조하세요.
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457138"
---
# <a name="trunk-failover-on-outbound-calls"></a>발신 전화에 대한 트렁크 장애 조치

이 항목에서는 Teams에서 SBC(세션 테두리 컨트롤러)로의 아웃바운드 호출에서 트렁크 장애 조치(failover)를 방지하는 방법에 대해 설명합니다.

## <a name="failover-on-network-errors"></a>네트워크 오류에 대한 장애 조치(failover)

어떤 이유로든 트렁크를 연결할 수 없는 경우 동일한 트렁크에 대한 연결은 다른 Microsoft Datacenter에서 시도됩니다. 데이터 센터는 현재 지역 외부의 다른 지역에 있을 수 있습니다. 연결이 거부되거나, TLS 시간 제한이 있거나, 다른 네트워크 수준 문제가 있는 경우 트렁크가 연결되지 않을 수 있습니다.

예를 들어 관리자가 잘 알려진 IP 주소에서만 SBC에 대한 액세스를 제한하지만 모든 Microsoft 직접 라우팅 데이터 센터의 IP 주소를 SBC의 ACL(Access Control 목록)에 두지 않으면 연결이 실패할 수 있습니다. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>SBC(세션 테두리 컨트롤러)에서 받은 특정 SIP 코드의 장애 조치(failover)

직접 라우팅이 나가는 초대에 대한 응답으로 4xx 또는 6xx SIP 오류 코드를 수신하는 경우 호출은 기본적으로 완료된 것으로 간주됩니다. 송신은 Teams 클라이언트에서 PSTN(공중 전화망)으로의 통화를 의미하며, 트래픽 흐름은 Teams 클라이언트 -> 직접 라우팅 -> SBC -> 전화 통신 네트워크입니다.

SIP 코드 목록은 [SIP(세션 시작 프로토콜) RFC](https://tools.ietf.org/html/rfc3261)에서 찾을 수 있습니다.

SBC가 "408 요청 시간 제한: 서버가 적절한 시간 내에 응답을 생성할 수 없는 경우(예: 사용자의 위치를 제시간에 확인할 수 없는 경우) 들어오는 초대에서 회신한 상황을 가정합니다. 클라이언트는 나중에 수정 없이 요청을 반복할 수 있습니다."

이 특정 SBC는 네트워크 잘못된 구성 또는 기타 오류로 인해 호출 수신자에 연결하는 데 어려움을 겪을 수 있습니다. 그러나 경로에 호출 수신자에게 연결할 수 있는 SBC가 하나 더 있습니다.

다음 다이어그램에서는 사용자가 전화번호를 호출할 때 경로에 잠재적으로 이 통화를 전달할 수 있는 두 개의 SBC가 있습니다. 처음에는 SBC1.contoso.com 호출에 대해 선택되었지만 SBC1.contoso.com 네트워크 문제로 인해 PTSN 네트워크에 연결할 수 없습니다.
기본적으로 통화는 현재 완료됩니다. 
 
![네트워크 문제로 인해 PSTN에 연결할 수 없는 SBC를 보여 주는 다이어그램](media/direct-routing-failover-response-codes1.png)

잠재적으로 호출을 전달할 수 있는 경로에 SBC가 하나 더 있습니다.
매개 변수 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`를 구성하는 경우 두 번째 SBC가 시도됩니다(다음 다이어그램에서 SBC2.contoso.com).

![두 번째 SBC로의 라우팅을 보여 주는 다이어그램](media/direct-routing-failover-response-codes2.png)

매개 변수 -FailoverResponseCodes를 설정하고 코드를 지정하면 라우팅을 미세 조정하고 네트워크 또는 기타 문제로 인해 SBC가 전화를 걸 수 없는 경우 잠재적인 문제를 방지할 수 있습니다.

기본값: 408, 503, 504

