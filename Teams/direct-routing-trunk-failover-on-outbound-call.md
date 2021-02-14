---
title: 발신 전화에 대한 트렁크 장애 조치
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 이 항목을 읽고 Teams에서 SBC(세션 테두리 컨트롤러)로의 아웃바운드 호출에서 트렁크 장애 조치(failover)를 처리하는 방법을 배워야 합니다.
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836180"
---
# <a name="trunk-failover-on-outbound-calls"></a>발신 전화에 대한 트렁크 장애 조치

이 항목에서는 Teams에서 SBC(세션 테두리 컨트롤러)로의 아웃바운드 호출에서 트렁크 장애 조치(failover)를 방지하는 방법을 설명하고 있습니다.

## <a name="failover-on-network-errors"></a>네트워크 오류에 대한 장애 조치

어떤 이유로든 트렁크를 연결할 수 없는 경우 다른 Microsoft 데이터 센터에서 동일한 트렁크에 대한 연결을 시도합니다. 트렁크가 연결되지 않을 수 있습니다. 예를 들어 연결이 거부되거나 TLS 시간 제한이 있는 경우 또는 다른 네트워크 수준 문제가 있는 경우입니다.
예를 들어 관리자가 잘 알려진 IP 주소에서만 SBC에 대한 액세스를 제한하지만 모든 Microsoft 직접 라우팅 데이터 센터의 IP 주소를 SBC의 ACL(액세스 제어 목록)에 넣지 못하면 연결이 실패할 수 있습니다. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>SBC(세션 테두리 컨트롤러)에서 받은 특정 SIP 코드의 장애 조치(failover)

직접 라우팅이 발신 초대에 대한 응답으로 4xx 또는 6xx SIP 오류 코드를 수신하는 경우 호출은 기본적으로 완료된 것으로 간주됩니다. 발신은 Teams 클라이언트에서 PSTN(공용 전환 전화 네트워크)으로의 통화를 의미하고, Teams 클라이언트 -> 직접 라우팅 -> SBC -> Telephony 네트워크입니다.

SIP 코드 목록은 [SIP(세션 시작 프로토콜) RFC에서 찾을 수 있습니다.](https://tools.ietf.org/html/rfc3261)

SBC가 들어오는 초대에 "408 요청 시간 제한: 서버가 적절한 시간 내에 응답을 생성하지 못했습니다(예: 시간 내에 사용자의 위치를 확인할 수 없는 경우). 클라이언트는 나중에 수정하지 않고 요청을 반복할 수 있습니다."

이 특정 SBC는 네트워크 구성 오류 또는 기타 오류로 인하여 호출자에 연결하는 데 어려움이 있을 수 있습니다. 그러나 경로에 발신자에 도달할 수 있는 SBC가 하나 더 있습니다.

다음 다이어그램에서는 사용자가 전화 번호로 전화를 걸 때 이 호출을 배달할 수 있는 경로에 두 개의 SBC가 있습니다. 처음에는 SBC1.contoso.com 선택되지만 네트워크 SBC1.contoso.com 문제로 인해 PTSN 네트워크에 도달할 수 없습니다.
기본적으로 이 순간에는 호출이 완료됩니다. 
 
![네트워크 문제로 인해 SBC가 PSTN에 도달할 수 없는 경우를 보여주는 다이어그램](media/direct-routing-failover-response-codes1.png)

하지만 경로에 호출을 배달할 수 있는 SBC가 하나 더 있습니다.
매개 변수를 구성하는 경우 다음 다이어그램에서 두 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` 번째 SBC가 SBC2.contoso.com 시도됩니다.

![두 번째 SBC로의 라우팅을 보여주는 다이어그램](media/direct-routing-failover-response-codes2.png)

매개 변수 -FailoverResponseCodes를 설정하고 코드를 지정하면 라우팅을 미세 조정하고 SBC가 네트워크 또는 기타 문제로 인해 호출을 할 수 없는 경우 잠재적인 문제를 방지할 수 있습니다.

기본값: 408, 503, 504

