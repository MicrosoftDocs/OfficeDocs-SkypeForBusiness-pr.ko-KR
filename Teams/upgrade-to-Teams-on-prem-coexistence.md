---
title: Microsoft Teams 및 비즈니스용 Skype와 공존
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드 - 공존
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0690af8226f3f992dcc12f68c6135c953eb043f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533615"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype와 공존

이 문서에서는 어떤 모드와 어떤 업그레이드 방법이 사용됐는가에 관계없이 동일한 조직에서 Teams 및 비즈니스용 Skype 클라이언트를 모두 실행하는 경우 경험할 수 있는 동작을 요약합니다.

- [모임](#meetings)
- [상호 연동성](#interoperability)
- [Teams 대화-Interop 및 네이티브 스레드](#teams-conversations---interop-versus-native-threads)
- [현재 상태](#presence)
- [페더레이션](#federation)
- [연락처](#contacts)



## <a name="meetings"></a>모임

모드에 관계없이 사용자는 비즈니스용 Skype 또는 Teams에 관계없이 초대된 모든 유형의 모임에 언제든지 참가할 수 있습니다.  그러나 사용자는 모임 유형과 일치하는 해당 클라이언트를 통해 모임에 참가해야 합니다.

- 모임이 Teams 모임인 경우 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)가 Teams 클라이언트를 사용하여 모임에 참가합니다. Teams가 설치되지 않은 경우 사용자는 모임에 참가하려고 할 때 웹으로 연결됩니다.

- 모임이 비즈니스용 Skype 모임인 경우 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)가 비즈니스용 Skype 클라이언트를 사용하여 모임에 참가합니다. 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 사용자는 Skype 모임 앱을 통해 참가하도록 웹으로 연결됩니다.

모임을 구성할 때 예약되는 모임 유형은 다음 표와 같이 이끌이의 모드를 기반으로 합니다.

| 이끌이 모드    |      동작 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Teams에서 예약된 모든 모임. Outlook에서는 비즈니스용 Skype 추가 기능을 사용할 수 없습니다. | 
| SfbWithTeamsCollab, SfbOnly   | 비즈니스용 Skype에서 예약된 모든 모임입니다. Outlook에서는 Teams 추가 기능을 사용할 수 없습니다. | 
| 아일랜드 | 기본적으로 비즈니스용 Skype 또는 Teams에서 모임을 예약할 수 있습니다. 두 추가 기능을 모두 Outlook에서 사용할 수 있습니다. 그러나 경우에 따라 Islands의 사용자가 PreferredMeetingProviderForIslandsMode=Teams를 사용하여 TeamsMeetingPolicy 인스턴스를 할당하여 Teams에서 항상 모임을 예약해야 할 수 있습니다.| 


## <a name="interoperability"></a>상호 연동성

Teams는 특정 시나리오에서 비즈니스용 Skype와의 상호 연동성("interop")을 지원합니다. 상호 통신은 비즈니스용 Skype 사용자와 Teams 사용자 간의 채팅 또는 통화를 참조합니다.  상호 통신은 두 사용자 간에만 가능합니다. 다자 채팅/통화 또는 추가 사용자 추가는 지원되지 않습니다.

다음 각각이 참일 때 두 사용자 간의 상호 채팅 또는 통화가 생성됩니다.

- 한 사용자가 Teams를 사용하고 다른 사용자는 비즈니스용 Skype를 사용하고 있습니다.

- 초기 통신을 받는 사람의 모드는 두 사용자가 동일한 조직에 있는 경우 NOT Islands(그렇지 않으면 통신이 동일한 클라이언트에 연결)입니다. 페더러드 시나리오에서 보내는 사용자는 Teams를 사용하고 받는 사람이 TeamsOnly 모드가 아닙니다. 

- Teams 사용자에게는 비즈니스용 Skype 계정이 없습니다. 

Interop 통신 내에서 채팅은 일반 텍스트 전용입니다. 또한 상호 채팅 자체에서는 파일 공유 및 화면 공유가 *불가능합니다.* 그러나 Interop 대화의 사용자는 아래 설명된 바와 같이 Interop 채팅 내에서, 즉, 대화형 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.

- Teams 사용자가 화면을 공유하려고 시도하면 요청 시 Teams 모임이 자동으로 만들어지며 해당 모임에 대한 초대 링크가 비즈니스용 Skype 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 비즈니스용 Skype 사용자가 Teams를 열고 모임에 참가합니다. 이제 두 사용자가 Teams 모임에 참가하고 있으며, 필요한 경우 공유할 수 있습니다.

- 비즈니스용 Skype 사용자가 2018년 이후의 클라이언트를 사용 중일 때 콘텐츠 공유를 시도하면 비즈니스용 Skype 모임이 자동으로 만들어지며 해당 모임에 대한 초대 링크가 Teams 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 Teams 사용자가 비즈니스용 Skype 모임에 참가하려고 합니다. Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있는 경우 해당 클라이언트가 열리며 로그인하라는 메시지가 표시됩니다(아직 로그인하지 않은 경우).  Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 웹 버전을 사용하라는 메시지가 표시됩니다. 두 사용자가 모두 로그인하면 비즈니스용 Skype 모임에 있으며 필요한 경우 공유할 수 있습니다.

## <a name="teams-conversations---interop-versus-native-threads"></a>Teams 대화 - Interop 및 네이티브 스레드

상호 운영 통신은 네이티브 Teams 대화의 일부 기능을 지원하지 않습니다. Teams 클라이언트는 Teams 간 및 Teams-To-Business 통신을 위해 별도의 대화 스레드를 유지 관리합니다. 이러한 대화는 사용자 인터페이스에서 다르게 렌더링됩니다. Interop 스레드는 다음을 통해 일반 네이티브 Teams 스레드와 차별화할 수 있습니다.

- 풍부한 텍스트, 파일/화면 공유, 사용자를 추가할 수 없는 컨트롤이 없습니다.
- 비즈니스용 Skype에 대한 "S"를 표시하는 대상 사용자의 아이콘을 수정합니다.

이러한 차이점은 다음 스크린샷에 표시됩니다.

사용자 G3 테스트와의 네이티브 Teams-팀 대화

![기본 Teams-팀 대화를 보여주는 다이어그램](media/teams-upgrade-native-thread.png)

동일한 사용자 G3 테스트와의 interop 대화

![Teams 간 대화를 보여주는 다이어그램](media/teams-upgrade-interop-thread.png)

대화 스레드가 만들어지면 해당 형식은 변경되지 않습니다. 생성되면 Teams의 interop 스레드는 항상 대상 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 네이티브 스레드는 항상 대상 사용자의 Teams 클라이언트로 라우팅됩니다.  받는 사람의 모드가 변경되면 해당 사용자에 대한 기존 Teams 스레드가 더 이상 작동하지 않습니다. 다음 스크린샷과 같이 새 네이티브 대화를 시작하는 링크가 있는 메모가 해당 채팅에 표시됩니다.


![업그레이드된 비즈니스용 Skype 사용자와의 채팅을 보여주는 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>현재 상태

주어진 사용자의 현재 상태는 클라이언트를 통한 서비스의 사용자 활동을 기반으로 합니다. 그러면 다른 사용자가 볼 수 있도록 현재 상태가 게시됩니다.  비즈니스용 Skype와 Teams는 별도의 클라이언트가 있는 별도 서비스이기 때문에 각 서비스에는 사용자에 대한 자체 스테이트 상태가 있습니다.   Teams와 비즈니스용 Skype Online의 현재 상태 서비스 간에도 동기화가 있습니다.  이렇게 하면 한 서비스가 필요한 경우 다른 서비스에서 사용자의 존재를 잠재적으로 게시할 수 있습니다. 

현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다. 세 가지 기본 사례가 있습니다.

- 사용자가 TeamsOnly 모드인 경우 사용하는 클라이언트에 관계없이 다른 모든 사용자에게 해당 사용자의 Teams 현재 상태가 표시됩니다.

- 사용자가 비즈니스용 Skype 모드에 있는 경우 사용하는 클라이언트에 관계없이 다른 모든 사용자에게 해당 사용자의 비즈니스용 Skype 현재 상태가 표시됩니다.

- 사용자가 제도 모드에 있는 경우 비즈니스용 Skype 및 Teams에 게시된 현재 상태는 독립적이기 때문에 동일한 조직 내의 사용자에게 표시되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라 갑니다. 페더맹된 조직의 사용자는 비즈니스용 Skype에 대한 페더러드 트래픽이 비즈니스용 Skype에 제공된 것이기 때문에 비즈니스용 Skype 활동을 기반으로 해당 사용자의 현재 상태가 표시됩니다.

예를 들어 사용자 A가 제도 모드에 있는 것으로 가정합니다. 사용자 A가 Teams에서 활성 상태이지만 비즈니스용 Skype에 로그인하지 않은 경우 다른 사용자는 사용자 A가 Teams 클라이언트에서 활성으로 표시되지만 비즈니스용 Skype 클라이언트에서는 사용자 A를 오프라인으로 볼 수 있습니다. 클라이언트를 실행하지 않는 경우 사용자 A에 도달할 수 없습니다. 


## <a name="federation"></a>페더레이션

Teams에서 비즈니스용 Skype를 사용하는 다른 사용자로 페더맹을 사용하려면 Teams 사용자가 비즈니스용 Skype에서 온라인으로 돌아와야 합니다. TeamsUpgradePolicy는 들어오는 페더레이드 채팅 및 통화에 대한 라우팅을 관리합니다. 페더러드 라우팅 동작은 제도 모드를 제외한 동일한 테넌트 시나리오의 경우와 동일합니다. 받는 사람이 제도 모드인 경우:

- Teams에서 시작된 채팅 및 통화는 받는 사람이 페더넌트 테넌트에 있는 경우 비즈니스용 Skype에 있습니다.
- 받는 사람이 동일한 테넌트에 있는 경우 Teams에서 시작된 채팅 및 통화가 Teams에 있습니다.
- 비즈니스용 Skype에서 시작된 채팅 및 통화는 항상 비즈니스용 Skype에 있습니다.

페더러드 채팅은 네이티브 스레드 또는 interop 스레드일 수 있습니다. Teams [대화---interop-vss-native-threads를 참조합니다.](#teams-conversations---interop-versus-native-threads)

- 받는 사람과 보낸 사람이 TeamsOnly 업그레이드 모드에 있는 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 기본 채팅 환경이 됩니다. 자세한 내용은 Teams에서 외부(페더러리) 사용자에 대한 네이티브 채팅 환경을 [읽어보아야 합니다.](native-chat-for-external-users.md) 

- 대화 참가자 중 한 자가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와 상호 운영 환경으로 남아 있습니다. 사용자 인터페이스는 사용자가 외부에 있는 것을 나타내는 메모가 있는 것을 제외하고 동일한 테넌트 interop 스레드와 비슷한 방식으로 페더링된 채팅을 노출합니다.

자세한 내용은 [Teams의](manage-external-access.md) 외부 사용자에 대한 Microsoft Teams 및 네이티브 채팅 환경의 외부 액세스 [관리를 참조하세요.](native-chat-for-external-users.md)

## <a name="contacts"></a>연락처

Teams와 비즈니스용 Skype에는 별도의 연락처 목록이 있습니다. 즉, 한 시스템에서 만든 연락처 추가, 제거 및 수정 내용이 다른 시스템과 동기화되지 않습니다. 그러나 비즈니스용 Skype의 연락처는 다음 두 가지 특정 이벤트 중 하나에서 발생하는 경우 자동으로 Teams로 복사됩니다. 

- 비즈니스용 Skype Online 사용자의 경우 Teams에 처음 로그인하면 비즈니스용 Skype의 연락처가 Teams로 복사됩니다.  이 동작은 비즈니스용 Skype Server의 프레미스 계정이 있는 사용자에게는 사용할 수 없습니다.  

- 사용자가 TeamsUpgradePolicy 할당을 통해 또는 Move-CsUser -MoveToTeams를 통해 TeamsOnly로 업그레이드된 후 다음에 사용자가 Teams에 로그인하면 비즈니스용 Skype의 기존 연락처가 Teams에 이미 있는 기존 연락처와 병합됩니다. 이 동작은 사용자의 비즈니스용 Skype 계정이 홈 또는 온라인에 있는지 여부에 따라 발생합니다. 

두 경우 모두 비즈니스용 Skype에서 Teams로 연락처를 이전하는 것은 비동기적이기 때문에 연락처가 Teams에 표시되기 몇 분 정도가 될 수 있습니다. 위의 두 이벤트는 복사를 트리거하는 이벤트입니다.  

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

