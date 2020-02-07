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
description: 팀에서 SBC (세션 경계 컨트롤러)로의 아웃 바운드 호출에서 트렁크 장애 조치를 처리 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836180"
---
# <a name="trunk-failover-on-outbound-calls"></a>발신 전화에 대한 트렁크 장애 조치

이 항목에서는 팀에서 세션 경계 컨트롤러 (SBC)로 나가는 호출에 대 한 트렁크 장애 조치를 방지 하는 방법에 대해 설명 합니다.

## <a name="failover-on-network-errors"></a>네트워크 오류에 대 한 장애 조치

트렁크를 어떤 이유로 든 연결할 수 없는 경우 같은 트렁크에 대 한 연결이 다른 Microsoft Datacenter에서 시도 됩니다. 연결이 거부 되었거나, TLS 시간이 초과 되거나, 기타 네트워크 수준 문제가 있는 경우 트렁크가 연결 되지 않을 수 있습니다.
예를 들어 관리자가 잘 알려진 IP 주소 에서만 SBC에 대 한 액세스를 제한 하는 경우 연결이 실패할 수 있지만 SBC의 ACL (액세스 제어 목록)에 모든 Microsoft 직접 라우팅 데이터 센터의 IP 주소를 넣지 않습니다. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>SBC (세션 경계 컨트롤러)에서 받은 특정 SIP 코드의 장애 조치

송신 초대에 대 한 응답으로 직접 라우팅이 4xx 또는 6xx SIP 오류 코드를 수신 하는 경우에는 통화가 기본적으로 완료 된 것으로 간주 됩니다. 발신은 팀 클라이언트에서 다음 트래픽 흐름을 통해 PSTN (공개 교환 전화 네트워크)로 전화를 거는 것을 의미 합니다. 팀 클라이언트 > 직접 라우팅-> SBC-> 전화 통신 네트워크.

SIP 코드 목록은 [sip (세션 시작 프로토콜) RFC](https://tools.ietf.org/html/rfc3261)에서 찾을 수 있습니다.

SBC에서 코드 "408 요청 시간 초과: 사용자의 위치를 확인할 수 없는 경우와 같이 적절 한 시간 내에 서버에서 응답을 생성할 수 없는 상황이 있다고 가정 합니다. 나중에 수정 하지 않고 클라이언트가 요청을 반복할 수 있습니다. "

이 특정 SBC는 네트워크를 잘못 구성 했거나 기타 오류로 인해 호출 수신자에 게 연결 하는 데 문제가 있을 수 있습니다. 그러나 경로에는 호출 수신자에 도달할 수 있는 SBC 하나가 있습니다.

다음 다이어그램에서 사용자가 전화 번호를 호출 하면 경로에 두 개의 SBCs가 있어이 통화를 잠재적으로 전달할 수 있습니다. 처음에는 통화를 위해 SBC1.contoso.com가 선택 되지만 SBC1.contoso.com는 네트워크 문제로 인해 PTSN 네트워크에 접속할 수 없습니다.
기본적으로이 통화는 현재 완료 됩니다. 
 
![네트워크 문제로 인해 SBC에 연결할 수 없음 SBC을 보여 주는 다이어그램](media/direct-routing-failover-response-codes1.png)

그러나 경로에는 통화를 전달할 수 있는 SBC가 하나 더 있습니다.
매개 변수 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`를 구성 하는 경우 두 번째 SBC는 다음 다이어그램에서 SBC2.contoso.com 시도 됩니다.

![두 번째 SBC에 대 한 라우팅을 보여 주는 다이어그램](media/direct-routing-failover-response-codes2.png)

FailoverResponseCodes 매개 변수를 설정 하 고 코드를 지정 하면 네트워크 또는 기타 문제로 인해 SBC에서 전화를 걸 수 없을 때 경로를 세부적으로 조정 하 고 잠재적인 문제를 방지 하는 데 도움이 됩니다.

기본값: 408, 503, 504

