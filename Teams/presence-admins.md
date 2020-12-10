---
title: Teams에서의 사용자 현재 상태
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams의 현재 상태 및 현재 상태 기능에 대한 관리 설정을 확인합니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff5a13d6b31527138b71d2ad3b2387f827933eda
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616952"
---
# <a name="user-presence-in-teams"></a>Teams에서의 사용자 현재 상태

현재 상태는 Microsoft Teams(및 Microsoft 365 또는 Office 365 전체)의 사용자 프로필의 일부입니다. 현재 상태는 사용자의 현재 가용성 및 다른 사용자에게 상태를 나타냅니다. 기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다. 모바일에서 페이지를 새로 고치면 현재 상태는 웹 및 데스크톱 버전에서 실시간으로 업데이트됩니다.

 > [!Note]
 > 다른 플랫폼의 Teams 사용자 프로필에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="presence-states-in-teams"></a>Teams에서의 현재 상태

|사용자가 구성함|앱이 구성함|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) 사용 가능, 부재 중. 참고: 부재 중은 사용자가 "자동 응답"을 설정하는 기간 동안 자동으로 설정됩니다. 이 기간 동안 사용자가 앱을 사용하는 경우 이중 현재 상태(예: "부재 중, 사용 가능")가 표시될 수 있습니다. |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중 |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) 통화 중|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) 회의 중 |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) 통화 중, 부재 중|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) 방해 금지 ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) 프레젠테이션 중|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) 포커스가 있습니다. 사용자가 일정에서 MyAnalytics/Insights에서 포커스 시간을 예약할 때 포커스가 발생합니다.|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움|
|| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) 곧 돌아오겠음| |
|![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 오프라인으로 표시|![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 오프라인.  사용자가 몇 분 동안 자신의 디바이스에 로그인하지 않은 경우 오프라인으로 표시됩니다. | |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) 상태 알 수 없음|
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) 부재 중. 부재 중 회신은 자동 회신이 설정되어 있는 경우 사용됩니다. (Outlook에서만 사용할 수 있습니다.) |
|||

앱으로 구성된 현재 상태는 사용자 활동(사용 가능, 자리 비우기), Outlook 일정 상태(모임에서) 또는 Teams 앱 상태(통화 중, 발표 중)를 기반으로 합니다. 일정을 기반으로 포커스 모드에  있는 경우 포커스가 Teams에서 사람들이 보는 상태가 됩니다. 포커스 모드는 다른 제품의 방해 **금지로** 표시됩니다.

컴퓨터를 잠그거나 컴퓨터가 유휴 모드 또는 절전 모드로 전환될 때 현재 상태는 Away로 변경됩니다. 모바일 장치에서 Teams 앱이 백그라운드에 있는 경우 현재 상태가 Away로 변경됩니다.

사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다. 누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다. 사용자 상태가 방해 금지로 설정된 경우 사용자는 채팅 메시지를 수신하지만 배너 알림은 표시되지 않습니다.

사용자는 방해 금지를 제외한 모든 현재 상태의 통화를 수신합니다. 이 경우 수신 전화가 음성 메일로 이동됩니다. 받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.

사용자는 Teams에서 **설정** > **개인 정보** 로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다. 우선 순위 액세스 권한이 있는 사용자는 사용자의 상태가 방해 금지로 설정된 경우에도 사용자에게 연락할 수 있습니다.

### <a name="dual-presence"></a>이중 현재 상태

  현재 상태가 대부분의 사용자에게 작동하는 방식은 일정 또는 디바이스 이벤트(예: 통화)의 동기를 부여합니다. 사용자는 만료 시간이 있는 상태를 수동으로 설정하여 UI에서 이 상태를 다시 설정할 수 있습니다.

## <a name="user-configured-states-expiration"></a>사용자가 구성한 상태 만료

사용자가 특정 스테이트 상태를 선택하면 앱 활동 업데이트보다 우선합니다. 예를 들어 사용자가 자신을 방해 금지로 설정하면 모임에 참석하거나 통화에 응답하는 경우에도 자신의 현재 상태는 방해 금지로 유지됩니다.

사용자가 구성한 상태는 사용자가 특정 기간 후에 관련이 없는 상태를 표시하지 못하도록 방지하기 위해 Teams에 기본 만료 설정이 있습니다.

|사용자가 구성한 상태|기본 만료|
|:--- |:---|
| 다른 용무 중|1일|
| 방해 금지|1일|
| 기타|7일|
|||

> [!NOTE]
> 사용자는 자신의 현재 상태 기간을 수동으로 구성할 수도 있습니다. 예를 들어 사용자는 내일 아침까지 자신을 오프라인으로 표시로 설정할 수 있습니다.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Teams의 관리자 설정을 비즈니스용 Skype와 비교

Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.

- Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다. Teams에서는 개인 정보(현재 상태 볼 수 있는 사용자 정의)를 구성할 수 없습니다.
- Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다. 연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.
- Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.
- Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.
- 조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.

> [!NOTE]
> Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Microsoft Outlook과 Teams의 관리자 설정 비교

Outlook의 Teams 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 동일한 조직의 연락처에 대해 지원됩니다.

사용자 계정의 업그레이드 모드 정책이 TeamsOnly로 설정된 경우 Outlook에서 Teams와 대화하여 현재 상태 정보를 얻습니다. 사용자 계정이 TeamsOnly로 설정되지 않은 경우 Outlook에서 비즈니스용 Skype와 대화합니다.

## <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

조직에서 비즈니스용 [Skype를](coexistence-chat-calls-presence.md) 사용할 때 Teams 현재 상태의 작동 방식에 대한 자세한 내용은 비즈니스용 Skype와의 공존을 참조하세요.
