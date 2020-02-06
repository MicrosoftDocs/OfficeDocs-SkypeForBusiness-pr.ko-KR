---
title: 영구 채팅 정책 기본 페이지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: 영구 채팅 그룹의 영구 채팅 정책 페이지를 통해 전역, 풀, 사이트 또는 사용자 수준에서 정책을 관리할 수 있습니다(배포에 대해 기본 전역 정책을 구성하고 하나 이상의 사용자 및 사이트 정책을 추가로 만드는 작업이 포함됨). 사용자가 정책에 따라 영구 채팅 서버를 사용 하도록 설정 하면 클라이언트에 영구 채팅 서버 환경이 표시 됩니다.
ms.openlocfilehash: 053e7fb4f03f7e152a238a3b155eac161433c141
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822521"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="6d3f6-104">영구 채팅 정책 기본 페이지</span><span class="sxs-lookup"><span data-stu-id="6d3f6-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="6d3f6-105">**영구 채팅** 그룹의 **영구 채팅 정책** 페이지를 통해 전역, 풀, 사이트 또는 사용자 수준에서 정책을 관리할 수 있습니다(배포에 대해 기본 전역 정책을 구성하고 하나 이상의 사용자 및 사이트 정책을 추가로 만드는 작업이 포함됨).</span><span class="sxs-lookup"><span data-stu-id="6d3f6-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="6d3f6-106">사용자가 정책에 따라 영구 채팅 서버를 사용 하도록 설정 하면 클라이언트에 영구 채팅 서버 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d3f6-107">토폴로지에서 영구 채팅 서버 사이트 정책은 전역, 사용자 당 풀 또는 사용자 당 사이트 또는 사용자 단위로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="6d3f6-108">영구 채팅 서버를 배포할 때 전역 정책이 자동으로 만들어지고,이를 구성할 수는 있지만 삭제 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="6d3f6-109">전역 정책은 모든 사용자에 게 적용 되므로 사용자 당 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="6d3f6-110">전역 정책과 함께 영구 채팅 서버용으로 사용자를 설정 하는 여러 사이트 및 사용자 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="6d3f6-111">풀 및 사이트 영구 채팅 서버 정책은 전역 영구 채팅 서버 정책 보다 우선 하며, 해당 사이트의 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="6d3f6-112">사용자 정책은 사용자 정책이 지정된 사용자에 대한 전역, 풀 및 사이트 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d3f6-113">영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="6d3f6-114">자세한 내용은 [비즈니스용 Skype 서버 2015 토폴로지에 영구 채팅 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="6d3f6-115">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="6d3f6-115">Tasks that you can perform</span></span>

<span data-ttu-id="6d3f6-116">**영구 채팅 정책** 페이지에서는 영구 채팅 서버 정책 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="6d3f6-117">영구 채팅에 대 한 전역 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="6d3f6-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="6d3f6-118">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d3f6-119">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6d3f6-120">비즈니스용 Skype 서버 제어판에서 **영구 채팅**을 클릭 한 다음 **영구 채팅 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="6d3f6-121">정책 목록에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6d3f6-122">**영구 채팅 정책 편집 - 전역**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="6d3f6-123">**이름**에서 전역 정책의 새 이름을 지정합니다(기본값인 "전역"을 사용하지 않으려는 경우).</span><span class="sxs-lookup"><span data-stu-id="6d3f6-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="6d3f6-124">**설명**에서 사용자 정책에 대 한 세부 정보를 제공 합니다 (예: _centralSiteName_의 글로벌 정책).</span><span class="sxs-lookup"><span data-stu-id="6d3f6-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="6d3f6-125">사이트 정책 또는 사용자 정책을 통해 구체적으로 제어 되지 않은 모든 사이트 및 사용자에 대해 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="6d3f6-126">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="6d3f6-127">사이트에 대 한 영구 채팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6d3f6-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="6d3f6-128">배포한 각 사이트에 대해 사이트별 영구 채팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="6d3f6-129">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="6d3f6-130">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d3f6-131">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6d3f6-132">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **영구 채팅 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="6d3f6-133">**새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="6d3f6-134">**사이트 선택**에서 정책을 적용할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="6d3f6-135">**새 영구 채팅 정책**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="6d3f6-136">**이름**에서 새 사이트 정책의 이름을 지정합니다(예: Redmond).</span><span class="sxs-lookup"><span data-stu-id="6d3f6-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="6d3f6-137">**설명**에서 사이트 정책에 대한 자세한 설명을 입력합니다(예: Redmond용 채팅방 정책).</span><span class="sxs-lookup"><span data-stu-id="6d3f6-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="6d3f6-138">사이트 정책을 통해 제어되지 않는 모든 사이트에 대해 영구 채팅을 제어하려면 **영구 채팅 사용** 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="6d3f6-139">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="6d3f6-140">영구 채팅에 대 한 사용자 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6d3f6-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="6d3f6-141">비즈니스용 Skype 서버 제어판에서 사용자에 게 할당할 수 있는 사용자 정책을 **정의 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d3f6-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="6d3f6-142">사용자 정책은 해당 정책이 할당된 특정 사용자에 한해 전역 정책 및 사이트 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="6d3f6-143">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d3f6-144">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6d3f6-145">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **영구 채팅 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="6d3f6-146">**새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="6d3f6-147">**새 영구 채팅 정책**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="6d3f6-148">**이름**에 새 사용자 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="6d3f6-149">**설명**에서 사용자 정책에 대 한 세부 정보를 제공 합니다 (예: 특정 사용자의 영구 채팅 정책).</span><span class="sxs-lookup"><span data-stu-id="6d3f6-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="6d3f6-150">사용자 정책을 통해 구체적으로 제어 되지 않는 모든 사용자의 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="6d3f6-151">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="6d3f6-152">사용자 계정에 영구 채팅 사용자 정책을 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="6d3f6-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="6d3f6-153">비즈니스용 Skype에 대해 사용자가 사용 하도록 설정 된 경우 특정 사용자에 게 적절 한 정책을 적용 하 여 영구 채팅 서버에 대해이를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="6d3f6-154">이 항목의 절차를 사용 하 여 하나 이상의 사용자 계정 또는 사용자 그룹에 이전에 만든 영구 채팅 사용자 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="6d3f6-155">CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d3f6-156">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6d3f6-157">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="6d3f6-158">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6d3f6-159">**Lync Server 사용자 편집** 의 **영구 채팅 정책**에서 적용 하려는 영구 채팅 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6d3f6-160">자동 설정은 기본 유효 정책을 적용 합니다. \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="6d3f6-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="6d3f6-161">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="6d3f6-162">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3f6-162">Click **Commit**.</span></span>
    

