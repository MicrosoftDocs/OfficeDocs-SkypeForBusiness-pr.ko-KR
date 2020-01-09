---
title: 영구 채팅 서버의 채팅방 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 채팅방을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: cbced7f62a4684e5541e35b5985b7e93cc7d3e66
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992123"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="760ac-103">영구 채팅 서버의 채팅방 관리</span><span class="sxs-lookup"><span data-stu-id="760ac-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="760ac-104">**요약:** 비즈니스용 Skype Server 2015에서 영구 채팅 서버 채팅방을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="760ac-105">다양 한 범주를 사용 하 여 채팅방을 만들고 관리 하는 것이 훨씬 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="760ac-106">범주는 채팅방을 만들거나 참가할 수 있는 사람을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="760ac-107">채팅방을 관리 하기 전에 비즈니스용 [Skype server 2015의 영구 채팅 범주, 채팅방 및 사용자 역할](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) 을 읽고 비즈니스용 [skype Server 2015에서 영구 채팅 서버의 범주를 관리](categories.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="760ac-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="760ac-108">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="760ac-109">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="760ac-110">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="760ac-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="760ac-111">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="760ac-112">Windows PowerShell 명령줄 인터페이스를 사용 하거나 채팅방의 구성원 인 경우 비즈니스용 Skype 클라이언트를 사용 하 여 채팅방을 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="760ac-113">이 항목에서는 Windows PowerShell 명령줄 인터페이스를 사용 하 여 채팅방을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="760ac-114">비즈니스용 Skype 클라이언트를 사용 하 여 채팅방을 관리 하려는 경우 클라이언트 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="760ac-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="760ac-115">채팅방은 일반 및 Auditorium 두 가지 유형 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="760ac-116">일반 채팅방에서 모든 구성원이 메시지를 게시 하 고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="760ac-117">Auditorium는 발표자만 게시할 수 있는 채팅방의 한 종류로, 모든 사람이 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="760ac-118">채팅방을 액세스 하 고 관리 하는 사람은 다음과 같이 사용자 역할에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="760ac-119">사용자가 메시지를 게시 하 고 읽을 수 있으려면 채팅방의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="760ac-120">발표자는 Auditorium 채팅방에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="760ac-121">관리자는 모든 채팅방에서 이전 콘텐츠 (예: 특정 날짜 이전에 게시 된 콘텐츠)를 삭제 하 여 데이터베이스가 너무 커지지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="760ac-122">또한 관리자는 특정 채팅방에 적합 하지 않은 것으로 간주 되는 메시지를 제거 하거나 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="760ac-123">메시지 작성자를 비롯 한 최종 사용자는 채팅방에서 콘텐츠를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="760ac-124">채팅방 관리자는 채팅방을 사용 하지 않도록 설정 하는 등의 모든 채팅방 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="760ac-125">그러나, 관리자는 채팅방을 삭제 하거나 룸 범주를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="760ac-126">관리자만이 채팅방을 만든 후 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="760ac-127">다음 Windows PowerShell cmdlet을 사용 하 여 채팅방을 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="760ac-128">**은**</span><span class="sxs-lookup"><span data-stu-id="760ac-128">**Cmdlet**</span></span>|<span data-ttu-id="760ac-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="760ac-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="760ac-130">새로운 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="760ac-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="760ac-131">새 채팅방 만들기</span><span class="sxs-lookup"><span data-stu-id="760ac-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="760ac-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="760ac-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="760ac-133">기존 방에 대 한 설정을 구성 합니다. 룸에 사용자 및 사용자 그룹 지정</span><span class="sxs-lookup"><span data-stu-id="760ac-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="760ac-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="760ac-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="760ac-135">채팅방에 대 한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="760ac-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="760ac-136">일반-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="760ac-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="760ac-137">채팅방에서 채팅방 또는 메시지 지우기</span><span class="sxs-lookup"><span data-stu-id="760ac-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="760ac-138">제거-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="760ac-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="760ac-139">채팅방 제거</span><span class="sxs-lookup"><span data-stu-id="760ac-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="760ac-140">제거-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="760ac-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="760ac-141">채팅방에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="760ac-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="760ac-142">**CsPersistentChatRoom** cmdlet을 사용 하 여 채팅방에 사용자를 추가 하는 것을 포함 하 여 기존 채팅방을 구성 하는 대화방 및 **집합-CsPersistentChatRoom** cmdlet을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="760ac-143">채팅방에 대해 다음 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="760ac-144">비활성화.</span><span class="sxs-lookup"><span data-stu-id="760ac-144">Disabled.</span></span> <span data-ttu-id="760ac-145">채팅방을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="760ac-146">보도록.</span><span class="sxs-lookup"><span data-stu-id="760ac-146">Invitations.</span></span> <span data-ttu-id="760ac-147">채팅방 구성원으로 추가 되었을 때 사용자에 게 알리는 데 사용 되는 채팅방 초대를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="760ac-148">초대에 대 한 기본 설정으로 채팅 채팅방에서 자신이 속한 범주에 구성 된 초대 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="760ac-149">채팅방 수준에서 초대 설정을 false로 구성 하면 범주 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="760ac-150">프라이버시.</span><span class="sxs-lookup"><span data-stu-id="760ac-150">Privacy.</span></span> <span data-ttu-id="760ac-151">채팅방이 열려 있는지, 닫혔는지, 비밀 인지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="760ac-152">모든 사용자가 열거나 회의실을 검색 하 고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="760ac-153">모든 사용자가 채팅방을 검색할 수 있지만 구성원만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="760ac-154">채팅방의 구성원만 비밀 방을 검색 하 고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="760ac-155">기본적으로 새 공간은 모두 닫힌 것으로 초기 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="760ac-156">입력할.</span><span class="sxs-lookup"><span data-stu-id="760ac-156">Type.</span></span> <span data-ttu-id="760ac-157">채팅방이 구성원이 게시 한 메시지를 허용 하는 일반 채팅방 인지 아니면 발표자만 게시 한 메시지를 허용 하는 Auditorium 채팅방을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="760ac-158">기능이.</span><span class="sxs-lookup"><span data-stu-id="760ac-158">Addin.</span></span> <span data-ttu-id="760ac-159">이전에 구성한 추가 기능을 채팅방과 연결 하 여 참여 중에 구성원이 URL 콘텐츠를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="760ac-160">위의 매개 변수 외에도 **CsPersistentChatRoom** cmdlet을 사용 하 여 사용자를 채팅방에 다음과 같이 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="760ac-161">멤버만.</span><span class="sxs-lookup"><span data-stu-id="760ac-161">Members.</span></span> <span data-ttu-id="760ac-162">채팅방에 대 한 구성원 자격을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-162">Configures membership for the chat room.</span></span> <span data-ttu-id="760ac-163">사용자의 SIP 주소를 지정 하 여 단일 cmdlet을 사용 하 여 개인 또는 다중 구성원을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="760ac-164">사용자를 대량으로 추가 하는 것을 허용 하기 위해 Active Directory 조직 구성 단위 또는 메일 그룹도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="760ac-165">Review.</span><span class="sxs-lookup"><span data-stu-id="760ac-165">Managers.</span></span> <span data-ttu-id="760ac-166">채팅방에 관리자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="760ac-167">관리자는 다른 설정에 따라 채팅방의 구성원을 정의할 수 있는 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="760ac-168">명의.</span><span class="sxs-lookup"><span data-stu-id="760ac-168">Presenters.</span></span> <span data-ttu-id="760ac-169">Auditorium 채팅방에 발표자를 배정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="760ac-170">모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="760ac-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="760ac-171">새 채팅방 만들기</span><span class="sxs-lookup"><span data-stu-id="760ac-171">Create a new room</span></span>

<span data-ttu-id="760ac-172">**새 CsPersistentChatRoom** cmdlet을 사용 하 여 새 방을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="760ac-173">예를 들어 다음 명령은 pool atl-cs-001.contoso.com에서 새 채팅방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="760ac-174">이 예제에서는 채팅방이 IT 범주에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="760ac-175">**참고:** 다음 중 하나가 참이 면 PersistentChatPoolFqdn 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="760ac-176">영구 채팅 서버 풀이 하나 밖에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="760ac-177">범주에 풀 FQDN을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="760ac-178">공간을 추가 하는 풀 FQDN을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="760ac-179">기존 채팅방 구성</span><span class="sxs-lookup"><span data-stu-id="760ac-179">Configure an existing room</span></span>

<span data-ttu-id="760ac-180">**Set-CsPersistentChatRoom** cmdlet을 사용 하 여 기존 방을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="760ac-181">예를 들어 다음 명령은 testCat Auditorium 방에 대해 구성원 및 발표자로 user1을 할당 하 고 관리자로 서,이를 이름으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="760ac-182">다음 예에서는 active Directory의 NorthAmericaUsers OU에 있는 모든 사용자를 NorthAmerica 채팅방에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="760ac-183">다음 예에서는 재무 메일 그룹의 모든 구성원을 같은 채팅방에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="760ac-184">회의실을 사용 하지 않거나 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="760ac-184">Disable or enable a room</span></span>

<span data-ttu-id="760ac-185">영구 채팅방의 항목이 더 이상 관련이 없다면 사용자가 채팅방을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="760ac-186">채팅방을 사용 하지 않도록 설정 하면 모든 구성원이 채팅방에서 바로 연결이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="760ac-187">채팅방을 사용 하지 않도록 설정한 후에는 사용자가 다시 참가 하거나 채팅방 검색에서 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="760ac-188">채팅방의 기록이 유지 되는 경우 채팅방을 사용 하지 않도록 설정한 경우 콘텐츠가 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="760ac-189">그러나 대화방을 사용할 수 없는 상태로 유지 하는 동안에는 검색에 해당 콘텐츠가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="760ac-190">나중에 채팅방을 사용 하도록 설정 하는 경우 사용자는 채팅방을 사용 하지 않도록 설정 하기 전에 게시 된 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="760ac-191">채팅방 기록 구성에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버의 범주 관리](categories.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="760ac-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="760ac-192">채팅방을 사용 하지 않도록 설정한 경우, 해당 채팅방의 회원 가입 목록 및 기타 설정이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="760ac-193">관리자는 사용 하지 않도록 설정 된 채팅방을 사용할 수 있으며 설정을 수동으로 다시 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="760ac-194">**CsPersistentChatRoom** cmdlet을 사용 하 고 Disabled 매개 변수를 True로 설정 하 여 채팅방을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="760ac-195">채팅방을 사용 하도록 설정 하려면 Disabled 매개 변수를 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="760ac-196">채팅방에 대 한 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="760ac-196">Get information about rooms</span></span>

<span data-ttu-id="760ac-197">조직에서 사용 하도록 구성 된 채팅방에 대 한 정보를 얻으려면 **CsPersistentChatRoom** cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="760ac-198">다음 명령은 조직에서 사용 하도록 구성 된 모든 채팅방에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="760ac-199">룸에서 모든 콘텐츠 제거</span><span class="sxs-lookup"><span data-stu-id="760ac-199">Remove all content from a room</span></span>

<span data-ttu-id="760ac-200">**CsPersistentChatRoom** cmdlet을 사용 하 여 채팅방에서 콘텐츠를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="760ac-201">예를 들어 다음 명령은 2015 년 3 월 1 일 이전에 룸에 추가 된 영구 채팅방 공간에서 모든 콘텐츠를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="760ac-202">채팅방에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="760ac-202">Remove a message from a room</span></span>

<span data-ttu-id="760ac-203">영구 채팅 데이터베이스에서 하나 이상의 메시지를 제거 하 고 필요에 따라 **CsPersistentChatMessage** cmdlet을 사용 하 여 메시지를 기본 메시지 또는 관리자가 제공한 메시지로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="760ac-204">예를 들어 다음 명령을 사용 하 여 사용자 kenmyer@contoso.com에 의해 게시 된 모든 메시지를 It 채팅방 채팅방에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="760ac-205">다음 예제에서는 제거 된 메시지를 메시지가 더 이상 사용할 수 없는 메모로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="760ac-206">채팅방 제거</span><span class="sxs-lookup"><span data-stu-id="760ac-206">Remove a room</span></span>

<span data-ttu-id="760ac-207">**CsPersistentChatRoom** cmdlet을 사용 하 여 채팅방을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="760ac-208">예를 들어 다음 명령은 채팅방 RedmondChatRoom를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="760ac-209">한 범주에서 다른 범주로 채팅방 이동</span><span class="sxs-lookup"><span data-stu-id="760ac-209">Move a room from one category to another</span></span>

<span data-ttu-id="760ac-210">채팅방 관리자에 다른 범주에 대 한 **작성자** 권한이 있는 경우 한 범주에서 다른 범주로 방을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="760ac-211">룸은 삭제 되었다가 다시 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="760ac-212">데이터베이스 내의 연결을 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="760ac-213">채팅방 범주를 변경 하는 작업은 거의 필요 하지 않으며 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="760ac-214">범주는 채팅방에 대해 허용 된 구성원 자격을 결정 하므로 채팅방을 다른 범주로 이동 하면 새 범주에서 더 이상 지원 되지 않는 모든 Sacl (시스템 액세스 제어 목록)이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="760ac-215">예를 들어 사용자가 채팅방의 구성원이 고 더 이상 새 범주에 허용 되지 않는 경우 룸 구성원 자격이 수정 되 고 사용자가 채팅방에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="760ac-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

