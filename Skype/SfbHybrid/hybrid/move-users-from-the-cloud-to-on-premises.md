---
title: 클라우드에서 사용자를 온-프레미스로 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: 비즈니스용 Skype Online에서 온-프레미스로 사용자를 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ec3aa727753ed9ac6564712d591ab6d2beac4ebf
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434731"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="0b485-103">클라우드에서 사용자를 온-프레미스로 이동</span><span class="sxs-lookup"><span data-stu-id="0b485-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="0b485-104">필요한 경우 이전에 온-프레미스에서 클라우드로 마이그레이션한 사용자를 이동할 수 있습니다 (비즈니스용 Skype Online 또는 팀만 사용).</span><span class="sxs-lookup"><span data-stu-id="0b485-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="0b485-105">비즈니스용 skype Online 또는 팀 전용 모드에서 사용자를 비즈니스용 Skype Server의 온-프레미스 배포로 다시 이동 하려면, 두 개의 온-프레미스 도구를 사용 하는 이동-CsUser cmdlet 또는 비즈니스용 Skype Server 제어판을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="0b485-106">사용자를 온-프레미스 배포로 다시 이동 하는 경우 사용자를 이동할 풀을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="0b485-107">사용자가 이전에 팀 전용 모드에 있고 CU8에서 비즈니스용 Skype Server 2015 이전 버전을 사용 하는 경우에는 해당 사용자의 TeamsUpgradePolicy에 대 한 팀 전용 모드 할당도 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="0b485-108">온-프레미스 사용자는 mode = TeamsOnly 모드에 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="0b485-109">이후 버전의 비즈니스용 Skype 서버는이 과제를 자동으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="0b485-110">자세한 내용은 [허용-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b485-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b485-111">필요 조건</span><span class="sxs-lookup"><span data-stu-id="0b485-111">Prerequisites</span></span>

- <span data-ttu-id="0b485-112">조직에서 Azure ad Connect가 올바르게 구성 되어 있어야 하 고 [AZURE Ad Connect 구성](configure-azure-ad-connect.md)에서 설명한 대로 사용자의 모든 관련 특성을 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="0b485-113">온라인에서 온-프레미스로 다시 이동 하려는 사용자가 온-프레미스 Active Directory에 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="0b485-114">비즈니스용 skype 하이브리드 [구성](configure-federation-with-skype-for-business-online.md)에서 설명한 대로 비즈니스용 skype 하이브리드을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="0b485-115">사용자를 온-프레미스로 다시 이동</span><span class="sxs-lookup"><span data-stu-id="0b485-115">Moving users back to on-premises</span></span>

<span data-ttu-id="0b485-116">클라우드에서 사용자를 다시 온-프레미스로 이동 하면 다음과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="0b485-117">사용자는 해당 기능에 대 한 비즈니스용 Skype 서버 배포와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="0b485-118">비즈니스용 Skype Online 또는 팀에 있던 모든 연락처는 비즈니스용 Skype Server로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="0b485-119">두 개의 연락처 집합을 병합 한 다음 온-프레미스로 다시 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="0b485-120">또한 팀에 사전 존재 하는 연락처는 팀에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="0b485-121">또한 사용자가 팀을 사용 하는 경우 비즈니스용 Skype 사용자와 상호 작용 하거나 페더레이션된 조직의 사용자와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="0b485-122">비즈니스용 Skype Online의 모임이 자동으로 온-프레미스로 다시 마이그레이션되지 *않습니다* .</span><span class="sxs-lookup"><span data-stu-id="0b485-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="0b485-123">사용자는 모임 일정을 재조정 하거나 원할 경우 [모임 마이그레이션 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="0b485-124">이동-CsUser와 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="0b485-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="0b485-125">이동-CsUser는 온-프레미스 비즈니스용 Business Management Shell PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="0b485-126">[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 Office 365 테 넌 트 및 온-프레미스 환경 모두에 충분 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="0b485-127">두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고, `-Credential` 매개 변수를 사용 하 여 Office 365에 대 한 자격 증명을 지정할 수 있습니다. 계정으로 필요한 Office 365 관리 역할을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="0b485-128">CsUser Move를 사용 하 여 사용자를 온-프레미스로 이동 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="0b485-129">Id 매개 변수를 사용 하 여 이동할 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="0b485-130">사용자를 호스트 하는 원하는 온-프레미스 풀의 정규화 된 도메인 이름으로-Target 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="0b485-131">온-프레미스 및 Office 365 모두에 충분 한 권한이 있는 계정이 없는 경우-credential 매개 변수를 사용 하 여 Office 365에서 충분 한 권한을 가진 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="0b485-132">Office 365에서 사용 권한이 있는 계정이 "on.microsoft.com"으로 끝나지 않으면-HostedMigrationOverrideUrl 매개 변수를 [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="0b485-133">다음 cmdlet 시퀀스를 사용 하 여 사용자를 비즈니스용 Skype 서버로 이동할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 가져오기 프롬프트에 대 한 입력으로 제공 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="0b485-134">비즈니스용 Skype Server 제어판을 사용 하 여 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="0b485-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0b485-135">비즈니스용 Skype 서버 제어판 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="0b485-136">왼쪽 탐색 창에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="0b485-137">**찾기를** 사용 하 여 온-프레미스로 다시 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="0b485-138">사용자를 선택한 다음 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 온-프레미스로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="0b485-139">마법사에서 사용자를 호스트 하는 사용자 풀을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="0b485-140">메시지가 표시 되 면 onmicrosoft.com에 종료 되 고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="0b485-141">**다음**을 클릭 하 고 **다음으로 한 번** 더 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="0b485-142">성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 기본 제어판 앱의 맨 위에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="0b485-143">TeamsOnly 모드 제거</span><span class="sxs-lookup"><span data-stu-id="0b485-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="0b485-144">CU8에서 비즈니스용 Skype 2015 이전 버전을 사용 중이 고 사용자가 TeamsOnly 모드에서 온-프레미스로 다시 이동 하는 경우, 사용자를 온-프레미스로 이동 `TeamsUpgradePolicy` 하기 전에 먼저 UpgradeToTeams 인스턴스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="0b485-145">다른 모드를 사용 하 여 정책을 명시적으로 부여 하거나 해당 사용자에 대 한 기존 정책 할당을 제거 하 여 전역 정책을 사용할 수 있습니다 (테 넌 트의 전역 정책이 업그레이드 되지 않은 경우에만 해당).</span><span class="sxs-lookup"><span data-stu-id="0b485-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="0b485-146">TeamsUpgradePolicy의 사용자 할당을 제거 하려면 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="0b485-147">또는 모드가 아닌 TeamsUpgradePolicy의 다른 인스턴스를 할당 하려면 cmdlet의 PolicyName 매개 변수 값으로 원하는 인스턴스 이름을 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b485-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="0b485-148">사용할 수 있는 TeamsUpgradePolicy 인스턴스 목록을 보려면 CsTeamsUpgradePolicy를 실행 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b485-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="0b485-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b485-149">See also</span></span>

[<span data-ttu-id="0b485-150">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="0b485-150">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
