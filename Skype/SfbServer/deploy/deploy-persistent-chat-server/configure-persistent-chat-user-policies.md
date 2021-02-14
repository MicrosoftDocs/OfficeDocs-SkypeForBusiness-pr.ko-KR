---
title: 비즈니스용 Skype 서버에서 영구 채팅 사용자 정책 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대한 초기 사용자 정책을 만드는 방법을 배워야 합니다. 영구 채팅 사용자 정책은 사용자가 채팅방에 액세스할 수 있는지 여부를 결정합니다.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802118"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="f5e20-104">비즈니스용 Skype 서버에서 영구 채팅 사용자 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f5e20-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f5e20-105">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대한 초기 사용자 정책을 만드는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="f5e20-106">영구 채팅 사용자 정책은 사용자가 채팅방에 액세스할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="f5e20-107">영구 채팅 서버 사용자 정책은 전역, 사이트 또는 사용자 수준에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="f5e20-108">처음에는 배포의 모든 사용자에 대해 영구 채팅 설정을 사용하도록 전역 정책을 구성한 다음 추가 사용자 및 사이트 정책을 만들어 특정 사용자 및 사이트에 대해 영구 채팅이 설정되어 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="f5e20-109">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="f5e20-110">글로벌 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f5e20-110">Configure the global policy</span></span>
    
- <span data-ttu-id="f5e20-111">사이트 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f5e20-111">Create a site policy</span></span>
    
- <span data-ttu-id="f5e20-112">사용자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f5e20-112">Create a user policy</span></span>
    
- <span data-ttu-id="f5e20-113">사용자 또는 사용자 그룹에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="f5e20-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="f5e20-114">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f5e20-115">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="f5e20-116">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="f5e20-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="f5e20-117">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="f5e20-118">글로벌 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f5e20-118">Configure the global policy</span></span>

<span data-ttu-id="f5e20-119">전역 정책을 구성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="f5e20-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="f5e20-120">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f5e20-121">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f5e20-122">비즈니스용 Skype 서버 제어판에서 영구 채팅을 클릭한 다음 영구 채팅 **정책을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="f5e20-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="f5e20-123">정책 목록에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f5e20-124">**영구적 채팅 정책 편집 - 전역** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="f5e20-125">**이름** 에서 글로벌 정책의 새 이름을 지정합니다(기본값인 "전역"을 사용하지 않으려는 경우).</span><span class="sxs-lookup"><span data-stu-id="f5e20-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="f5e20-126">**설명에서** 사용자 정책에 대한 세부 정보(예: _centralSiteName에 대한 글로벌 정책)를 제공합니다._</span><span class="sxs-lookup"><span data-stu-id="f5e20-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="f5e20-127">사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 영구 채팅을 제어하려면 영구 채팅 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="f5e20-128">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="f5e20-129">사이트 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f5e20-129">Create a site policy</span></span>

<span data-ttu-id="f5e20-130">배포한 각 사이트에 대해 사이트별 영구 채팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="f5e20-131">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="f5e20-132">사이트 정책을 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="f5e20-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="f5e20-133">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f5e20-134">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f5e20-135">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="f5e20-136">**새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="f5e20-137">**사이트 선택** 에서 정책을 적용할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="f5e20-138">**새 영구적 채팅 정책** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="f5e20-139">**이름** 에서 새 사이트 정책의 이름을 지정합니다(예: Redmond).</span><span class="sxs-lookup"><span data-stu-id="f5e20-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="f5e20-140">**설명** 에서 사이트 정책에 대한 자세한 설명을 입력합니다(예: Redmond용 채팅방 정책).</span><span class="sxs-lookup"><span data-stu-id="f5e20-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="f5e20-141">사이트 정책을 통해 제어되지 않는 모든 사이트에 대해 영구 채팅을 제어하려면 영구 채팅 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="f5e20-142">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="f5e20-143">사용자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f5e20-143">Create a user policy</span></span>

<span data-ttu-id="f5e20-144">전역 정책 및 사용자가 속한 사이트 정책을 다시 정의하는 사용자별 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="f5e20-145">사용자 정책을 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="f5e20-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="f5e20-146">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f5e20-147">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f5e20-148">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="f5e20-149">**새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="f5e20-150">**새 영구적 채팅 정책** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="f5e20-151">**이름** 에서 새 사용자 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="f5e20-152">**설명에서** 사용자 정책에 대한 세부 정보(예: 특정 사용자에 대한 영구 채팅 정책)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="f5e20-153">사용자 정책을 통해 제어되지 않는 모든 사용자에 대해 영구 채팅을 제어하려면 영구 채팅 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="f5e20-154">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="f5e20-155">사용자 계정에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="f5e20-155">Apply a policy to a user account</span></span>

<span data-ttu-id="f5e20-156">정책을 만든 후 다음과 같이 사용자 계정에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="f5e20-157">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f5e20-158">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f5e20-159">왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="f5e20-160">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f5e20-161">영구 채팅 정책에서 비즈니스용 **Skype** 서버 사용자 편집에서 적용할 영구 채팅 사용자 정책을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="f5e20-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f5e20-162">이 **\<Automatic\>** 설정은 기본 유효 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="f5e20-163">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="f5e20-164">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e20-164">Click **Commit**.</span></span>
    

