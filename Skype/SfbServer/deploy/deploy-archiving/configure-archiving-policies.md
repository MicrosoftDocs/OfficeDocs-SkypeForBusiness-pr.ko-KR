---
title: 비즈니스용 Skype 서버에 대 한 보관 정책 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '요약: 비즈니스용 Skype 서버 사용자에 대 한 초기 보관 정책을 구성 하는 방법을 알아보려면이 항목을 참조 하세요.'
ms.openlocfilehash: 4e1bf5d713201604df18db9d63c2057bfa5bb4e8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234555"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="560e8-103">비즈니스용 Skype 서버에 대 한 보관 정책 구성</span><span class="sxs-lookup"><span data-stu-id="560e8-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="560e8-104">**요약:** 이 항목에서는 비즈니스용 Skype 서버 사용자의 초기 보관 정책을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="560e8-105">비즈니스용 Skype 서버에서는 정책을 사용 하 여 비즈니스용 Skype 서버에 있는 사용자에 대 한 내부 통신 및 외부 통신을 사용 하거나 보관 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="560e8-106">여기에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-106">This includes the following:</span></span>
  
- <span data-ttu-id="560e8-107">비즈니스용 Skype 서버를 배포할 때 기본적으로 생성 되는 글로벌 정책</span><span class="sxs-lookup"><span data-stu-id="560e8-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="560e8-108">특정 사이트에 대해 보관을 구현 하는 방법을 지정 하는 사이트 수준 정책 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="560e8-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="560e8-109">특정 사용자에 대해 보관을 구현 하는 방법을 지정 하는 사용자 수준 정책 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="560e8-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="560e8-110">보관 정책을 처음에 설정 했지만 배포 후에 정책을 변경, 추가, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="560e8-111">비즈니스용 Skype Server 제어판에서 **보관 및 모니터링** 그룹의 **보관 정책** 페이지를 사용 하 여 전역, 사이트 및 사용자 수준에서 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="560e8-112">보관 구현을 제어 하려면 IM 또는 회의 보관 여부, 중요 한 모드 사용, 제거 옵션 등의 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="560e8-113">기본적으로 전역 보관 구성 또는 사이트 또는 풀 보관 구성에서는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="560e8-114">내부 또는 외부 통신을 위해 보관을 사용 하도록 설정 하기 전에 모든 적절 한 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="560e8-115">자세한 내용은 [비즈니스용 Skype 서버 보관 옵션 구성을](configure-archiving-options.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="560e8-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="560e8-116">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 원본 위치 유지 정책에서 Exchange를 사용 하는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="560e8-117">전역, 사이트 및 사용자 정책에 대 한 계층 구조를 포함 하 여 보관 정책이 작동 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="560e8-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="560e8-118">배포 후 정책을 관리 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 정책 관리](../../manage/archiving/policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="560e8-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="560e8-119">전역 정책</span><span class="sxs-lookup"><span data-stu-id="560e8-119">Global policy</span></span>

<span data-ttu-id="560e8-120">프런트 엔드 서버를 배포 하는 경우 비즈니스용 Skype Server는 보관을 위한 전역 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="560e8-121">기본적으로 글로벌 정책에서는 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="560e8-122">전역 정책은 사이트 또는 사용자 정책을 설정 하거나, 전역 정책을 재정의 하거나, Microsoft Exchange 통합을 일부 또는 모두에 대해 사용 하는 경우가 아니면 전체 배포에 대해 보관을 사용할 수 있는지 여부를 제어 합니다. 사용자.</span><span class="sxs-lookup"><span data-stu-id="560e8-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="560e8-123">Microsoft Exchange 통합을 사용 하는 경우 전역 정책은 Exchange에 속한 사용자에 게 적용 되지 않으며 사서함이 원본 위치 유지에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="560e8-124">비즈니스용 Skype Server 보관 데이터베이스용으로 보관할 전역 정책 구성</span><span class="sxs-lookup"><span data-stu-id="560e8-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="560e8-125">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="560e8-126">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="560e8-127">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="560e8-128">**보관 정책** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="560e8-129">**보관 정책 편집-전역**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="560e8-130">**Name**에서 global의 기본 이름을 사용 하지 않으려면 전역 정책의 새 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="560e8-131">**설명**에서 정책에 대 한 정보를 제공 합니다 (예: *divisionName* 의 글로벌 정책).</span><span class="sxs-lookup"><span data-stu-id="560e8-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="560e8-132">사이트 정책 또는 사용자 정책을 통해 구체적으로 제어 되지 않은 모든 사이트 및 사용자에 대 한 내부 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="560e8-133">사이트 정책 또는 사용자 정책을 통해 구체적으로 제어 되지 않은 모든 사이트 및 사용자에 대해 외부 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="560e8-134">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="560e8-135">사이트 정책</span><span class="sxs-lookup"><span data-stu-id="560e8-135">Site policies</span></span>

<span data-ttu-id="560e8-136">해당 사이트 각각에 대해 보관 정책을 만들어 특정 사이트의 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="560e8-137">사이트 정책은 전역 정책 보다 우선 하지만 사용자 정책은 사이트 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="560e8-138">Microsoft Exchange 통합을 사용 하지 않는 경우 또는 Microsoft Exchange 통합을 사용 하는 경우 Exchange에 포함 되지 않고 사서함이 원본 위치 유지에 배치 되도록 하는 사용자가 있는 경우에만 보관 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="560e8-139">사이트에 대 한 보관 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="560e8-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="560e8-140">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="560e8-141">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="560e8-142">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="560e8-143">전역, 사이트 및 사용자 정책에 대 한 계층 구조를 포함 하 여 보관 정책이 작동 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="560e8-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="560e8-144">**새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="560e8-145">**사이트 선택**에서 정책을 적용할 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="560e8-146">**새 보관 정책**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="560e8-147">**이름**에 사이트 정책의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="560e8-148">**설명**에서 사이트 정책에 대 한 정보를 제공 합니다 (예: Redmond의 사이트 정책).</span><span class="sxs-lookup"><span data-stu-id="560e8-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="560e8-149">지정 된 사이트에 대 한 내부 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="560e8-150">지정 된 사이트에 대 한 외부 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="560e8-151">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="560e8-152">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="560e8-152">User policies</span></span>

<span data-ttu-id="560e8-153">사용자의 보관 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 정책을 적용 하 여 특정 사용자에 대해 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="560e8-154">사용자 정책은 모든 글로벌 정책 또는 사이트 정책에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="560e8-155">Microsoft Exchange 통합을 사용 하지 않는 경우 또는 Microsoft Exchange 통합을 사용 하는 경우 Exchange에 포함 되지 않고 사서함이 원본 위치 유지에 배치 되도록 하는 사용자가 있는 경우에만 보관 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="560e8-156">비즈니스용 Skype 서버에 속한 사용자에 대 한 보관 정책 구성</span><span class="sxs-lookup"><span data-stu-id="560e8-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="560e8-157">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="560e8-158">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="560e8-159">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="560e8-160">**새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="560e8-161">**새 보관 정책**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="560e8-162">**이름**에 사용자 정책의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="560e8-163">**설명**에서 사용자 정책에 대 한 정보를 제공 합니다 (예: 법률 부서의 사용자 정책).</span><span class="sxs-lookup"><span data-stu-id="560e8-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="560e8-164">사용자 정책에 대 한 내부 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="560e8-165">사용자 정책에 대 한 외부 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="560e8-166">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-166">Click **Commit**.</span></span>
    
<span data-ttu-id="560e8-167">사용자 정책은 정책을 할당 한 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="560e8-168">사용자에 게 비즈니스용 Skype 서버 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="560e8-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="560e8-169">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="560e8-170">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="560e8-171">왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 구성 하려는 사용자 계정을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="560e8-172">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="560e8-173">**보관 정책**에서 **비즈니스용 Skype 서버 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="560e8-174">자동 설정은 기본 서버 설치 설정을 적용 합니다. \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="560e8-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="560e8-175">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="560e8-176">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="560e8-176">Click **Commit**.</span></span>
    

