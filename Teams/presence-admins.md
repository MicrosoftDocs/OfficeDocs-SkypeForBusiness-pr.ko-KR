---
title: 팀의 사용자 현재 상태
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 정보 관리자는 팀의 현재 상태에 대해 이해 해야 합니다.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184382"
---
# <a name="user-presence-in-teams"></a>팀의 사용자 현재 상태

현재 상태는 Microsoft 팀 (및 Office 365)에서 사용자 프로필의 일부 이며 조직의 다른 사용자에 대 한 사용자의 현재 사용 가능한 시간 및 상태를 나타냅니다. 기본적으로 팀을 사용 하는 조직의 모든 사용자는 다른 사용자가 온라인으로 사용할 수 있는지 여부에 상관 없이 거의 실시간으로 볼 수 있습니다.

## <a name="presence-states-in-teams"></a>팀의 현재 상태

팀에서 사용할 수 있는 사용자 현재 상태는 다음과 같습니다.

|사용자 구성 됨|앱 구성 됨|
|:--- |:---|
| ![현재 상태를 나타내는 진한 녹색 chek 표시](media/Presence_Available.png) 공간이|![현재 상태를 나타내는 진한 녹색 chek 표시](media/Presence_Available.png) 공간이|
|| ![녹색 chek 표시, 사용 가능한 oof 표시](media/Presence_Available_OOF.png) 사용 가능, 부재 중 |
|  ![약속 있음을 표시 하는 빨간색 실선 원](media/Presence_Busy.png) 작업 |  ![약속 있음을 표시 하는 빨간색 실선 원](media/Presence_Busy.png) 작업  |
|| ![통화 중임을 나타내는 빨간색 원 실선](media/Presence_Busy.png) 통화 중|
|| ![모임의 약속 있음을 나타내는 빨간색 원 실선](media/Presence_Busy.png) 모임에서 |
|| ![부재 중 통화를 나타내는 빨간색 원 열기](media/Presence_Busy_OOF.png) 통화 중, 부재 중|
|  ![흰색 선이 있는 빨간색 원 (방해 금지 표시)](media/Presence_DND.png) 방해 금지 ||
|| ![흰색 선이 있는 빨간색 원 (프레젠테이션 표시)](media/Presence_DND.png) 프레젠테이션할|
| ![자리를 표시 하지 않는 노란색 시계 아이콘](media/Presence_Away.png) 방향| ![자리를 표시 하지 않는 노란색 시계 아이콘](media/Presence_Away.png) 방향|
|| ![마지막으로 표시 되는](media/Presence_Away.png) *동안* 자리를 비운 노란색 시계 아이콘|
|![자리 비움을 나타내는 노란색 시계 아이콘을 오른쪽으로 뒤로](media/Presence_Away.png) 곧 돌아오겠음| |
|| ![자리 비움으로 표시 되는 노란색 시계 아이콘](media/Presence_Away.png)  작업 해제|
|| ![X가 있는 회색 원, 오프 라인 상태임](media/Presence_Offline.png) 이거나 |
|| ![알 수 없는 상태를 나타내는 회색 원 열기](media/Presence_Unknown.png) 알 수 없는 상태|
||![대각선이 있는 빨간 원 (차단 됨 표시)을 엽니다.](media/Presence_Blocked.png) 약속이 |
|| ![화살표를 사용 하 여 부재 중 표시 되는 자주색 원](media/Presence_OOF.png) 부재 중|
|||
 
사용자는 일부 옵션에 대 한 현재 현재 상태 상태를 수동으로 설정할 수 있으며 해당 상태는 다른 모든 사용자에 게 적용 됩니다. 또한 추가 사용자 현재 상태 세부 정보는 사용자 활동 (예: 사용 가능 또는 자리 비움), Outlook 일정 상태 (예: 모임) 또는 팀 앱 상태 (통화 중 표시), 목록에서 들여쓴 상태에 따라 자동으로 업데이트 됩니다.

사용자의 현재 현재 상태 상태가 자리 비움으로 다시 설정 될 때까지 15 분 동안 비활동 시간이 초과 됩니다.

사용자는 끊을 수 있는 사용자를 지정할 수 있습니다 (방해 금지 설정을 재정의 하도록 연락). 이러한 설정은 앱에서 사용할 수 있습니다.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>비즈니스용 Skype와 팀의 관리 설정

다음 관리 설정 비즈니스용 Skype는 팀에서 서로 다릅니다.

- 팀에서 조직의 사용자는 항상 현재 상태 공유를 사용할 수 있습니다. 팀에서는 개인 정보 (현재 상태를 볼 수 있는 사람 결정) 구성을 사용할 수 없습니다.
- 팀의 사용자는 모든 사용자 (페더레이션된 서비스 포함)와의 현재 상태 공유를 항상 사용할 수 있습니다. 대화 상대 목록 (비즈니스용 Skype에서 하나가 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처**아래에 표시 됩니다.
- 클라이언트가 방해 금지이 고 팀의 사용자에 게 탁월한 기능을 항상 사용할 수 있습니다.
- Outlook과 통합 된 팀의 사용자는 일정 (부재 중 및 다른 일정 정보 포함) 통합이 항상 활성화 되어 있습니다.
- 팀의 사용자에 게는 *마지막으로 표시* 된 또는 *자리 비움* (비즈니스용 Skype를 사용 하는 이중 환경) 표시기가 항상 활성화 되어 있습니다.

> [!NOTE]
> 이러한 설정을 사용자 지정 하는 팀 관리자의 기능은 현재 지원 되지 않습니다.

## <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 공존

비즈니스용 Skype로 공존할 때의 팀 현재 상태 기능에 대 한 자세한 내용은 비즈니스용 [skype를 사용 하 여 함께 공존](coexistence-chat-calls-presence.md) 을 참조 하세요. 
