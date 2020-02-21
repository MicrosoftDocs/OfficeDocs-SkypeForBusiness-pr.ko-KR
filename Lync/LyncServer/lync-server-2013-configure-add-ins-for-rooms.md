---
title: 'Lync Server 2013: 대화방에 대 한 추가 기능 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca916731f34bf08e59ae2ba281a1c6d723b46ae8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="92e5a-102">Lync Server 2013에서 대화방에 대 한 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="92e5a-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92e5a-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="92e5a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="92e5a-104">Lync Server 2013 제어판에서는 **영구** 채팅 페이지의 **추가 기능** 섹션을 사용 하 여 url을 영구 채팅방과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="92e5a-105">이러한 Url은 대화 확장 창의 대화방에 있는 Lync 2013 클라이언트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="92e5a-106">관리자가 등록 된 추가 기능 목록에 추가 기능을 추가 하 고, 사용자가 Lync 2013 클라이언트에서이 업그레이드를 볼 수 있도록 대화방 관리자/작성자가 등록 된 추가 기능 중 하 나와 대화방을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="92e5a-107">추가 기능은 방 내의 환경을 확장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="92e5a-108">일반적인 추가 기능에는 주식 시세 표시를 대화방에 게시할 때 가로채기를 가로채는 Silverlight 응용 프로그램을 가리키는 URL을 포함할 수 있으며,이를 통해 확장성 창에 주식 기록을 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="92e5a-109">다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="92e5a-110">채팅방의 추가 기능을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="92e5a-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="92e5a-111">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92e5a-112">**시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="92e5a-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92e5a-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="92e5a-114">Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="92e5a-115">자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92e5a-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="92e5a-116">왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **추가 기능**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="92e5a-117">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="92e5a-118">**추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="92e5a-119">**서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="92e5a-120">추가 기능은 풀 간에 이동하거나 서로 다른 풀 간에 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="92e5a-121">**새 추가 기능**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="92e5a-122">**이름**에서 새 추가 기능의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="92e5a-p106">**URL**에서 추가 기능과 연결할 URL을 지정합니다. http 및 https 프로토콜의 URL만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="92e5a-125">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92e5a-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92e5a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92e5a-126">See Also</span></span>


[<span data-ttu-id="92e5a-127">Lync Server 2013 관리 도구 열기</span><span class="sxs-lookup"><span data-stu-id="92e5a-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="92e5a-128">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="92e5a-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

