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
description: 라우팅 매개 변수, 채팅 & 라우팅, 기존 스레드에서 & 채팅, 현재 상태 등 Teams & 비즈니스용 Skype 간의 공존 & 동작입니다.
ms.openlocfilehash: 603356df5e6f5006ea67f6a84141acf1347c1235
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122342"
---
# <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

비즈니스용 Skype 클라이언트와 Teams 클라이언트와 사용자 간의 공존 및 상호 연동성은 TeamsUpgrade 모드로 정의됩니다. 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 실행성 지침에 [설명되어 있습니다.](migration-interop-guidance-for-teams-with-skype.md)

지정된 모든 사용자에게는 기본적으로 또는 관리자에 의해 명시적으로 TeamsUpgrade 모드가 항상 할당됩니다. 기본값은 *Islands입니다.* Teams로 업그레이드된 사용자는 *TeamsOnly의 모드를 습니다.* *SfBOnly,* *SfBWithTeamsCollab* 및 *SfBWithTeamsCollabAndMeetings도* 가능한 모드입니다.


## <a name="routing-parameters"></a>라우팅 매개 변수

받는 사람의 TeamsUpgrade 모드는 테넌트 내 및 페더리드 테넌트에서 채팅, 통화 및 현재 상태의 동작을 결정하는 데 핵심입니다.

보낸 사람이 Teams를 사용하는 경우 새 대화 스레드를 만들 때 라우팅 결정을 내릴 수 있습니다. Teams의 기존 대화 스레드는 항상 스레드를 만들 때 결정된 라우팅 메서드를 유지합니다. Teams는 영구 스레드를 지원합니다.

 스레드 라우팅 메서드는:  

- *Teams* to Teams 대화 인 테넌트에 대한 네이티브
- *테넌트* 내 비즈니스용 Skype 대화에 대한 Teams 간 interop
- *테넌트에서* 페더리된 대화에 페더리드

스레드 라우팅 메서드를 결정하는 매개 변수는 다음입니다.

- 받는 사람의 TeamsUpgrade 모드
- 보낸 사람이 사용하는 클라이언트
- 대화가 새로 추가되거나 기존 스레드의 일부인지 여부
- 대화가 테넌트 내인지 페더리드인지 여부
- 대화가 가능할지 여부
    - *테넌트* 내 상호 연동성은 테넌트가 순수 온라인 또는 비즈니스용 Skype 하이브리드일 수 있습니다. 순수하게 프레미스 테넌트는 테넌트 내 상호 연동성을 사용할 수 없습니다.
    - *테넌트* 간 페더전은 항상 적절한 비즈니스용 Skype 페더넌트 구성과 두 테넌트의 적절한 Teams 페더넌트 구성이 필요합니다. 비즈니스용 Skype 하이브리드는 테넌트가 필요하지 않습니다.
    - 발신자의 비즈니스용 Skype 계정이 프레미스에 있는 경우 해당 사용자는 테넌트 내 상호 실행성 또는 페더니에 대해 Teams 클라이언트를 사용할 수 없습니다. 해당 사용자는 비즈니스용 Skype 클라이언트만 상호 실행성 및 페더리에 사용할 수 있습니다.
    - Teams 간 통신은 항상 테넌트에서 가능합니다.

> [!NOTE]
> 받는 사람 및 보낸 사람이 TeamsOnly 업그레이드 모드인 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 네이티브 채팅 환경이 됩니다. 자세한 내용은 Teams의 외부(페더리화) 사용자에 대한 네이티브 채팅 환경을 [읽어보아야 합니다.](native-chat-for-external-users.md) 대화 참가자 중 하나가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와 상호 운영 환경으로 남아 있습니다.

## <a name="chat-and-call-routing"></a>채팅 및 통화 라우팅

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 테넌트 내 라우팅 

아래 표는 테넌트 내 채팅 및 통화의 라우팅을 캡처하며, 기존 스레드에서 시작되지 않은 새 통화 또는 채팅에 유효합니다. 왼쪽에 있는 사용자가 시작한 경우 오른쪽의 테넌트 받는 사람 사용자에게 새 호출 또는 채팅을 받을 클라이언트를 설명합니다.

TeamsOnly 사용자에게 전송된 메시지는 항상 Teams로 라우팅됩니다. 위에서 설명한 대로 대화가 가능한 경우 SfB 사용자에게 보낸 메시지는 항상 \* 비즈니스용 Skype로 라우팅됩니다. Islands 사용자에게 보낸 메시지는 항상 전송된 동일한 클라이언트로 라우팅됩니다.

아래 표에는 발신자 모드, 선택한 클라이언트 및 비즈니스용 Skype 클라이언트가 있는 위치(프레미스 또는 온라인)에 따라 발신자(가장 왼쪽 세 개의 열)에서 호출을 받을 클라이언트가 표시됩니다.

다음 표에서 다음을 수행합니다. 
- **SfB \** _ 는 다음 모드 중 _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings를 나타내고 있습니다.*

- *이탈 텍스트는* 상호 대화를 강조 표시합니다.

- **불가능은** 채팅 또는 통화가 불가능한 상황을 나타 내는 것입니다. 발신자는 이러한 경우 대신 비즈니스용 Skype를 사용해야 합니다. 이는 Microsoft의 프레미스/하이브리드 고객에 대한 지침이 Teams로의 업그레이드 여정의 시작점으로 아일랜드(일반적으로 SfBWithTeamsCollab)가 아니라 다른 모드를 사용하는 이유 중 하나입니다.

**표 1a: 테넌트 내 새 채팅 또는 섬 모드 받는 사람에게 라우팅 호출**

| <br/><br/> 모드 | 발신자 <br/><br/> 클라이언트 | <br/><br/> SfB &nbsp; 홈 |<br/><br/>Route->| 받는 사람 <br/><br/> Islands  |
|--- |--- |--- |--- |--- |
| Islands | Teams <br/> 비즈니스용 Skype<br/> Teams<br/> 비즈니스용 Skype| 온라인<br/> 온라인<br/> On-prem<br/>On-prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> 비즈니스용 Skype<br/> Teams<br/> 비즈니스용 Skype|
|SfB\* <br/> | 비즈니스용 Skype<br/>비즈니스용 Skype<br/> | 온라인<br/> On-prem<br/> |&boxv;<br/>&boxv;|비즈니스용 Skype<br/>비즈니스용 Skype<br/>|
|TeamsOnly |Teams| 온라인<br/>|&boxv;<br/>|Teams|
| | | | | |

**표 1b: SfB 모드에서 받는 사람에게 테넌트 내 새 채팅 또는 통화 라우팅 \***

| <br/><br/> 모드   | 발신자 <br/><br/> 클라이언트 | <br/><br/> SfB &nbsp; 홈 |<br/><br/>Route-> |   받는 사람 <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Islands |Teams<br/>비즈니스용 Skype<br/>Teams <br/>비즈니스용 Skype  |온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *비즈니스용 Skype* <br/> 비즈니스용 Skype<br/> **가능하지 않습니다.** <br/>비즈니스용 Skype<br/> |
|SfB\* <br/> | 비즈니스용 Skype<br/>비즈니스용 Skype<br/> | 온라인<br/> On-prem<br/> |&boxv;<br/>&boxv; |  비즈니스용 Skype<br/>비즈니스용 Skype<br/> |
|TeamsOnly |Teams| 온라인<br/>|&boxv;<br/> |  *비즈니스용 Skype* <br/>| 
| | | | | |

**표 1c: 테넌트 내 새 채팅 또는 TeamsOnly 모드 받는 사람에게 라우팅 호출**

| <br/><br/> 모드   | 발신자 <br/><br/> 클라이언트 | <br/><br/> SfB &nbsp; 홈 |<br/><br/>Route->|   받는 사람 <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Islands   |Teams<br/>비즈니스용 Skype<br/>Teams <br/>비즈니스용 Skype<br/>|온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | 비즈니스용 Skype<br/>비즈니스용 Skype<br/> | 온라인<br/> On-prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | 온라인 |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 페더리된 라우팅
  
아래 표는 페더링된 통화 및 채팅의 라우팅을 캡처하며 새 통화 또는 채팅에 유효합니다. 왼쪽에 있는 사용자가 시작한 경우 오른쪽의 페더리드 대상 사용자에게 새 호출 또는 채팅을 받을 클라이언트를 설명합니다.

요약하면 위에서 설명한 대로 대화가 가능한 경우 TeamsOnly 사용자에게 보낸 메시지는 항상 Teams에 표시됩니다. SfB 사용자에게 보낸 메시지는 항상 비즈니스용 Skype에 상륙합니다. 아일랜드 사용자에게 보낸 메시지는 보낸 클라이언트에 관계없이 항상 \* 비즈니스용 Skype에 표시됩니다. 페더링된 채팅 및 통화에 대한 라우팅은 아일랜드 사용자가 항상 비즈니스용 Skype에서 페더리드 통신을 수신하는 테넌트 내 라우팅과 다릅니다.

이는 페더러드 비즈니스용 Skype 파트너가 이미 아일랜드 모드인 경우 Teams를 사용했다고 가정할 수 없습니다. 섬은 기본 모드지만 모든 섬 사용자가 Teams를 실행하고 있는 것으로 가정할 수 없습니다. 비즈니스용 Skype로 라우팅하여 아일랜드 사용자와의 통신이 실패하지 않도록 합니다. Teams로 라우팅한 경우 대상이 Teams를 사용하지 않는 경우 해당 통신이 누락될 수 있습니다. 비즈니스용 Skype로 라우팅하면 메시지가 항상 수신되도록 합니다.  

> [!NOTE]
> Teams 페더넌트의 현재 구현은 비즈니스용 Skype 페더전을 기반으로 하므로 상호 운영성 인프라를 활용합니다(이는 시작자 테넌트가 순수 온라인 또는 비즈니스용 Skype 하이브리드로 필요함) 네이티브 스레드에 비해 기능의 감소 집합을 제공합니다. 향후에는 네이티브 Teams를 Teams 페더전에 제공할 예정입니다. 이 시점에서 스레드는 네이티브로 제공되어 전체 기능을 제공할 예정입니다.

아래 표에서는 발신자 모드, 선택한 클라이언트, 비즈니스용 Skype 클라이언트가 있는 위치(프레미스 또는 온라인)에 따라 발신자(가장 왼쪽 세 개 열)로부터 전화를 받을 클라이언트를 설명합니다.

**표 2a: 섬 받는 사람에게 새 채팅 또는 통화 라우팅 페더링**

| <br/><br/>모드   | 발신자<br/><br/> 클라이언트| <br/><br/>SfB 홈|<br/><br/>Route-> | 받는 사람<br/><br/> Islands |
|--- |--- |--- |--- |--- |
| Islands |Teams<br/>비즈니스용 Skype <br/>Teams <br/>비즈니스용 Skype  |온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *비즈니스용 Skype* <br/> 비즈니스용 Skype <br/> **가능하지 않습니다.**   <br/> 비즈니스용 Skype |
| SfB\* |비즈니스용 Skype <br/>비즈니스용 Skype |온라인<br/> On-prem<br/> | &boxv;<br/>&boxv;|비즈니스용 Skype <br/>비즈니스용 Skype |
| TeamsOnly |Teams |온라인| &boxv;|*비즈니스용 Skype* |
|  | | | | 

**표 2b: SfB 모드에서 받는 사람에게 새 채팅 또는 통화 라우팅 페더링 \***

| <br/><br/>모드   | 발신자<br/><br/> 클라이언트| <br/><br/>SfB 홈|<br/><br/>Route->|  받는 사람<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Islands |Teams<br/>비즈니스용 Skype <br/>Teams <br/>비즈니스용 Skype <br/>|온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *비즈니스용 Skype* <br/> 비즈니스용 Skype <br/> **가능하지 않습니다.** <br/>비즈니스용 Skype <br/> |  
| SfB\* |비즈니스용 Skype <br/>비즈니스용 Skype  |온라인<br/> On-prem<br/>  |&boxv;<br/>&boxv; | 비즈니스용 Skype <br/>비즈니스용 Skype  |
| TeamsOnly | Teams|온라인 |&boxv; |*비즈니스용 Skype*  |
|  | | | | |

**표 2c: TeamsOnly 모드 받는 사람에 대한 페더링된 새 채팅 또는 통화 라우팅**

| <br/><br/>모드 | 발신자<br/><br/> 클라이언트| <br/><br/>SfB 홈|<br/><br/>Route->|  받는 사람<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Islands  |Teams<br/>비즈니스용 Skype <br/>Teams <br/>비즈니스용 Skype <br/>|온라인<br/> 온라인<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**가능하지 않습니다.** <br/>*Teams* |
| SfB\* |비즈니스용 Skype <br/>비즈니스용 Skype  | 온라인<br/> On-prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |온라인 |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>기존 스레드에서 채팅 및 호출

### <a name="from-teams"></a>Teams에서

해당 라우팅 옵션을 계속 사용할 수 있는 경우 Teams의 기존 영구 스레드에서 시작된 호출 또는 채팅은 해당 스레드와 동일한 방식으로 라우팅됩니다.

Teams의 기존 영구 스레드가 네이티브 스레드(예: Teams로 라우팅)인 경우 해당 스레드의 추가 채팅 메시지와 호출이 Teams로 이동됩니다. 인터팝 스레드(예: 비즈니스용 Skype로 라우팅)인 경우 추가 채팅 메시지 및 통화가 비즈니스용 Skype로 이동됩니다(라우팅 옵션을 사용할 수 있는 경우 다시 한 번).

> [!NOTE]
> 이제 Teams로 업그레이드된 사용자에게 스레드가 인터팝 스레드인 경우와 같이 Teams의 기존 스레드가 더 이상 라우팅할 수 없습니다. 스레드가 인터프 스레드로 만들어지기 때문에 스레드는 비즈니스용 Skype로 라우팅되지만 해당 사용자는 더 이상 채팅 및 통화에 비즈니스용 Skype를 사용할 수 없습니다. 이 경우 스레드를 사용하지 않도록 설정하고 추가 통신을 허용하지 않습니다.

### <a name="from-skype-for-business"></a>비즈니스용 Skype에서

비즈니스용 Skype 스레드는 10분 이상 지속되지 않습니다. SIP 세션 시간 제한. SIP 세션이 만료하기 전에 비즈니스용 Skype의 기존 스레드에서 채팅 및 호출은 스레드와 동일한 방식으로 라우팅됩니다. SIP 세션 시간 초과의 비즈니스용 Skype의 기존 스레드에서 호출 및 채팅은 원래 스레드가 다른 쪽에서 온 클라이언트에 관계없이 원격 파티의 비즈니스용 Skype로 라우팅됩니다.

### <a name="availability"></a>가용성

위에서 설명한 테넌트 내 및 페더리드 동작 모두 사용할 수 있으며, 다음과 같은 제한 사항이 있습니다.

- 테넌트가 다른 GoLocal 배포 또는 지리에 있는 외부 참석자는 "페더리드" 모임에서 IM 채팅을 볼 수 없습니다.
- Multitenant O365와 Sovereign Clouds 간의 페더전 및 인터팝은 지원되지 않습니다.

## <a name="presence"></a>현재 상태

일부 사용자가 Teams 클라이언트를 사용하고 다른 사용자가 비즈니스용 Skype 클라이언트를 여전히 사용하고 있는 상황이 있는 경우 두 클라이언트를 모두 사용하는 사용자 수가 있을 수 있습니다. 개별 사용자가 어떤 클라이언트를 가졌다고 하여도 현재 상태는 모든 사용자와 공유할 수 있습니다. 조직에서 공유되는 경우 사용자는 채팅을 시작하거나 전화를 걸 수 있는 것이 적절한지 여부를 더 잘 결정할 수 있습니다.

예를 들어, 발신자 채팅 또는 통화가 대상의 비즈니스용 Skype 클라이언트에 착륙해야 하는 경우 비즈니스용 Skype 클라이언트의 현재 상태입니다. 대상의 Teams 클라이언트에 연결해야 하는 경우 표시해야 하는 Teams 클라이언트의 현재 상태입니다.

예상되는 동작을 알기 위해 현재 상태는 사용자의 공존 모드에 따라 공유되는 것을 이해해야 합니다.

* 사용자가 TeamsOnly 모드인 경우 다른 사용자(Teams 또는 비즈니스용 Skype)에서 TeamsOnly 사용자의 Teams 존재 여부가 표시됩니다.
* 사용자가 \* SfB 모드(SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings)에 있는 경우 다른 사용자(Teams 또는 비즈니스용 Skype)에서 SfB 사용자의 비즈니스용 Skype 현재 상태 표시 \*
* 사용자가 제도(또는 레거시) 모드에 있는 경우 Teams 및 비즈니스용 Skype의 현재 상태는 독립적(값이 일치하지 않습니다)을 표시하며, 다른 사용자는 동일한 테넌트에 있는지, 페더리된 테넌트에 있는지, 어떤 클라이언트에서 사용하는 클라이언트에 따라 아일랜드 사용자의 현재 상태 중 하나 또는 다른 존재를 볼 수 있습니다.
    * Teams에서 동일한 테넌트 내의 다른 사용자는 Islands 사용자의 Teams 존재를 볼 수 있습니다. 위의 테넌트 내 라우팅 테이블과 정렬됩니다.
    * Teams에서 페더리드 테넌트의 다른 사용자는 Islands 사용자의 비즈니스용 Skype 존재를 볼 수 있습니다. 위의 페더링된 라우팅 테이블과 정렬됩니다.
    * 비즈니스용 Skype에서 다른 사용자는 Islands 사용자의 비즈니스용 Skype 현재 상태(테넌트 및 페더리드 모두)를 볼 수 있습니다. 위의 라우팅 테이블과 정렬됩니다.


### <a name="in-tenant-presence"></a>테넌트 내 현재 상태

TeamsOnly 사용자에게 전송된 메시지는 항상 Teams에 표시됩니다. 위에서 설명한 대로 대화가 가능한 경우 SfB 사용자에게 보낸 메시지는 항상 \* 비즈니스용 Skype에 표시됩니다. Islands 사용자에게 전송된 메시지는 항상 원래 클라이언트에 연결됩니다.

이 표에서는 게시자 모드와 Watcher 클라이언트(새 스레드의 경우)에 따라 Watcher에서 볼 수 있는 게시자의 현재 상태에 대해 설명합니다.

**표 3: 테넌트 내 현재 상태(새 스레드)**

|감시자 <br/><br/>클라이언트|<br/><br/>Route-> |<br/><br/>Islands |게시자 <br/><br/>SfB\* |<br/>Teams Only|
|--- |--- |--- |--- |---|
|비즈니스용 Skype |&boxv;|비즈니스용 Skype | 비즈니스용 Skype | Teams|
|Teams |&boxv; |Teams |비즈니스용 Skype |Teams |
| | | | |

### <a name="federated-presence"></a>페더리드 현재 상태

페더리드 상태는 표 2에 표시된 페더리드 도달성을 기반으로 합니다.

아래 표에서는 퍼블리셔의 모드와 Watcher 클라이언트(새 스레드의 경우)에 따라 Watcher에서 볼 수 있는 퍼블리셔의 현재 상태에 대해 설명합니다. 실제로 Watcher의 클라이언트는 이 단계에서 페더리에 차이가 없습니다.

**표 4: 페더리드된 현재 상태(새 스레드)**

|감시자 <br/><br/> 클라이언트 |<br/><br/>Route->|<br/><br/> Islands  |게시자 <br/><br/> SfB\* |<br/><br/> Teams Only |
|--- |--- |--- |--- |---|
|비즈니스용 Skype |&boxv; |비즈니스용 Skype  | 비즈니스용 Skype  | Teams  |
|Teams | &boxv;|비즈니스용 Skype |비즈니스용 Skype |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>기존 스레드의 현재 상태

기존 스레드에서 현재 상태 및 도달성을 정렬하기 위해 스레드에 노출된 대상의 현재 상태는 스레드의 라우팅에 맞춰야 합니다. 라우팅이 가능하다고 생각하면 됩니다.

특히 이전에 영구 상호프 대화 스레드가 있는 받는 사람이 Teams로 업그레이드된 경우 해당 스레드는 더 이상 정확한 존재를 반영하지 않고 더 이상 라우팅할 수 없습니다. 새 스레드를 시작해야 합니다.

## <a name="related-links"></a>관련 링크
[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](./migration-interop-guidance-for-teams-with-skype.md)

[비디오: SfB와 Teams 간의 공존 및 상호 운영성 관리](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)