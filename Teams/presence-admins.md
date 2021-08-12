---
title: Teams에서의 사용자 현재 상태
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams에서 현재 상태 및 현재 상태 기능에 대한 관리 설정에 대해 알아 봅니다.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17848cd1abd588ea1cd5106327ee576a318191bd06035389a8475b1fc258f8f2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350520"
---
# <a name="user-presence-in-teams"></a>Teams에서의 사용자 현재 상태

현재 상태는 Microsoft Teams에서(및 Microsoft 365 또는 Office 365 전체) 사용자 프로필의 일부입니다. 현재 상태는 다른 사용자에게 사용자의 현재 근무 가능 여부 및 상태를 나타냅니다. 기본적으로 Teams를 사용하는 조직의 모든 사용자는 다른 사용자가 온라인 상에 있는지 여부를 (거의 실시간으로) 확인할 수 있습니다. 모바일에서 페이지를 다시 고치면 웹 및 데스크톱 버전에서 현재 상태가 실시간으로 업데이트됩니다.

 > [!NOTE]
 > 여러 플랫폼에서의 Teams 사용자 프로필에 대한 자세한 내용은 [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조하세요.

 > [!NOTE]
 > Teams는 개인 정보 구성을 준수하므로 개인 정보 모드를 사용하도록 설정한 경우 사용자의 현재 상태가 외부 사용자에게 표시되지 않습니다.
## <a name="presence-states-in-teams"></a>Teams에서의 현재 상태

|사용자가 구성함|앱이 구성함|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) 대화 가능, 부재 중. 참고: 부재 중은 사용자가 “자동 회신”을 설정한 기간 동안 자동으로 설정됩니다. 사용자가 이 기간 동안 앱을 사용하는 경우, “부재 중, 대화 가능”과 같이 현재 상태가 이중으로 표시될 수 있습니다. |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중 |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) 통화 중|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) 회의 중 |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) 통화 중, 부재 중|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) 방해 금지 ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) 프레젠테이션 중|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) 방해 금지. 포커스는 사용자가 일정의 MyAnalytics/Insights에서 포커스 시간을 예약할 때 발생합니다.|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움|
|| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) 곧 돌아오겠음| |
|![x가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 오프라인으로 표시|![x가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 오프라인. 사용자가 몇 분 동안 장치에 로그인하지 않으면 오프라인으로 표시됩니다. | |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) 상태 알 수 없음|
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) 부재 중. 부재 중은 자동 회신이 설정된 경우에 사용됩니다. |
|||
 > [!NOTE]
 > 사서함이 온-프레미스에 호스트된 사용자의 경우 1시간(최대)의 현재 상태 지연이 예상됩니다.

앱에서 구성된 현재 상태는 사용자 활동(대화 가능, 자리 비움), Outlook 일정 상태(모임 중) 또는 Teams 앱 상태(통화 중, 프레젠테이션 중)를 기준으로 합니다. 일정에 따라 포커스 모드에 있을 때 Teams에서 사람들에게 상태가 **포커싱** 으로 보이게 됩니다. 다른 제품에서 포커스 모드는 **방해 금지** 로 표시됩니다.

컴퓨터를 잠그거나 컴퓨터가 유휴 또는 절전 모드로 들어가면 사용자의 현재 상태는 자리 비움으로 변경됩니다. 휴대폰에서 Teams 앱이 백그라운드에 있을 때마다 현재 상태가 자리 비움으로 변경됩니다.

사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다. 누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다. 사용자 상태가 방해 금지로 설정된 경우, 사용자는 여전히 채팅 메시지를 받지만 배너 알림은 표시되지 않습니다.

사용자는 수신 전화가 음성 사서함으로 넘어가는 방해 금지를 제외한 모든 현재 상태에서 전화를 받습니다. 받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.

사용자는 Teams에서 **설정** > **개인 정보** 로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다. 우선 순위 액세스 권한이 있는 사용자는 상대방이 방해 금지로 설정되어 있더라도 연락할 수 있습니다.

### <a name="dual-presence"></a>이중 현재 상태

  대부분의 사용자에게 현재 상태가 작동하는 방식은 일정에 있는 이벤트 또는 통화와 같은 장치 이벤트에 따라 결정됩니다. 사용자는 일부 만료 시간이 있는 상태를 수동으로 설정하여 UI 상에서 이 상태를 재정의할 수 있습니다.

## <a name="user-configured-states-expiration"></a>사용자 구성 상태 만료

사용자가 특정 현재 상태를 선택하면 모든 앱 활동 업데이트보다 우선합니다. 예를 들어 사용자가 자신을 방해 금지로 설정하면, 모임에 참석하거나 전화를 받는 경우도 방해 금지로 남게 됩니다.

사용자가 일정 시간 후 관련이 없는 상태로 표시되는 것을 방지하기 위해 Teams의 사용자 구성 상태에는 기본 만료 설정이 있습니다.

|사용자 구성 상태|기본 만료|
|:--- |:---|
| 다른 용무 중|1일|
| 방해 금지|1일|
| 기타|7일|
|||

> [!NOTE]
> 사용자는 자신의 현재 상태에 대한 기간을 수동으로 구성할 수도 있습니다. 예를 들면 사용자는 내일 아침까지 자신을 오프라인 표시로 설정할 수 있습니다.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Teams의 관리자 설정을 비즈니스용 Skype와 비교

Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.

- Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다. Teams에서는 개인 정보(현재 상태를 볼 수 있는 사용자를 정의하는 위치) 구성을 사용할 수 없습니다.
- Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다. 연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.
- Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.
- Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.
- 조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.

> [!NOTE]
> Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Teams의 관리자 설정을 Microsoft Outlook과 비교

Outlook에 있는 Teams의 현재 상태는 동일한 조직의 연락처에 대해 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.

사용자 계정의 업그레이드 모드 정책이 TeamsOnly로 설정된 경우, Outlook은 Teams의 현재 상태를 얻기 위해 통신합니다. 사용자 계정이 TeamsOnly로 설정되지 않은 경우 Outlook은 비즈니스용 Skype와 통신합니다.

## <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

조직에서 또한 비즈니스용 Skype를 사용할 때, Teams의 현재 상태 기능이 작동하는 방법에 대한 자세한 내용은 [비즈니스용 Skype와 동시 사용](coexistence-chat-calls-presence.md)을 참조하세요.
