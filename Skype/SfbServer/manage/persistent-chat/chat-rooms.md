---
title: 영구 채팅 서버의 채팅방 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 채팅방을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815108"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="84b1b-103">영구 채팅 서버의 채팅방 관리</span><span class="sxs-lookup"><span data-stu-id="84b1b-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="84b1b-104">**요약:** 영구 채팅 서버 채팅방을 관리하는 방법을 비즈니스용 Skype 서버 2015에서 자세히 알아보는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="84b1b-105">범주를 올바르게 사용하여 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="84b1b-106">범주는 채팅방을 만들거나 참가할 수 있는 대상을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="84b1b-107">대화방을 관리하기 전에 비즈니스용 Skype 서버 [2015에서](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) 영구 채팅 범주, 채팅방 및 사용자 역할을 읽고 비즈니스용 Skype 서버 [2015의](categories.md)영구 채팅 서버에서 범주를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="84b1b-108">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="84b1b-109">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="84b1b-110">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="84b1b-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="84b1b-111">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="84b1b-112">Windows PowerShell 명령줄 인터페이스를 사용하여 채팅방을 구성하고 관리할 수도 있으며, 채팅방의 구성원인 경우 비즈니스용 Skype 클라이언트를 사용하여 채팅방을 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="84b1b-113">이 항목에서는 명령줄 인터페이스를 사용하여 대화방을 관리하는 Windows PowerShell 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="84b1b-114">비즈니스용 Skype 클라이언트를 사용하여 대화방을 관리하려는 경우 클라이언트 도움말을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84b1b-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="84b1b-115">대화방은 보통 및 강당의 두 가지 유형 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="84b1b-116">일반 대화방에서는 모든 구성원이 메시지를 게시하고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="84b1b-117">강당은 발표자만 게시할 수 있지만 모든 사람이 읽을 수 있는 일종의 대화방입니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="84b1b-118">채팅방에 액세스하고 관리할 수 있는 사용자는 다음과 같은 사용자 역할에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="84b1b-119">사용자가 메시지를 게시하고 읽을 수 있도록 대화방의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="84b1b-120">발표자는 강당 방에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="84b1b-121">관리자는 데이터베이스가 너무 크게 증가하지 않도록 방지하기 위해 채팅방에서 이전 콘텐츠(예: 특정 일 수 이전에 게시된 콘텐츠)를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="84b1b-122">관리자는 특정 대화방에 부적절한 것으로 간주되는 메시지를 제거하거나 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="84b1b-123">메시지 작성자를 포함하여 최종 사용자는 채팅방의 콘텐츠를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="84b1b-124">채팅방 관리자는 채팅방을 사용할 수 없는 경우를 포함하여 모든 채팅방 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="84b1b-125">그러나 관리자는 방을 삭제하거나 방의 범주를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="84b1b-126">만든 채팅방은 관리자만 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="84b1b-127">다음 cmdlet을 사용하여 채팅방을 구성하고 관리할 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="84b1b-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="84b1b-128">**Cmdlet**</span></span>|<span data-ttu-id="84b1b-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="84b1b-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84b1b-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="84b1b-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="84b1b-131">새 대화방 만들기</span><span class="sxs-lookup"><span data-stu-id="84b1b-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="84b1b-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="84b1b-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="84b1b-133">기존 방에 대한 설정을 구성합니다. 방에 사용자 및 사용자 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="84b1b-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="84b1b-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="84b1b-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="84b1b-135">방에 대한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="84b1b-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="84b1b-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="84b1b-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="84b1b-137">방 또는 방에서 메시지 지우기</span><span class="sxs-lookup"><span data-stu-id="84b1b-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="84b1b-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="84b1b-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="84b1b-139">방 제거</span><span class="sxs-lookup"><span data-stu-id="84b1b-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="84b1b-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="84b1b-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="84b1b-141">방에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="84b1b-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="84b1b-142">**New-CsPersistentChatRoom** cmdlet을 사용하여 채팅방을 만들고 **Set-CsPersistentChatRoom** cmdlet을 사용하여 채팅방에 사용자를 추가하는 등 기존 채팅방을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="84b1b-143">채팅방에 대해 다음 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="84b1b-144">사용 안 하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-144">Disabled.</span></span> <span data-ttu-id="84b1b-145">대화방을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="84b1b-146">초대.</span><span class="sxs-lookup"><span data-stu-id="84b1b-146">Invitations.</span></span> <span data-ttu-id="84b1b-147">대화방 구성원으로 추가될 때 사용자에게 알리는 데 사용되는 대화방 초대를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="84b1b-148">상속되는 초대에 대한 기본 설정으로 인해 채팅방이 속한 범주에 구성된 초대 설정을 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="84b1b-149">채팅방 수준에서 초대 설정을 false로 구성하면 범주 설정을 의어로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="84b1b-150">개인 정보 보호.</span><span class="sxs-lookup"><span data-stu-id="84b1b-150">Privacy.</span></span> <span data-ttu-id="84b1b-151">대화방이 열려 있는지, 닫혀 있는지, 비밀 대화방인지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="84b1b-152">열려 있는 방은 누구나 검색하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="84b1b-153">모든 사람이 닫힌 방을 검색할 수 있지만 구성원만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="84b1b-154">비밀 방은 방의 구성원만 검색하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="84b1b-155">기본적으로 각 새 방은 처음에 Closed로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="84b1b-156">유형입니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-156">Type.</span></span> <span data-ttu-id="84b1b-157">대화방이 구성원이 게시한 메시지를 수락하는 일반 방인지 또는 발표자만 게시한 메시지를 허용하는 강당 방인지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="84b1b-158">추가 기능.</span><span class="sxs-lookup"><span data-stu-id="84b1b-158">Addin.</span></span> <span data-ttu-id="84b1b-159">이전에 구성된 추가 기능을 대화방과 연결하여 구성원이 URL 콘텐츠를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="84b1b-160">위의 매개 변수 외에도 **Set-CsPersistentChatRoom** cmdlet을 사용하면 다음과 같이 사용자를 채팅방에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="84b1b-161">구성원.</span><span class="sxs-lookup"><span data-stu-id="84b1b-161">Members.</span></span> <span data-ttu-id="84b1b-162">대화방의 구성원 자격을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-162">Configures membership for the chat room.</span></span> <span data-ttu-id="84b1b-163">사용자의 SIP 주소를 지정하여 단일 cmdlet을 사용하여 개별 구성원 또는 여러 구성원을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="84b1b-164">사용자를 대량으로 추가할 수 있도록 Active Directory 조직 구성 단위 또는 메일 그룹도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="84b1b-165">관리자.</span><span class="sxs-lookup"><span data-stu-id="84b1b-165">Managers.</span></span> <span data-ttu-id="84b1b-166">대화방에 관리자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="84b1b-167">관리자에게는 다른 설정과 함께 채팅방의 구성원 자격을 정의할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="84b1b-168">발표자.</span><span class="sxs-lookup"><span data-stu-id="84b1b-168">Presenters.</span></span> <span data-ttu-id="84b1b-169">강당 대화방에 발표자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="84b1b-170">모든 매개 변수를 포함한 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="84b1b-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="84b1b-171">새 방 만들기</span><span class="sxs-lookup"><span data-stu-id="84b1b-171">Create a new room</span></span>

<span data-ttu-id="84b1b-172">**New-CsPersistentChatRoom** cmdlet을 사용하여 새 방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="84b1b-173">예를 들어 다음 명령은 풀 그룹에서 ITChatRoom이라는 새 대화방을 atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="84b1b-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="84b1b-174">이 예에서는 채팅방이 IT 범주에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="84b1b-175">**참고:** 다음 중 하나에 해당하면 PersistentChatPoolFqdn이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="84b1b-176">영구 채팅 서버 풀은 하나뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="84b1b-177">범주에 풀 FQDN을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="84b1b-178">추가하는 채팅방에 풀 FQDN을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="84b1b-179">기존 방 구성</span><span class="sxs-lookup"><span data-stu-id="84b1b-179">Configure an existing room</span></span>

<span data-ttu-id="84b1b-180">**Set-CsPersistentChatRoom** cmdlet을 사용하여 기존 방을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="84b1b-181">예를 들어 다음 명령은 testCat 강당 방의 user1을 구성원 및 발표자, user2를 관리자로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="84b1b-182">다음 예에서는 Active Directory의 NorthAmericaUsers OU의 모든 사용자를 NorthAmerica 대화방에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="84b1b-183">다음 예에서는 Finance 메일 그룹의 모든 구성원을 동일한 대화방에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="84b1b-184">방 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="84b1b-184">Disable or enable a room</span></span>

<span data-ttu-id="84b1b-185">영구 채팅방의 주제가 더 이상 관련이 없는 경우 대화방을 사용하지 않고 사용자가 대화방을 사용할 수 없게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="84b1b-186">대화방을 사용하지 않도록 설정하면 모든 구성원이 대화방에서 즉시 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="84b1b-187">대화방을 사용하지 않도록 설정한 후 사용자는 대화방에 다시 추가하거나 채팅방 검색에서 채팅방을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="84b1b-188">대화방 기록이 유지되면 대화방을 사용하지 않도록 설정하면 콘텐츠가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="84b1b-189">그러나 대화방이 비활성화된 상태로 유지되는 동안에는 해당 콘텐츠가 검색에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="84b1b-190">나중에 대화방을 사용하도록 설정하면 사용자가 대화방을 사용하지 않도록 설정하기 전에 게시된 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="84b1b-191">채팅방 기록 구성에 대한 자세한 내용은 영구 채팅 서버의 범주 [관리(비즈니스용 Skype 서버 2015)를 참조하세요.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="84b1b-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="84b1b-192">대화방을 사용하지 않도록 설정하면 해당 구성원 자격 목록 및 기타 설정이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="84b1b-193">관리자는 사용하지 않도록 설정한 방을 사용하도록 설정할 수 있으며 설정을 수동으로 다시 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="84b1b-194">**Set-CsPersistentChatRoom** cmdlet을 사용하고 Disabled 매개 변수를 True로 설정하여 회의실을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="84b1b-195">대화방을 사용하도록 설정하려면 Disabled 매개 변수를 False로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="84b1b-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="84b1b-196">회의실에 대한 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="84b1b-196">Get information about rooms</span></span>

<span data-ttu-id="84b1b-197">조직에서 사용하도록 구성된 방에 대한 정보를 얻습니다. **Get-CsPersistentChatRoom** cmdlet을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="84b1b-198">다음 명령은 조직에서 사용하도록 구성된 모든 채팅방에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="84b1b-199">방에서 모든 콘텐츠 제거</span><span class="sxs-lookup"><span data-stu-id="84b1b-199">Remove all content from a room</span></span>

<span data-ttu-id="84b1b-200">**Clear-CsPersistentChatRoom** cmdlet을 사용하여 방에서 콘텐츠를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="84b1b-201">예를 들어 다음 명령은 2015년 3월 1일 또는 그 이전의 채팅방에 추가된 모든 콘텐츠를 영구 채팅방 ITChatRoom에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="84b1b-202">방에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="84b1b-202">Remove a message from a room</span></span>

<span data-ttu-id="84b1b-203">영구 채팅 데이터베이스에서 메시지를 하나 이상 제거하고, 필요한 경우 **Remove-CsPersistentChatMessage** cmdlet을 사용하여 메시지를 기본 메시지 또는 관리자가 제공한 메시지로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="84b1b-204">예를 들어 다음 명령은 ITChatRoom 대화방에서 사용자가 게시한 모든 메시지를 kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="84b1b-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="84b1b-205">다음 예제에서는 제거된 메시지를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="84b1b-206">방 제거</span><span class="sxs-lookup"><span data-stu-id="84b1b-206">Remove a room</span></span>

<span data-ttu-id="84b1b-207">**Remove-CsPersistentChatRoom** cmdlet을 사용하여 방을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="84b1b-208">예를 들어 다음 명령은 채팅방 RedmondChatRoom을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="84b1b-209">한 범주에서 다른 범주로 방 이동</span><span class="sxs-lookup"><span data-stu-id="84b1b-209">Move a room from one category to another</span></span>

<span data-ttu-id="84b1b-210">채팅방 관리자에게  다른 범주의 작성자 권한이 있는 경우 방을 한 범주에서 다른 범주로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="84b1b-211">방은 삭제되지 않고 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="84b1b-212">데이터베이스 내의 연결에 대한 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="84b1b-213">채팅방 범주를 변경하는 경우는 드물지만 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="84b1b-214">범주는 해당 채팅방에 대해 허용되는 구성원 자격을 결정하므로 채팅방을 다른 범주로 이동하면 새 범주에 따라 더 이상 지원되지 않는 모든 SACL(시스템 액세스 제어 목록)이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="84b1b-215">예를 들어 사용자가 방의 구성원이고 새 범주에서 더 이상 허용된 구성원이 아 없는 경우 방 구성원 자격이 수정되고 사용자가 방에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b1b-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

