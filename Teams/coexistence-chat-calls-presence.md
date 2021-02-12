---
title: 비즈니스용 Skype와 동시 사용
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: '& 라우팅 매개 변수, 채팅 & 라우팅, 기존 스레드의 & 채팅, 현재 상태 등 Teams 및 비즈니스용 Skype & 함께 동작합니다.'
ms.openlocfilehash: 9dd2baa717466b0f414168356256b6d78ce33f6a
ms.sourcegitcommit: e5e60079cf9d62627de6b26dd4badd353bcc190c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48661350"
---
# <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

비즈니스용 Skype와 Teams 클라이언트와 사용자 간의 공존 및 상호 연동성은 TeamsUpgrade 모드로 정의됩니다. 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침에 설명되어 [있습니다.](migration-interop-guidance-for-teams-with-skype.md)

지정된 모든 사용자에게는 기본적으로 또는 관리자가 명시적으로 TeamsUpgrade 모드가 할당됩니다. 기본값은 *제도입니다.* Teams로 업그레이드된 사용자는 *TeamsOnly 모드가 있습니다.* *SfBOnly,* *SfBWithTeamsCollab* 및 *SfBWithTeamsCollabAndMeetings도* 가능한 모드입니다.


## <a name="routing-parameters"></a>라우팅 매개 변수

받는 사람의 TeamsUpgrade 모드는 테넌트 내 및 페더링된 테넌트에서 채팅, 통화 및 현재 상태의 동작을 결정하는 데 핵심입니다.

보낸 사람이 Teams를 사용하는 경우 새 대화 스레드를 만들 때 라우팅이 결정됩니다. Teams의 기존 대화 스레드는 스레드가 생성될 때 결정되는 라우팅 방법을 항상 유지합니다. Teams는 영구 스레드를 지원합니다.

 스레드 라우팅 방법은  

- *테넌트* 내 Teams-Teams 대화를 위한 네이티브
- *테넌트* 내 비즈니스용 Skype 간 대화를 위한 Interop
- *테넌트에서* 페더러드된 대화에 대해 페더러화

스레드 라우팅 방법을 결정하는 매개 변수는

- 받는 사람의 TeamsUpgrade 모드
- 보낸 사람이 사용하는 클라이언트
- 대화가 새 대화인지 아니면 기존 스레드의 일부인지 여부
- 대화가 테넌트 내인지 페더러인지 여부
- 대화가 가능한지 여부
    - *테넌트* 내 상호 연동성을 위해서는 테넌트가 순수 온라인 또는 비즈니스용 Skype 하이브리드가 필요합니다. 순수하게 프레미스 테넌트는 테넌트 내 상호 연동성을 사용할 수 없습니다.
    - *테넌트* 간 페더넌트는 항상 적절한 비즈니스용 Skype 페더넌트 구성과 두 테넌트의 적절한 Teams 페더넌트 구성이 필요합니다. 비즈니스용 Skype 하이브리드는 테넌트에 필요하지 않습니다.
    - 발신자에 대한 비즈니스용 Skype 계정이 프레미스에 있는 경우 해당 사용자는 테넌트 내 상호 연동성 또는 페더넌트에 Teams 클라이언트를 사용할 수 없습니다. 해당 사용자는 상호 연동성 및 페더러전을 위해 비즈니스용 Skype 클라이언트만 사용할 수 있습니다.
    - Teams 간 통신은 항상 테넌트에서 가능합니다.

> [!NOTE]
> 받는 사람과 보낸 사람이 TeamsOnly 업그레이드 모드에 있는 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 기본 채팅 환경이 됩니다. 자세한 내용은 Teams에서 외부(페더러리) 사용자에 대한 네이티브 채팅 환경을 [읽어보아야 합니다.](native-chat-for-external-users.md) 대화 참가자 중 한 자가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와 상호 운영 환경으로 남아 있습니다.

## <a name="chat-and-call-routing"></a>채팅 및 통화 라우팅

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 테넌트 내 라우팅 

아래 표는 테넌트 내 채팅 및 통화의 라우팅을 캡처하며 기존 스레드에서 시작되지 않은 새 통화 또는 채팅에 유효합니다. 왼쪽의 사용자가 시작한 경우 오른쪽의 테넌트 내 받는 사람에게 새 통화 또는 채팅을 받을 클라이언트를 설명합니다.

TeamsOnly 사용자에게 전송된 메시지는 항상 Teams로 라우팅됩니다. 위에서 설명한 대로 대화가 가능한 경우 SfB 사용자에게 전송된 메시지는 항상 비즈니스용 \* Skype로 라우팅됩니다. 제도 사용자에게 전송된 메시지는 항상 전송된 동일한 클라이언트로 라우팅됩니다.

아래 표에서는 발신자 모드, 선택한 클라이언트 및 비즈니스용 Skype 클라이언트가 있는 위치(프레미스 또는 온라인)에 따라 시작자(가장 왼쪽 세 개 열)에서 전화를 받을 클라이언트를 보여 주세요.

다음 표에서 다음을 수행 합니다. 
- **SfB \** _는 _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings* 모드를 나타남

- *이탈 텍스트는* 상호 대화를 강조합니다.

- **불가능은** 채팅 또는 통화가 불가능한 상황을 나타 내는 것입니다. 발신자는 이러한 경우 대신 비즈니스용 Skype를 사용해야 합니다. 이는 프레미스/하이브리드 고객에 대한 Microsoft의 객관적 지침이 Teams 업그레이드의 시작점으로 Islands(일반적으로 SfBWithTeamsCollab) 외의 모드를 사용하는 이유 중 하나입니다.

**표 1a: 테넌트 내 새 채팅 또는 섬 모드 수신자에 대한 통화 라우팅**

| <br/><br/> 모드 | Originator <br/><br/> 클라이언트 | <br/><br/> SfB &nbsp; 홈 |<br/><br/>Route-->| 받는 사람 <br/><br/> 아일랜드  |
|--- |--- |--- |--- |--- |
| 아일랜드 | Teams <br/> 비즈니스용 Skype<br/> Teams<br/> 비즈니스용 Skype| 온라인<br/> 온라인<br/> On-prem<br/>On-prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> 비즈니스용 Skype<br/> Teams<br/> 비즈니스용 Skype|
|SfB\* <br/> | 비즈니스용 Skype<br/>비즈니스용 Skype<br/> | 온라인<br/> On-prem<br/> |&boxv;<br/>&boxv;|비즈니스용 Skype<br/>비즈니스용 Skype<br/>|
|TeamsOnly |Teams| 온라인<br/>|&boxv;<br/>|Teams|
| | | | | |

**표 1b: SfB 모드에서 받는 사람에게 테넌트 내 새 채팅 또는 통화 라우팅 \***

| <br/><br/> 모드   | Originator <br/><br/> 클라이언트 | <br/><br/> SfB &nbsp; 홈 |<br/><br/>Route--> |   받는 사람 <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| 아일랜드 |Teams<br/>비즈니스용 Skype<br/>Teams <br/>비즈니스용 Skype  |온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *비즈니스용 Skype* <br/> 비즈니스용 Skype<br/> **가능하지 않습니다.** <br/>비즈니스용 Skype<br/> |
|SfB\* <br/> | 비즈니스용 Skype<br/>비즈니스용 Skype<br/> | 온라인<br/> On-prem<br/> |&boxv;<br/>&boxv; |  비즈니스용 Skype<br/>비즈니스용 Skype<br/> |
|TeamsOnly |Teams| 온라인<br/>|&boxv;<br/> |  *비즈니스용 Skype* <br/>| 
| | | | | |

**표 1c: 테넌트 내 새 채팅 또는 TeamsOnly 모드 수신자에게 라우팅 라우팅**

| <br/><br/> 모드   | Originator <br/><br/> 클라이언트 | <br/><br/> SfB &nbsp; 홈 |<br/><br/>Route-->|   받는 사람 <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| 아일랜드   |Teams<br/>비즈니스용 Skype<br/>Teams <br/>비즈니스용 Skype<br/>|온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | 비즈니스용 Skype<br/>비즈니스용 Skype<br/> | 온라인<br/> On-prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | 온라인 |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 페더링된 라우팅
  
아래 표는 페더링된 통화 및 채팅의 라우팅을 캡처하며 새 통화 또는 채팅에 유효합니다. 왼쪽에 있는 사용자가 시작한 경우 오른쪽의 페더맹된 대상 사용자에게 새 호출 또는 채팅을 받을 클라이언트를 설명합니다.

요약하면 위에서 설명한 대로 대화가 가능한 경우 TeamsOnly 사용자에게 전송된 메시지는 항상 Teams에 전송됩니다. SfB 사용자에게 전송된 메시지는 항상 비즈니스용 Skype에 전송됩니다. 이 사용자에게 전송된 메시지는 보낸 클라이언트에 관계없이 항상 비즈니스용 \* Skype에 전송됩니다. 페더넌트 채팅 및 통화 라우팅은 제도 사용자가 항상 비즈니스용 Skype에서 페더링 통신을 받을 수 있는 테넌트 내 라우팅과 다릅니다.

이는 페더러드 비즈니스용 Skype 파트너가 이미 Teams를 사용하고 있는 경우 아일랜드 모드로 사용된다고 가정할 수 있기 때문에입니다. 제도는 기본 모드입니다. 하지만 모든 제도 사용자가 Teams를 실행하고 있는 것으로 가정할 수 없습니다. 비즈니스용 Skype로 라우팅하면 섬 사용자와의 통신이 실패하지 않습니다. Teams로 라우팅한 경우 대상이 Teams를 사용하지 않는 경우 해당 통신이 누락될 수 있습니다. 비즈니스용 Skype로 라우팅하면 메시지가 항상 수신됩니다.  

> [!NOTE]
> Teams 페더넌트의 현재 구현은 비즈니스용 Skype 페더넌트에 기반하므로 상호 운영성 인프라를 활용합니다(원래자 테넌트가 순수 온라인 또는 비즈니스용 Skype 하이브리드가 필요) 네이티브 스레드에 비해 기능의 감소된 집합을 제공합니다. 향후에는 원시 Teams를 Teams 페더러에 제공해야 합니다. 이 시점에서 스레드는 네이티브로 제공될 것이고 모든 기능을 제공합니다.

아래 표에서는 발신자 모드, 선택한 클라이언트 및 비즈니스용 Skype 클라이언트가 있는 위치(프레미스 또는 온라인)에 따라 발신자(가장 왼쪽 세 개 열)로부터 전화를 받는 클라이언트를 설명합니다.

**표 2a: 제도 받는 사람에게 새 채팅 또는 통화 라우팅 페더링**

| <br/><br/>모드   | Originator<br/><br/> 클라이언트| <br/><br/>SfB 홈|<br/><br/>Route--> | 받는 사람<br/><br/> 아일랜드 |
|--- |--- |--- |--- |--- |
| 아일랜드 |Teams<br/>비즈니스용 Skype <br/>Teams <br/>비즈니스용 Skype  |온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *비즈니스용 Skype* <br/> 비즈니스용 Skype <br/> **가능하지 않습니다.**   <br/> 비즈니스용 Skype |
| SfB\* |비즈니스용 Skype <br/>비즈니스용 Skype |온라인<br/> On-prem<br/> | &boxv;<br/>&boxv;|비즈니스용 Skype <br/>비즈니스용 Skype |
| TeamsOnly |Teams |온라인| &boxv;|*비즈니스용 Skype* |
|  | | | | 

**표 2b: SfB 모드에서 받는 사람에게 새 채팅 또는 통화 라우팅 페더링 \***

| <br/><br/>모드   | Originator<br/><br/> 클라이언트| <br/><br/>SfB 홈|<br/><br/>Route-->|  받는 사람<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| 아일랜드 |Teams<br/>비즈니스용 Skype <br/>Teams <br/>비즈니스용 Skype <br/>|온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *비즈니스용 Skype* <br/> 비즈니스용 Skype <br/> **가능하지 않습니다.** <br/>비즈니스용 Skype <br/> |  
| SfB\* |비즈니스용 Skype <br/>비즈니스용 Skype  |온라인<br/> On-prem<br/>  |&boxv;<br/>&boxv; | 비즈니스용 Skype <br/>비즈니스용 Skype  |
| TeamsOnly | Teams|온라인 |&boxv; |*비즈니스용 Skype*  |
|  | | | | |

**표 2c: TeamsOnly 모드 수신자에게 새 채팅 또는 통화 라우팅 페더링**

| <br/><br/>모드 | Originator<br/><br/> 클라이언트| <br/><br/>SfB 홈|<br/><br/>Route-->|  받는 사람<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| 아일랜드  |Teams<br/>비즈니스용 Skype <br/>Teams <br/>비즈니스용 Skype <br/>|온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**가능하지 않습니다.** <br/>*Teams* |
| SfB\* |비즈니스용 Skype <br/>비즈니스용 Skype  | 온라인<br/> On-prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |온라인 |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>기존 스레드의 채팅 및 통화

### <a name="from-teams"></a>Teams에서

해당 라우팅 옵션을 계속 사용할 수 있는 경우 Teams의 기존 영구 스레드에서 시작된 호출 또는 채팅은 해당 스레드와 동일한 방식으로 라우팅됩니다.

Teams의 기존 영구 스레드가 네이티브 스레드(예: Teams로 라우팅)인 경우 해당 스레드의 추가 채팅 메시지와 통화가 Teams로 이동됩니다. 상호 연결 스레드(예: 비즈니스용 Skype로 라우팅)인 경우 추가 채팅 메시지와 통화가 비즈니스용 Skype로 전송됩니다(다시 라우팅 옵션을 사용할 수 있는 경우).

> [!NOTE]
> 스레드가 이제 Teams로 업그레이드된 사용자에 대한 interop 스레드인 경우와 같이 Teams의 기존 스레드를 더 이상 라우팅할 수 없습니다. 스레드가 상호 연동 스레드로 만들어지기 때문에 스레드는 비즈니스용 Skype로 라우팅되지만 해당 사용자는 더 이상 채팅 및 통화에 비즈니스용 Skype를 사용할 수 없습니다. 이 경우 스레드가 비활성화되어 추가 통신을 허용하지 않습니다.

### <a name="from-skype-for-business"></a>비즈니스용 Skype에서

비즈니스용 Skype 스레드는 10분을 초과하여 유지되지 않습니다. SIP 세션 시간 제한입니다. SIP 세션이 만료하기 전에 비즈니스용 Skype의 기존 스레드에서 채팅 및 통화는 스레드와 동일한 방식으로 라우팅됩니다. SIP 세션 시간 제한을 초과하는 비즈니스용 Skype의 기존 스레드에서 호출 및 채팅은 원래 스레드가 다른 쪽에서 온 클라이언트에 관계없이 원격 파티의 비즈니스용 Skype로 라우팅됩니다.

### <a name="availability"></a>가용성

위에서 설명한 테넌트 내 동작과 페더리된 동작을 모두 사용할 수 있으며 다음과 같은 제한 사항이 있습니다.

- 테넌트가 다른 GoLocal 배포 또는 지리에 있는 외부 참석자는 "페더넌트" 모임 중에는 IM 채팅을 볼 수 없습니다.
- 다중텐트 O365와 소버린 클라우드 간의 페더ation 및 interop은 지원되지 않습니다.

## <a name="presence"></a>현재 상태

일부 사용자가 Teams 클라이언트를 사용하고 다른 사용자가 여전히 비즈니스용 Skype 클라이언트를 사용하고 있는 경우 두 클라이언트를 모두 사용하는 사용자가 여러명 있을 수 있습니다. 개별 사용자가 있는 클라이언트에 관계없이 현재 상태는 모든 사용자와 공유하도록 할 수 있습니다. 조직에서 공유하는 경우 사용자는 채팅을 시작하거나 전화를 걸 수 있는 것이 적절한지 더 잘 결정할 수 있습니다.

예를 들어, 발신자 채팅 또는 통화가 대상의 비즈니스용 Skype 클라이언트에 상주해야 하는 경우 발신자에 표시해야 하는 비즈니스용 Skype 클라이언트의 현재 상태입니다. 대상의 Teams 클라이언트에 연결해야 하는 경우 표시해야 하는 Teams 클라이언트의 현재 상태입니다.

예상되는 동작을 이해하려면 사용자의 공존 모드를 기반으로 하여 현재 상태가 공유되는 것을 이해해야 합니다.

* 사용자가 TeamsOnly 모드인 경우 다른 사용자(Teams 또는 비즈니스용 Skype)에 TeamsOnly 사용자의 Teams 현재 상태 표시
* 사용자가 \* SfB 모드(SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings)에 있는 경우 다른 사용자(Teams 또는 비즈니스용 Skype)는 해당 SfB 사용자의 비즈니스용 Skype 현재 상태 확인 \*
* 사용자가 제도(또는 레거시) 모드에 있는 경우 Teams의 현재 상태와 비즈니스용 Skype의 현재 상태는 독립적(값이 일치하지 않을 필요) 다른 사용자가 동일한 테넌트에 있는지, 페더러티 테넌트에 있는지, 어떤 클라이언트에 사용하느냐에 따라 하나 또는 다른 제도 사용자의 존재를 볼 수 있습니다.
    * Teams에서 동일한 테넌트 내의 다른 사용자는 제도 사용자의 Teams 현재 상태와 같은 정보를 볼 수 있습니다. 이는 위의 테넌트 내 라우팅 테이블과 정렬됩니다.
    * Teams에서 페더넌트 테넌트의 다른 사용자는 Islands 사용자의 비즈니스용 Skype 현재 상태와 같은 정보를 볼 수 있습니다. 이는 위의 페더링된 라우팅 테이블과 정렬됩니다.
    * 비즈니스용 Skype에서 다른 사용자는 아일랜드 사용자의 비즈니스용 Skype 현재 상태(인-테넌트 및 페더러티)를 볼 수 있습니다. 위의 라우팅 테이블과 정렬됩니다.


### <a name="in-tenant-presence"></a>테넌트 내 현재 상태

TeamsOnly 사용자에게 전송된 메시지는 항상 Teams에 전송됩니다. 위에서 설명한 대로 대화가 가능한 경우 SfB 사용자에게 전송된 메시지는 항상 비즈니스용 \* Skype에 전송됩니다. 제도 사용자에게 전송된 메시지는 항상 해당 사용자가 시작된 클라이언트로 전송됩니다.

이 표에서는 게시자 모드 및 Watcher의 클라이언트(새 스레드의 경우)에 따라 Watcher가 볼 수 있는 게시자의 현재 상태에 대해 설명하고 있습니다.

**표 3: 테넌트 내 현재 상태(새 스레드)**

|감시자 <br/><br/>클라이언트|<br/><br/>Route--> |<br/><br/>아일랜드 |Publisher <br/><br/>SfB\* |<br/>Teams만 해당|
|--- |--- |--- |--- |---|
|비즈니스용 Skype |&boxv;|비즈니스용 Skype | 비즈니스용 Skype | Teams|
|Teams |&boxv; |Teams |비즈니스용 Skype |Teams |
| | | | |

### <a name="federated-presence"></a>페더러드 현재 상태

페더러가 있는 현재 상태는 표 2에 표시된 페더러드된 도달 가능성에 기반합니다.

아래 표에서는 게시자 모드 및 Watcher의 클라이언트(새 스레드의 경우)에 따라 Watcher가 볼 수 있는 게시자의 현재 상태에 대해 설명합니다. 실제로 Watcher의 클라이언트는 이 단계에서 페더러에 차이가 없습니다.

**표 4: 페더러드 현재 상태(새 스레드)**

|감시자 <br/><br/> 클라이언트 |<br/><br/>Route-->|<br/><br/> 아일랜드  |Publisher <br/><br/> SfB\* |<br/><br/> Teams만 해당 |
|--- |--- |--- |--- |---|
|비즈니스용 Skype |&boxv; |비즈니스용 Skype  | 비즈니스용 Skype  | Teams  |
|Teams | &boxv;|비즈니스용 Skype |비즈니스용 Skype |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>기존 스레드의 현재 상태

기존 스레드에서 현재 상태 및 도달 가능성에 맞추기 위해 라우팅이 가능할 경우 스레드에 노출된 대상의 현재 상태는 스레드 라우팅에 맞춰야 합니다.

특히 이전에 영구 상호 운영 대화 스레드를 사용했던 받는 사람이 Teams로 업그레이드된 경우 해당 스레드는 더 이상 정확한 현재 상태의 반영을 반영하지 않고 더 이상 라우팅할 수 없습니다. 새 스레드를 시작해야 합니다.

## <a name="related-links"></a>관련 링크
[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[비디오: SfB와 Teams 간의 공존 및 상호 운영성 관리](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
