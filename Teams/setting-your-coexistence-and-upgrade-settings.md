---
title: 공존 및 업그레이드 설정 지정
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
description: 조직의 모든 사용자 또는 조직의 단일 또는 사용자 집합에 대해 동시에 공존 및 업그레이드 설정을 설정하는 방법에 대해 자세히 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940608"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>공존 및 업그레이드 설정 지정


Teams를 사용하기 위해 비즈니스용 Skype 사용자를 업그레이드할 때 사용자에게 원활한 프로세스를 만드는 데 도움이 되는 몇 가지 옵션이 있습니다. 조직의 모든 사용자에 대해 동시에 공존 및 업그레이드 설정을 만들거나 조직의 단일 또는 사용자 집합에 대한 설정을 변경할 수 있습니다. 이전 버전의 비즈니스용 Skype 클라이언트는 이러한 설정을 적용하지 않을 수 있습니다. 비즈니스용 Skype 클라이언트 버전에 대한 자세한 내용은 비즈니스용 Skype 다운로드 및 업데이트 [페이지로 이동하세요.](https://docs.microsoft.com/skypeforbusiness/software-updates) 

비즈니스용 Skype와의 Microsoft Teams 및 [비즈니스용 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 공존 및 상호 연동성 또는 공존 이해를 읽어 사용할 수 있는 모드를 더 잘 이해할 [수 있습니다.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>조직의 모든 사용자에 대한 업그레이드 옵션 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. Microsoft [Teams 관리 센터의](https://admin.teams.microsoft.com/)왼쪽 탐색 모음에서 Teams 업그레이드의 **전체**  >  **설정으로 이동합니다.** 

2. Teams 업그레이드 페이지의 맨 **위에** 있는 다음 옵션을 원하는 경우 수정합니다.
    - 공존 **모드를** 설정합니다.
        - **제도** - 사용자가 비즈니스용 Skype와 Teams를 동시에 사용할 수 있도록 하려는 경우 이 설정을 사용하세요.
        - **비즈니스용 Skype만** - 사용자가 비즈니스용 Skype만 사용하게 하려는 경우 이 설정을 사용하세요.
        - **Teams** 공동 작업을 사용하는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널)에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.
        - **Teams** 공동 작업 및 모임이 있는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널) 및 Teams 모임에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.
        - **Teams만** - 사용자가 Teams만 사용하게 하려는 경우 이 설정을 사용 합니다. 이 설정에서도 사용자는 비즈니스용 Skype에서 호스트된 모임에 참가할 수 있습니다.
        
    - Teams를 업그레이드할 수 있도록 **비즈니스용 Skype 사용자에게 알림으로 설정하세요.** 이 기능을 설정하면 비즈니스용 Skype 사용자에게 곧 Teams 앱으로 업그레이드될 것 을 알 수 있습니다.
    - 사용자가 **비즈니스용 Skype 모임에 참가할 수 있도록 기본 설정 앱을 설정하세요.** 이 설정은 비즈니스용 Skype 모임에 참가하는 데 사용되는 앱을 결정하며 공존 모드의 값에 관계없이 사용됩니다.
      - **Skype 모임 앱**
      - **제한된 기능이 있는 비즈니스용 Skype**
    - 비즈니스용 Skype 사용자의 백그라운드에서 Teams 앱을 **다운로드할지 여부를 설정하세요.**  이 설정은 Windows에서 비즈니스용 Skype를 실행하는 사용자를 위한 Teams 앱을 자동으로 다운로드합니다. 사용자의 공존 모드가 Teams 전용인 경우 또는 비즈니스용 Skype에서 보류 중인 업그레이드 알림을 사용하도록 설정한 경우 이 모드가 사용됩니다.
3. 변경한 **후** 저장을 클릭합니다.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>조직의 단일 사용자에 대한 업그레이드 옵션 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 사용자로 이동한 다음 **목록에서** 사용자를 선택합니다. 
2. 사용자의 **계정** 탭의 Teams **업그레이드 아래에서** 편집을 **클릭합니다.**
3. 공존 모드를 **설정할 수 있습니다.** 다음 옵션에서 선택합니다.
     - **전체 설정** 사용 - 사용자가 전체 설정에서 설정을 사용하려면 이 설정을 **사용합니다.** 
     - **제도** - 사용자가 비즈니스용 Skype와 Teams를 모두 사용할 수 있도록 하려는 경우 이 설정을 사용하세요. 
     - **비즈니스용 Skype만** - 사용자가 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.
     - **Teams** 공동 작업을 사용하는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널)에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.
      - **Teams** 공동 작업 및 모임이 있는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널) 및 Teams 모임에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.
     - **Teams만** - 사용자가 Teams만 사용하게 하려는 경우 이 설정을 사용 합니다. 사용자는 여전히 비즈니스용 Skype 모임에 참가할 수 있습니다.
4. 전체 설정  사용 외의 공존 모드를 선택하는 경우 사용자의 비즈니스용 Skype 앱에서 Teams로 업그레이드하는 알림을 사용할 수 있는 옵션이 곧 제공될 예정입니다. 비즈니스용 Skype 사용자 알림 옵션을 설정하여 사용자에 대해 이 알림을 사용하도록 **설정할 수** 있습니다.
5. 변경한 **후** 저장을 클릭합니다.

### <a name="related-topics"></a>관련 항목
[IT 관리자를 위해 비즈니스용 Skype에서 Teams로 업그레이드](upgrade-to-teams-on-prem-overview.md)

[여정 계획](upgrade-plan-journey.md)

[비즈니스용 Skype 및 Teams의 공존 및 업그레이드 여정 이해](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md)
