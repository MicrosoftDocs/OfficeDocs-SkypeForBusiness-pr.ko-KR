---
title: 영구 채팅 구성 기본 페이지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 영구 채팅 서버 구축은 많은 동시 영구 채팅방을 호스트할 수 있습니다. 채팅방은 서버에서 범주 집합으로 구성할 수 있습니다. 각 채팅방은 한 범주에 속하며 해당 범주의 일부 설정을 상속합니다. 이러한 구성은 비즈니스 목적에 따라 대화를 식별하는 데 유용한 구조를 만들며 위임된 관리 및 간소화된 관리를 용이하게 합니다.
ms.openlocfilehash: 2de93fc5dfe85f9ab6b16d66f62df12faccde5e2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699943"
---
# <a name="persistent-chat-configuration-main-page"></a><span data-ttu-id="fbb57-106">영구 채팅 구성 기본 페이지</span><span class="sxs-lookup"><span data-stu-id="fbb57-106">Persistent Chat Configuration Main Page</span></span>
 
<span data-ttu-id="fbb57-107">영구 채팅 서버 구축은 많은 동시 영구 채팅방을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="fbb57-108">채팅방은 서버에서 범주 집합으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="fbb57-109">각 채팅방은 한 범주에 속하며 해당 범주의 일부 설정을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="fbb57-110">이러한 구성은 비즈니스 목적에 따라 대화를 식별하는 데 유용한 구조를 만들며 위임된 관리 및 간소화된 관리를 용이하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fbb57-111">다양 한 채팅방의 관리 기능을 사용자에 게 영구 채팅을 실행 하는 컴퓨터에서 사용할 수 있지만, **cspersistentchatadministrator** 역할의 영구 채팅 관리자는 제어판 또는 관리 셸 cmdlet을 사용 하 여 범주를 만들거나 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="fbb57-112">영구 채팅 관리자는 비즈니스용 Skype Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 하 고 조직의 사용자에 대 한 채팅방에 대 한 액세스를 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="fbb57-113">하나 이상의 채팅방을 관리 하는 기능이 있는 영구 채팅방 관리자는 클라이언트를 사용 하 여 채팅방 관리 웹 응용 프로그램을 실행 하 여 회의실을 만들고 관리 하며 (또는 고객이 호출할 사용자 지정 솔루션 및 워크플로를 만들 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="fbb57-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> 
  
<span data-ttu-id="fbb57-p103">채팅방 관리자는 채팅방의 범주 변경을 제외한 모든 채팅방 속성을 변경할 수 있습니다. 채팅방 관리자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="fbb57-116">채팅방 비활성화</span><span class="sxs-lookup"><span data-stu-id="fbb57-116">Disabling a chat room</span></span>
    
- <span data-ttu-id="fbb57-117">채팅방 이름 변경</span><span class="sxs-lookup"><span data-stu-id="fbb57-117">Changing a chat room name</span></span>
    
- <span data-ttu-id="fbb57-118">채팅방 설명 변경</span><span class="sxs-lookup"><span data-stu-id="fbb57-118">Changing a chat room description</span></span>
    
- <span data-ttu-id="fbb57-119">채팅방 유형 변경(강당 및 일반)</span><span class="sxs-lookup"><span data-stu-id="fbb57-119">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="fbb57-120">채팅방의 개인 정보 공개 여부 변경(공개, 비공개 및 비밀)</span><span class="sxs-lookup"><span data-stu-id="fbb57-120">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="fbb57-121">구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="fbb57-121">Adding or removing members</span></span>
    
- <span data-ttu-id="fbb57-122">채팅방 관리자 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="fbb57-122">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="fbb57-123">추가 기능 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="fbb57-123">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="fbb57-124">초대장 등의 설정 변경 (범주에서 허용 하는 항목에 따라)</span><span class="sxs-lookup"><span data-stu-id="fbb57-124">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="fbb57-125">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="fbb57-125">Tasks that you can perform</span></span>

<span data-ttu-id="fbb57-126">**영구 채팅 구성** 페이지에서 영구 채팅 서버 옵션을 전역적으로 또는 특정 풀에 대해 구성 하 여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-126">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="fbb57-127">영구 채팅 옵션을 전역적으로 구성</span><span class="sxs-lookup"><span data-stu-id="fbb57-127">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="fbb57-128">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-128">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fbb57-129">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-129">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="fbb57-130">왼쪽 탐색 메뉴에서 **영구 채팅**을 클릭하고 **영구 채팅 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-130">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="fbb57-131">**영구 채팅 구성** 페이지에서 **새로 만들기를** 클릭 한 다음 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-131">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fbb57-132">사이트에 배포 된 모든 영구 채팅 서버 풀에 구성을 적용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-132">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="fbb57-133">구성을 특정 영구 채팅 서버 풀에 적용 하려면 **풀 구성을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-133">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="fbb57-134">**사이트 선택**에서 영구 채팅 서버 사이트 구성에 대해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-134">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="fbb57-135">**새 영구 채팅 구성**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-135">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="fbb57-p105">**이름**에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="fbb57-p106">**기본 채팅 기록**에서 첫 번째 요청 시 각 채팅방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="fbb57-141">영구 채팅 서버는 이러한 메시지를 메모리에 캐시 하므로이 번호를 늘리면 더 많은 메시지가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-141">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="fbb57-142">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-142">You can always access historical content by search.</span></span> <span data-ttu-id="fbb57-143">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-143">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="fbb57-p108">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 채팅방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="fbb57-147">**참가자 업데이트 제한**에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-147">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="fbb57-148">영구 채팅 서버는 연결 된 사용자 수가이 번호에 도달할 때까지 모든 참가자에 게 대화방에 연결 된 명단 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-148">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="fbb57-149">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-149">By default, the number is 75.</span></span> <span data-ttu-id="fbb57-150">이 제한은 영구 채팅 서버에서 대화방에 있는 사용자에 대 한 연결 된 클라이언트에 게 명단 업데이트 보내기를 중지 하는 특정 방에 대 한 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-150">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="fbb57-151">(선택 사항). **채팅방 관리 url**에서 채팅방 관리 url을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-151">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="fbb57-152">웹 기반 사용자 지정 룸 관리의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-152">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="fbb57-153">공간 관리를 사용자 지정할 필요가 없고 기본 설정을 사용 하는 경우에는이 옵션을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-153">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="fbb57-154">URL이 설정 된 후에는 내부 및 외부 대화방 관리 URL로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-154">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="fbb57-155">회의실 만들기 환경을 사용자 지정 하 고 특정 비즈니스 워크플로를 포함 하려는 경우 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 회의실 관리 솔루션을 빌드하고 여기에 URL을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-155">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="fbb57-156">이 URL은 클라이언트로 전송되므로 사용자가 채팅방을 보거나 만들려고 할 때 사용자 지정 채팅방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-156">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="fbb57-157">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-157">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="fbb57-158">특정 영구 채팅 서버 풀에 대해 영구 채팅 옵션을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="fbb57-158">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="fbb57-159">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-159">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fbb57-160">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-160">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="fbb57-161">왼쪽 탐색 메뉴에서 **영구 채팅**을 클릭하고 **영구 채팅 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-161">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="fbb57-162">**영구 채팅 구성** 페이지에서 **새로 만들기**를 클릭하고 **풀 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-162">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="fbb57-163">**서비스 선택**에서 구성할 영구 채팅 서버 풀과 연결 된 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-163">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="fbb57-164">**새 영구 채팅 구성**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-164">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="fbb57-p112">**이름**에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 풀 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p112">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="fbb57-p113">**기본 채팅 기록**에서 첫 번째 요청 시 각 채팅방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p113">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="fbb57-170">영구 채팅 서버는 이러한 메시지를 메모리에 캐시 하므로이 번호를 늘리면 더 많은 메시지가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-170">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="fbb57-171">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-171">You can always access historical content by search.</span></span> <span data-ttu-id="fbb57-172">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-172">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="fbb57-p115">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 채팅방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-p115">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="fbb57-176">**참가자 업데이트 제한**에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-176">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="fbb57-177">영구 채팅 서버는 연결 된 사용자 수가이 번호에 도달할 때까지 모든 참가자에 게 대화방에 연결 된 명단 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-177">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="fbb57-178">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-178">By default, the number is 75.</span></span> <span data-ttu-id="fbb57-179">이 제한은 영구 채팅 서버에서 대화방에 있는 사용자에 대 한 연결 된 클라이언트에 게 명단 업데이트 보내기를 중지 하는 특정 방에 대 한 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-179">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="fbb57-180">**채팅방 관리 URL**에서 채팅방 관리 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-180">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="fbb57-181">이 URL은 웹 기반 채팅방 관리 배포를 위한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-181">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="fbb57-182">공간 관리를 사용자 지정할 필요가 없고 기본 설정을 사용 하는 경우에는이 옵션을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-182">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="fbb57-183">회의실 만들기 환경을 사용자 지정 하 고 특정 비즈니스 워크플로를 포함 하려는 경우 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 회의실 관리 솔루션을 빌드하고 여기에 URL을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-183">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="fbb57-184">이 URL은 클라이언트로 전송되므로 사용자가 채팅방을 보거나 만들려고 할 때 사용자 지정 채팅방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-184">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="fbb57-185">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb57-185">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fbb57-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbb57-186">See also</span></span>

<span data-ttu-id="fbb57-187">영구 채팅 서버 기능 및 기능에 대 한 자세한 내용은 비즈니스용 skype Server 2015의 영구 채팅 서버에 [대 한 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), 비즈니스용 [skype Server 2015의 영구 채팅 서버 배포](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)및 비즈니스용 [Skype Server 2015에서 영구 채팅 서버 관리](../../manage/persistent-chat/persistent-chat.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbb57-187">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

