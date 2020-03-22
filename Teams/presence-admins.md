---
title: Teams에서의 사용자 현재 상태
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams에서의 현재 상태에 대한 관리자를 위한 정보.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863199"
---
# <a name="user-presence-in-teams"></a>Teams에서의 사용자 현재 상태

현재 상태는 Microsoft Teams(및 Office 365 전체)의 사용자 프로필의 일부로서 다른 사용자에게 사용자의 현재 대화 가능 여부 및 상태를 나타냅니다. 기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다.

> [!IMPORTANT]
> 사용자가 **Teams 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거하면 Outlook 및 기타 Office 앱에서 현재 상태가 작동하지 않습니다. 현재 상태는 Teams에서 잘 작동합니다. 해결 방법: **Teams 전용** 모드에서 팀을 실행하는 경우에도 Outlook (및 기타 Office 앱)에서 현재 상태를 보려면 비즈니스용 Skype를 설치해야 합니다. Microsoft는 이 문제를 알고 있으며 해결하기 위해 노력하고 있습니다.

Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.

## <a name="presence-states-in-teams"></a>Teams에서의 현재 상태

Teams에서 사용할 수 있는 사용자 현재 상태는 다음과 같습니다.

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
 
사용자는 수동으로 현재 상태를 몇 가지 옵션으로 설정하고 해당 상태를 다른 모든 사용자에게 보여지도록 할 수 있습니다. 더 많은 사용자 현재 상태 세부 정보 또한 자동으로 업데이트됩니다. 변경 사항은 사용자 활동(대화 가능, 자리 비움), Outlook 일정 상태(회의 중) 또는 Teams 앱 상태(통화 중, 프레젠테이션 중)에 따라 목록에 들여쓰기된 상태를 기준으로 합니다. 15분의 비활성 시간 제한이 있으며, 해당 시간이 지나면 현재 상태가 자리 비움으로 재설정됩니다.

사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다. 누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다. 사용자가 방해 금지 상태인 경우에도 채팅 메시지는 계속 받게 되나 배너 알림은 표시되지 않습니다.

사용자는 방해 금지 상태를 제외한 모든 현재 상태에서 걸려오는 전화를 받게 되며, 방해 금지 상태에서는 전화가 음성 메일로 전달됩니다. 받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.

사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다. 우선 순위 액세스 권한이 있는 사용자는 상대방이 방해 금지 상태에 있더라도 연락이 가능합니다.

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
