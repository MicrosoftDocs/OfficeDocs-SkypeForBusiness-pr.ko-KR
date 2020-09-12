---
title: 외부 액세스 (페더레이션) 관리
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: cb470bb0388c09f1914f7dbdba98a425baa40a7a
ms.sourcegitcommit: 8c043265becbe3d12658805e12a9cf0b2881a430
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2020
ms.locfileid: "47449402"
---
<a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams에서 외부 액세스 관리
======================================================

외부 액세스는 전체 외부 도메인의 팀 사용자가 팀에서 모임을 검색, 통화, 채팅 및 설정 하는 방법입니다. 외부 액세스를 사용 하 여 아직 비즈니스용 Skype (온라인 및 온-프레미스)와 Skype (미리 보기)를 사용 중인 외부 사용자와 통신할 수도 있습니다.

> [!NOTE]
> 허용 또는 차단 된 도메인은 모임에 대 한 익명 액세스가 "해제" 인 경우 모임에만 적용 됩니다.

외부 사용자가 팀과 채널에 액세스할 수 있도록 하려면 게스트 액세스를 사용하는 것이 좋습니다. 외부 액세스와 게스트 액세스 사이의 차이점에 대한 자세한 내용은 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조하세요. 

다음과 같은 경우에 외부 액세스를 사용합니다.
  
- 다른 도메인에 공동 작업을 해야 하는 사용자가 있는 경우 예를 들어 Rob@contoso.com 및 Ann@northwindtraders.com은 contoso.com 및 northwindtraders.com 도메인의 다른 사용자들과 함께 프로젝트를 작업하고 있습니다.

- 조직 내 사용자가 Teams를 사용하여 조직 외부의 특정 비즈니스에 참여하는 사용자와 연락하도록 하려는 경우

- Teams를 사용하는 전 세계의 모든 사람이 전자 메일 주소를 사용하여 사용자를 찾고 연락할 수 있게 하려고 합니다. 

> [!IMPORTANT]
> 팀 클라이언트를 사용 하 여 외부 사용자와 통신 하려면 (해당 사용자가 팀을 사용 하 고 있는지 여부에 관계 없이) 팀 사용자가 비즈니스용 Skype Online에 있어야 합니다.

## <a name="plan-for-external-access"></a>외부 액세스 계획

기본적으로 외부 액세스는 Teams에서 활성화되어 있습니다. 즉, 조직에서 모든 외부 도메인과 의사소통할 수 있습니다. 차단된 도메인을 추가하면 다른 모든 도메인이 허용됩니다. 허용된 도메인을 추가하면 다른 모든 도메인이 차단됩니다. 이 규칙에 대 한 예외는 모임에서 익명 참가자가 허용 되는 경우입니다. Teams 관리 센터에서 외부 액세스를 설정하는 세 가지 시나리오가 있습니다(**조직 전체 설정** > **외부 액세스**).

- **열려 있는 페더레이션**: 이는 Teams의 기본 설정이며, 조직의 사용자가 조직 외부의 사용자를 찾아서 통화하고, IM/채팅을 전송하고, 모임을 설정할 수 있습니다.

    이 시나리오에서는 사용자가 Temas 또는 비즈니스용 Skype를 실행하고 열려 있는 페더레이션을 사용하거나 내 도메인을 허용 목록에 추가한 모든 외부 도메인과 통신할 수 있습니다.

- **특정 도메인 허용**: **허용** 목록에 도메인을 추가하여 외부 액세스를 허용된 도메인만으로 제한합니다. 허용된 도메인 목록을 설정하면 다른 모든 도메인은 차단됩니다. 특정 도메인을 허용하려면 **도메인 추가**를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업**을 클릭한 다음 **허용됨**을 선택합니다.

- **특정 도메인 차단** - **차단** 목록에 도메인을 추가하여 차단한 도메인을 *제외*한 모든 외부 도메인과 통신할 수 있습니다. 특정 도메인을 차단하려면 **도메인 추가**를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업**을 클릭한 다음 **차단됨**을 선택합니다. 차단된 도메인 목록을 설정하면 다른 모든 도메인은 허용됩니다.

> [!NOTE]
> 조직에서 외부 액세스를 해제 하는 경우 외부 사용자는 여전히 익명 참가를 통해 모임에 참가할 수 있습니다. 자세히 알아보려면 [팀에서 모임 설정 관리](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)를 참고 하세요.

## <a name="allow-or-block-domains"></a>도메인 허용 또는 차단

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>1 단계-조직이 다른 팀 또는 비즈니스용 Skype 조직과 통신할 수 있도록 설정

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


## <a name="communicate-with-skype-users-in-preview"></a>Skype 사용자와의 통신(미리 보기)

조직의 Teams 사용자가 Skype 사용자와 채팅하고 통화하려면 다음 단계를 따르세요. 그런 다음 Teams 사용자는 일대일 텍스트 전용 대화 또는 Skype 사용자와의 음성/화상 통화를 검색 및 시작할 수 있으며 그 반대의 경우도 마찬가지입니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png)  **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **조직 전체 설정** > **외부 액세스**로 이동합니다.

2. **사용자가 Skype 사용자의 통신할 수 있음** 설정을 켭니다.

    ![사용자가 Skype 사용자의 통신할 수 있음 설정이 켜진 스크린샷](media/manage-external-access-5.png).

적용되는 제한 사항을 포함하여 Teams 사용자 및 Skype 사용자가 통신할 수 있는 방법에 대한 자세한 내용은 [Teams 및 Skype 상호 운용성](teams-skype-interop.md)을 참조하세요.

## <a name="common-external-access-scenarios"></a>일반적인 외부 액세스 시나리오

다음 섹션에서는 일반적인 외부 액세스 시나리오의 페더레이션을 사용 하는 방법과 TeamsUpgradePolicy에서 수신 채팅 및 통화의 배달을 결정 하는 방법에 대해 설명 합니다.

### <a name="enable-federation"></a>페더레이션 사용

조직의 사용자가 다른 조직의 사용자와 통신할 수 있도록 하려면 두 조직 모두 페더레이션을 사용 해야 합니다. 지정 된 조직에 대해 페더레이션을 사용 하도록 설정 하는 단계는 조직이 완전히 온라인 상태 인지 하이브리드 또는 순수 온 일에 따라 달라 집니다.

|**조직이** |**페더레이션을 다음과 같이 설정**  |
|:---------|:-----------------------|
|비즈니스용 Skype 온-프레미스 없이 온라인 상태입니다. 여기에는 사용자 및/또는 비즈니스용 Skype Online 사용자만을 보유 하 고 있는 조직이 포함 됩니다.| 팀 관리 센터를 사용 하는 경우: <br>- **사용자가 다른 비즈니스용 Skype 및 팀 사용자와 통신할 수** 있는지 확인 합니다 .는 외부 액세스에서 사용 하도록 설정 되어 있습니다.<br>-열려 있는 페더레이션 (다른 도메인과 페더레이션이 허용 되는 경우)을 사용 하지 않는 경우에는 허용 목록에 외부 도메인을 추가 합니다.<br><br>PowerShell을 사용 하는 경우:<br>-테 넌 트가 페더레이션에 대해 사용 하도록 설정 되어 있는지 확인: `Get-CsTenantFederationConfiguration` 반드시 표시 해야 `AllowFederatedUsers=true` 합니다. <br>-사용자의 유효 값 `CsExternalAccessPolicy` 이 있어야 `EnableFederationAccess=true` 합니다.<br>-Open federation를 사용 하지 않는 경우 대상 도메인이에 나열 되어 있는지 확인 `AllowedDomains` `CsTenantFederationConfiguration` 합니다. |
|순수 온-프레미스 | 온-프레미스 도구: <br>-페더레이션이 사용 하도록 설정 되어 있는지 확인 `CsAccessEdgeConfiguration` 합니다.<br>-사용자에 대 한 페더레이션이 `ExternalAccessPolicy` 전역 정책, 사이트 정책 또는 사용자 지정 정책에 따라 사용 하도록 설정 되어 있는지 확인 합니다. <br> -Open federation를 사용 하지 않는 경우 대상 도메인이에 나열 되어 있는지 확인 `AllowedDomains` 합니다. |
|일부 사용자 (비즈니스용 Skype 또는 팀)와 일부 사용자 (온-프레미스)를 온라인으로 혼합 합니다. | 온라인 및 온-프레미스 조직 모두에 대해 위 단계를 따르세요. |

### <a name="delivery-of-incoming-chats-and-calls"></a>걸려오는 채팅 및 통화 전달 

페더레이션 조직의 수신 채팅 및 통화는 TeamsUpgradePolicy의 받는 사람 사용자 모드에 따라 사용자의 팀 또는 비즈니스용 Skype 클라이언트에 배치 됩니다.

|**원하는 경우** |**실행할 작업:**  |
|:---------|:-----------------------|
| 받는 페더레이션 채팅 및 통화가 사용자의 팀 클라이언트에 도착 하는지 확인 합니다. | 사용자를 TeamsOnly 하도록 구성 합니다.
| 사용자의 비즈니스용 Skype 클라이언트에 수신 페더레이션 채팅 및 통화가 도착 하는지 확인 | 사용자가 TeamsOnly 이외의 다른 모드에 있도록 구성 합니다. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>조직의 사용자와 Skype 소비자 사용자 간 페더레이션을 사용 하도록 설정

조직의 사용자와 Skype의 소비자 사용자 간 페더레이션을 사용 하도록 설정 하려면 다음을 수행 합니다.

|**조직이** |**다음과 같이 소비자 페더레이션을 사용 합니다.**  |
|:---------|:-----------------------|
| 비즈니스용 Skype 온-프레미스가 없는 순수한 온라인.  여기에는 사용자 및/또는 비즈니스용 Skype Online 사용자만을 보유 하 고 있는 조직이 포함 됩니다. | 팀 관리 센터를 사용 하는 경우: <br>- **사용자가 Skype 사용자와 통신할 수** 있도록 외부 액세스에서 사용 하도록 설정 되어 있는지 확인 합니다.<br><br>PowerShell을 사용 하는 경우: <br>-테 넌 트가 페더레이션에 대해 사용 하도록 설정 되어 있는지 확인: `Get-CsTenantFederationConfiguration` 반드시 표시 해야 `AllowPublicUsers=true` 합니다. <br> -사용자의 유효 값 `CsExternalAccessPolicy` 이 있어야 `EnablePublicCloudAccess=true` 합니다. |
| 순수 온-프레미스 | 온-프레미스 도구: <br> -Skype를 페더레이션 파트너로 사용할 수 있는지 확인 합니다. <br> - `EnablePublicCloudAccess=true` 사용자에 게 `ExternalAccessPolicy` (전역 정책, 사이트 정책 또는 사용자 지정 된 정책)를 통해 확인|
| 일부 사용자 (비즈니스용 Skype 또는 팀)와 일부 사용자 (온-프레미스)를 온라인으로 혼합 합니다.| 온라인 및 온-프레미스 조직 모두에 대해 위 단계를 따르세요.


> [!IMPORTANT]
> Teams 또는 비즈니스용 Skype Online 사용자가 조직 내부 또는 외부의 Skype 사용자와 통신할 수 있도록 허용하려면 **Skype 도메인**을 허용된 도메인으로 추가할 필요가 없습니다. 모든 **Skype 도메인**이 허용 목록에 포함됩니다. 이것은 모든 도메인이 허용됨으로 간주됨을 의미합니다.

## <a name="how-does-external-access-compare-with-guest-access"></a>외부 액세스는 게스트 액세스와 어떻게 비교하나요?

외부 액세스와 게스트 액세스의 차이점에 대한 자세한 내용은 [다른 조직의 사용자와 의사 소통](communicate-with-users-from-other-organizations.md)을 참조하세요.

## <a name="related-topics"></a>관련 항목

- [외부 (페더레이션) 사용자를 위한 기본 채팅 환경](native-chat-for-external-users.md)
