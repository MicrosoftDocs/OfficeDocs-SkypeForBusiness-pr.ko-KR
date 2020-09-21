---
title: Microsoft 팀과 비즈니스용 Skype 동시 사용
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 팀으로 업그레이드-공존
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5993611a383ee9b7040dfa4b74dae1b392253f
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955965"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>팀과 비즈니스용 Skype 동시 사용

이 문서에서는 모드와 사용 되는 업그레이드 방법에 관계 없이 동일한 조직의 비즈니스용 Skype 클라이언트와 팀을 모두 실행할 때 발생할 수 있는 문제에 대해 간략하게 설명 합니다.

- [모임](#meetings)
- [운용할](#interoperability)
- [팀 대화-상호 운용성 및 네이티브 스레드](#teams-conversations---interop-versus-native-threads)
- [현재 상태](#presence)
- [페더레이션](#federation)
- [연락처](#contacts)



## <a name="meetings"></a>모임

이 모드에 관계 없이 사용자는 자신이 초대 하는 모든 유형의 모임에 언제 든 지 참가할 수 있습니다 (비즈니스용 Skype 또는 팀).  그러나 사용자는 모임 형식과 일치 하는 해당 클라이언트를 사용 하 여 모임에 참가 해야 합니다.

- 모임이 팀에 참가 하는 경우 모든 참가자 (예를 들어 출장만, 군도 또는 비즈니스용 Skype 사용자)는 팀 클라이언트를 사용 하 여 모임에 참석 합니다. 팀이 설치 되어 있지 않은 경우, 모임에 참가 하려고 할 때 사용자가 웹으로 전송 됩니다.

- 모임이 비즈니스용 Skype 모임 인 경우 모든 참가자 (이 팀이 TeamsOnly, 군도 또는 비즈니스용 Skype 사용자 인지 여부)에는 비즈니스용 Skype 클라이언트를 사용 하 여 모임에 참가 합니다. 비즈니스용 Skype 클라이언트가 설치 되어 있지 않으면 사용자가 Skype 모임 앱을 통해 참가 하도록 웹으로 전송 됩니다.

모임을 구성할 때 예약 된 모임 유형은 다음 표에 표시 된 대로 이끌이의 모드를 기반으로 합니다.

| 구성 도우미 모드    |      결과가 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    팀에서 예약 된 모든 모임 Outlook에서는 비즈니스용 Skype 추가 기능을 사용할 수 없습니다. | 
| SfbWithTeamsCollab, SfbOnly   | 비즈니스용 Skype에서 예약 된 모든 모임 Outlook에서는 팀 추가 기능을 사용할 수 없습니다. | 
| 아일랜드 | 기본적으로 Skype for Business 또는 팀에서 모임을 예약할 수 있습니다. 두 추가 기능은 모두 Outlook에서 사용할 수 있습니다. 그러나 경우에 따라 아일랜드 사용자가 항상 PreferredMeetingProviderForIslandsMode = 팀으로 TeamsMeetingPolicy 인스턴스를 할당 하 여 팀에서 모임을 예약 하도록 할 수 있습니다.| 


## <a name="interoperability"></a>운용할

팀은 특정 시나리오에서 비즈니스용 Skype와의 상호 운용성 ("interop")을 지원 합니다. Interop 통신은 비즈니스용 Skype 사용자와 팀 사용자 간의 채팅 또는 통화를 의미 합니다.  Interop 통신은 두 사용자 간에만 가능 합니다. 여러 명의 파티 채팅/통화 또는 추가 사용자 추가는 지원 되지 않습니다.

두 사용자 간 interop 채팅 또는 통화는 다음 각 조건이 충족 될 때 만들어집니다.

- 한 명의 사용자가 팀을 사용 하는 경우와 다른 하나는 비즈니스용 Skype를 사용 하 고 있습니다.

- 최초 통신의 받는 사람 모드는 아일랜드가 되지 않습니다 (그렇지 않은 경우 두 사용자가 같은 조직에 있는 경우 통신은 동일한 클라이언트에 연결 됨). 페더레이션 시나리오에서 보내는 사용자는 팀을 사용 하 고 있으며 받는 사람이 TeamsOnly 모드에 있지 않습니다. 

- 또한 팀 사용자는 비즈니스용 Skype 계정을 온-프레미스로가지고 있지 않습니다. 

Interop 통신 내에서 채팅은 일반 텍스트 전용입니다. 또한 *interop 채팅 자체에서는*파일 공유 및 화면 공유를 사용할 수 없습니다. 그러나 interop 대화의 사용자는 아래에 설명 된 대로 interop 채팅 내에서 주문형 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.

- 팀 사용자가 자신의 화면을 공유 하려고 시도 하는 경우 주문형 팀 모임이 자동으로 만들어지고 해당 모임에 대 한 초대 링크가 비즈니스용 Skype 사용자의 클라이언트로 전송 됩니다. 링크를 클릭 하면 비즈니스용 Skype 사용자가 팀을 열고 모임에 참가 합니다. 이제 두 사용자 모두 팀 모임에 있으며 필요에 따라 공유할 수 있습니다.

- 비즈니스용 Skype 사용자가 2018 이상에서 클라이언트를 사용 하는 경우 콘텐츠를 공유 하려고 하면 주문형 비즈니스용 Skype 모임이 자동으로 만들어지고 해당 모임에 대 한 초대 링크가 팀 사용자의 클라이언트로 전송 됩니다. 링크를 클릭 하면 팀 사용자가 비즈니스용 Skype 모임에 참가 하려고 시도 합니다. 팀 사용자가 비즈니스용 Skype 클라이언트를 설치한 경우, 로그인 하 라는 메시지가 사용자에 게 표시 됩니다 (아직 로그인 하지 않은 경우).  팀 사용자에 게 비즈니스용 Skype 클라이언트가 설치 되어 있지 않으면 사용자에 게 웹 버전을 사용 하 라는 메시지가 표시 됩니다. 두 사용자가 모두 로그인 한 후에는 비즈니스용 Skype 모임에 있으며 필요에 따라 공유할 수 있습니다.

## <a name="teams-conversations---interop-versus-native-threads"></a>팀 대화-상호 운용성 및 네이티브 스레드

Interop 통신은 네이티브 팀 대화의 모든 기능을 지원 하지 않으므로 팀 클라이언트는 팀과 팀 간 또는 팀에서 비즈니스용 Skype 통신에 대해 별도의 대화 스레드를 유지 관리 합니다. 이러한 대화는 사용자 인터페이스에서 다르게 렌더링 됩니다. Interop 스레드는 다음과 같이 일반 네이티브 팀 스레드와 차별화 될 수 있습니다.

- 서식 있는 텍스트, 파일/화면 공유에 대 한 컨트롤이 부족 하 여 사용자를 추가 하지 못하는 경우
- 비즈니스용 Skype에 대 한 "S"를 표시 하는 대상 사용자의 아이콘 수정입니다.

이러한 차이점은 다음 스크린샷에 나와 있습니다.

사용자 G3 테스트에 대 한 기본 팀 간 대화

![기본 팀 간 대화를 보여 주는 다이어그램](media/teams-upgrade-native-thread.png)

동일한 사용자 G3 테스트를 사용 하는 interop 대화

![Interop 팀 간 대화를 보여 주는 다이어그램](media/teams-upgrade-interop-thread.png)

대화 스레드를 만든 후에는 해당 형식이 변경 되지 않습니다. 생성 된 팀의 interop 스레드는 항상 대상 사용자의 비즈니스용 Skype 클라이언트로 라우팅합니다. 네이티브 스레드는 항상 대상 사용자의 팀 클라이언트로 라우팅 됩니다.  받는 사람 사용자의 모드가 변경 되 면 해당 사용자에 대 한 기존 팀 스레드가 더 이상 작동 하지 않으며 다음 스크린샷에 표시 된 대로 새 기본 대화를 시작 하는 링크가 포함 된 메모가 해당 채팅에 표시 됩니다.


![업그레이드 된 비즈니스용 Skype 사용자와의 채팅을 보여 주는 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>현재 상태

지정 된 사용자에 대 한 현재 상태는 클라이언트를 통한 서비스의 사용자 활동을 기반으로 합니다. 그런 다음 다른 사용자가 볼 수 있도록 현재 상태가 게시 됩니다.  비즈니스용 Skype와 팀은 별도의 클라이언트가 있는 별도의 서비스 이므로 각 서비스에는 사용자에 대 한 고유한 현재 상태가 있습니다.   또한 팀의 현재 상태 서비스와 비즈니스용 Skype Online 간에 동기화가 있습니다.  이렇게 하면 한 서비스가 필요한 경우 다른 서비스의 사용자 현재 상태를 게시할 수 있습니다. 

현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다. 다음과 같은 세 가지 기본 경우가 있습니다.

- 사용자가 팀 전용 모드일 경우 다른 모든 사용자는 사용 하는 클라이언트에 관계 없이 해당 사용자에 대 한 팀 현재 상태를 볼 수 있습니다.

- 사용자가 비즈니스용 Skype 모드에 있는 경우 다른 사용자는 사용 하는 클라이언트에 관계 없이 해당 사용자에 대 한 비즈니스용 Skype의 현재 상태를 볼 수 있습니다.

- 사용자가 군도 모드에 있는 경우 비즈니스용 Skype 및 팀에 게시 된 상태는 독립적 이므로 같은 조직 내의 사용자에 게 표시 되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라 집니다. 페더레이션 조직의 사용자는 비즈니스용 Skype에서 고립 모드 사용자에 게 연결 된 페더레이션 트래픽을 통해 비즈니스용 Skype 활동을 기준으로 해당 사용자의 현재 상태를 볼 수 있습니다.

예를 들어 사용자 A가 군도 모드 라고 가정 합니다. 사용자 A가 팀에서 활성 상태 이지만 비즈니스용 Skype에 로그인 되어 있지 않은 경우에는 다른 사용자가 팀 클라이언트에서 사용자 A의 활성 상태로 표시 되지만 비즈니스용 Skype 클라이언트에서는 사용자 A가 오프 라인으로 표시 됩니다. 이것은 사용자 A가 클라이언트를 실행 하지 않는 경우에 도달할 수 없기 때문에 의도적으로 설계 된 것입니다. 


## <a name="federation"></a>페더레이션

비즈니스용 Skype를 사용 하 여 팀에서 다른 사용자에 게 페더레이션 하려면 비즈니스용 Skype에서 팀 사용자를 온라인으로 홈에 설치 해야 합니다. TeamsUpgradePolicy는 들어오는 페더레이션된 채팅 및 통화에 대 한 라우팅을 제어 합니다. 페더레이션된 라우팅 동작은 아일랜드 모드를 제외 하 고 동일한 테 넌 트 시나리오와 동일 합니다. 받는 사람이 아일랜드 모드일 때:

- 받는 사람이 페더레이션 테 넌 트에 있는 경우 비즈니스용 Skype의 팀에서 시작한 채팅 및 통화입니다.
- 받는 사람이 동일한 테 넌 트에 있는 경우 팀에서 팀에서 시작한 채팅 및 통화입니다.
- 비즈니스용 skype에서 시작 된 채팅 및 통화는 항상 비즈니스용 Skype에 있습니다.

페더레이션 채팅은 네이티브 스레드 또는 interop 스레드 일 수 있습니다. [팀 대화---interop vs-네이티브 스레드](#teams-conversations---interop-versus-native-threads)를 참조 하세요.

- 받는 사람과 보낸 사람이 모두 TeamsOnly 모드인 경우 대화는 다양 한 메시징 및 통화 기능을 모두 포함 하는 기본 채팅 환경이 됩니다. 자세한 내용은 [팀의 외부 (페더레이션된) 사용자를 위한 기본 채팅 환경에 대해](native-chat-for-external-users.md)알아보세요. 

- 대화 참가자 중 하나가 TeamsOnly 모드에 있지 않은 경우 대화는 텍스트 전용 메시지를 사용 하 여 interop 환경으로 유지 됩니다. 사용자 인터페이스는 사용자가 외부 임을 나타내는 메모가 있다는 점을 제외 하 고 동일한 테 넌 트 interop 스레드와 비슷한 방식으로 페더레이션 채팅을 제공 합니다.

자세한 내용은 [팀의 외부 (페더레이션된) 사용자를 위한 Microsoft 팀 및 기본 채팅 환경](native-chat-for-external-users.md) [에서 외부 액세스 관리](manage-external-access.md) 를 참조 하세요.

## <a name="contacts"></a>연락처

팀과 비즈니스용 Skype에는 별도의 연락처 목록이 있습니다. 즉, 한 시스템에서 이루어진 연락처 추가, 제거, 수정 내용이 다른 시스템과 동기화 되지 않습니다. 그러나 비즈니스용 Skype의 연락처는 다음 두 가지 특정 이벤트 중 하나가 발생할 때 자동으로 팀에 복사 됩니다. 

- 비즈니스용 Skype Online 사용자는 처음으로 팀에 로그온 할 때 비즈니스용 Skype의 연락처가 팀에 복사 됩니다.  비즈니스용 Skype 서버에서 온-프레미스 계정을 사용 하는 사용자는이 동작을 사용할 수 없습니다.  

- 사용자가 TeamsUpgradePolicy 또는 Move-CsUser-MoveToTeams를 통해 자신을 업그레이드 한 후에는 다음에 사용자가 팀에 로그인 할 때 비즈니스용 Skype의 기존 연락처가 이미 팀에 있는 기존 연락처와 병합 됩니다. 이 동작은 사용자의 비즈니스용 Skype 계정이 온-프레미스 또는 온라인 인지에 관계 없이 발생 합니다. 

두 경우 모두 비즈니스용 Skype에서 팀으로 연락처를 전송 하는 것이 비동기적 이므로 연락처가 팀에 표시 되기까지 몇 분이 걸릴 수 있습니다. 위의 두 가지 이벤트는 복사본을 트리거하는 것입니다.  

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

