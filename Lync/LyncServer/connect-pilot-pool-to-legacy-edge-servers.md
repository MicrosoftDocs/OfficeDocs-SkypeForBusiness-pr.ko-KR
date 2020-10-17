---
title: 레거시 에지 서버에 파일럿 풀 연결
description: 파일럿 풀을 레거시에 지 서버에 연결 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550274"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="8cf1a-103">레거시 에지 서버에 파일럿 풀 연결</span><span class="sxs-lookup"><span data-stu-id="8cf1a-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cf1a-104">_**마지막으로 수정 된 항목:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8cf1a-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8cf1a-105">Lync Server 2013를 배포한 후에는 사이트에 대 한 페더레이션 경로를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="8cf1a-106">Lync Server 2010에서 사용 중인 페더레이션 경로를 사용 하려면이 경로를 사용 하도록 Lync Server 2013을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="8cf1a-107">Lync server 2013 사이트에서 Lync Server 2010 배포의 디렉터 및에 지 서버를 사용할 수 있도록 설정 하려면 토폴로지 작성기를 사용 하 여 레거시에 지 풀을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="8cf1a-108">토폴로지 작성기를 사용하여 레거시 에지 풀을 연결하려면</span><span class="sxs-lookup"><span data-stu-id="8cf1a-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="8cf1a-109">**토폴로지 작성기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="8cf1a-110">**Lync Server** 노드 바로 아래에 있는 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="8cf1a-111">**동작** 메뉴에서 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="8cf1a-112">왼쪽 창에서 **페더레이션 경로**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="8cf1a-113">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 lync server 2010 디렉터를 선택 하거나, 디렉터가 없는 경우 Lync Server 2010에 지 서버를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="8cf1a-114">![속성 편집, 페더레이션 경로 페이지](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "속성 편집, 페더레이션 경로 페이지")</span><span class="sxs-lookup"><span data-stu-id="8cf1a-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="8cf1a-115">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="8cf1a-116">토폴로지 작성기의 Lync Server 2013 노드에서 **Standard edition Server** 또는 **Enterprise Edition 프런트 엔드 풀**로 이동 하 고 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="8cf1a-117">**연결**에서 **에지 풀 연결(미디어 구성 요소)** 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="8cf1a-118">목록에서 레거시 에지 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="8cf1a-119">![속성 편집 대화 상자, 레거시에 지 선택](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "속성 편집 대화 상자, 레거시에 지 선택")</span><span class="sxs-lookup"><span data-stu-id="8cf1a-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="8cf1a-120">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="8cf1a-121">**토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="8cf1a-122">**동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="8cf1a-123">**게시 마법사**가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf1a-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

