---
title: 비즈니스용 Skype 서버에서의 회의를 위한 위치 기반 라우팅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Consultative 통화 전송을 포함 하 여 비즈니스용 Skype Server Enterprise Voice에서 회의를 위한 위치 기반 라우팅에 대 한 계획
ms.openlocfilehash: d9ca03920fe361cf4d7692fd80031bef01b03b17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187662"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서의 회의를 위한 위치 기반 라우팅

Consultative 통화 전송을 포함 하 여 비즈니스용 Skype Server Enterprise Voice에서 회의를 위한 위치 기반 라우팅에 대 한 계획

위치 기반 라우팅을 사용 하면 통화 중 파티의 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 호출 라우팅을 제한할 수 있습니다. 회의를 위한 위치 기반 라우팅을 사용 하면 모임 (즉, 회의)에 위치 기반 라우팅 규칙을 적용 하 여 PSTN 유료 바이패스를 방지할 수 있습니다. 이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 사용자의 위치를 기준으로 위치 기반 라우팅 제한을 적용 합니다. 또한 회의 응용 프로그램의 위치 기반 라우팅을 사용 하 여 위치 기반 라우팅 제한을 적용 하 여 PSTN 끝점 관련 consultative 전송을 적용할 수 있습니다.

위치 기반 라우팅 회의 응용 프로그램은 PSTN 유료 바이패스를 방지 하기 위한 메커니즘을 비즈니스용 Skype 컨퍼런스에 제공 합니다. 이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 비즈니스용 Skype 사용자의 위치를 기반으로 위치 기반 라우팅 제한을 적용 합니다.

위치 기반 라우팅 회의 응용 프로그램에서 다음 조건을 충족 하는 경우 비즈니스용 Skype 모임에 위치 기반 라우팅이 적용 되는지 여부를 결정 합니다.

- 모임 이끌이는 위치 기반 회람을 사용할 수 있습니다. 위치 기반 라우팅 제한은 위치 기반 라우팅을 사용 하도록 설정 된 사용자가 구성한 회의에만 적용 됩니다.

- 하나 이상의 모임 참가자가 PSTN 끝점입니다. 위치 기반 라우팅 제한은 PSTN 끝점을 포함 하는 회의에만 적용할 수 있습니다.

- PSTN에 전화를 연결 하는 데 사용 되는 PSTN 게이트웨이는 물론 이끌이와 참가자가 연결 되는 네트워크 사이트에 대 한 네트워크 사이트를 찾습니다.

위치 기반 회의 응용 프로그램의 라우팅에서는 비즈니스용 Skype 사용자와 다양 한 네트워크 사이트의 PSTN 종점이 같은 회의에 참가 하는 것을 방지 합니다. 모임 이끌이가 위치 기반 회람을 사용 하도록 설정 되어 있는 경우 회의 응용 프로그램에서 다음 제한 사항이 적용 됩니다.

- 비즈니스용 Skype 모임에 참가할 수 있는 끝점은 이미 전화 회의에 참가 한 끝점에 따라 다르며,이 제한은 참가 한 끝점 종료 및 새 끝점이 회의에 참가 하는 것 처럼 조정 됩니다. 이끌이 및 참가자가 같은 네트워크 사이트에서 비즈니스용 Skype 모임에 참가 하는 경우 PSTN 끝점, 같은 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트의 참가자가 만든 다른 참가자 참가할 수 있습니다.

- 이끌이 및 참가자가 서로 다른 네트워크나 알 수 없는 네트워크 사이트에서 모임에 참가 하는 경우 PSTN 호출이 위치 기반 라우팅에 대해 사용 하도록 설정 된 SIP 트렁크의 ingresses에서 모임에 참가할 수 없습니다.

- 이끌이 및 참가자가 모두 동일한 네트워크 사이트의 모임에 참가 하 고 있으며 PSTN에서 같은 모임에 참가 하는 참가자가 있는 경우 다른 네트워크 사이트의 비즈니스용 Skype 끝점은 모임에 참가할 수 없습니다.

이러한 회의 위치 기반 라우팅 제한은 다음 표에 요약 되어 있습니다.

| |

|**지정 된 시점에 회의의 사용자**|**회의에 참가할 수 있는 사용자 (들)**|**사용자가 회의에 참가할 수 없습니다.**|
|:-----|:-----|:-----|
|단일 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |동일한 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 다른 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더레이션된 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> PSTN 끝점에서 참가 하는 사용자  <br/> |없음  <br/> |
|알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더레이션된 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |PSTN 끝점을 통해 참가 하는 사용자  <br/> |
|다른 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |모든 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더레이션된 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |PSTN 끝점을 통해 참가 하는 사용자  <br/> |
|단일 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자 및 PSTN 끝점에서 참가 하는 사용자  <br/> |동일한 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |다른 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 알 수 없는 네트워크 사이트의 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> 페더레이션된 비즈니스용 Skype VoIP 클라이언트 사용자  <br/> |

다음은 회의 응용 프로그램을 위한 위치 기반 라우팅의 추가 특성입니다.

- 사용자가 전화 회의에 참가 하도록 허용 되지 않는 경우에는 회의에 대 한 통화가 거부 되 고 비즈니스용 Skype 클라이언트에서 통화가 완료 되지 않았거나 종료 되었다는 것을 보고 합니다.

- 위치 기반 라우팅 enforcements를 사용 하 여 전화 회의에 참가 하는 PSTN 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 트렁크를 통해 끝점에 참가 하는 경우 상태에 관계 없이 전화 회의에 참가 하도록 제한 되지 않습니다.

- PSTN으로 발신 되지 않는 SIP 트렁크를 통해 중재 서버에 연결 된 PBX 시스템은 SIP 트렁크가 정의 된 동일한 네트워크 사이트에 있는 비즈니스용 Skype 사용자와 동일한 enforcements를 갖습니다. 예를 들어 PSTN 끝점은 PBX 사용자와 Skype for Business 사용자 (동일한 네트워크 사이트에 있는 경우)와 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 비즈니스용 Skype 사용자가 아닌 다른 네트워크 사이트에 있는 경우에는 PSTN 종점이 전화 회의에 참가할 수 없게 됩니다.

> [!NOTE]
> 비즈니스용 Skype 누적 업데이트 4를 사용 하 여 다음 표의 동작을 준수 해야 합니다.

|**클릭할**|**다른 파티**|**함수**|**발생**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 모바일  <br/> |PSTN  <br/> |비즈니스용 Skype Mobile이 PSTN 통화 중입니다. 비즈니스용 Skype 모바일을 전화 회의 자동 전화 교환 (CAA)으로 이동 합니다.  <br/> |통화가 차단 되 고 적절 한 오류 메시지가 발생 합니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |비즈니스용 Skype 클라이언트 또는 페더레이션 사용자  <br/> |클라이언트 또는 페더레이션 사용자는 비즈니스용 Skype 모바일 위치 기반 라우팅 사용자에 게 VoIP 통화를 하 고 있으며, 파티는 CAA로 전달 됩니다.  <br/> |에스컬레이션 통화가 차단 되 고 적절 한 오류 메시지가 발생 합니다.  <br/> |

## <a name="consultative-call-transfers"></a>Consultative 통화 전송

비즈니스용 Skype 모임에 대 한 위치 기반 라우팅을 적용 하는 것 외에도, 회의 응용 프로그램의 위치 기반 라우팅은 PSTN 끝점으로 송신 되는 consultative call 전송에 위치 기반 라우팅 제한을 적용 합니다. Consultative 통화 전송은 파티 중 하나가 새 사용자에 게 통화를 전송 하는 두 당사자 간에 설정 된 통화입니다. 예를 들어 PSTN 끝점은 사용자 A (비즈니스용 Skype 피호출자)를 호출 합니다. 사용자 A는 PSTN 사용자를 사용자 B (비즈니스용 Skype 사용자)로 전달 해야 하는지 결정 합니다. 사용자 A는 통화를 PSTN 사용자에 게 대기 상태로 설정 하 고 사용자 B를 호출 합니다. 사용자 B가 PSTN 사용자와 대화 하는 데 동의 합니다. 사용자 A가 사용자 B에 게 통화를 전송 합니다.

**Consultative 통화 이전 통화 흐름**

![회의에 대한 위치 기반 라우팅 다이어그램](../../media/LocationBasedRoutingForConferencing.jpg)

위치 기반 라우팅이 사용 하도록 설정 된 사용자가 PSTN 끝점의 consultative call 전송이 시작 되 면 (앞의 그림과 같이), PSTN 사용자와 비즈니스용 Skype 사용자 A 간 통화와 Skype 간에 각각의 활성 통화를 만듭니다. 비즈니스 사용자 A 및 비즈니스용 Skype 사용자 B: 다음 동작은 회의 응용 프로그램의 위치 기반 라우팅에 따라 적용 됩니다.

- PSTN 통화 라우팅에 대 한 SIP 트렁크에서 비즈니스용 Skype 사용자 B (즉, 전송 대상)가 있는 네트워크 사이트로 PSTN 통화를 다시 라우팅하도록 승인 된 경우에는 통화 전송이 허용 됩니다. 그렇지 않으면 consultative 통화 전송이 차단 됩니다. 이 인증은 현재 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 같은 네트워크 사이트에 있는 상대방의 위치를 기반으로 수행 됩니다.

- 인바운드 PSTN 통화 라우팅에 대 한 SIP 트렁크에서 전송 된 파티 (비즈니스용 Skype 사용자 B)가 있는 네트워크 사이트에 대 한 통화를 라우팅할 권한이 없거나, 전송 된 파티가 알 수 없는 네트워크 사이트에 있는 경우 consultative 통화 전송은 PSTN 끝점 (즉, 통화 전송 대상)이 차단 됩니다.

다음 표에서는 consultative 통화 전송에 대 한 회의 응용 프로그램의 위치 기반 라우팅에 따라 위치 기반 라우팅 제한이 적용 되는 방식을 설명 합니다. PBX 끝점은 네트워크 사이트와 직접 연결 되지 않지만 PBX에 연결 된 SIP 트렁크에는 네트워크 사이트를 할당할 수 있습니다. 따라서 PBX 끝점은 네트워크 사이트와 간접적으로 연결 될 수 있습니다.


|**통화의 네트워크 사이트 전송 파티**|**통화 전송 대상의 네트워크 사이트**|**결과가**|
|:-----|:-----|:-----|
|PSTN 끝점  <br/> |동일한 네트워크 사이트 (즉, 1 사이트)의 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 됩니다.  <br/> |
|PSTN 끝점  <br/> |다양 한 네트워크 사이트 (즉, 사이트 2)의 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |알 수 없는 네트워크 사이트의 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |페더레이션된 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 되지 않습니다.  <br/> |
|PSTN 끝점  <br/> |동일한 사이트의 PBX 끝점 (즉, 사이트 1)  <br/> |Consultative 전송이 허용 됩니다.  <br/> |
|PSTN 끝점  <br/> |다른 사이트의 PBX 끝점 (즉, 사이트 2)  <br/> |Consultative 전송이 허용 되지 않습니다.  <br/> |
|동일한 사이트의 PBX 끝점 (즉, 사이트 1)  <br/> |PSTN 끝점  <br/> |Consultative 전송이 허용 됩니다.  <br/> |
|다른 사이트의 PBX 끝점 (즉, 사이트 2)  <br/> |PSTN 끝점  <br/> |Consultative 전송이 허용 되지 않습니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |동일한 네트워크 사이트 (즉, 1 사이트)의 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |다양 한 네트워크 사이트 (즉, 사이트 2)의 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |알 수 없는 네트워크 사이트의 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 됩니다.  <br/> |
|모든 사이트의 PBX 끝점  <br/> |페더레이션된 비즈니스용 Skype 사용자  <br/> |Consultative 전송이 허용 됩니다.  <br/> |

## <a name="requirements"></a>요구 사항

회의 응용 프로그램의 위치 기반 라우팅에는 비즈니스용 Skype Server 또는 Lync Server 2013 누적 업데이트 2가 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 배포 되어 있어야 합니다. 이러한 서버 버전이 토폴로지의 일부 서버에 설치 되어 있지 않은 경우에는 위치 기반 라우팅 제한을 모임 및 consultative 통화 전송에 완벽 하 게 적용할 수 없습니다.

다음 표에서는 위치 기반 라우팅을 지 원하는 서버 역할 및 버전의 조합을 식별 합니다.


|**프런트 엔드 풀 버전**|**중재 서버 버전**|**지원**|
|:-----|:-----|:-----|
|비즈니스용 Skype Server 또는 Lync Server 2013 누적 업데이트 2  <br/> |비즈니스용 Skype Server 또는 Lync Server 2013 누적 업데이트 2  <br/> |'  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Lync Server 2013 누적 업데이트 1  <br/> |아니요  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Lync Server 2010  <br/> |아니요  <br/> |
|Lync Server 2013 누적 업데이트 2  <br/> |Office Communications Server 2007 R2  <br/> |아니요  <br/> |
|Lync Server 2013 누적 업데이트 1  <br/> |이상  <br/> |아니요  <br/> |
|Lync Server 2010  <br/> |이상  <br/> |아니요  <br/> |
|Office Communications Server 2007 R2  <br/> |이상  <br/> |아니요  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>회의를 위한 위치 기반 라우팅 구성

회의 응용 프로그램에 대 한 위치 기반 라우팅은 위치 기반 라우팅의 구성을 따릅니다. 기본 구성은 다음과 같습니다.

- 모임에 참가 하는 참가자의 위치는 해당 네트워크 사이트에 따라 결정 됩니다. 위치 기반 라우팅을 적용 하려면 네트워크 사이트 및 관련 네트워크 서브넷을 비즈니스용 Skype 서버에서 정의 해야 합니다.

- 위치 기반 모임 회람을 적용 하려면 위치 기반 라우팅에 대해 비즈니스용 Skype 참가자를 사용 하도록 설정 해야 합니다.

- 모임에 참가 하는 PSTN 끝점의 위치 기반 라우팅을 적용 하려면, PSTN 끝점을 연결 하는 데 사용 된 SIP 트렁크를 위치 기반 라우팅에 대해 구성 해야 합니다.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>회의를 위한 위치 기반 라우팅 사용

회의 응용 프로그램의 위치 기반 라우팅은 기본적으로 사용 되지 않습니다. 이 응용 프로그램을 사용 하기 전에 응용 프로그램에 할당할 올바른 우선 순위를 결정 해야 합니다. 이 우선 순위를 결정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하세요.

Get-CsServerApplication-Id 서비스: 등록자:<Pool FQDN>이 cmdlet에서는 \<풀 FQDN\> 이 회의 응용 프로그램의 위치 기반 라우팅을 사용 하도록 설정 되는 풀입니다.

이 cmdlet은 비즈니스용 Skype Server에서 호스트 하는 응용 프로그램 목록 및 각각에 대 한 우선 순위 값을 반환 합니다. 회의 응용 프로그램의 위치 기반 라우팅에는 "UdcAgent" 응용 프로그램 보다 크고 "DefaultRouting", "ExumRouting" 및 "OutboundRouting" 응용 프로그램 보다 작은 우선 순위 값이 할당 되어야 합니다. "UdcAgent" 응용 프로그램의 우선 순위 값 보다 1 점이 더 높은 우선 순위 값을 사용 하 여 회의 응용 프로그램에 대 한 위치 기반 라우팅을 할당 하는 것이 좋습니다.

예를 들어 "UdcAgent" 응용 프로그램의 우선 순위 값이 "2" 이면 "DefaultRouting" 응용 프로그램의 우선 순위 값이 "8"이 되 고 "ExumRouting" 응용 프로그램의 우선 순위 값은 "9"이 고 "OutboundRouting" 응용 프로그램의 우선 순위 값은 "10"입니다. 회의 응용 프로그램의 위치 기반 라우팅 (우선 순위 값 "3")을 할당 해야 합니다. 이렇게 하면 다른 응용 프로그램 (우선 순위: 0에서 1로), "UdcAgent" (우선 순위: 2), 위치 기반 라우팅 회의 응용 프로그램 (우선 순위: 3), 기타 응용 프로그램 (우선 순위: 4 ~ 8), "순으로 응용 프로그램의 우선 순위를 다음 순서로 배치 합니다. DefaultRouting "(Priority: 9)," ExumRouting "(Priority: 10) 및" OutboundRouting "(Priority: 11).

회의 응용 프로그램의 위치 기반 라우팅에 대 한 올바른 우선 순위 값을 찾은 후에는 위치 기반 라우팅에 대해 사용자가 사용 하도록 설정 된 각 프런트 엔드 풀 또는 Standard Edition 서버에 대해 다음 cmdlet을 입력 합니다.

새-CsServerApplication-Id 서비스: 등록자:`<Pool FQDN`>/Lbrouting-우선 \<순위의 응용\> 프로그램 우선 순위-사용 $true-중요 $true-Uri<http://www.microsoft.com/LCS/LBRouting> 

예를 들면 다음과 같습니다.

새-CsServerApplication-Id 서비스: 등록자:Ls2013.62lbrpool. c o m/LBRouting-Priority 3-사용 $true-중요 $true-Urihttp://www.microsoft.com/LCS/LBRouting 

이 cmdlet을 사용한 후에는 풀의 모든 프런트 엔드 서버를 다시 시작 하거나, 회의 응용 프로그램에 대 한 위치 기반 라우팅이 사용 하도록 설정 된 스탠더드 버전 서버를 해제 합니다.

> [!IMPORTANT]
> 회의 또는 consultative 전송에 대 한 위치 기반 라우팅 enforcements는 해당 풀 또는 Standard Edition 서버의 모든 프런트 엔드 서버가 다시 시작 될 때까지 적용 되지 않습니다. 앞의 cmdlet **** 에서 **$true** 하도록 설정한 경우, Skype for Business Server 서비스가 즉시 다시 시작 됩니다. 이러한 서비스를 즉시 다시 시작 하지 않으려면 지금 **$false** 하도록 설정한 **** 다음, 서비스를 다시 시작한 후에 **설정-csserverapplication** 을 사용 하 여 나중에 **$true** 에 **중요** 한 것으로 변경 합니다.

회의 응용 프로그램을 위한 위치 기반 라우팅이 성공적으로 사용 하도록 설정 되 고 해당 서버가 모두 다시 시작 되 면 위치 기반 라우팅에 대해 사용 하도록 설정 된 비즈니스용 Skype 사용자가 구성한 모든 회의가 모니터링 됩니다. PSTN 유료 바이패스


