---
title: 공존 및 업그레이드 설정 설정
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 이 문서는 공존 모드를 선택 하 고 다른 공존 설정을 설정 하는 데 도움이 될 것입니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce472ca1c5307dd8a5573ca076c58e32e2d41df9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571527"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>공존 및 업그레이드 설정 설정

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

비즈니스용 Skype 사용자를 업그레이드 하 여 팀을 사용 하는 경우 사용자를 위한 원활한 프로세스를 수행 하는 데 도움이 되는 몇 가지 옵션이 있습니다. 조직의 모든 사용자에 대해 동시에 동시 사용 및 업그레이드 설정을 설정 하거나 조직의 단일 또는 사용자 집합에 대 한 설정을 변경할 수 있습니다. 이전 버전의 비즈니스용 Skype 클라이언트에서는 이러한 설정을 인식 하지 못할 수 있다는 점에 유의 하세요. 비즈니스용 Skype 클라이언트 버전에 대 한 자세한 내용을 보려면 비즈니스용 [skype 다운로드 및 업데이트 페이지로](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)이동 하세요. 

비즈니스용 [skype에서](coexistence-chat-calls-presence.md) [Microsoft 팀과 비즈니스용 skype 공존 및 상호 운용성](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 또는 공존을 이해 하 여 사용할 수 있는 모드 유형을 더 잘 이해할 수 있습니다.  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>조직의 모든 사용자에 대 한 업그레이드 옵션 설정

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **조직 전체 설정** > **팀 업그레이드**로 이동 합니다. 

2. **팀 업그레이드** 페이지의 맨 위에서 해당 작업을 수행할 경우 다음과 같이 변경 합니다.
    - **공존** 모드를 설정 합니다.
        - **아일랜드** -사용자가 비즈니스용 Skype와 팀을 동시에 사용할 수 있게 하려는 경우이 설정을 사용 합니다.
        - 비즈니스용 **skype 전용** -사용자가 비즈니스용 skype만을 사용 하도록 하려는 경우이 설정을 사용 합니다.
        - **팀 전용** (일부 조직의 경우 미리 보기)-사용자가 팀만 사용할 수 있도록 하려면이 설정을 사용 합니다. 이 설정을 사용 하는 경우에도 사용자는 비즈니스용 Skype에서 호스트 된 모임에 참가할 수 있습니다.
    - **팀이 업그레이드에 사용할 수 있는 비즈니스용 Skype 사용자에 게 알림을**설정 합니다. 이 기능을 켜면 비즈니스용 Skype 사용자에 게 곧 팀 앱으로 업그레이드 될 것으로 표시 됩니다.
    - **사용자가 비즈니스용 Skype 모임에 참가 하도록 기본 설정 앱**을 설정할 수 있습니다. 이 설정은 비즈니스용 Skype 모임에 참가 하는 데 사용 되는 앱을 결정 하 고 공존 모드 값에 관계 없이 적용 됩니다.
      - **Skype 모임 앱**
      - **기능이 제한 된 비즈니스용 Skype**
    - **비즈니스용 Skype 사용자를 위해 백그라운드에서 팀 앱을 다운로드할지**여부를 설정 합니다.  이 설정은 Windows에서 비즈니스용 Skype를 실행 하는 사용자를 위해 팀 앱을 자동으로 다운로드 합니다. 이는 사용자의 공존 모드가 팀 전용 이거나 비즈니스용 Skype에서 보류 중인 업그레이드의 알림을 사용 하는 경우에만 허용 됩니다.
3. 변경한 후 **저장** 을 클릭 합니다.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>조직의 단일 사용자에 대 한 업그레이드 옵션 설정

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **사용자**로 이동한 다음 목록에서 사용자를 선택 합니다. 
2. 사용자의 **계정** 탭에서 **팀 업그레이드**아래에서 **편집**을 클릭 합니다.
3. **공존 모드**를 설정할 수 있습니다. 다음 옵션 중에서 선택 합니다.
     - **조직 전체 설정 사용** -사용자가 **조직 전체** 설정의 설정을 사용 하도록 하려면이 설정을 사용 합니다. 
     - **아일랜드** -사용자가 비즈니스용 Skype와 팀을 모두 사용할 수 있도록 하려면이 설정을 사용 합니다. 
     - 비즈니스용 **skype 전용** -사용자가 비즈니스용 skype를 사용 하도록 하려는 경우이 설정을 사용 합니다. 
     - **팀 전용** -사용자가 팀만 사용할 수 있도록 하려면이 설정을 사용 합니다. 사용자는 계속 비즈니스용 Skype 모임에 참가할 수 있습니다.
4. **조직 전체 설정을 사용**하는 것 이외의 **공존 모드** 를 선택 하면 사용자의 비즈니스용 Skype 앱에서 팀으로 업그레이드 하는 알림을 사용할 수 있는 옵션이 제공 됩니다. **비즈니스용 Skype 사용자에 게 알림** 옵션을 설정 하 여 사용자에 대해이 알림을 사용 하도록 설정할 수 있습니다.
5. 변경한 후 **저장** 을 클릭 합니다.

### <a name="related-topics"></a>관련 항목
[여행 계획](upgrade-plan-journey.md)

[비즈니스용 Skype 및 팀에 대 한 공존 및 업그레이드 여행 이해](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)
