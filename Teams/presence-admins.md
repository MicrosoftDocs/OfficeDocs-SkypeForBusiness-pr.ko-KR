---
title: Teams에서의 사용자 현재 상태
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 팀의 현재 상태와 현재 상태 기능에 대 한 관리 설정에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fd066fe06126043475a7264b3b2c4501c7ac3ae
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650951"
---
# <a name="user-presence-in-teams"></a>Teams에서의 사용자 현재 상태

현재 상태는 Microsoft 팀에서 사용자 프로필의 일부 이며 (Microsoft 365 또는 Office 365에 걸쳐 있는 경우)입니다. 현재 상태는 사용자의 현재 사용 가능 시간 및 다른 사용자에 대 한 상태를 나타냅니다. 기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다. 모바일에서 페이지를 새로 고치면 웹 및 데스크톱 버전에서 실시간으로 현재 상태가 업데이트 됩니다.

 > [!Note]
 > 다른 플랫폼의 팀 사용자 프로필에 대 한 자세한 내용은 [플랫폼용 팀 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조 하세요.

## <a name="presence-states-in-teams"></a>Teams에서의 현재 상태

|사용자가 구성함|앱이 구성함|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) 사용 가능, 부재 중. 참고: 사용자가 "자동 회신"을 설정한 기간 동안에는 부재 중 office가 자동으로 설정 됩니다. 이 기간 동안 사용자가 앱을 사용 하는 경우 "부재 중, 사용 가능" 등의 이중 현재 상태가 표시 될 수 있습니다. |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중 |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) 통화 중|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) 회의 중 |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) 통화 중, 부재 중|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) 방해 금지 ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) 프레젠테이션 중|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) 집중할. 포커스는 사용자가 일정에서 MyAnalytics/Insights의 포커스 시간을 예약할 때 발생 합니다.|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움|
|| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) 곧 돌아오겠음| |
|![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 오프 라인으로 표시 됩니다. 팀에서 곧 제공 될 예정입니다.|![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 이거나.  사용자가 몇 분 동안 장치에 로그인 하지 않으면 오프 라인으로 표시 됩니다. | |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) 상태 알 수 없음|
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) 부재 중. 자동 회신이 설정 된 경우 부재 중 Office가 사용 됩니다. (Outlook 에서만 사용할 수 있습니다.) |
|||

앱 구성 현재 상태는 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중)를 기반으로 합니다. 일정을 기반으로 하는 포커스 모드에서는 포커스가 팀에 **표시 되는** 상태가 됩니다. 포커스 모드는 다른 제품에서 **방해** 금지로 표시 됩니다.

컴퓨터를 잠그거나 컴퓨터가 유휴 또는 절전 모드로 전환 되 면 현재 상태 상태가 "자리 비움"으로 변경 됩니다. 모바일 장치에서 팀 앱이 백그라운드에 있을 때마다 현재 상태가 자리 비움으로 변경 됩니다.

사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다. 누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다. 사용자 상태가 방해 금지로 설정 된 경우에도 사용자는 채팅 메시지를 받지만 배너 알림이 표시 되지 않습니다.

사용자는 수신 전화를 음성 메일로 이동 하는 방해 금지를 제외한 모든 현재 상태에서 전화를 받습니다. 받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.

사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다. 우선 순위가 높은 권한이 있는 사용자는 사용자의 상태가 방해 금지로 설정 된 경우에도 사용자에 게 연락할 수 있습니다.

### <a name="dual-presence"></a>이중 현재 상태

  현재 상태는 대부분의 사용자에 게 작동 하는 방식으로 일정 또는 장치 이벤트 (예: 통화)의 이벤트에 의해 동기를 갖습니다. 사용자는 만료 시간이 일부 인 상태를 수동으로 설정 하 여 UI에서이 상태를 재정의할 수 있습니다.

## <a name="user-configured-states-expiration"></a>사용자 구성 상태 만료

사용자가 특정 현재 상태를 선택 하는 경우 앱 활동 업데이트 보다 우선 순위를 갖습니다. 예를 들어 사용자가 자신을 방해 금지로 설정 하는 경우에는 모임을 참석할 전화를 걸거나 응답 하더라도 현재 상태는 방해 금지로 유지 됩니다.

사용자가 일정 기간 후에는 관련이 없을 수 있는 상태를 표시 하지 않도록 하려면 팀의 기본 만료 설정을 사용 하는 상태입니다.

|사용자 구성 상태|기본 만료|
|:--- |:---|
| 다른 용무 중|1 일|
| 방해 금지|1 일|
| 타인|7 일|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Teams의 관리자 설정을 비즈니스용 Skype와 비교

Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.

- Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다. 개인 정보 (현재 상태를 볼 수 있는 사용자를 정의 하는 위치) 구성은 팀에서 사용할 수 없습니다.
- Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다. 연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.
- Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.
- Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.
- 조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.

> [!NOTE]
> Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Microsoft Outlook과 팀의 관리자 설정

Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.

사용자 계정의 업그레이드 모드 정책이 팀 전용으로 설정 되어 있는 경우 Outlook에서 현재 상태를 확인 하는 데 사용 됩니다. 사용자 계정이 팀 전용으로 설정 되어 있지 않은 경우에는 Outlook이 비즈니스용 Skype와 통신 합니다.

## <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

조직에서 비즈니스용 Skype를 사용 하는 경우 팀의 현재 상태 기능에 대 한 자세한 내용은 [비즈니스용 skype를 사용 하 여 함께 공존](coexistence-chat-calls-presence.md) 을 참조 하세요.
