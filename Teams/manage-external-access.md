---
title: 외부 액세스 (페더레이션) 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: 팀 또는 IT 관리자가 다른 도메인(페더레이션)의 사용자가 Teams에 참여할 수 있도록 해당 도메인에 대한 외부 액세스를 구성할 수 있습니다.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: cb7225df0503bc65ff61130702f62f26b85bc329
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780047"
---
<a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams에서 외부 액세스 관리
======================================================

외부 액세스는 전체 외부 도메인의 팀 사용자가 팀에서 모임을 검색, 통화, 채팅 및 설정 하는 방법입니다. 외부 액세스를 사용 하 여 아직 비즈니스용 Skype (온라인 및 온-프레미스)와 Skype (미리 보기)를 사용 중인 외부 사용자와 통신할 수도 있습니다.

외부 사용자가 팀과 채널에 액세스할 수 있도록 하려면 게스트 액세스를 사용하는 것이 좋습니다. 외부 액세스와 게스트 액세스 사이의 차이점에 대한 자세한 내용은 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조하세요. 

다음과 같은 경우에 외부 액세스를 사용합니다.
  
- 다른 도메인에 공동 작업을 해야 하는 사용자가 있는 경우 예를 들어 Rob@contoso.com 및 Ann@northwindtraders.com은 contoso.com 및 northwindtraders.com 도메인의 다른 사용자들과 함께 프로젝트를 작업하고 있습니다.

- 조직 내 사용자가 Teams를 사용하여 조직 외부의 특정 비즈니스에 참여하는 사용자와 연락하도록 하려는 경우

- Teams를 사용하는 전 세계의 모든 사람이 전자 메일 주소를 사용하여 사용자를 찾고 연락할 수 있게 하려고 합니다. 

> [!IMPORTANT]
> 현재 Microsoft Teams 앱 내에서 현재 사용자의 Azure AD(Azure Active Directory) 또는 테넌트의 게스트가 아닌 조직 외부의 외부 사용자에게 페더레이션하려면 하이브리드용으로 올바르게 설정하고 비즈니스용 Skype Online으로 이동해야 합니다. 2019년 2월 25일 현재 Teams에서는 비즈니스용 Skype Online에 SIP 프로필 사용자가 없는 경우 네이티브 페더레이션을 지원하지 않습니다. 하이브리드 계정을 설정한 다음 Teams으로 이동하는 방법에 대한 자세한 내용은 [비즈니스용 Skype 하이브리드 배포를 Teams로 업그레이드](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)를 참조하세요.

## <a name="plan-for-external-access"></a>외부 액세스 계획

기본적으로 외부 액세스는 Teams에서 활성화되어 있습니다. 즉, 조직에서 모든 외부 도메인과 의사소통할 수 있습니다. 차단된 도메인을 추가하면 다른 모든 도메인이 허용됩니다. 허용된 도메인을 추가하면 다른 모든 도메인이 차단됩니다. Teams 관리 센터에서 외부 액세스를 설정하는 세 가지 시나리오가 있습니다(**조직 전체 설정** > **외부 액세스**).

- **열려 있는 페더레이션**: 이는 Teams의 기본 설정이며, 조직의 사용자가 조직 외부의 사용자를 찾아서 통화하고, IM/채팅을 전송하고, 모임을 설정할 수 있습니다.

    이 시나리오에서는 사용자가 Temas 또는 비즈니스용 Skype를 실행하고 열려 있는 페더레이션을 사용하거나 내 도메인을 허용 목록에 추가한 모든 외부 도메인과 통신할 수 있습니다.

- **특정 도메인 허용**: **허용** 목록에 도메인을 추가하여 외부 액세스를 허용된 도메인만으로 제한합니다. 허용된 도메인 목록을 설정하면 다른 모든 도메인은 차단됩니다. 특정 도메인을 허용하려면 **도메인 추가**를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업**을 클릭한 다음 **허용됨**을 선택합니다.

- **특정 도메인 차단** - **차단** 목록에 도메인을 추가하여 차단한 도메인을 *제외*한 모든 외부 도메인과 통신할 수 있습니다. 특정 도메인을 차단하려면 **도메인 추가**를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업**을 클릭한 다음 **차단됨**을 선택합니다. 차단된 도메인 목록을 설정하면 다른 모든 도메인은 허용됩니다.

## <a name="allow-or-block-domains"></a>도메인 허용 또는 차단

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>1단계 - 조직이 다른 Teams 조직과 통신할 수 있도록 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png)  **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **조직 전체 설정** > **외부 액세스**로 이동합니다.

2. **사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음** 설정을 켭니다.

     ![사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음 설정이 켜진 스크린샷](media/manage-external-access-2.png).

3. 모든 Teams 조직이 조직의 사용자와 통신하도록하려면 5단계로 건너뜁니다.

4. 조직의 사용자와 통신할 수 있는 조직을 제한하려면 일부 도메인을 제외한 모든 도메인을 허용하거나 특정 도메인만 허용할 수 있습니다. 

    - 일부 도메인을 제외한 모든 도메인을 허용하려면 **도메인 추가**를 클릭하여 차단할 도메인을 추가합니다. **도메인 추가** 창에서 도메인 이름을 입력하고 **차단됨**을 클릭한 다음 **완료**를 클릭합니다. 
    - 특정 조직에 대한 통신을 제한하려면 해당 도메인을 **허용됨** 상태인 목록에 추가합니다. 도메인을 허용 목록에 추가하면 다른 조직과의 통신은 도메인이 허용 목록에 있는 조직으로만 제한됩니다. 

5. **저장**을 클릭합니다.

6. 다른 Teams 조직의 관리자가 동일한 단계를 완료하도록 합니다. 예를 들어 **허용된 도메인** 목록에서 관리자가 사용자와 통신할 수있는 조직을 제한하는 경우 해당 관리자가 비즈니스 도메인을 입력해야 합니다.

### <a name="step-2---test-it"></a>2단계 - 테스트

설정을 테스트하려면 사용자의 방화벽 외부에 있는 Teams 사용자가 필요합니다.
  
1. 사용자와 조직의 관리자가 **외부 액세스 설정**을 변경한 후에는 계속 진행할 수 있습니다.

2. Teams 앱에서 전자 메일 주소로 사용자를 검색하고 채팅 요청을 보냅니다.

3. 사용자의 Teams 연락처에 요청하여 사용자에게 채팅 요청을 보냅니다. 요청을 받지 못한 경우 (방화벽 설정이 올바른지 이미 확인했다고 가정한다면) 방화벽 설정에 문제가 있는 것입니다.

4. 방화벽에 문제가 있는지 테스트하는 또 다른 방법은 방화벽 외부에 있는 WiFi 위치로 이동하는 것입니다. 커피숍과 같은 위치에서 Teams를 사용하여 연락처에 채팅 요청을 보냅니다. 메시지가 WiFi 위치를 통과하지만, 회사 내부에 있을 때는 통과하지 않으면 방화벽에 문제가 있음을 알 수 있습니다.

> [!NOTE]
> 사용자와 다른 사용자가 모두 외부 액세스를 켜고 서로의 도메인을 허용하는 경우 이 작업을 수행할 수 있습니다. 그래도 문제가 해결되지 않으면 다른 사용자가 구성에서 사용자의 도메인을 차단하고 있지 않은지 확인해야 합니다.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>비즈니스용 Skype Online 조직에서 사용자와의 통신

Teams 사용자가 사용자에게 연락할 수 있는 사람을 제한하는 비즈니스용 Skype 조직의 사용자를 찾고 연락할 수 있도록 설정하려는 경우 도메인에서 다른 조직의 도메인으로 외부 액세스를 설정하는 단계를 따르세요. 그런 다음 다른 조직의 관리자에게 다음 단계에 따라 비즈니스용 Skype Online에 대한 외부 액세스를 구성하도록 요청합니다.

일반적인 비즈니스용 Skype Online 시나리오에 대한 구체적인 지침은 아래 [일반적인 외부 액세스 시나리오](#common-external-access-scenarios)를 참조하세요.

![비즈니스용 skype 로고를 나타내는 아이콘](media/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

해당 조직의 관리자에게 다음 단계를 수행하도록 합니다.

1. Microsoft 365 관리 센터에서 **관리 센터** > **Teams & Skype** > **레거시 포털**로 이동합니다.
  
2. **비즈니스용 Skype 관리 센터**에서 **조직** > **외부 통신**을 선택합니다.

3. 드롭다운 상자에서 특정 비즈니스 또는 다른 도메인의 사용자와의 통신을 설정하려면 **허용된 도메인에 대해서만**을 선택합니다.

    또는 비즈니스용 Skype 정책을 공개한 전 세계의 모든 사용자와 통신할 수 있도록 설정하려는 경우 **차단된 도메인 제외**를 선택합니다. 기본 설정입니다.

4. **차단되거나 허용되는 도메인**에서 **+** 을 선택한 다음 허용하려는 도메인의 이름을 추가합니다.

## <a name="communicate-with-skype-users-in-preview"></a>Skype 사용자와의 통신(미리 보기)

조직의 Teams 사용자가 Skype 사용자와 채팅하고 통화하려면 다음 단계를 따르세요. 그런 다음 Teams 사용자는 일대일 텍스트 전용 대화 또는 Skype 사용자와의 음성/화상 통화를 검색 및 시작할 수 있으며 그 반대의 경우도 마찬가지입니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png)  **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **조직 전체 설정** > **외부 액세스**로 이동합니다.

2. **사용자가 Skype 사용자의 통신할 수 있음** 설정을 켭니다.

    ![사용자가 Skype 사용자의 통신할 수 있음 설정이 켜진 스크린샷](media/manage-external-access-5.png).

적용되는 제한 사항을 포함하여 Teams 사용자 및 Skype 사용자가 통신할 수 있는 방법에 대한 자세한 내용은 [Teams 및 Skype 상호 운용성](teams-skype-interop.md)을 참조하세요.

## <a name="common-external-access-scenarios"></a>일반적인 외부 액세스 시나리오

|**원하는 작업**  |**방법**  |
|---------|-----------------------|
|조직의 **Teams 사용자**가 다른 (외부) 조직의 **Teams 사용자**와 통신할 수 있도록 합니다.|외부 액세스에서 허용 목록에 외부 도메인을 추가하거나 열려 있는 페더레이션을 사용합니다. 그런 다음 다른 Teams 조직의 관리자가 동일한 작업을 수행하도록 합니다.      |
|조직의 **Teams 사용자**가 동일한 조직의 **비즈니스용 Skype Online 사용자**와 통신할 수 있도록 합니다.  |공존 모드를 사용하도록 설정하거나 Islands 업그레이드 모드를 선택하여 조직의 비즈니스용 Skype 사용자를 지원하세요.   |
|조직의 **Teams 사용자**가 다른 (외부) 조직의 **비즈니스용 Skype Online 사용자**와 통신할 수 있도록 합니다.      |외부 액세스에서 허용 목록에 외부 도메인을 추가하거나 열려 있는 페더레이션을 사용합니다. <br><br>외부 액세스에서 **사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음** 설정을 켭니다. 그런 다음 다른 Teams 조직의 관리자가 동일한 작업을 수행하도록 합니다. <br><br>**참고**: 비즈니스용 Skype 사용자를 포함하는 외부 도메인은 공존 모드를 사용하도록 설정하거나 Islands 업그레이드 모드를 선택하여 해당 조직의 비즈니스용 Skype 사용자를 지원해야 합니다.|
|조직의 **Teams 사용자**가 **Skype** 사용자와 통신할 수 있도록 합니다.<br> (미리 보기)  |외부 액세스에서 **사용자가 Skype 사용자의 통신할 수 있음** 설정을 켭니다. |
|**비즈니스용 Skype Online 사용자가** 다른 Microsoft 365 또는 Office 365에서 **팀 사용자** 와 통신할 수 있도록 합니다.| 비즈니스용 Skype Online 사용자는 Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings 업그레이드 모드 중 하나이고 다른 조직의 Teams 사용자가 TeamsOnly 모드인 경우 다른 조직의 Teams 사용자와 통신할 수 있습니다. <br><br>외부 액세스에서 **사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음** 설정을 켭니다. 그런 다음 다른 Teams 조직의 관리자가 동일한 작업을 수행하도록 합니다.|
|**Skype For Business online 사용자가** 다른 Microsoft 365 또는 Office 365의 비즈니스용 **skype online 사용자** 와 통신할 수 있도록 합니다.    | 비즈니스용 Skype Online 사용자는 Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings 업그레이드 모드 중 하나이고 다른 조직의 비즈니스용 Skype Online 사용자가 Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings 업그레이드 모드 중 하나인 경우 다른 조직의 비즈니스용 Skype Online 사용자와 통신할 수 있습니다.<br><br>외부 액세스에서 **사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음** 설정을 켭니다. 그런 다음 다른 Teams 조직의 관리자가 동일한 작업을 수행하도록 합니다.|
|**비즈니스용 Skype Online 사용자**가 온-프레미스 조직의 **비즈니스용 Skype 사용자**와 통신할 수 있도록 합니다.     |비즈니스용 Skype Online 사용자는 Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings 업그레이드 모드 중 하나이고 다른 조직의 비즈니스용 Skype Online 사용자가 Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings 업그레이드 모드 중 하나인 경우 온-프레미스 조직의 비즈니스용 Skype 사용자와 통신할 수 있습니다.<br><br>외부 액세스에서 **사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음** 설정을 켭니다. 그런 다음 다른 Teams 조직의 관리자가 동일한 작업을 수행하도록 합니다.|
|**비즈니스용 Skype Online 사용자**가 (조직 내부 또는 외부의) **Skype 사용자**와 통신할 수 있도록 합니다.   |외부 액세스에서 **사용자가 Skype 사용자의 통신할 수 있음** 설정을 켭니다.|

> [!IMPORTANT]
> Teams 또는 비즈니스용 Skype Online 사용자가 조직 내부 또는 외부의 Skype 사용자와 통신할 수 있도록 허용하려면 **Skype 도메인**을 허용된 도메인으로 추가할 필요가 없습니다. 모든 **Skype 도메인**이 허용 목록에 포함됩니다. 이것은 모든 도메인이 허용됨으로 간주됨을 의미합니다.

## <a name="how-does-external-access-compare-with-guest-access"></a>외부 액세스는 게스트 액세스와 어떻게 비교하나요?

외부 액세스와 게스트 액세스의 차이점에 대한 자세한 내용은 [다른 조직의 사용자와 의사 소통](communicate-with-users-from-other-organizations.md)을 참조하세요.

## <a name="related-topics"></a>관련 항목

- [외부 (페더레이션) 사용자를 위한 기본 채팅 환경](native-chat-for-external-users.md)
