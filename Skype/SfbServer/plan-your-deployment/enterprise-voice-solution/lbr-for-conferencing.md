---
title: Location-Based 서버의 회의 라우팅
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 컨설팅 통화 전송을 포함하여 비즈니스용 Skype 서버 Enterprise Voice 회의에 대한 위치 기반 라우팅 계획
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825578"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based 서버의 회의 라우팅

컨설팅 통화 전송을 포함하여 비즈니스용 Skype 서버 Enterprise Voice 회의에 대한 위치 기반 라우팅 계획

Location-Based 라우팅을 사용하면 통화의 당사자 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 통화 라우팅을 제한할 수 있습니다. Location-Based 라우팅을 사용하면 PSTN 전화 우회를 방지하기 위해 Location-Based 라우팅 규칙을 모임(예: 회의)에 적용할 수 있습니다. 응용 프로그램은 활성 회의를 모니터링하고 Location-Based 위치에 따라 라우팅 제한을 적용합니다. 또한 Location-Based 응용 프로그램에 대한 Location-Based 라우팅을 통해 PSTN 끝점과 관련된 컨설팅 전송에 대한 Location-Based 라우팅 제한을 적용합니다.

Location-Based 라우팅 회의 응용 프로그램은 PSTN 전화 우회를 방지하는 메커니즘을 비즈니스용 Skype 회의에 제공합니다. 응용 프로그램은 활성 회의를 모니터링하고 Location-Based 비즈니스용 Skype 사용자의 위치에 따라 라우팅 제한을 적용합니다.

Location-Based 라우팅 회의 응용 프로그램은 다음 조건을 충족하는 경우 Location-Based 라우팅을 비즈니스용 Skype 모임에 적용할지 여부를 결정합니다.

- 모임 이끌이가 모임 라우팅에 Location-Based 사용하도록 설정됩니다. Location-Based 라우팅을 사용하도록 설정된 사용자가 구성한 회의에만 라우팅 제한이 Location-Based 적용됩니다.

- 하나 이상의 모임 참가자가 PSTN 끝점입니다. Location-Based 라우팅 제한은 PSTN 끝점이 포함된 회의에만 적용할 수 있습니다.

- 회의를 PSTN으로 브리지하는 데 사용되는 PSTN 게이트웨이가 있는 네트워크 사이트는 물론 이끌이와 참가자가 연결하는 네트워크 사이트도 있습니다.

회의 Location-Based 라우팅을 통해 비즈니스용 Skype 사용자 및 PSTN 끝점이 서로 다른 네트워크 사이트에서 동일한 회의로 참가할 수 없습니다. 모임 이끌이가 라우팅을 사용하도록 Location-Based 경우 회의 응용 프로그램에서 다음 제한을 적용합니다.

- 비즈니스용 Skype 모임에 참가할 수 있는 끝점은 이미 전화 회의에 참가한 끝점에 따라 달라지며, 참가된 끝점이 나가고 새 끝점이 회의에 참가하면 이 제한이 조정됩니다. 이끌이와 참가자가 동일한 네트워크 사이트에서 비즈니스용 Skype 모임에 참가하는 경우 PSTN 끝점, 동일한 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트의 다른 참가자 또는 알 수 없는 네트워크 사이트의 참가자가 참가할 수 있습니다.

- 이끌이와 참가자가 서로 다르거나 알 수 없는 네트워크 사이트에서 모임에 참가하는 경우 PSTN 끝점은 PSTN 통화가 라우팅을 사용하도록 설정된 SIP 트렁크에서 전화를 걸 경우 모임에 참가할 수 Location-Based 없습니다.

- 이끌이와 참가자가 모두 같은 네트워크 사이트에서 모임에 참가하는 경우 PSTN에서 같은 모임에 참가하는 참가자가 있는 경우 다른 네트워크 사이트의 비즈니스용 Skype 끝점에서 모임에 참가할 수 없습니다.

이러한 회의 Location-Based 라우팅 제한에 대한 설명은 다음 표에 요약되어 있습니다.

|회의의 사용자(중)는 모든 지점에서|회의에 참가할 수 있는 사용자|사용자가 회의에 참가할 수 없습니다.|
|:-----|:-----|:-----|
|단일 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |동일한 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 다른 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더리드 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> PSTN 끝점에서 사용자 가입  <br/> |없음  <br/> |
|알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |모든 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더리드 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |PSTN 끝점을 통한 사용자 가입  <br/> |
|다른 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |모든 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더리드 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |PSTN 끝점을 통한 사용자 가입  <br/> |
|단일 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자 및 PSTN 끝점에서 참가하는 사용자  <br/> |동일한 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |다른 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더리드 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |

다음은 회의 응용 프로그램에 대한 Location-Based 특성입니다.

- 사용자가 라우팅 제한이 Location-Based 전화 회의에 참가할 수 없는 경우 전화 회의에 대한 통화가 거부됩니다. 비즈니스용 Skype 클라이언트는 통화가 완료되지 않았다거나 종료했다고 보고합니다.

- Location-Based 라우팅 적용을 통해 전화 회의에 참가하는 PSTN 끝점은 끝점이 Location-Based 라우팅을 사용할 수 없는 트렁크를 통해 참가하는 경우 해당 상태와 관계없이 전화 회의에 참가하는 것으로 제한되지 않습니다.

- PSTN으로 통화를 전송하지 않는 SIP 트렁크를 통해 중재 서버에 연결된 PBX 시스템은 SIP 트렁크가 정의된 동일한 네트워크 사이트에 있는 비즈니스용 Skype 사용자와 동일한 적용을 하게 됩니다. 예를 들어 PSTN 끝점은 PBX 사용자 및 비즈니스용 Skype 사용자가 동일한 네트워크 사이트에 있는 경우 전화 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 비즈니스용 Skype 사용자와 다른 네트워크 사이트에 있는 경우 PSTN 끝점에서 전화 회의에 참가할 수 없습니다.

> [!NOTE]
> 비즈니스용 Skype 누적 업데이트 4에서는 다음 표의 동작을 관찰해야 합니다.

|사용자|기타 파티|작업|결과|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 모바일  <br/> |PSTN  <br/> |비즈니스용 Skype 모바일이 PSTN 통화 중입니다. 그런 다음 비즈니스용 Skype 모바일은 통화를 CAA(Conference 자동 전화 교환)로 에스컬레이터합니다.  <br/> |적절한 오류 메시지와 함께 통화가 차단됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |비즈니스용 Skype 클라이언트 또는 페더리트 사용자  <br/> |클라이언트 또는 페더레이터 사용자는 비즈니스용 Skype 모바일 Location-Based 라우팅 사용자에 대한 VoIP 통화를 진행 중이면 어느 한 쪽이 CAA로 에스컬레이터합니다.  <br/> |적절한 오류 메시지와 함께 에스컬레이터 호출이 차단됩니다.  <br/> |

## <a name="consultative-call-transfers"></a>컨설팅 통화 전송

비즈니스용 Skype 모임에 Location-Based 라우팅을 적용하는 것 외에도 Location-Based 회의용 Location-Based 라우팅 응용 프로그램은 PSTN 끝점으로 전송되는 컨설팅 통화 전송에 대해 Location-Based 라우팅 제한을 적용합니다. 컨설팅 통화 전송은 두 당사자 간에 설정되는 통화로, 한 당사자가 통화를 새 사용자에게 전송합니다. 예를 들어 PSTN 끝점은 사용자 A(비즈니스용 Skype 발신자)를 호출합니다. 사용자 A는 PSTN 사용자를 사용자 B(비즈니스용 Skype 사용자)에게 전달해야 한다고 판단합니다. 사용자 A는 PSTN 사용자와 통화를 보류하고 사용자 B에게 전화를 걸고 사용자 B는 PSTN 사용자와 통화하는 데 동의합니다. 사용자 A는 통화를 보류된 사용자 B로 전송합니다.

**컨설팅 통화 전송 통화 흐름**

![회의 다이어그램의 위치 기반 라우팅](../../media/LocationBasedRoutingForConferencing.jpg)

Location-Based 라우팅을 사용하도록 설정된 사용자가 PSTN 끝점의 컨설팅 통화 전송을 시작하면 PSTN 사용자와 비즈니스용 Skype 사용자 A 간의 통화 한 번과 비즈니스용 Skype 사용자 A와 비즈니스용 Skype 사용자 B 간의 두 개의 활성 통화가 생성됩니다. 다음 동작은 Location-Based 회의 응용 프로그램에 의해 적용됩니다.

- PSTN 통화를 라우팅하는 SIP 트렁크가 PSTN 통화를 비즈니스용 Skype 사용자 B(예: 전송 대상)가 있는 네트워크 사이트로 다시 라우팅할 수 있는 권한이 있는 경우 통화 전송이 허용됩니다. 그렇지 않으면 컨설팅 통화 전송이 차단됩니다. 이 권한 부여는 활성 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 동일한 네트워크 사이트에 있는 전송된 사용자 위치에 따라 수행됩니다.

- 인바운드 PSTN 통화를 라우팅하는 SIP 트렁크가 전송된 사용자(비즈니스용 Skype 사용자 B)가 위치하거나 전송된 사용자가 알 수 없는 네트워크 사이트에 있는 네트워크 사이트로 통화를 라우팅할 수 있는 권한이 없는 경우 PSTN 끝점(즉, 통화 전송 대상)으로의 컨설팅 통화 전송이 차단됩니다.

다음 표에서는 Location-Based 통화 전송을 위한 Location-Based 라우팅 응용 프로그램에 의해 Location-Based 라우팅 제한을 적용하는 방법에 대해 설명되어 있습니다. PBX 끝점은 네트워크 사이트에 직접 연결되어 있지는 않습니다. PBX에 연결된 SIP 트렁크는 네트워크 사이트에 할당할 수 있습니다. 따라서 PBX 끝점은 네트워크 사이트에 간접적으로 연결될 수 있습니다.


|통화 전송자 네트워크 사이트|통화 전송 대상의 네트워크 사이트|동작|
|:-----|:-----|:-----|
|PSTN 끝점  <br/> |동일한 네트워크 사이트의 비즈니스용 Skype 사용자(예: 사이트 1)  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|PSTN 끝점  <br/> |다른 네트워크 사이트의 비즈니스용 Skype 사용자(예: 사이트 2)  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |알 수 없는 네트워크 사이트의 비즈니스용 Skype 사용자  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |페더리드 비즈니스용 Skype 사용자  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |같은 사이트의 PBX 끝점(예: 사이트 1)  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|PSTN 끝점  <br/> |다른 사이트의 PBX 끝점(예: 사이트 2)  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|같은 사이트의 PBX 끝점(예: 사이트 1)  <br/> |PSTN 끝점  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|다른 사이트의 PBX 끝점(예: 사이트 2)  <br/> |PSTN 끝점  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |동일한 네트워크 사이트의 비즈니스용 Skype 사용자(예: 사이트 1)  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |다른 네트워크 사이트의 비즈니스용 Skype 사용자(예: 사이트 2)  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |알 수 없는 네트워크 사이트의 비즈니스용 Skype 사용자  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |페더리드 비즈니스용 Skype 사용자  <br/> |컨설팅 전송이 허용됩니다.  <br/> |

## <a name="requirements"></a>요구 사항

회의 응용 프로그램에 대한 Location-Based 라우팅을 사용하려면 토폴로지의 모든 Front-End 풀 및 Standard Edition Server에 비즈니스용 Skype 서버 또는 Lync Server 2013 누적 업데이트 2를 배포해야 합니다. 이러한 서버 버전이 토폴로지의 일부 서버에 설치되어 있지 않은 경우 Location-Based 통화 전송에 라우팅 제한을 완전히 적용할 수 없습니다.

다음 표에서는 라우팅을 지원하는 서버 역할과 버전이 Location-Based 식별합니다.


|Front-End 풀 버전|중재 서버 버전|지원|
|:-----|:-----|:-----|
|비즈니스용 Skype 서버 또는 Lync Server 2013 누적 업데이트 2  <br/> |비즈니스용 Skype 서버 또는 Lync Server 2013 누적 업데이트 2  <br/> |예  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Lync Server 2013 누적 업데이트 1  <br/> |아니요  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Lync Server 2010  <br/> |아니요  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Office Communications Server 2007 R2  <br/> |아니요  <br/> |
|Lync Server 2013 누적 업데이트 1  <br/> |모두  <br/> |아니요  <br/> |
|Lync Server 2010  <br/> |모두  <br/> |아니요  <br/> |
|Office Communications Server 2007 R2  <br/> |모두  <br/> |아니요  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>회의에 Location-Based 라우팅 구성

회의 Location-Based 라우팅은 Location-Based 라우팅의 구성에 따라 다릅니다. 주요 구성은 다음과 같습니다.

- 모임에 참가하는 참가자의 위치는 네트워크 사이트에 따라 결정됩니다. 네트워크 사이트 및 연결된 네트워크 서브넷은 비즈니스용 Skype 서버에 정의되어 있어야 Location-Based 라우팅을 적용할 수 있습니다.

- 모임의 Location-Based 라우팅을 적용하려면 비즈니스용 Skype 참가자가 모임 라우팅에 대해 Location-Based 설정해야 합니다.

- 모임에 Location-Based PSTN 끝점의 라우팅을 적용하려면 PSTN 끝점을 연결하는 데 사용되는 SIP 트렁크를 Location-Based 라우팅을 구성해야 합니다.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>회의에 Location-Based 라우팅 사용

회의 Location-Based 라우팅은 기본적으로 사용하지 않도록 설정됩니다. 이 응용 프로그램을 사용하도록 설정하기 전에 응용 프로그램에 할당할 올바른 우선 순위를 결정해야 합니다. 이 우선 순위를 결정하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행합니다.

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

이 cmdlet에서 회의 응용 프로그램에 대한 Location-Based 라우팅을 사용할 \<Pool FQDN\> 풀입니다.

이 cmdlet은 비즈니스용 Skype 서버에서 호스팅하는 응용 프로그램 목록과 각 응용 프로그램의 우선 순위 값을 반환합니다. 회의 Location-Based 라우팅에는 "UdcAgent" 응용 프로그램보다 크고 "DefaultRouting", "ExumRouting" 및 "OutboundRouting" 응용 프로그램보다 작은 우선 순위 값을 할당해야 합니다. 회의 응용 프로그램에 대한 Location-Based 라우팅을 "UdcAgent" 응용 프로그램의 우선 순위 값보다 1포인트 더 높은 우선 순위 값을 할당하는 것이 좋습니다.

예를 들어 "UdcAgent" 응용 프로그램의 우선 순위 값이 "2"이면 "DefaultRouting" 응용 프로그램의 우선 순위 값이 "8"이고, "ExumRouting" 응용 프로그램의 우선 순위 값이 "9"이고 "OutboundRouting" 응용 프로그램에 우선 순위 값이 "10"인 경우 회의 응용 프로그램에 대한 Location-Based 라우팅을 우선 순위 값 "3"으로 할당해야 합니다. 이렇게 하면 다른 응용 프로그램(우선 순위: 0 ~1), "UdcAgent"(우선 순위: 2), Location-Based 라우팅 회의 응용 프로그램(우선 순위: 1) 순서대로 응용 프로그램의 우선 순위가 지정됩니다. 3), 기타 응용 프로그램(우선 순위: 4 ~8), "DefaultRouting"(우선 순위: 9), "ExumRouting"(우선 순위: 10) 및 "OutboundRouting"(우선 순위: 11)

회의 응용 프로그램에 대한 Location-Based 라우팅에 대한 올바른 우선 순위 값을 찾은 후 Front-End 라우팅을 사용하도록 설정된 사용자가 있는 각 Front-End 풀 또는 Standard Edition Server에 대해 다음 cmdlet을 Location-Based 입력합니다.

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

예제:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

이 cmdlet을 사용한 후 회의 응용 프로그램에 대한 Location-Based 라우팅을 사용하도록 설정된 풀 또는 Standard Edition Server의 모든 프런트 엔드 서버를 다시 시작합니다.

> [!IMPORTANT]
> Location-Based 풀 또는 Standard Edition Server의 모든 프런트 엔드 서버가 다시 시작될 때까지는 회의 또는 컨설팅 전송에 대한 라우팅 적용이 적용되지 않습니다. 이전 cmdlet에서  **-Critical을** $true 경우 비즈니스용 Skype 서버 서비스가 즉시 다시 시작됩니다. 이러한 서비스를  즉시 다시 **시작하지** 못하게 하려는 경우 **-Critical을** 현재 $false 설정한 다음 **Set-CsServerApplication을** 사용하여 서비스를 다시 시작한 후 $true **-Critical로** 변경합니다.

회의 응용 Location-Based 라우팅을 사용하도록 설정하고 해당 서버가 모두 다시 시작되면 Location-Based 라우팅을 사용하도록 설정된 비즈니스용 Skype 사용자가 구성한 모든 회의를 모니터링하여 PSTN 전화 우회를 방지합니다.


