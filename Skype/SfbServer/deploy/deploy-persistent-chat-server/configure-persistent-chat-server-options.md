---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 옵션 구성
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
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: '요약: 비즈니스용 Skype 서버 2015에서 전역, 사이트 또는 풀 수준에서 영구 채팅 서버 옵션을 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 9c0b6d5e03b9bc4f7d955ea0dae3e1c45b14ada3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802128"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="ccf1e-103">비즈니스용 Skype 서버 2015에서 영구 채팅 서버 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ccf1e-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ccf1e-104">**요약:** 비즈니스용 Skype 서버 2015에서 전역, 사이트 또는 풀 수준에서 영구 채팅 서버 옵션을 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ccf1e-105">영구 채팅 서버에 대해 전역적으로, 사이트 내의 모든 풀 또는 사이트 내의 특정 풀에 적용할 수 있는 몇 가지 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="ccf1e-106">영구 채팅 서버 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="ccf1e-107">기본 채팅 기록입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-107">Default Chat History.</span></span> <span data-ttu-id="ccf1e-108">첫 번째 요청 시 각 대화방에 사용할 수 있는 채팅 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="ccf1e-109">전역 기본값은 채팅 메시지 30개입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="ccf1e-110">최대 파일 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-110">Maximum File Size.</span></span> <span data-ttu-id="ccf1e-111">방에 업로드하거나 방에서 다운로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-111">The maximum size of a file that can be uploaded to or downloaded from a room.</span></span> <span data-ttu-id="ccf1e-112">전역 기본값은 20MB입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-112">The global default is 20MB.</span></span>
    
- <span data-ttu-id="ccf1e-113">참가자 업데이트 제한.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-113">Participant Update Limit.</span></span> <span data-ttu-id="ccf1e-114">영구 채팅에서 로스터 업데이트를 보낼 주어진 대화방의 최대 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="ccf1e-115">전역 기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-115">The global default is 75.</span></span>
    
- <span data-ttu-id="ccf1e-116">방 관리 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-116">Room Management URL.</span></span> <span data-ttu-id="ccf1e-117">사용자 지정 대화방 관리에 사용되는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="ccf1e-118">이 설정을 사용하면 사용자 지정 방 관리 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="ccf1e-119">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ccf1e-120">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="ccf1e-121">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="ccf1e-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ccf1e-122">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="ccf1e-123">영구 채팅 서버 전역 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ccf1e-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="ccf1e-124">영구 채팅 서버 전역 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="ccf1e-125">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ccf1e-126">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ccf1e-127">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="ccf1e-128">영구 채팅 구성 **페이지에서** 새로  고치기 및 사이트 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccf1e-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ccf1e-129">사이트에 배포된 모든 영구 채팅 서버 풀에 구성을 적용하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="ccf1e-130">**구성을** 특정 영구 채팅 서버 풀에 적용하려면 풀 구성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="ccf1e-131">사이트 **선택에서** 영구 채팅 서버 사이트 구성에 대해 구성할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="ccf1e-132">**새 영구적 채팅 구성** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="ccf1e-p108">**이름** 에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="ccf1e-p109">**기본 채팅 기록** 에서 첫 번째 요청 시 각 방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="ccf1e-138">영구 채팅 서버는 이러한 메시지를 메모리에 캐시하기 때문에 이 수를 늘리면 더 많은 메시지가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="ccf1e-139">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-139">You can always access historical content by search.</span></span> <span data-ttu-id="ccf1e-140">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="ccf1e-p111">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 대화방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="ccf1e-144">**참가자 업데이트 제한** 에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="ccf1e-145">영구 채팅 서버는 연결된 사용자 수가 이 수에 도달할 때까지 모든 참가자에게 대화방에 연결된 사용자명 정보를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="ccf1e-146">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-146">By default, the number is 75.</span></span> <span data-ttu-id="ccf1e-147">이 제한은 영구 채팅 서버가 대화방에 있는 사용자에 대한 연결된 클라이언트에 대한 로스터 업데이트 전송을 중지하는 해당 채팅방의 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="ccf1e-148">(선택 사항) 방 **관리 URL에서** 방 관리 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="ccf1e-149">웹 기반 사용자 지정 방 관리의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="ccf1e-150">방 관리를 사용자 지정할 필요가 없는 경우 기본 설정만 사용하는 경우 이 옵션을 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="ccf1e-151">URL을 설정한 후 내부 및 외부 방 관리 URL로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="ccf1e-152">채팅방 만들기 환경을 사용자 지정하고 특정 비즈니스 워크플로를 포함하려는 경우 영구 채팅 서버 SDK(소프트웨어 개발 키트)를 사용하여 사용자 지정 채팅방 관리 솔루션을 작성하고 원하는 곳에 호스팅한 다음 URL을 여기에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="ccf1e-153">이 URL은 클라이언트로 전송되므로 사용자가 방을 보거나 만들려고 할 때 사용자 지정 방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="ccf1e-154">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="ccf1e-155">특정 영구 채팅 서버 풀에 대한 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ccf1e-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="ccf1e-156">특정 영구 채팅 서버 풀에 대한 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="ccf1e-157">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ccf1e-158">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 열고 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ccf1e-159">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **영구적 채팅 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="ccf1e-160">**영구적 채팅 구성** 페이지에서 **새로 만들기** 를 클릭하고 **풀 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="ccf1e-161">서비스 **선택에서** 구성할 영구 채팅 서버 풀과 연결된 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="ccf1e-162">**새 영구적 채팅 구성** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="ccf1e-p115">**이름** 에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 풀 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="ccf1e-p116">**기본 채팅 기록** 에서 첫 번째 요청 시 각 방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="ccf1e-168">영구 채팅 서버는 이러한 메시지를 메모리에 캐시하기 때문에 이 수를 늘리면 더 많은 메시지가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="ccf1e-169">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-169">You can always access historical content by search.</span></span> <span data-ttu-id="ccf1e-170">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="ccf1e-p118">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 대화방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="ccf1e-174">**참가자 업데이트 제한** 에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="ccf1e-175">영구 채팅 서버는 연결된 사용자 수가 이 수에 도달할 때까지 모든 참가자에게 대화방에 연결된 사용자명 정보를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="ccf1e-176">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-176">By default, the number is 75.</span></span> <span data-ttu-id="ccf1e-177">이 제한은 영구 채팅 서버가 대화방에 있는 사용자에 대한 연결된 클라이언트에 대한 로스터 업데이트 전송을 중지하는 해당 채팅방의 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="ccf1e-178">**방 관리 URL** 에서 방 관리 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="ccf1e-179">이 URL은 웹 기반 방 관리 배포를 위한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="ccf1e-180">방 관리를 사용자 지정할 필요가 없는 경우 기본 설정만 사용하는 경우 이 옵션을 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="ccf1e-181">채팅방 만들기 환경을 사용자 지정하고 특정 비즈니스 워크플로를 포함하려는 경우 영구 채팅 서버 SDK(소프트웨어 개발 키트)를 사용하여 사용자 지정 채팅방 관리 솔루션을 작성하고 원하는 곳에 호스팅한 다음 URL을 여기에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="ccf1e-182">이 URL은 클라이언트로 전송되므로 사용자가 방을 보거나 만들려고 할 때 사용자 지정 방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="ccf1e-183">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf1e-183">Click **Commit**.</span></span>
    

