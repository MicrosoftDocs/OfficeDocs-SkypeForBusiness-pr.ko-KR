---
title: 영구 채팅 정책
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 영구 채팅 그룹의 영구 채팅 정책 페이지를 사용하여 기본 글로벌 정책을 구성하고 배포에 대해 하나 이상의 추가 사용자 및 사이트 정책을 만드는 등 전역, 풀, 사이트 또는 사용자 수준에서 정책을 관리할 수 있습니다. 정책을 통해 사용자에 대해 영구 채팅 서버를 사용하도록 설정하면 영구 채팅 서버 환경이 클라이언트에 표시됩니다.
ms.openlocfilehash: e7148530f571a46937ee8d8a3bf44315ac692eb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819298"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="630e1-104">영구 채팅 정책</span><span class="sxs-lookup"><span data-stu-id="630e1-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="630e1-105">영구 채팅  그룹의 영구 채팅 정책  페이지를 사용하여 기본 글로벌 정책을 구성하고 배포에 대해 하나 이상의 추가 사용자 및 사이트 정책을 만드는 등 전역, 풀, 사이트 또는 사용자 수준에서 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="630e1-106">정책을 통해 사용자에 대해 영구 채팅 서버를 사용하도록 설정하면 영구 채팅 서버 환경이 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="630e1-107">전역 정책은 영구 채팅 서버를 배포할 때 자동으로 만들어지며 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="630e1-108">전역 정책은 모든 사용자에게 적용되어 있기 때문에 사용자당 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="630e1-109">전역 정책과 함께 사용자가 영구 채팅 서버에 대해 사용하도록 설정하는 여러 사이트 및 사용자 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="630e1-110">풀 및 사이트 영구 채팅 서버 정책은 해당 사이트의 사용자에 한해 전역 영구 채팅 서버 정책을 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="630e1-111">사용자 정책은 사용자 정책이 지정된 사용자에 대한 전역, 풀 및 사이트 정책을 모두 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="630e1-112">영구 채팅 서버를 구성하고 사용하려면 먼저 토폴로지 작성기에서 영구 채팅 서버 지원을 토폴로지에 추가한 다음 토폴로지 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="630e1-113">자세한 내용은 영구 채팅 서버를 비즈니스용 [Skype 서버 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)토폴로지에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="630e1-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="630e1-114">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="630e1-114">Tasks that you can perform</span></span>

<span data-ttu-id="630e1-115">영구 채팅 정책 페이지에서는  영구 채팅 서버 정책을 사용하도록 설정할 수 있습니다. 영구 채팅 서버 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="630e1-116">영구 채팅에 대한 글로벌 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="630e1-117">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="630e1-118">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="630e1-119">비즈니스용 Skype 서버 제어판에서 영구 채팅을 클릭한 다음 영구 채팅 **정책을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="630e1-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="630e1-120">정책 목록에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="630e1-121">**영구적 채팅 정책 편집 - 전역** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="630e1-122">**이름** 에서 글로벌 정책의 새 이름을 지정합니다(기본값인 "전역"을 사용하지 않으려는 경우).</span><span class="sxs-lookup"><span data-stu-id="630e1-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="630e1-123">**설명에서** 사용자 정책에 대한 세부 정보(예: _centralSiteName에 대한 글로벌 정책)를 제공합니다._</span><span class="sxs-lookup"><span data-stu-id="630e1-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="630e1-124">사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 영구 채팅을 제어하려면 영구 채팅 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="630e1-125">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="630e1-126">사이트에 대한 영구 채팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="630e1-127">배포한 각 사이트에 대해 사이트별 영구 채팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="630e1-128">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="630e1-129">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="630e1-130">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="630e1-131">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="630e1-132">**새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="630e1-133">**사이트 선택** 에서 정책을 적용할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="630e1-134">**새 영구적 채팅 정책** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="630e1-135">**이름** 에서 새 사이트 정책의 이름을 지정합니다(예: Redmond).</span><span class="sxs-lookup"><span data-stu-id="630e1-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="630e1-136">**설명** 에서 사이트 정책에 대한 자세한 설명을 입력합니다(예: Redmond용 채팅방 정책).</span><span class="sxs-lookup"><span data-stu-id="630e1-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="630e1-137">사이트 정책을 통해 제어되지 않는 모든 사이트에 대해 영구 채팅을 제어하려면 영구 채팅 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="630e1-138">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="630e1-139">영구 채팅에 대한 사용자 정책을 만들 경우</span><span class="sxs-lookup"><span data-stu-id="630e1-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="630e1-140">비즈니스용 Skype 서버 제어판에서 사용자의 사용자에게 할당할 수 있는 사용자 정책을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="630e1-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="630e1-141">사용자 정책은 해당 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="630e1-142">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="630e1-143">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="630e1-144">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="630e1-145">**새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="630e1-146">**새 영구적 채팅 정책** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="630e1-147">**이름** 에서 새 사용자 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="630e1-148">**설명에서** 사용자 정책에 대한 세부 정보(예: 특정 사용자에 대한 영구 채팅 정책)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="630e1-149">사용자 정책을 통해 제어되지 않는 모든 사용자에 대해 영구 채팅을 제어하려면 영구 채팅 사용 확인란을 **선택하거나** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="630e1-150">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="630e1-151">영구 채팅 사용자 정책을 사용자 계정에 적용하려면</span><span class="sxs-lookup"><span data-stu-id="630e1-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="630e1-152">사용자가 비즈니스용 Skype 서버를 사용하도록 설정한 경우 특정 사용자에게 적절한 정책을 적용하여 영구 채팅 서버에 대해 해당 정책을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="630e1-153">이 항목의 절차에 따라 이전에 만든 영구 채팅 사용자 정책을 하나 이상의 사용자 계정 또는 사용자 그룹에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="630e1-154">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="630e1-155">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="630e1-156">왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="630e1-157">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="630e1-158">영구 **채팅 정책에서 Lync Server 사용자** 편집에서 적용할 영구 채팅 사용자 정책을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="630e1-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="630e1-159">이 **\<Automatic\>** 설정은 기본 유효 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="630e1-160">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="630e1-161">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="630e1-161">Click **Commit**.</span></span>
    

