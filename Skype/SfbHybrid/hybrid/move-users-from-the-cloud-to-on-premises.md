---
title: 클라우드에서 사내로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 사용자를 비즈니스용 Skype Online에서온-프레미스로 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110614"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="d25f5-103">클라우드에서 사내로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="d25f5-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="d25f5-104">필요한 경우 이전에 마이그레이션한 사용자를 클라우드로 이동할 수 있습니다(비즈니스용 Skype Online 또는 Teams만 사용).</span><span class="sxs-lookup"><span data-stu-id="d25f5-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="d25f5-105">비즈니스용 Skype Online 또는 TeamsOnly 모드에서 비즈니스용 Skype 서버의 사내 배포로 사용자를 다시 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용하세요. 이러한 cmdlet은 모두 사내 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="d25f5-106">사용자를 다시 사내 배포로 이동할 때 사용자를 이동할 풀을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="d25f5-107">사용자가 이전에 TeamsOnly 모드에 있는 경우 CU8이 있는 비즈니스용 Skype 서버 2015보다 이전 버전을 사용하는 경우 해당 사용자에 대한 TeamsUpgradePolicy의 TeamsOnly 모드 할당도 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="d25f5-108">On-premises users must not have mode= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d25f5-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="d25f5-109">이후 버전의 비즈니스용 Skype 서버는 이 할당을 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="d25f5-110">자세한 내용은 [Grant-CsTeamsUpgradePolicy를 참조합니다.](/powershell/module/skype/grant-csteamsupgradepolicy)</span><span class="sxs-lookup"><span data-stu-id="d25f5-110">For more details, see [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d25f5-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d25f5-111">Prerequisites</span></span>

- <span data-ttu-id="d25f5-112">조직은 Azure AD Connect 구성에 설명된 바와 같이 Azure AD Connect를 올바르게 구성하고 사용자에 대한 모든 관련 특성을 [동기화해야 합니다.](configure-azure-ad-connect.md)</span><span class="sxs-lookup"><span data-stu-id="d25f5-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="d25f5-113">다시 온라인에서 다시 사내로 이동하는 사용자는 이미온-프레미스 Active Directory에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="d25f5-114">비즈니스용 Skype 하이브리드 구성에 설명된 바와 같이 비즈니스용 Skype 하이브리드를 [구성해야 합니다.](configure-federation-with-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="d25f5-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="d25f5-115">사용자를 다시온-프레미스로 이동</span><span class="sxs-lookup"><span data-stu-id="d25f5-115">Moving users back to on-premises</span></span>

<span data-ttu-id="d25f5-116">사용자를 클라우드에서 다시 On-premises로 이동한 후:</span><span class="sxs-lookup"><span data-stu-id="d25f5-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="d25f5-117">사용자는 해당 기능을 위해 비즈니스용 Skype 서버 배포와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="d25f5-118">비즈니스용 Skype Online 또는 Teams에 있는 연락처는 비즈니스용 Skype 서버로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="d25f5-119">두 연락처 집합이 병합된 다음 다시 사내로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="d25f5-120">또한 Teams에 기존에 있는 연락처는 Teams에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="d25f5-121">또한 사용자가 Teams를 사용하는 경우 비즈니스용 Skype 사용자와 상호 협력할 수 없으며 페더맹 조직의 사용자와 통신할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="d25f5-122">비즈니스용 Skype Online의 모임은 *자동으로* 다시 사내로 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="d25f5-123">사용자는 모임을 다시 설정하거나 원하는 경우 모임 마이그레이션 도구를 [사용해야 합니다.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)</span><span class="sxs-lookup"><span data-stu-id="d25f5-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="d25f5-124">사용자 이동을 Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="d25f5-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="d25f5-125">Move-CsUser 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="d25f5-126">필수 관리 자격 증명 에 설명된 바와 같이 클라우드 서비스 조직(Microsoft 365 또는 Office 365)뿐만 아니라 사내 환경 모두에 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="d25f5-126">You must have sufficient privileges in both the on-premises environment as well as the cloud service organization (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="d25f5-127">두 환경에서 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 사내 자격 증명으로 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할이 있는 `-Credential` Microsoft 365 또는 Office 365 계정에 대한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="d25f5-128">Move-CsUser를 사용하여 사용자를 사내로 이동하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d25f5-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="d25f5-129">Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="d25f5-130">사용자를 호스팅할 원하는 온-프레미스 풀의 정식 도메인 이름으로 -Target 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="d25f5-131">사내 및 클라우드 서비스(Microsoft 365 또는 Office 365)에서 충분한 사용 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Microsoft 365 또는 Office 365에 충분한 사용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-131">If you do not have one account with sufficient permissions in both on-premises and the cloud service (Microsoft 365 or Office 365), use the -credential parameter to supply an account with sufficient permissions in Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="d25f5-132">Microsoft 365 또는 Office 365에서 사용 권한이 있는 계정이 "on.microsoft.com"로 끝나지 않으면 필수 관리 자격 증명에 설명된 올바른 값으로 -HostedMigrationOverrideUrl 매개 변수를 지정해야 [합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="d25f5-132">If the account with permissions in Microsoft 365 or Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="d25f5-133">다음 cmdlet 시퀀스를 사용하여 사용자를 비즈니스용 Skype 서버로 이동할 수 있으며 Microsoft 365 또는 Office 365 자격 증명이 별도의 계정으로 제공된 것으로 가정하고 Get-Credential 프롬프트에 대한 입력으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="d25f5-134">비즈니스용 Skype 서버 제어판을 사용하여 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="d25f5-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d25f5-135">비즈니스용 Skype 서버 제어판 앱을 니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="d25f5-136">왼쪽 탐색에서 사용자 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d25f5-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="d25f5-137">**Find를** 사용하여 다시 사내로 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="d25f5-138">사용자를 선택하고 목록 위의 작업  드롭다운에서 선택한 사용자를 프레미스로 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d25f5-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="d25f5-139">마법사에서 사용자를 호스팅할 사용자 풀을 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d25f5-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="d25f5-140">메시지가 표시될 경우 .onmicrosoft.com 계정으로 Microsoft 365 또는 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-140">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="d25f5-141">**다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="d25f5-142">성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="d25f5-143">TeamsOnly 모드 제거</span><span class="sxs-lookup"><span data-stu-id="d25f5-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="d25f5-144">CU8이 있는 비즈니스용 Skype 2015 이전 버전을 사용하고 있으며 사용자가 TeamsOnly 모드에서 다시 On-premises로 이동되는 경우 사용자를 이동하기 전에 UpgradeToTeams 인스턴스를 제거해야 `TeamsUpgradePolicy` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="d25f5-145">다른 모드를 사용하여 정책을 명시적으로 부여하거나 해당 사용자의 기존 정책 할당을 제거하여 테넌트의 글로벌 정책이 UpgradeToTeams가 아닌 경우 글로벌 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="d25f5-146">사용자의 TeamsUpgradePolicy 할당을 제거하려면 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="d25f5-147">또는 mode=TeamsOnly가 없는 TeamsUpgradePolicy의 다른 인스턴스를 할당하기 위해 cmdlet에서 원하는 인스턴스의 이름을 PolicyName 매개 변수 값으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="d25f5-148">TeamsUpgradePolicy의 사용 가능한 인스턴스 목록을 표시하기 위해 Get-CsTeamsUpgradePolicy를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="d25f5-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d25f5-149">See also</span></span>

[<span data-ttu-id="d25f5-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="d25f5-150">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)