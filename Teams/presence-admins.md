---
title: Teams에서의 사용자 현재 상태
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 팀의 현재 상태 및 현재 상태 기능에 대 한 관리 설정에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6432bac9dbbfe65cf3e139ecae00b02cd5ae8651
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905770"
---
# <a name="user-presence-in-teams"></a>Teams에서의 사용자 현재 상태

현재 상태는 Microsoft 팀 (및 Office 365)의 사용자 프로필의 일부로, 다른 사용자에 대 한 현재의 가용성과 상태를 표시 합니다. 기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다.

Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.

## <a name="presence-states-in-teams"></a>Teams에서의 현재 상태

|사용자가 구성함|앱이 구성함|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) 대화 가능|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) 대화 가능, 부재 중 |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중 |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) 다른 용무 중  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) 통화 중|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) 회의 중 |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) 통화 중, 부재 중|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) 방해 금지 ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) 프레젠테이션 중|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) 집중하는 중|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) 자리 비움|
|| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) 곧 돌아오겠음| |
|| ![노란색 시계 아이콘, 퇴근 표시](media/Presence_Away.png)  퇴근|
|| ![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) 오프라인 |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) 상태 알 수 없음|
||![대각선이 있는 빈 빨간색 원, 차단됨 표시](media/Presence_Blocked.png) 차단됨 |
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) 부재 중|
|||

앱 구성 현재 상태는 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중)를 기반으로 합니다.

컴퓨터를 잠그거나 유휴 또는 절전 모드로 전환 하면 현재 상태 상태가 ' 자리 비움 '으로 변경 됩니다. 모바일에서 팀 앱이 백그라운드에 있을 때마다 현재 상태는 자리 비움으로 변경 됩니다.

사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다. 누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다. 사용자가 방해 금지를 사용 하는 경우 채팅 메시지는 계속 표시 되지만 배너 알림은 나타나지 않습니다.

사용자는 수신 전화를 음성 메일로 이동 하는 방해 금지를 제외한 모든 현재 상태에서 전화를 받습니다. 받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.

사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다. 우선 순위 액세스 권한이 있는 사용자는 사용자가 방해 금지 인 경우에도 사용자에 게 연락할 수 있습니다.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Teams의 관리자 설정을 비즈니스용 Skype와 비교

Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.

- Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다. Teams에서는 개인 정보(현재 상태를 볼 수 있는 사용자를 정의하는 위치) 구성을 사용할 수 없습니다.
- Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다. 연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.
- Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.
- Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.
- 조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.

> [!NOTE]
> Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.

## <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 현재 상태가 작동하는 방법에 대한 자세한 내용은 [비즈니스용 Skype와 동시 사용](coexistence-chat-calls-presence.md)을 참조하세요.
