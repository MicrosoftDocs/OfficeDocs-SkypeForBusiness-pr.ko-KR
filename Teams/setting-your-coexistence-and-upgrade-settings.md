---
title: 공존 및 업그레이드 설정 지정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 조직의 모든 사용자 또는 조직의 단일 사용자 또는 집합에 대해 공존 및 업그레이드 설정을 설정하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8062c4a9b12c067091fcc95f192ac519f680937d
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846537"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>공존 및 업그레이드 설정 지정


Teams 사용하도록 비즈니스용 Skype 사용자를 업그레이드하는 경우 사용자에게 원활한 프로세스를 만드는 데 도움이 되는 몇 가지 옵션이 있습니다. 조직의 모든 사용자에 대해 한 번에 공존 및 업그레이드 설정을 만들거나 조직의 단일 사용자 또는 사용자 집합에 대한 설정을 변경할 수 있습니다. 이전 버전의 비즈니스용 Skype 클라이언트는 이러한 설정을 적용하지 않을 수 있습니다. 비즈니스용 Skype 클라이언트 버전에 대한 자세한 내용은 [비즈니스용 Skype 다운로드 및 업데이트 페이지](/skypeforbusiness/software-updates)로 이동하세요. 

Microsoft Teams [이해 및 비즈니스용 Skype 공존 및 상호 운용성](teams-and-skypeforbusiness-coexistence-and-interoperability.md) [또는](coexistence-chat-calls-presence.md) 비즈니스용 Skype 공존을 읽어 사용할 수 있는 모드를 더 잘 이해할 수 있습니다.  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>조직의 모든 사용자에 대한 업그레이드 옵션 설정

 **Microsoft Teams 관리 센터 사용**

1. [Microsoft Teams 관리 센터의](https://admin.teams.microsoft.com/) 왼쪽 탐색 영역에서 **Teams** >  **Teams 업그레이드 설정** 으로 이동합니다. 

2. **Teams 업그레이드** 페이지의 맨 위에서 원하는 대로 다음 옵션을 수정합니다.

    - **공존** 모드를 설정합니다.
        - **Islands** - 사용자가 비즈니스용 Skype 및 Teams 동시에 사용할 수 있도록 하려면 이 설정을 사용합니다.
        - **비즈니스용 Skype 전용** - 사용자가 비즈니스용 Skype만 사용하려면 이 설정을 사용합니다.
        - **Teams 협업 비즈니스용 Skype** - 사용자가 그룹 공동 작업(채널)에 Teams 사용하는 것 외에도 비즈니스용 Skype 사용하려는 경우 이 설정을 사용합니다.
        - **Teams 공동 작업 및 모임** 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널) 및 Teams 모임에 Teams 사용하는 것 외에도 비즈니스용 Skype 사용하려는 경우 이 설정을 사용합니다.
        - **Teams 전용** - 사용자가 Teams만 사용하도록 하려면 이 설정을 사용합니다. 이 설정을 사용하는 경우에도 사용자는 비즈니스용 Skype 호스팅되는 모임에 참가할 수 있습니다.

          > [!IMPORTANT]
          > 다음 단계가 모두 완료된 후에만 TeamsOnly 모드를 전체 테넌트에 할당할 수 있습니다.
          >  - 모든 온-프레미스 사용자가 비즈니스용 Skype 서버 온-프레미스 도구 집합의 Move-CsUser 사용하여 Teams 이동되었습니다.
          >  - Microsoft 365 가리키도록 비즈니스용 Skype DNS 레코드를 업데이트했습니다. 
          >
          > 자세한 내용은 [하이브리드 구성을 사용하지 않도록 설정하여 Teams만 마이그레이션을 완료합니다](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - **Teams 업그레이드에 사용할 수 있음을 비즈니스용 Skype 사용자에게 알리도록** 설정합니다. 이 기능을 켜면 비즈니스용 Skype 사용자에게 곧 Teams 앱으로 업그레이드될 것임을 알립니다.

    - **사용자가 비즈니스용 Skype 모임에 참가할 수 있도록 기본 설정 앱을** 설정합니다. 이 설정은 비즈니스용 Skype 모임에 참가하는 데 사용되는 앱을 결정하며 공존 모드의 값에 관계없이 적용됩니다.
      - **Skype 모임 앱**
      - **제한된 기능이 있는 비즈니스용 Skype**

    - **비즈니스용 Skype 사용자를 위해 백그라운드에서 Teams 앱을 다운로드** 할지 여부를 설정합니다. 이 설정은 Windows 비즈니스용 Skype 실행하는 사용자에 대한 Teams 앱을 자동으로 다운로드합니다. 사용자의 공존 모드가 Teams 경우에만 적용되며, 비즈니스용 Skype 보류 중인 업그레이드 알림이 사용하도록 설정된 경우에만 적용됩니다.

3. 변경한 후 **저장** 을 클릭합니다.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>조직의 단일 사용자에 대한 업그레이드 옵션 설정

 **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 영역에서 **UsersManage** >  사용자로 이동한 다음 목록에서 사용자를 선택합니다. 
2. 사용자의 **계정** 탭에서 **Teams 업그레이드** 에서 **편집** 을 클릭합니다.
3. **공존 모드** 를 설정할 수 있습니다. Teams 이외의 모드는 비즈니스용 Skype 서버 온-프레미스에 있는 사용자에게만 적용할 수 있으며, 반대로 클라우드에 있는 사용자만 TeamsOnly 모드를 사용할 수 있습니다.  다음 옵션 중에서 선택합니다.
     - **조직 전체 설정 사용** - 사용자가 **조직 전체** 설정에서 설정을 사용하도록 하려면 이 설정을 사용합니다. 
     - **Islands** - 사용자가 비즈니스용 Skype 및 Teams 모두 사용할 수 있도록 하려면 이 설정을 사용합니다. 
     - **비즈니스용 Skype 전용** - 사용자가 비즈니스용 Skype 사용하려는 경우 이 설정을 사용합니다.
     - **Teams 협업 비즈니스용 Skype** - 사용자가 그룹 공동 작업(채널)에 Teams 사용하는 것 외에도 비즈니스용 Skype 사용하려는 경우 이 설정을 사용합니다.
      - **Teams 공동 작업 및 모임** 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널) 및 Teams 모임에 Teams 사용하는 것 외에도 비즈니스용 Skype 사용하려는 경우 이 설정을 사용합니다.
     - **Teams 전용** - 사용자가 Teams만 사용하려면 이 설정을 사용합니다. 사용자는 여전히 비즈니스용 Skype 모임에 참가할 수 있습니다.
4. **조직 전체 설정 사용** 이외의 **공존 모드** 를 선택하는 경우 Teams 업그레이드가 곧 제공될 사용자의 비즈니스용 Skype 앱에서 알림을 사용하도록 설정하는 옵션이 있습니다. 비즈니스용 Skype 사용자 알림 옵션을 켜면 **사용자에게** 이 알림을 사용하도록 설정할 수 있습니다.
5. 변경한 후 **저장** 을 클릭합니다.

### <a name="related-topics"></a>관련 항목
[여정 계획](upgrade-plan-journey.md)

[비즈니스용 Skype 및 Teams 대한 공존 및 업그레이드 경험 이해](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[비즈니스용 Skype 함께 Teams 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)

[온-프레미스 비즈니스용 Skype 환경 서비스 해제](/skypeforbusiness/hybrid/decommission-on-prem-overview)
