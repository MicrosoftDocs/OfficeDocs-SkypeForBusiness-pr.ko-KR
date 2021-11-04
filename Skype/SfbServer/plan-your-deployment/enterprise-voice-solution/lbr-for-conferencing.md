---
title: Location-Based 회의에 대한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 문의 전화 전송을 포함하여 비즈니스용 Skype 서버 Enterprise Voice 회의에 대한 위치 기반 라우팅 계획
ms.openlocfilehash: 118ccd13fb85f9566c7b62736514936d4f41f9bd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768516"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based 회의에 대한 비즈니스용 Skype 서버

문의 전화 전송을 포함하여 비즈니스용 Skype 서버 Enterprise Voice 회의에 대한 위치 기반 라우팅 계획

Location-Based 라우팅을 사용하면 통화의 당사자 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 통화 라우팅을 제한할 수 있습니다. Location-Based 라우팅을 사용하면 모임(예: 회의)에 Location-Based 라우팅 규칙을 적용하여 PSTN 전화 회의 우회를 방지할 수 있습니다. 응용 프로그램은 활성 회의를 모니터링하고 Location-Based 사용자의 위치에 따라 라우팅 제한을 적용합니다. 또한 Location-Based 회의 응용 프로그램에 대한 라우팅을 사용하면 PSTN 끝점과 관련된 Location-Based 전송에 대한 라우팅 제한을 적용하는 데도 사용할 수 있습니다.

Location-Based 라우팅 회의 응용 프로그램은 PSTN 비즈니스용 Skype 우회를 방지하는 메커니즘을 회의에 제공합니다. 응용 프로그램은 활성 회의를 모니터링하고 Location-Based 사용자의 위치에 따라 비즈니스용 Skype 라우팅 제한을 적용합니다.

Location-Based 라우팅 회의 응용 프로그램에서 Location-Based 조건이 충족될 경우 비즈니스용 Skype 모임에 비즈니스용 Skype 라우팅을 적용할지 여부를 결정합니다.

- 모임 이끌이가 라우팅에 Location-Based 사용하도록 설정됩니다. Location-Based 라우팅 제한은 라우팅을 사용하도록 설정된 사용자가 구성한 회의에만 Location-Based 적용됩니다.

- 하나 이상의 모임 참가자가 PSTN 끝점입니다. Location-Based 라우팅 제한은 PSTN 끝점이 포함된 회의에만 적용할 수 있습니다.

- 회의를 PSTN으로 브리지하는 데 사용되는 PSTN 게이트웨이가 있는 네트워크 사이트는 물론 이끌이와 참가자가 연결하는 네트워크 사이트도 있습니다.

회의 Location-Based 라우팅 응용 프로그램은 여러 네트워크 사이트에서 동일한 회의에 비즈니스용 Skype 사용자 및 PSTN 끝점이 참가하지 못하게 합니다. 모임 이끌이가 Location-Based 라우팅을 사용하도록 설정하면 회의 응용 프로그램에서 다음 제한을 적용합니다.

- 비즈니스용 Skype 모임에 참가할 수 있는 끝점은 이미 회의에 참가한 끝점에 따라 달라지며, 이 제한은 가입된 끝점이 나가고 새 끝점이 회의에 참가할 때 조정됩니다. 이끌이와 참가자가 동일한 네트워크 사이트에서 비즈니스용 Skype 모임에 참가하는 경우 PSTN 끝점, 동일한 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트의 다른 참가자 또는 알 수 없는 네트워크 사이트의 참가자가 참가할 수 있습니다.

- 이끌이와 참가자가 서로 다르거나 알 수 없는 네트워크 사이트에서 모임에 참가하는 경우 PSTN 끝점은 PSTN 통화가 라우팅에 사용하도록 설정된 SIP 트렁크에서 Location-Based 허용되지 않습니다.

- 이끌이와 참가자가 모두 같은 네트워크 사이트에서 모임에 참가하고 PSTN에서 같은 모임에 참가하는 참가자가 있는 경우 다른 네트워크 사이트의 비즈니스용 Skype 끝점에서 모임에 참가할 수 없습니다.

이러한 회의 Location-Based 라우팅 제한에 대한 설명은 다음 표에 요약되어 있습니다.

|주어진 지점에서 회의의 사용자|회의에 참가할 수 있는 사용자|사용자가 회의에 참가할 수 없습니다.|
|:-----|:-----|:-----|
|비즈니스용 Skype 단일 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> |비즈니스용 Skype 동일한 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> 비즈니스용 Skype 다른 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> 비즈니스용 Skype 알 수 없는 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> VoIP 클라이언트 비즈니스용 Skype 페더전된 사용자  <br/> PSTN 끝점에서 사용자 가입  <br/> |없음  <br/> |
|비즈니스용 Skype 알 수 없는 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> |비즈니스용 Skype 모든 사이트의 VoIP 클라이언트 사용자  <br/> 비즈니스용 Skype 알 수 없는 사이트의 VoIP 클라이언트 사용자  <br/> VoIP 클라이언트 비즈니스용 Skype 페더전된 사용자  <br/> |PSTN 끝점을 통해 사용자 가입  <br/> |
|비즈니스용 Skype 다른 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> |비즈니스용 Skype 모든 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> 비즈니스용 Skype 알 수 없는 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> VoIP 클라이언트 비즈니스용 Skype 페더전된 사용자  <br/> |PSTN 끝점을 통해 사용자 가입  <br/> |
|비즈니스용 Skype 단일 네트워크 사이트의 VoIP 클라이언트 사용자 및 PSTN 끝점에서 참가하는 사용자  <br/> |비즈니스용 Skype 동일한 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> |비즈니스용 Skype 다른 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> 비즈니스용 Skype 알 수 없는 네트워크 사이트의 VoIP 클라이언트 사용자  <br/> VoIP 클라이언트 비즈니스용 Skype 페더전된 사용자  <br/> |

다음은 회의 응용 프로그램에 대한 Location-Based 특성입니다.

- 사용자가 라우팅 제한이 Location-Based 전화 회의에 참가할 수 없는 경우 전화 회의에 대한 통화가 거부되어 비즈니스용 Skype 클라이언트는 통화가 완료되지 않았다거나 종료된 것으로 보고합니다.

- Location-Based 라우팅 적용을 통해 전화 회의에 참가하는 PSTN 끝점은 끝점이 Location-Based 라우팅을 사용할 수 없는 트렁크를 통해 참가하는 경우의 상태와 관계없이 전화 회의에 참가할 수 없습니다.

- PSTN으로 통화를 전송하지 않는 SIP 트렁크를 통해 중재 서버에 연결된 PBX 시스템은 SIP 트렁크가 정의된 동일한 네트워크 사이트에 있는 비즈니스용 Skype 사용자와 동일한 적용을 하게 됩니다. 예를 들어 PSTN 끝점은 동일한 네트워크 사이트에 있는 경우 PBX 사용자 및 비즈니스용 Skype 사용자와 함께 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 사용자와 다른 네트워크 사이트에 있는 경우 PSTN 끝점에서 회의에 참가할 비즈니스용 Skype 없습니다.

> [!NOTE]
> 누적 비즈니스용 Skype 4를 사용할 경우 다음 표의 동작을 관찰해야 합니다.

|사용자|기타 파티|조치|결과|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 모바일  <br/> |PSTN  <br/> |비즈니스용 Skype 모바일이 PSTN 통화 중입니다. 비즈니스용 Skype 그런 다음 모바일은 통화를 CAA(전화 회의 자동 전화 교환 에스컬레이터합니다.  <br/> |적절한 오류 메시지와 함께 통화가 차단됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |비즈니스용 Skype 클라이언트 또는 페더리트 사용자  <br/> |클라이언트 또는 페더레이터 사용자가 라우팅 사용자로 비즈니스용 Skype Location-Based VoIP를 호출 중이면 두 사용자 모두 CAA로 에스컬레이터됩니다.  <br/> |적절한 오류 메시지와 함께 에스컬레이터 호출이 차단됩니다.  <br/> |

## <a name="consultative-call-transfers"></a>컨설팅 통화 전송

Location-Based 모임에 Location-Based 비즈니스용 Skype 라우팅을 적용하는 것 외에도 Location-Based 회의용 라우팅 응용 프로그램은 PSTN 끝점으로 전송되는 Location-Based 통화 전송에 대해 Location-Based 라우팅 제한을 적용합니다. 컨설팅 통화 전송은 두 당사자 간에 설정되는 통화로, 한 당사자가 통화를 새 사용자에게 전송합니다. 예를 들어 PSTN 끝점은 사용자 A(비즈니스용 Skype 호출합니다. 사용자 A는 PSTN 사용자를 사용자 B(사용자)로 전달해야 비즈니스용 Skype 합니다. 사용자 A가 PSTN 사용자와 통화를 보류하고 사용자 B에게 전화를 걸고 사용자 B는 PSTN 사용자와의 통화에 동의합니다. 사용자 A가 통화를 보류된 사용자 B로 전송합니다.

**컨설팅 통화 전송 통화 흐름**

![회의 다이어그램의 위치 기반 라우팅입니다.](../../media/LocationBasedRoutingForConferencing.jpg)

Location-Based 라우팅을 사용하도록 설정된 사용자가 PSTN 끝점의 컨설팅 통화 전송을 시작하면 PSTN 사용자와 비즈니스용 Skype 사용자 A 간의 통화와 비즈니스용 Skype 사용자 A와 비즈니스용 Skype 사용자 B 간의 두 개의 활성 통화가 생성됩니다. 다음 동작은 회의용 Location-Based 라우팅에 의해 적용됩니다. n:

- PSTN 통화를 라우팅하는 SIP 트렁크가 PSTN 통화를 비즈니스용 Skype 사용자 B(예: 전송 대상)가 있는 네트워크 사이트로 다시 라우팅할 수 있는 권한이 있는 경우 통화 전송이 허용됩니다. 그렇지 않으면 컨설팅 통화 전송이 차단됩니다. 이 권한 부여는 현재 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 동일한 네트워크 사이트에 있는 전송된 사용자 위치에 따라 수행됩니다.

- 인바운드 PSTN 통화를 라우팅하는 SIP 트렁크가 전송된 사용자(비즈니스용 Skype 사용자 B)가 위치하거나 전송된 사용자가 알 수 없는 네트워크 사이트에 있는 네트워크 사이트로 통화를 라우팅할 수 있는 권한이 없는 경우 PSTN 끝점(즉, 통화 전송 대상)으로의 문의 통화 전송이 차단됩니다.

다음 표에서는 Location-Based 통화 전송을 위한 회의 Location-Based 라우팅 응용 프로그램에서 Location-Based 라우팅 제한을 적용하는 방법에 대해 설명하고 있습니다. PBX 끝점은 네트워크 사이트에 직접 연결되어 있지는 않은 경우 PBX에 연결된 SIP 트렁크를 네트워크 사이트에 할당할 수 있습니다. 따라서 PBX 끝점은 네트워크 사이트와 간접적으로 연결될 수 있습니다.


|통화 전송된 파티의 네트워크 사이트|통화 전송 대상의 네트워크 사이트|동작|
|:-----|:-----|:-----|
|PSTN 끝점  <br/> |비즈니스용 Skype 사이트(예: 사이트 1)에 있는 사용자  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|PSTN 끝점  <br/> |비즈니스용 Skype 사이트(예: 사이트 2)의 사용자 수  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |비즈니스용 Skype 네트워크 사이트의 사용자 이름  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |페더 비즈니스용 Skype 사용자  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |동일한 사이트의 PBX 끝점(예: 사이트 1)  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|PSTN 끝점  <br/> |다른 사이트의 PBX 끝점(예: 사이트 2)  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|동일한 사이트의 PBX 끝점(예: 사이트 1)  <br/> |PSTN 끝점  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|다른 사이트의 PBX 끝점(예: 사이트 2)  <br/> |PSTN 끝점  <br/> |컨설팅 전송이 지원되지 않습니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |비즈니스용 Skype 사이트(예: 사이트 1)에 있는 사용자  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |비즈니스용 Skype 사이트(예: 사이트 2)의 사용자 수  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |비즈니스용 Skype 네트워크 사이트의 사용자 이름  <br/> |컨설팅 전송이 허용됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |페더 비즈니스용 Skype 사용자  <br/> |컨설팅 전송이 허용됩니다.  <br/> |

## <a name="requirements"></a>요구 사항

Location-Based 회의용 라우팅 응용 프로그램을 사용하려면 토폴로지의 모든 Front-End 풀 및 Standard Edition 서버에 비즈니스용 Skype 서버 또는 Lync Server 2013 누적 업데이트 2를 배포해야 합니다. 이러한 서버 버전이 토폴로지의 일부 서버에 설치되어 있지 않은 경우에는 Location-Based 통화 전송에 라우팅 제한을 완전히 적용할 수 없습니다.

다음 표에는 라우팅을 지원하는 서버 역할 및 버전이 Location-Based 설명되어 있습니다.


|Front-End 풀 버전|중재 서버 버전|지원|
|:-----|:-----|:-----|
|비즈니스용 Skype 서버 또는 Lync Server 2013 누적 업데이트 2  <br/> |비즈니스용 Skype 서버 또는 Lync Server 2013 누적 업데이트 2  <br/> |예  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Lync Server 2013 누적 업데이트 1  <br/> |아니오  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Lync Server 2010  <br/> |아니오  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Office Communications Server 2007 R2  <br/> |아니오  <br/> |
|Lync Server 2013 누적 업데이트 1  <br/> |모두  <br/> |아니오  <br/> |
|Lync Server 2010  <br/> |모두  <br/> |아니오  <br/> |
|Office Communications Server 2007 R2  <br/> |모두  <br/> |아니오  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>회의에 Location-Based 라우팅 구성

회의 Location-Based 응용 프로그램에 대한 라우팅은 Location-Based 라우팅의 구성에 따라 다릅니다. 주요 구성은 다음과 같습니다.

- 모임에 참가하는 참가자의 위치는 네트워크 사이트에 따라 결정됩니다. 네트워크 사이트 및 연결된 네트워크 서브넷은 라우팅을 적용하려면 비즈니스용 Skype 서버 정의해야 Location-Based 합니다.

- 모임 Location-Based 라우팅을 적용하려면 비즈니스용 Skype 라우팅에 대해 Location-Based 설정해야 합니다.

- 모임에 Location-Based PSTN 끝점의 라우팅을 적용하려면 PSTN 끝점을 연결하는 데 사용되는 SIP 트렁크를 Location-Based 라우팅에 대해 구성해야 합니다.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>회의에 Location-Based 라우팅 사용

회의 Location-Based 라우팅은 기본적으로 사용하지 않도록 설정되어 있습니다. 이 응용 프로그램을 사용하도록 설정하기 전에 응용 프로그램에 할당할 올바른 우선 순위를 결정해야 합니다. 이 우선 순위를 결정하기 위해 관리 셸에서 비즈니스용 Skype 서버 실행합니다.

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

이 cmdlet에서 는 회의 응용 프로그램에 대한 Location-Based 라우팅을 사용할 \<Pool FQDN\> 풀입니다.

이 cmdlet은 호스트되는 응용 프로그램 목록과 각 응용 비즈니스용 Skype 서버 우선 순위 값을 반환합니다. 회의 Location-Based 라우팅은 "UdcAgent" 응용 프로그램보다 크고 "DefaultRouting", "ExumRouting" 및 "OutboundRouting" 응용 프로그램보다 작은 우선 순위 값을 할당해야 합니다. 회의 응용 프로그램에 Location-Based 라우팅을 "UdcAgent" 응용 프로그램의 우선 순위 값보다 1포인트 더 높은 우선 순위 값을 할당하는 것이 좋습니다.

예를 들어 "UdcAgent" 응용 프로그램의 우선 순위 값이 "2"이면 "DefaultRouting" 응용 프로그램의 우선 순위 값이 "8"이고 " ExumRouting" 응용 프로그램의 우선 순위 값은 "9"이고 "OutboundRouting" 응용 프로그램에 우선 순위 값이 "10"인 경우 회의 응용 프로그램에 대한 Location-Based 라우팅을 우선 순위 값 "3"으로 할당해야 합니다. 이렇게 하면 다른 응용 프로그램(우선 순위: 0에서 1까지), "UdcAgent"(우선 순위: 2), Location-Based 라우팅 회의 응용 프로그램(우선 순위: 1) 순서로 응용 프로그램의 우선 순위가 지정됩니다. 3), 기타 응용 프로그램(우선 순위: 4 ~8), "DefaultRouting"(우선 순위: 9), "ExumRouting"(우선 순위: 10) 및 "아웃바운드 아웃바운드"(우선 순위: 11)

Location-Based 회의 응용 프로그램에 대해 올바른 우선 순위 값을 찾은 후 Standard Edition 라우팅을 사용하도록 설정된 사용자를 홈으로 사용하는 각 Front-End 풀 또는 Standard Edition Server에 대해 다음 cmdlet을 입력합니다 Location-Based.

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

예제:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

이 cmdlet을 사용한 후 회의 응용 프로그램에 대한 Location-Based 라우팅을 사용하도록 설정된 풀 또는 Standard Edition 서버의 모든 프런트 엔드 서버를 다시 시작합니다.

> [!IMPORTANT]
> Location-Based 풀 또는 회의 서버의 모든 프런트 엔드 서버가 다시 시작될 때까지 회의 또는 컨설팅 전송에 대한 라우팅 Standard Edition 적용됩니다. 이전 cmdlet에서  **-Critical을** $true 경우 비즈니스용 Skype 서버 서비스가 즉시 다시 시작됩니다. 이러한 서비스를 즉시 다시 시작하지 못하게 하려는 경우 **-Critical을** 지금 $false 설정한 다음 **Set-CsServerApplication을** 사용하여 서비스를 다시 시작한 후 나중에 **-critical으로** **$true** -Critical을 변경합니다. 

Location-Based 회의 응용 프로그램에 대한 Location-Based 라우팅이 사용하도록 설정되고 적용 가능한 모든 서버가 다시 시작되면 비즈니스용 Skype 라우팅을 사용하도록 설정된 Location-Based 사용자가 구성한 모든 회의가 모니터링되어 PSTN 무료 우회를 방지합니다.


