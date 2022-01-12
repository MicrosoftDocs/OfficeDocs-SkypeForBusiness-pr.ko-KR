---
title: 외부 액세스 관리(페더레이션)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: Teams 또는 IT 관리자는 다른 도메인(페더레이션)에 대한 외부 액세스를 구성하여 해당 도메인의 사용자가 사용자와의 모임을 찾고, 통화하고, 채팅하고, 설정할 수 있도록 할 수 있습니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5a52e479b7dd813af786c33e494675fe7b8e9743
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766611"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams에서 외부 액세스 관리

외부 액세스는 조직 외부의 Teams 사용자가 Teams에서 사용자와 모임을 찾고, 통화하고, 채팅하고, 설정할 수 있는 방법입니다. 외부 액세스를 사용하여 비즈니스용 Skype(온라인 및 온-프레미스) 및 Skype (미리 보기)를 계속 사용하는 다른 조직의 사용자와 통신할 수도 있습니다.

다른 조직의 사용자가 팀과 채널에 액세스할 수 있도록 하려면 게스트 액세스를 대신 사용합니다. 외부 액세스와 게스트 액세스 사이의 차이점에 대한 자세한 내용은 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조하세요. 

다음과 같은 경우에 외부 액세스를 사용합니다.
  
- 공동 작업을 해야 하는 외부 도메인의 사용자가 있습니다. 예를 들어 Rob@contoso.com 및 Ann@northwindtraders.com contoso.com 및 northwindtraders.com 도메인의 다른 사용자와 함께 프로젝트에서 작업합니다.

- 조직 내 사용자가 Teams를 사용하여 조직 외부의 특정 비즈니스에 참여하는 사용자와 연락하도록 하려는 경우

- Teams를 사용하는 전 세계의 모든 사람이 전자 메일 주소를 사용하여 사용자를 찾고 연락할 수 있게 하려고 합니다. 

## <a name="plan-for-external-access"></a>외부 액세스 계획

기본적으로 외부 액세스는 Teams에서 활성화되어 있습니다. 즉, 조직에서 모든 외부 도메인과 의사소통할 수 있습니다. 차단된 도메인을 추가하면 다른 모든 도메인이 허용됩니다. 허용된 도메인을 추가하면 다른 모든 도메인이 차단됩니다. 이 규칙의 예외는 익명 참가자가 모임에서 허용되는 경우입니다. Teams 관리 센터에서 외부 액세스를 설정하는 세 가지 시나리오(**사용자** > **외부 액세스**)가 있습니다.

> [!NOTE]
> Teams 사용자는 다른 조직의 사용자와 모임 또는 채팅을 호스트할 때 앱을 추가할 수 있습니다. 또한 해당 조직에서 호스트하는 모임 또는 채팅에 참가할 때 다른 조직의 사용자가 공유하는 앱을 사용할 수도 있습니다. 호스팅 사용자 조직의 데이터 정책과 해당 사용자 조직에서 공유하는 타사 앱의 데이터 공유 사례가 적용됩니다.

> [!NOTE]
> 조직에서 외부 액세스를 해제하는 경우 외부 사용자는 여전히 익명 참가를 통해 모임에 참가할 수 있습니다. 자세한 내용은 [Teams에서 모임 정책 관리](meeting-settings-in-teams.md)를 참조하세요.

- **모든 외부 도메인 허용**: Teams의 기본 설정이며 조직의 사용자가 모든 도메인에서 조직 외부 사용자와 모임을 찾고, 통화하고, 채팅하고, 설정할 수 있습니다.

    이 시나리오에서는 사용자가 Teams 또는 비즈니스용 Skype를 실행하거나 모든 외부 도메인을 허용하거나 허용 목록에 도메인을 추가한 모든 외부 도메인과 통신할 수 있습니다.

- **특정 외부 도메인만 허용**: **허용** 목록에 도메인을 추가하면 허용된 도메인으로만 외부 액세스를 제한할 수 있습니다. 허용된 도메인 목록을 설정하면 다른 모든 도메인은 차단됩니다. 특정 도메인을 허용하려면 **도메인 추가** 를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업** 을 클릭한 다음 **허용됨** 을 선택합니다.

- **특정 도메인 차단** - **차단** 목록에 도메인을 추가하여 차단한 도메인을 *제외* 한 모든 외부 도메인과 통신할 수 있습니다. 특정 도메인을 차단하려면 **도메인 추가** 를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업** 을 클릭한 다음 **차단됨** 을 선택합니다. 차단된 도메인 목록을 설정하면 다른 모든 도메인은 허용됩니다.

- **모든 외부 도메인 차단** - 조직의 사용자가 모든 도메인에서 조직 외부의 사용자와 모임을 찾고, 통화하고, 채팅하고, 설정할 수 없도록 합니다.

> [!NOTE]
> 허용된 도메인 또는 차단된 도메인은 모임에 대한 익명 액세스가 "꺼진" 경우 모임에만 적용됩니다.

## <a name="allow-or-block-domains"></a>도메인 허용 또는 차단

  **Microsoft Teams 관리 센터 사용**

특정 도메인을 허용하려면

1. Teams 관리 센터에서 **사용자** > **외부 액세스** 로 이동합니다.

2. **사용자가액세스할 수 있는 도메인을 선택하고**, **특정 외부 도메인만 허용을 선택합니다**.

3. **도메인 허용** 을 선택합니다.

4. **도메인** 상자에 허용할 도메인을 입력한 다음 **완료** 를 클릭합니다.

5. 다른 도메인을 허용하려면 **도메인 추가** 를 클릭합니다.

6. **저장** 을 클릭합니다.

특정 도메인을 차단하려면

1. Teams 관리 센터에서 **사용자** > **외부 액세스** 로 이동합니다.

2. **사용자가 액세스할 수 있는 도메인을 선택하고**, **특정 외부 도메인만 차단을 선택합니다**.

3. **도메인 차단** 을 선택합니다.

4. **도메인** 상자에 허용할 도메인을 입력한 다음 **완료** 를 클릭합니다.

5. 다른 도메인을 차단하려면 **도메인 추가** 를 클릭합니다.

6. **저장** 을 클릭합니다.

다른 Teams 조직의 관리자가 동일한 단계를 완료하는지 확인합니다. 예를 들어 **허용된 도메인** 목록에서 관리자는 사용자와 통신할 수 있는 조직을 제한하는 경우 비즈니스용 도메인을 입력해야 합니다.

## <a name="communicate-with-skype-users-preview"></a>Skype 사용자와 통신(미리 보기)

조직의 Teams 사용자가 Skype 사용자와 채팅하고 통화하려면 다음 단계를 따르세요. 그런 다음 Teams 사용자는 일대일 텍스트 전용 대화 또는 Skype 사용자와의 음성/화상 통화를 검색 및 시작할 수 있으며 그 반대의 경우도 마찬가지입니다.

  **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자** > **외부 액세스** 로 이동합니다.

2. **조직의 사용자가 Skype 사용자와 통신할 수 있도록 허용** 설정을 켭니다.

적용되는 제한 사항을 포함하여 Teams 사용자 및 Skype 사용자가 통신할 수 있는 방법에 대한 자세한 내용은 [Teams 및 Skype 상호 운용성](teams-skype-interop.md)을 참조하세요.

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>관리되지 않는 외부 Teams 사용자와의 원치 않는 연락 차단

조직의 Teams 사용자가 조직에서 관리하지 않는 계정을 가진 외부 Teams 사용자와 원치 않는 접촉을 하지 않도록 하려면 다음 단계를 따르세요.

  **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자** > **외부 액세스** 로 이동합니다.

2. 다음 단계 중 하나를 따르세요.

    - 조직의 Teams 사용자가 조직에서 계정을 관리하지 않는 외부 Teams 사용자와 통신하지 못하도록 차단하려면 **내 조직의 사용자는 조직에서 계정을 관리하지 않는 Teams 사용자와 통신할 수 있음** 설정을 끕니다. **조직에서 관리하지 않는 Teams 계정을 가진 외부 사용자가 내 조직의 사용자에게 연락할 수 있음** 확인란의 선택을 취소합니다.

    - Teams 사용자가 연락을 시작한 경우 조직의 Teams 사용자가 조직에서 계정을 관리하지 않는 외부 Teams 사용자와 통신할 수 있도록 하려면 **내 조직의 사람들이 계정이 관리되지 않는 Teams 사용자와 통신할 수 있음을 켭니다. 조직** 을 설정하고 **조직에서 관리하지 않는 Teams 계정을 가진 외부 사용자가 내 조직의 사용자에게 연락할 수 있음** 확인란의 선택을 취소합니다.

    - 조직의 Teams 사용자가 조직에서 계정을 관리하지 않는 외부 Teams 사용자와 통신하고 해당 외부 Teams 사용자와 통신하기 위한 요청을 수신할 수 있도록 하려면 **내 조직의 사람들이 조직에서 계정을 관리되지 않는 Teams 사용자와 통신할 수 있음** 설정을 켜고 **조직에서 관리하지 않는 Teams 계정을 가진 외부 사용자가 내 조직의 사용자에게 연락할 수 있음** 확인란을 선택합니다.

## <a name="test-access"></a>액세스 테스트

설정을 테스트하려면 사용자의 방화벽 외부에 있는 Teams 사용자가 필요합니다.
  
1. 사용자와 조직의 관리자가 **외부 액세스 설정** 을 변경한 후에는 계속 진행할 수 있습니다.

2. Teams 앱에서 전자 메일 주소로 사용자를 검색하고 채팅 요청을 보냅니다.

3. 사용자의 Teams 연락처에 요청하여 사용자에게 채팅 요청을 보냅니다. 요청을 받지 못한 경우 (방화벽 설정이 올바른지 이미 확인했다고 가정한다면) 방화벽 설정에 문제가 있는 것입니다.

4. 방화벽에 문제가 있는지 테스트하는 또 다른 방법은 방화벽 외부에 있는 WiFi 위치로 이동하는 것입니다. 커피숍과 같은 위치에서 Teams를 사용하여 연락처에 채팅 요청을 보냅니다. 메시지가 WiFi 위치를 통과하지만, 회사 내부에 있을 때는 통과하지 않으면 방화벽에 문제가 있음을 알 수 있습니다.

> [!NOTE]
> 사용자와 다른 사용자가 모두 외부 액세스를 켜고 서로의 도메인을 허용하는 경우 이 작업을 수행할 수 있습니다. 그래도 문제가 해결되지 않으면 다른 사용자가 구성에서 사용자의 도메인을 차단하고 있지 않은지 확인해야 합니다.

## <a name="limit-external-access-to-specific-people"></a>특정 사용자에 대한 외부 액세스 제한

**내 조직의 사용자는 조직에서 계정을 관리하지 않는 Teams 사용자와 통신할 수 있음** 을 사용하도록 설정한 경우 PowerShell을 사용하여 특정 사용자에 대한 외부 액세스를 제한할 수 있습니다.

아래 예제 스크립트를 사용하여 정책에 부여할 이름을 *PolicyName* 으로 대체하고 외부 액세스를 사용할 수 있게 하려는 각 사용자를 *UserName* 으로 대체할 수 있습니다.

스크립트를 실행하기 전에 [Microsoft Teams PowerShell 모듈](/microsoftteams/teams-powershell-install)을 설치했는지 확인하세요.

```PowerShell
Connect-MicrosoftTeams

# Disable external access globally
Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

# Create a new external access policy
New-CsExternalAccessPolicy -Identity <PolicyName> -EnableTeamsConsumerAccess $true

# Assign users to the policy
$users_ids = @("<UserName1>", "<UserName2>")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "<PolicyName>" -Identity $users_ids

```

예를 들면 다음과 같습니다.

```PowerShell
Connect-MicrosoftTeams

Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

New-CsExternalAccessPolicy -Identity ContosoExternalAccess -EnableTeamsConsumerAccess $true

$users_ids = @("MeganB@contoso.com", "AlexW@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "ContosoExternalAccess" -Identity $users_ids

```

사용자 목록을 컴파일하는 방법에 대한 추가 예는 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)을 참조하세요.

`Get-CsExternalAccessPolicy`을(를) 실행하여 새 정책을 볼 수 있습니다.


[New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy) 및 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)도 참조하세요.

## <a name="common-external-access-scenarios"></a>일반적인 외부 액세스 시나리오

다음 섹션에서는 일반적인 외부 액세스 시나리오에서 페더레이션을 사용하도록 설정하는 방법과 TeamsUpgradePolicy에서 들어오는 채팅 및 통화의 전달을 결정하는 방법에 대해 설명합니다.

### <a name="enable-federation"></a>페더레이션 사용

조직의 사용자가 다른 조직의 사용자와 통신할 수 있도록 설정하려면 두 조직 모두 페더레이션 기능을 사용하도록 설정해야 합니다. 특정 조직에 대해 페더레이션을 사용하도록 설정하는 단계는 조직이 온라인인지, 하이브리드인지 또는 온-프레미스인지에 따라 다를 수 있습니다.

| 조직에서 데스크톱 시각화에 대한 | 다음과 같이 페더레이션을 사용하는 경우 |
|:---------|:-----------------------|
|비즈니스용 Skype 온-프레미스가 아닌 사용자. 여기에는 TeamsOnly 사용자 및/또는 비즈니스용 Skype Online 사용자가 있는 조직이 포함됩니다.| Teams 관리 센터를 사용하는 경우: <br>- 외부 액세스에서 통신하려는 도메인이 허용되는지 확인합니다.<br><br>PowerShell을 사용하는 경우:<br>- 테넌트가 페더레이션에 대해 `Get-CsTenantFederationConfiguration`이 `AllowFederatedUsers=true`를 표시하는지 확인합니다. <br>- 사용자의 `CsExternalAccessPolicy`에 적합한 값인 `EnableFederationAccess=true`가 있는지 확인합니다.<br>- 공개 페더레이션을 사용하지 않는 경우, 대상 도메인이 `CsTenantFederationConfiguration`의 `AllowedDomains`에 나열되어 있는지 확인합니다. |
|온-프레미스에서만 | 온-프레미스 도구에서: <br>- 페더레이션이 `CsAccessEdgeConfiguration`에서 사용하도록 설정되어 있는지 확인합니다.<br>- 사용자에 대한 페더레이션이 `ExternalAccessPolicy`를 통해(또는 전역 정책, 사이트 정책 또는 사용자에게 할당된 정책) 사용하도록 설정되어 있는지 확인합니다. <br> - 공개 페더레이션을 사용하지 않는 경우, 대상 도메인이 `AllowedDomains`에 나열되어 있는지 확인합니다. |
|일부 사용자(비즈니스용 Skype 또는 Teams)와 사내 일부 사용자와의 하이브리드 기능을 제공합니다. | 온라인 및 온-프레미스 조직은 위의 단계를 따르세요. |

### <a name="delivery-of-incoming-chats-and-calls"></a>수신 채팅 및 통화 전달 

페더레이션 조직의 수신 채팅 및 통화는 TeamsUpgradePolicy의 받는 사람의 모드에 따라 사용자의 Teams 또는 비즈니스용 Skype 클라이언트에 연결됩니다.

| 원하는 작업 | 방법 |
|:---------|:-----------------------|
| 수신 페더레이션 채팅 및 통화가 사용자의 Teams 클라이언트에 도착하는지 확인합니다. | 사용자를 TeamsOnly로 구성합니다.
| 수신 페더레이션 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트에 도착하는지 확인합니다. | 사용자가 TeamOnly 이외의 다른 모드를 사용하도록 구성합니다. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>조직의 사용자와 Skype 고객 사용자 간 페더레이션을 사용하도록 설정

조직의 사용자와 Skype 고객 사용자 간 페더레이션을 사용하도록 설정하는 방법

| 조직에서 데스크톱 시각화에 대한 | 다음과 같이 페더레이션을 사용하는 경우 |
|:---------|:-----------------------|
| 비즈니스용 Skype 온-프레미스가 아닌 사용자.  여기에는 TeamsOnly 사용자 및/또는 비즈니스용 Skype Online 사용자가 있는 조직이 포함됩니다. | Teams 관리 센터를 사용하는 경우: <br>- 반드시 **조직의 사용자가 외부 액세스에서 Skype 사용자와 통신하도록 허용** 해야 합니다.<br><br>PowerShell을 사용하는 경우: <br>-테넌트가 페더레이션에 대해 `Get-CsTenantFederationConfiguration`이 `AllowPublicUsers=true`를 표시하는지 확인합니다. <br> - 사용자의 `CsExternalAccessPolicy`에 적합한 값인 `EnablePublicCloudAccess=true`가 있는지 확인합니다. |
| 온-프레미스에서만 | 온-프레미스 도구에서: <br> - Skype를 페더레이션되는 파트너로 사용하도록 설정되어 있는지 확인합니다. <br> - 사용자에 대한 `EnablePublicCloudAccess=true`가 `ExternalAccessPolicy`를 통해(또는 전역 정책, 사이트 정책 또는 사용자에게 할당된 정책) 사용하도록 설정되어 있는지 확인합니다.|
| 일부 사용자(비즈니스용 Skype 또는 Teams)와 사내 일부 사용자와의 하이브리드 기능을 제공합니다.| 온라인 및 온-프레미스 조직은 위의 단계를 따르세요.


> [!IMPORTANT]
> Teams 또는 비즈니스용 Skype Online 사용자가 조직 내부 또는 외부의 Skype 사용자와 통신할 수 있도록 허용된 도메인으로 **Skype 도메인** 을 추가할 필요가 없습니다. 모든 **Skype 도메인** 이 허용됩니다.

## <a name="federation-diagnostic-tool"></a>페더레이션 진단 도구

관리자인 경우 다음 진단 도구를 사용하여 Teams 사용자가 페더레이션된 Teams 사용자와 통신할 수 있는지 확인할 수 있습니다.

1. 아래의 **테스트 실행** 을 선택하면 Microsoft 365 관리 센터에서 진단이 채워집니다. 

   > [!div class="nextstepaction"]
   > [테스트 실행: Teams 페더레이션](https://aka.ms/TeamsFederationDiag)

2. 진단 실행 창에서 **SIP(Session Initiation Protocol) 주소** 및 **페더레이션 테넌트의 도메인 이름** 을 입력한 다음 **테스트 실행** 을 선택합니다.

3. 테스트는 페더레이션된 사용자와의 통신을 방해하는 테넌트 또는 정책 구성을 해결하기 위한 최상의 다음 단계를 반환합니다.


## <a name="related-topics"></a>관련 항목

- [외부 (페더레이션) 사용자를 위한 기본 채팅 환경](native-chat-for-external-users.md)
