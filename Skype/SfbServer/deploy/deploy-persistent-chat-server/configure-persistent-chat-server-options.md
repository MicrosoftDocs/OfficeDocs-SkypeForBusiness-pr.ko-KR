---
title: 영구 채팅 서버 구성 옵션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: '요약: 비즈니스용 Skype 서버 2015에서 전역, 사이트 또는 풀 수준으로 영구 채팅 서버 옵션을 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: c842d0c0790f7aad18dda6f3f9cabe5382eb4f33
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793566"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="89f29-103">영구 채팅 서버 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="89f29-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89f29-104">**요약:** 비즈니스용 Skype 서버 2015에서 전역, 사이트 또는 풀 수준으로 영구 채팅 서버 옵션을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="89f29-105">전역 또는 사이트 내의 모든 풀 또는 사이트 내의 특정 풀에 전체적으로 적용할 수 있는 영구 채팅 서버에 대해 여러 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="89f29-106">영구 채팅 서버 옵션에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="89f29-107">기본 채팅 기록입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-107">Default Chat History.</span></span> <span data-ttu-id="89f29-108">처음 요청할 때 각 채팅방에서 사용할 수 있는 채팅 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="89f29-109">전역 기본값은 채팅 메시지 30 개입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="89f29-110">최대 파일 크기.</span><span class="sxs-lookup"><span data-stu-id="89f29-110">Maximum File Size.</span></span> <span data-ttu-id="89f29-111">채팅방에서 업로드 하거나 다운로드할 수 있는 최대 파일 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-111">The maximum size of a file that can be uploaded to or downloaded from a room.</span></span> <span data-ttu-id="89f29-112">전역 기본값은 20MB입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-112">The global default is 20MB.</span></span>
    
- <span data-ttu-id="89f29-113">참가자 업데이트 제한.</span><span class="sxs-lookup"><span data-stu-id="89f29-113">Participant Update Limit.</span></span> <span data-ttu-id="89f29-114">영구 채팅에서 명단 업데이트를 보내는 특정 채팅방의 최대 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="89f29-115">전역 기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-115">The global default is 75.</span></span>
    
- <span data-ttu-id="89f29-116">채팅방 관리 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-116">Room Management URL.</span></span> <span data-ttu-id="89f29-117">사용자 지정 채팅방 관리에 사용 되는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="89f29-118">이 설정을 통해 사용자 지정 회의실 관리 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="89f29-119">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="89f29-120">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="89f29-121">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="89f29-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="89f29-122">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="89f29-123">영구 채팅 서버 전역 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="89f29-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="89f29-124">영구 채팅 서버 전역 옵션을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="89f29-125">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89f29-126">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="89f29-127">왼쪽 탐색 메뉴에서 **영구 채팅**을 클릭하고 **영구 채팅 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="89f29-128">**영구 채팅 구성** 페이지에서 **새로 만들기를** 클릭 한 다음 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="89f29-129">사이트에 배포 된 모든 영구 채팅 서버 풀에 구성을 적용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="89f29-130">구성을 특정 영구 채팅 서버 풀에 적용 하려면 **풀 구성을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="89f29-131">**사이트 선택**에서 영구 채팅 서버 사이트 구성에 대해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="89f29-132">**새 영구 채팅 구성**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="89f29-p108">**이름**에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="89f29-p109">**기본 채팅 기록**에서 첫 번째 요청 시 각 채팅방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="89f29-138">영구 채팅 서버는 이러한 메시지를 메모리에 캐시 하므로이 번호를 늘리면 더 많은 메시지가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="89f29-139">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-139">You can always access historical content by search.</span></span> <span data-ttu-id="89f29-140">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="89f29-p111">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 채팅방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="89f29-144">**참가자 업데이트 제한**에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="89f29-145">영구 채팅 서버는 연결 된 사용자 수가이 번호에 도달할 때까지 모든 참가자에 게 대화방에 연결 된 명단 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="89f29-146">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-146">By default, the number is 75.</span></span> <span data-ttu-id="89f29-147">이 제한은 영구 채팅 서버에서 대화방에 있는 사용자에 대 한 연결 된 클라이언트에 게 명단 업데이트 보내기를 중지 하는 특정 방에 대 한 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="89f29-148">(선택 사항). **채팅방 관리 url**에서 채팅방 관리 url을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="89f29-149">웹 기반 사용자 지정 룸 관리의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="89f29-150">공간 관리를 사용자 지정할 필요가 없고 기본 설정을 사용 하는 경우에는이 옵션을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="89f29-151">URL이 설정 된 후에는 내부 및 외부 대화방 관리 URL로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="89f29-152">회의실 만들기 환경을 사용자 지정 하 고 특정 비즈니스 워크플로를 포함 하려는 경우 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 회의실 관리 솔루션을 빌드하고 여기에 URL을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="89f29-153">이 URL은 클라이언트로 전송되므로 사용자가 채팅방을 보거나 만들려고 할 때 사용자 지정 채팅방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="89f29-154">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="89f29-155">특정 영구 채팅 서버 풀에 대 한 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="89f29-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="89f29-156">특정 영구 채팅 서버 풀에 대 한 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="89f29-157">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89f29-158">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="89f29-159">왼쪽 탐색 메뉴에서 **영구 채팅**을 클릭하고 **영구 채팅 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="89f29-160">**영구 채팅 구성** 페이지에서 **새로 만들기**를 클릭하고 **풀 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="89f29-161">**서비스 선택**에서 구성할 영구 채팅 서버 풀과 연결 된 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="89f29-162">**새 영구 채팅 구성**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="89f29-p115">**이름**에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 풀 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="89f29-p116">**기본 채팅 기록**에서 첫 번째 요청 시 각 채팅방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="89f29-168">영구 채팅 서버는 이러한 메시지를 메모리에 캐시 하므로이 번호를 늘리면 더 많은 메시지가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="89f29-169">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-169">You can always access historical content by search.</span></span> <span data-ttu-id="89f29-170">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="89f29-p118">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 채팅방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="89f29-174">**참가자 업데이트 제한**에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="89f29-175">영구 채팅 서버는 연결 된 사용자 수가이 번호에 도달할 때까지 모든 참가자에 게 대화방에 연결 된 명단 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="89f29-176">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-176">By default, the number is 75.</span></span> <span data-ttu-id="89f29-177">이 제한은 영구 채팅 서버에서 대화방에 있는 사용자에 대 한 연결 된 클라이언트에 게 명단 업데이트 보내기를 중지 하는 특정 방에 대 한 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="89f29-178">**채팅방 관리 URL**에서 채팅방 관리 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="89f29-179">이 URL은 웹 기반 채팅방 관리 배포를 위한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="89f29-180">공간 관리를 사용자 지정할 필요가 없고 기본 설정을 사용 하는 경우에는이 옵션을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="89f29-181">회의실 만들기 환경을 사용자 지정 하 고 특정 비즈니스 워크플로를 포함 하려는 경우 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 회의실 관리 솔루션을 빌드하고 여기에 URL을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="89f29-182">이 URL은 클라이언트로 전송되므로 사용자가 채팅방을 보거나 만들려고 할 때 사용자 지정 채팅방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="89f29-183">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89f29-183">Click **Commit**.</span></span>
    

