---
title: Teams에서 사용자 현재 상태 확인
author: jambirk
ms.author: jambirk
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 팀의 현재 상태에 대 한 관리자 정보.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7660cc35986b8b0debc449bacde686bb9e2694b
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41580925"
---
# <a name="user-presence-in-teams"></a>Teams에서 사용자 현재 상태 확인

현재 상태는 Microsoft 팀 (및 Office 365)의 사용자 프로필의 일부로, 다른 사용자에 대 한 현재의 가용성과 상태를 표시 합니다. 다른 사용자가 온라인 상태를 사용할 수 있는 경우 기본적으로 팀을 사용 하는 조직의 모든 사용자가 거의 실시간으로 볼 수 있습니다.

> [!IMPORTANT]
> 사용자가 **Teams 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거하면 Outlook 및 기타 Office 앱에서 현재 상태가 작동하지 않습니다. 현재 상태는 Teams에서 잘 작동합니다. 해결 방법: Outlook (및 다른 Office 앱)에서 현재 상태를 확인 하려면 팀 **전용** 모드로 팀을 실행 하는 경우에도 비즈니스용 Skype를 설치 해야 합니다. Microsoft는 이 문제를 알고 있으며 해결하기 위해 노력하고 있습니다.

Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.

## <a name="presence-states-in-teams"></a>팀의 현재 상태

팀에서 사용할 수 있는 사용자 현재 상태는 다음과 같습니다.

|사용자 구성 됨|앱 구성 됨|
|:--- |:---|
| ![현재 상태를 나타내는 녹색 확인 표시가 있습니다.](media/Presence_Available.png) 공간이|![현재 상태를 나타내는 녹색 확인 표시가 있습니다.](media/Presence_Available.png) 공간이|
|| ![녹색 확인 표시를 열고 사용 가능한 oof를 나타냅니다.](media/Presence_Available_OOF.png) 사용 가능, 부재 중 |
|  ![빨간색 실선 원으로, 약속이 있음을 나타냅니다.](media/Presence_Busy.png) 작업 |  ![빨간색 실선 원으로, 약속이 있음을 나타냅니다.](media/Presence_Busy.png) 작업  |
|| ![빨간색 원으로 표시 되며 통화 중입니다.](media/Presence_Busy.png) 통화 중|
|| ![빨간색 실선 원으로, 모임에서 약속이 있음을 나타냅니다.](media/Presence_Busy.png) 모임에서 |
|| ![빨간색 원 열림, 약속이 있음을 나타냅니다.](media/Presence_Busy_OOF.png) 전화 걸기, 부재 중|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) 방해 금지 ||
|| ![흰색 선이 있는 빨간색 원으로 프레젠테이션 표시](media/Presence_DND.png) 프레젠테이션할|
|| ![흰색 선이 있는 빨간색 원이 포커스를 나타냄](media/Presence_DND.png) 집중할|
| ![노란색 시계 아이콘, 자리 비움 상태임을 나타냄](media/Presence_Away.png) 방향| ![노란색 시계 아이콘, 자리 비움 상태임을 나타냄](media/Presence_Away.png) 방향|
|| ![노란색 시계 아이콘, 마지막으로](media/Presence_Away.png) 표시 되는 자리 비움 *시간* 표시|
|![노란색 시계 아이콘, 자리 비움 표시, 오른쪽으로](media/Presence_Away.png) 곧 돌아오겠음| |
|| ![자리 비움, 작업 시간을 나타내는 노란색 시계 아이콘](media/Presence_Away.png)  작업 해제|
|| ![X가 있는 회색 원, 오프 라인 상태임을 나타냄](media/Presence_Offline.png) 이거나 |
|| ![회색 원 열림, 알 수 없는 상태 표시](media/Presence_Unknown.png) 알 수 없는 상태|
||![대각선이 있는 빨간색 원 열림, 차단 됨을 나타냄](media/Presence_Blocked.png) 약속이 |
|| ![화살표가 있는 자주색 원, 부재 중임을 나타냄](media/Presence_OOF.png) 부재 중|
|||
 
사용자는 일부 옵션에 대 한 현재 현재 상태 상태를 수동으로 설정할 수 있으며 해당 상태는 다른 모든 사용자에 게 적용 됩니다. 또한 추가 사용자 현재 상태 정보도 자동으로 업데이트 됩니다. 변경 사항은 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중 발표 됨)에 따라 목록에서 들여쓰기 되는 상태에 기반 합니다. 현재 현재 상태가 자리 비움으로 다시 설정 되는 데 15 분 비활성 시간 제한이 있습니다.

사용자는 현재 상태에 관계 없이 팀에서 전송 된 모든 채팅 메시지를 받습니다. 다른 사람이 메시지를 보낼 때 사용자가 오프 라인 상태 이면 다음에 사용자가 온라인 상태일 때 채팅 메시지가 팀에 표시 됩니다. 사용자가 방해 금지 상태에 있는 경우 채팅 메시지는 계속 표시 되지만 배너 알림을 표시할 수 없습니다.

사용자는 수신 통화가 음성 메일로 배달 되는 방해 금지 상태를 제외한 모든 현재 상태에서 전화를 받습니다. 받는 사람이 호출자를 차단 하면 통화가 전달 되지 않으며 발신자는 받는 사람의 현재 상태를 오프 라인으로 간주 합니다.

사용자는 팀의 **설정** > **개인 정보** 로 연결 하 여 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다. 우선 순위가 높은 권한이 있는 사용자는 사용자가 방해 금지 상태에 있더라도 사용자에 게 연락할 수 있습니다.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>비즈니스용 Skype와 팀의 관리 설정

다음 관리 설정 비즈니스용 Skype는 팀에서 서로 다릅니다.

- 팀에서 조직의 사용자는 항상 현재 상태 공유를 사용할 수 있습니다. 개인 정보 (현재 상태를 볼 수 있는 사용자를 정의 하는 위치) 구성은 팀에서 사용할 수 없습니다.
- 팀의 사용자는 모든 사용자 (페더레이션된 서비스 포함)와의 현재 상태 공유를 항상 사용할 수 있습니다. 대화 상대 목록 (비즈니스용 Skype에서 하나가 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처**아래에 표시 됩니다.
- 클라이언트가 방해 금지이 고 팀의 사용자에 게 탁월한 기능을 항상 사용할 수 있습니다.
- 일정 (부재 중 및 다른 일정 정보 포함) 통합은 팀이 Outlook과 통합 될 때 항상 사용자가 사용할 수 있도록 설정 됩니다.
- 조직에서 비즈니스용 Skype를 사용 하는 경우 팀의 사용자는 표시기를 볼 수 있는 *마지막* 또는 *반대* 입니다.

> [!NOTE]
> 이러한 설정을 사용자 지정 하는 팀 관리자의 기능은 현재 지원 되지 않습니다.

## <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 공존

조직에서 비즈니스용 Skype를 사용 하는 경우 팀의 현재 상태 기능에 대 한 자세한 내용은 [비즈니스용 skype를 사용 하 여 함께 공존](coexistence-chat-calls-presence.md) 을 참조 하세요.
