---
title: 'Lync Server 2013: 영구 채팅 서버 풀에 대해 또는 전역적으로 영구 채팅 서버 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed79d1144c1ccb7abeac8dcf7d1f4d44c63e93e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="f6182-102">Lync Server 2013에서 영구 채팅 서버 풀에 대해 또는 전역적으로 영구 채팅 서버 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="f6182-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6182-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f6182-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f6182-104">Lync Server 2013 제어판에서 **영구** 채팅 페이지의 영구 채팅 **구성** 섹션을 사용 하 여 모든 영구 채팅 서버 풀 또는 특정 영구 채팅 서버 풀에 적용 되는 영구 채팅 설정을 전역적으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6182-105">영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="f6182-106">자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6182-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="f6182-107">영구 채팅 옵션을 전역적으로 구성</span><span class="sxs-lookup"><span data-stu-id="f6182-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="f6182-108">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6182-109">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="f6182-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6182-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6182-111">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="f6182-112">자세한 내용은 배포 설명서의 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6182-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="f6182-113">왼쪽 탐색 메뉴에서 **영구 채팅**을 클릭하고 **영구 채팅 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="f6182-114">**영구 채팅 구성** 페이지에서 **새로 만들기를** 클릭 한 다음 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6182-115">사이트에 배포 된 모든 영구 채팅 서버 풀에 구성을 적용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="f6182-116">구성을 특정 영구 채팅 서버 풀에 적용 하려면 <STRONG>풀 구성을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="f6182-117">**사이트 선택**에서 영구 채팅 서버 사이트 구성에 대해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="f6182-118">**새 영구 채팅 구성**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="f6182-p105">**이름**에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="f6182-p106">**기본 채팅 기록**에서 첫 번째 요청 시 각 채팅방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f6182-124">영구 채팅 서버는 이러한 메시지를 메모리에 캐시 하므로이 번호를 늘리면 더 많은 메시지가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="f6182-125">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-125">You can always access historical content by search.</span></span> <span data-ttu-id="f6182-126">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="f6182-p108">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 채팅방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f6182-130">이 설정은 사용자 지정 응용 프로그램 또는 이전 그룹에서 Office Communications Server 2007 R2&nbsp;그룹 채팅 서버 또는 Lync server 2010를 사용 하 여 클라이언트를 채팅 하기 때문에 서버에서 적용 됩니다. 그룹 채팅을 통해 룸에 파일을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="f6182-131">Lync 2013 클라이언트에는 파일 업로드/다운로드 기능이 없기 때문에 순수한 Lync 2013 배포 또는 Lync 2013 클라이언트를 사용 하는 경우 영구 채팅 서버 채팅방에 파일을 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="f6182-132">**참가자 업데이트 제한**에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="f6182-133">영구 채팅 서버는 연결 된 사용자 수가이 번호에 도달할 때까지 모든 참가자에 게 대화방에 연결 된 명단 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="f6182-134">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-134">By default, the number is 75.</span></span> <span data-ttu-id="f6182-135">이 제한은 영구 채팅 서버에서 대화방에 있는 사용자에 대 한 연결 된 클라이언트에 게 명단 업데이트 보내기를 중지 하는 특정 방에 대 한 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="f6182-p111">원하는 경우 **채팅방 관리 URL**에서 채팅방 관리 URL을 선택합니다. 이 URL은 웹 기반 사용자 지정 채팅방 관리를 위한 URL입니다. 채팅방 관리를 사용자 지정할 필요가 없으며 기본 설정만 사용하는 경우에는 이 옵션을 비워 둡니다. 설정된 URL은 내부 및 외부 채팅방 관리 URL로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="f6182-140">회의실 만들기 환경을 사용자 지정 하 고 특정 비즈니스 워크플로를 포함 하려는 경우 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 회의실 관리 솔루션을 빌드하고 여기에 URL을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="f6182-141">이 URL은 클라이언트로 전송되므로 사용자가 채팅방을 보거나 만들려고 할 때 사용자 지정 채팅방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="f6182-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="f6182-143">특정 영구 채팅 서버 풀에 대해 영구 채팅 옵션을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="f6182-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="f6182-144">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6182-145">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="f6182-146">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6182-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6182-147">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="f6182-148">자세한 내용은 배포 설명서의 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6182-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="f6182-149">왼쪽 탐색 메뉴에서 **영구 채팅**을 클릭하고 **영구 채팅 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="f6182-150">**영구 채팅 구성** 페이지에서 **새로 만들기**를 클릭하고 **풀 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="f6182-151">**서비스 선택**에서 구성할 영구 채팅 서버 풀과 연결 된 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="f6182-152">**새 영구 채팅 구성**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="f6182-p115">**이름**에서 새 구성 설정의 이름을 지정합니다. 기본적으로 사이트 풀 이름은 이미 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="f6182-p116">**기본 채팅 기록**에서 첫 번째 요청 시 각 채팅방에 대해 처리할 채팅 메시지 수를 정의합니다. 기본값은 30입니다. 이 설정은 전역 기본값이며, 관리자는 범주별로 채팅 기록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f6182-158">영구 채팅 서버는 이러한 메시지를 메모리에 캐시 하므로이 번호를 늘리면 더 많은 메시지가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="f6182-159">항상 검색을 통해 기록 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-159">You can always access historical content by search.</span></span> <span data-ttu-id="f6182-160">기본값은 단순히 채팅방 연결 시 처음 표시되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="f6182-p118">**최대 파일 크기(KB)** 에서 각 채팅 기록의 최대 파일 크기를 선택합니다. 기본값은 20MB(20,000KB)입니다. 이 값은 해당하는 **범주** 설정에 의해 파일 업로드가 사용하도록 설정된 시스템의 각 채팅방에 업로드할 수 있는 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f6182-164">이 설정은 사용자 지정 응용 프로그램 또는 이전 그룹 채팅 클라이언트 (Office Communications Server 2007 R2&nbsp;그룹 채팅 서버 또는 Lync server 2010, 그룹 채팅)가 채팅방에 파일을 게시할 수 있기 때문에 서버에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="f6182-165">Lync 2013 클라이언트에는 파일 업로드/다운로드 기능이 없기 때문에 순수한 Lync 2013 배포 또는 Lync 2013 클라이언트를 사용 하는 경우 영구 채팅 서버 채팅방에 파일을 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="f6182-166">**참가자 업데이트 제한**에서 참가자 업데이트에 대한 제한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="f6182-167">영구 채팅 서버는 연결 된 사용자 수가이 번호에 도달할 때까지 모든 참가자에 게 대화방에 연결 된 명단 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="f6182-168">기본값은 75입니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-168">By default, the number is 75.</span></span> <span data-ttu-id="f6182-169">이 제한은 영구 채팅 서버에서 대화방에 있는 사용자에 대 한 연결 된 클라이언트에 게 명단 업데이트 보내기를 중지 하는 특정 방에 대 한 최대 참가자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="f6182-p121">**채팅방 관리 URL**에서 채팅방 관리 URL을 선택합니다. 이 URL은 웹 기반 채팅방 관리 배포를 위한 URL입니다. 채팅방 관리를 사용자 지정할 필요가 없으며 기본 설정만 사용하는 경우에는 이 옵션을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="f6182-173">회의실 만들기 환경을 사용자 지정 하 고 특정 비즈니스 워크플로를 포함 하려는 경우 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 회의실 관리 솔루션을 빌드하고 여기에 URL을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="f6182-174">이 URL은 클라이언트로 전송되므로 사용자가 채팅방을 보거나 만들려고 할 때 사용자 지정 채팅방 관리 솔루션으로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="f6182-175">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6182-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

