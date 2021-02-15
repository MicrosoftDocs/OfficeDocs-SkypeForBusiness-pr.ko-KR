---
title: 영구적 채팅 구성
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
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 영구 채팅 서버 배포에서는 여러 개의 동시 영구 채팅방을 호스팅할 수 있습니다. 채팅방은 서버에서 범주 집합으로 구성할 수 있습니다. 각 채팅방은 범주 하나에 속하며 해당 범주의 일부 설정을 상속합니다. 이러한 구성에서는 대화를 해당 업무상 용도에 따라 식별할 수 있는 유용한 구조가 작성되며, 위임된 관리 및 간편한 관리를 용이하게 수행할 수 있도록 합니다.
ms.openlocfilehash: ca059cd739093840028a6e9b952e12566ccfa5c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829398"
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="34299-106">영구 채팅 구성</span><span class="sxs-lookup"><span data-stu-id="34299-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="34299-107">영구 채팅 서버 배포에서는 여러 개의 동시 영구 채팅방을 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="34299-108">채팅방은 서버에서 범주 집합으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="34299-109">각 채팅방은 범주 하나에 속하며 해당 범주의 일부 설정을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="34299-110">이러한 구성에서는 대화를 해당 업무상 용도에 따라 식별할 수 있는 유용한 구조가 작성되며, 위임된 관리 및 간편한 관리를 용이하게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34299-111">사용자의 영구 채팅을 실행하는 컴퓨터에서는 대부분의 채팅방 관리 기능을 사용할 수 있습니다. 그러나 영구 채팅 **관리자(cspersistentchatadministrator** 역할)는 제어판 또는 관리 셸 cmdlet을 사용하여 범주를 만들거나 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="34299-112">영구 채팅 관리자는 비즈니스용 Skype 서버 제어판 또는 Windows PowerShell cmdlet을 사용하여 범주를 만들고 관리하고 조직의 사용자에 대한 대화방 액세스를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="34299-113">하나 이상의 대화방을 관리할 수 있는 영구 채팅방 관리자는 클라이언트를 사용하여 채팅방 관리 웹 응용 프로그램을 시작하여 채팅방을 만들고 관리할 수 있습니다(또는 고객이 호출할 사용자 지정 솔루션 및 워크플로를 만들 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="34299-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="34299-114">영구 채팅</span><span class="sxs-lookup"><span data-stu-id="34299-114">Persistent Chat</span></span>
  
<span data-ttu-id="34299-115">영구 채팅 관리자는 또한 제어판 또는 Windows PowerShell cmdlet을 사용하여 채팅방을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="34299-p104">채팅방 관리자는 방 범주 변경을 제외한 모든 채팅방 속성을 변경할 수 있습니다. 채팅방 관리자가 다음과 같은 작업을 수행하지 못하도록 제한할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="34299-118">채팅방 비활성화</span><span class="sxs-lookup"><span data-stu-id="34299-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="34299-119">채팅방 이름 변경</span><span class="sxs-lookup"><span data-stu-id="34299-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="34299-120">채팅방 설명 변경</span><span class="sxs-lookup"><span data-stu-id="34299-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="34299-121">채팅방 유형 변경(강당/일반)</span><span class="sxs-lookup"><span data-stu-id="34299-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="34299-122">방 개인 정보 변경(공개/비공개/비밀)</span><span class="sxs-lookup"><span data-stu-id="34299-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="34299-123">구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="34299-123">Adding or removing members</span></span>
    
- <span data-ttu-id="34299-124">채팅방 관리자 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="34299-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="34299-125">추가 기능 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="34299-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="34299-126">초대와 같은 설정 변경(범주에서 허용하는 설정에 따라)</span><span class="sxs-lookup"><span data-stu-id="34299-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="34299-127">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="34299-127">Tasks that you can perform</span></span>

<span data-ttu-id="34299-128">영구 채팅 구성 페이지에서는  영구 채팅 서버 옵션을 전역적으로 구성하거나 특정 풀에 대해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="34299-129">영구 채팅 옵션을 전역적으로 구성</span><span class="sxs-lookup"><span data-stu-id="34299-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="34299-130">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="34299-131">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="34299-132">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="34299-133">영구 채팅 구성 **페이지에서** 새로  고치기 및 사이트 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34299-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="34299-134">사이트에 배포된 모든 영구 채팅 서버 풀에 구성을 적용하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="34299-135">**구성을** 특정 영구 채팅 서버 풀에 적용하려면 풀 구성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="34299-136">사이트 **선택에서** 영구 채팅 서버 사이트 구성에 대해 구성할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="34299-137">**새 영구적 채팅 구성** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="34299-p106">**이름** 에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="34299-p107">**기본 채팅 기록** 에서 첫 번째 요청 시 각 방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="34299-143">영구 채팅 서버는 이러한 메시지를 메모리에 캐시하기 때문에 이 수를 늘리면 더 많은 메시지가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34299-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="34299-144">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-144">You can always access historical content by search.</span></span> <span data-ttu-id="34299-145">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="34299-p109">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 대화방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="34299-149">**참가자 업데이트 제한** 에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="34299-150">영구 채팅 서버는 연결된 사용자 수가 이 수에 도달할 때까지 모든 참가자에게 대화방에 연결된 사용자명 정보를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="34299-151">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="34299-151">By default, the number is 75.</span></span> <span data-ttu-id="34299-152">이 제한은 영구 채팅 서버가 대화방에 있는 사용자에 대한 연결된 클라이언트에 대한 로스터 업데이트 전송을 중지하는 해당 채팅방의 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34299-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="34299-153">(선택 사항) 방 **관리 URL에서** 방 관리 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="34299-154">웹 기반 사용자 지정 방 관리의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="34299-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="34299-155">방 관리를 사용자 지정할 필요가 없는 경우 기본 설정만 사용하는 경우 이 옵션을 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="34299-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="34299-156">URL을 설정한 후 내부 및 외부 방 관리 URL로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34299-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="34299-157">채팅방 만들기 환경을 사용자 지정하고 특정 비즈니스 워크플로를 포함하려는 경우 영구 채팅 서버 SDK(소프트웨어 개발 키트)를 사용하여 사용자 지정 채팅방 관리 솔루션을 작성하고 원하는 곳에 호스팅한 다음 URL을 여기에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="34299-158">이 URL은 클라이언트로 전송되므로 사용자가 방을 보거나 만들려고 할 때 사용자 지정 방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34299-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="34299-159">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="34299-160">특정 영구 채팅 서버 풀에 대해 영구 채팅 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="34299-161">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="34299-162">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 열고 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="34299-163">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="34299-164">**영구적 채팅 구성** 페이지에서 **새로 만들기** 를 클릭하고 **풀 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="34299-165">서비스 **선택에서** 구성할 영구 채팅 서버 풀과 연결된 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="34299-166">**새 영구적 채팅 구성** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="34299-p113">**이름** 에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 풀 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="34299-p114">**기본 채팅 기록** 에서 첫 번째 요청 시 각 방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="34299-172">영구 채팅 서버는 이러한 메시지를 메모리에 캐시하기 때문에 이 수를 늘리면 더 많은 메시지가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34299-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="34299-173">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-173">You can always access historical content by search.</span></span> <span data-ttu-id="34299-174">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="34299-p116">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 대화방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="34299-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="34299-178">**참가자 업데이트 제한** 에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="34299-179">영구 채팅 서버는 연결된 사용자 수가 이 수에 도달할 때까지 모든 참가자에게 대화방에 연결된 사용자명 정보를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="34299-180">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="34299-180">By default, the number is 75.</span></span> <span data-ttu-id="34299-181">이 제한은 영구 채팅 서버가 대화방에 있는 사용자에 대한 연결된 클라이언트에 대한 로스터 업데이트 전송을 중지하는 해당 채팅방의 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34299-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="34299-182">원하는 경우 **방 관리 URL** 에서 방 관리 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="34299-183">이 URL은 웹 기반 방 관리 배포를 위한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="34299-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="34299-184">방 관리를 사용자 지정할 필요가 없는 경우 기본 설정만 사용하는 경우 이 옵션을 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="34299-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="34299-185">채팅방 만들기 환경을 사용자 지정하고 특정 비즈니스 워크플로를 포함하려는 경우 영구 채팅 서버 SDK(소프트웨어 개발 키트)를 사용하여 사용자 지정 채팅방 관리 솔루션을 작성하고 원하는 곳에 호스팅한 다음 URL을 여기에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34299-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="34299-186">이 URL은 클라이언트로 전송되므로 사용자가 방을 보거나 만들려고 할 때 사용자 지정 방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34299-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="34299-187">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34299-187">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34299-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34299-188">See also</span></span>

<span data-ttu-id="34299-189">영구 채팅 서버 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)영구 채팅 서버 계획, 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)영구 채팅 서버 배포 및 영구 채팅 서버 관리(비즈니스용 [Skype 서버 2015)를](../../manage/persistent-chat/persistent-chat.md)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34299-189">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

