---
title: 클라우드에서 사용자를 온-프레미스로 이동
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
description: 비즈니스용 Skype Online에서 온-프레미스로 사용자를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: 0b2143a1705aff3f0b74fb0194d3d10e3d55771b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726738"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="3fbd8-103">클라우드에서 사용자를 온-프레미스로 이동</span><span class="sxs-lookup"><span data-stu-id="3fbd8-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="3fbd8-104">필요한 경우 이전에 온-프레미스에서 클라우드로 마이그레이션한 사용자를 이동할 수 있습니다 (비즈니스용 Skype Online 또는 팀만 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="3fbd8-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="3fbd8-105">비즈니스용 skype Online 또는 TeamsOnly 모드에서 사용자를 비즈니스용 Skype 서버의 온-프레미스 배포로 다시 이동 하려면 둘 다 온-프레미스 도구인 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="3fbd8-106">사용자를 온-프레미스 배포로 다시 이동 하는 경우 사용자를 이동할 풀을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="3fbd8-107">사용자가 이미 TeamsOnly 모드에 있고 않았습니다에서 비즈니스용 Skype 서버 2015 보다 이전 버전을 사용 하는 경우에는 해당 사용자에 대해 TeamsOnly 모드 할당 TeamsUpgradePolicy도 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="3fbd8-108">온-프레미스 사용자는 mode = TeamsOnly 모드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="3fbd8-109">이후 버전의 비즈니스용 Skype 서버에서는이 할당을 자동으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="3fbd8-110">자세한 내용은 [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fbd8-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3fbd8-111">Prerequisites</span></span>

- <span data-ttu-id="3fbd8-112">조직은 azure ad [Connect 구성](configure-azure-ad-connect.md)에 설명 된 대로 Azure ad connect를 올바르게 구성 하 고 사용자에 대 한 모든 관련 특성을 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="3fbd8-113">온라인에서 온-프레미스로 다시 이동 하는 사용자가 온-프레미스 Active Directory에 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="3fbd8-114">비즈니스용 [skype 하이브리드 구성](configure-federation-with-skype-for-business-online.md)에 설명 된 대로 비즈니스용 skype 하이브리드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="3fbd8-115">사용자를 온-프레미스로 다시 이동</span><span class="sxs-lookup"><span data-stu-id="3fbd8-115">Moving users back to on-premises</span></span>

<span data-ttu-id="3fbd8-116">클라우드에서 사용자를 다시 온-프레미스로 이동 하면 다음과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="3fbd8-117">사용자가 해당 기능을 위해 비즈니스용 Skype 서버 배포와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="3fbd8-118">비즈니스용 Skype Online 또는 팀에 있던 모든 연락처는 비즈니스용 Skype 서버로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="3fbd8-119">두 연락처 집합이 병합 된 다음 온-프레미스로 다시 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="3fbd8-120">또한 팀에서 이전에 기존 연락처는 팀에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="3fbd8-121">사용자가 팀을 사용 하는 경우에는 비즈니스용 Skype 사용자와 상호 운용할 수 없으며, 페더레이션 조직의 사용자와도 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="3fbd8-122">비즈니스용 Skype Online의 모임은 자동으로 온-프레미스로 마이그레이션되지 *않습니다* .</span><span class="sxs-lookup"><span data-stu-id="3fbd8-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="3fbd8-123">사용자는 모임 일정을 다시 조정 하거나, 원한다 면 [모임 마이그레이션 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="3fbd8-124">사용자를 이동 하는 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="3fbd8-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="3fbd8-125">이동-CsUser는 온-프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="3fbd8-126">[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 Office 365 테 넌 트 뿐만 아니라 온-프레미스 환경 둘 다에도 충분 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="3fbd8-127">두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고 `-Credential` 매개 변수를 사용 하 여 필요한 office 365 관리 역할이 있는 office 365 계정에 대 한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="3fbd8-128">CsUser를 사용 하 여 사용자를 온-프레미스로 이동 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="3fbd8-129">Identity 매개 변수를 사용 하 여 이동할 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="3fbd8-130">사용자를 호스팅할 원하는 온-프레미스 풀의 정규화 된 도메인 이름으로-Target 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="3fbd8-131">온-프레미스 및 Office 365 둘 다에서 충분 한 사용 권한이 있는 계정이 없는 경우-credential 매개 변수를 사용 하 여 Office 365에서 충분 한 사용 권한을 가진 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="3fbd8-132">Office 365에서 사용 권한이 있는 계정이 "on.microsoft.com"로 끝나지 않는 경우에는 [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여-HostedMigrationOverrideUrl 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="3fbd8-133">다음 cmdlet 시퀀스를 사용 하 여 사용자를 비즈니스용 Skype 서버로 이동할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 확인에 대 한 입력으로 제공 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="3fbd8-134">비즈니스용 Skype 서버 제어판을 사용 하 여 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="3fbd8-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3fbd8-135">비즈니스용 Skype 서버 제어판 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="3fbd8-136">왼쪽 탐색 영역에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="3fbd8-137">**찾기를** 사용 하 여 온-프레미스로 다시 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="3fbd8-138">사용자를 선택 하 고 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 온-프레미스로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="3fbd8-139">마법사에서 사용자를 호스팅할 사용자 풀을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="3fbd8-140">메시지가 표시 되 면 onmicrosoft.com로 끝나고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="3fbd8-141">**다음**을 클릭 하 고 **다음으로 한 번** 더 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="3fbd8-142">성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 주 제어판 앱의 위쪽에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="3fbd8-143">TeamsOnly 모드 제거</span><span class="sxs-lookup"><span data-stu-id="3fbd8-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="3fbd8-144">않았습니다과 함께 비즈니스용 Skype 2015 이전 버전을 사용 하는 경우 사용자가 TeamsOnly 모드에서 온-프레미스로 다시 이동 하는 경우 사용자를 온-프레미스로 이동 하기 전에의 `TeamsUpgradePolicy` UpgradeToTeams 인스턴스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="3fbd8-145">정책을 다른 모드로 명시적으로 부여 하거나, 해당 사용자에 대 한 기존 정책 할당을 제거 하 여 전역 정책을 사용 하도록 할 수 있습니다 (테 넌 트의 전역 정책이 업그레이드 되지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="3fbd8-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="3fbd8-146">TeamsUpgradePolicy에 대 한 사용자의 할당을 제거 하려면 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="3fbd8-147">또는 모드를 포함 하지 않는 TeamsUpgradePolicy의 다른 인스턴스를 할당 하려면 cmdlet에서 원하는 인스턴스의 이름을 PolicyName 매개 변수 값으로 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="3fbd8-148">사용 가능한 TeamsUpgradePolicy 인스턴스 목록을 보려면 CsTeamsUpgradePolicy을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbd8-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="3fbd8-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fbd8-149">See also</span></span>

[<span data-ttu-id="3fbd8-150">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="3fbd8-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
