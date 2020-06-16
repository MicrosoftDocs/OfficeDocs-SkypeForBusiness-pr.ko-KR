---
title: 레거시 에지 서버에 파일럿 풀 연결
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="f992b-102">레거시 에지 서버에 파일럿 풀 연결</span><span class="sxs-lookup"><span data-stu-id="f992b-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f992b-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f992b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f992b-104">Lync Server 2013을 배포한 후에는이 사이트에 대 한 페더레이션 경로가 구성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="f992b-105">Office Communications Server 2007 R2에서 사용 중인 페더레이션 경로를 사용 하려면이 경로를 사용 하도록 Lync Server 2013을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="f992b-106">Lync Server 2013 사이트에서 BackCompatSite의 디렉터 및에 지 서버를 사용할 수 있도록 설정 하려면 토폴로지 작성기를 사용 하 여 레거시에 지 풀을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="f992b-107">토폴로지 작성기를 사용하여 레거시 에지 풀을 연결하려면</span><span class="sxs-lookup"><span data-stu-id="f992b-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="f992b-108">토폴로지 작성기에서 파일럿 풀을 열려면</span><span class="sxs-lookup"><span data-stu-id="f992b-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="f992b-109">Lync Server 2013 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="f992b-110">**동작** 메뉴에서 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="f992b-111">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 Office Communications server 2007 r2 디렉터 또는 디렉터를 나열 하지 않은 경우 Office communications Server 2007 r2에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="f992b-112">![속성 편집 대화 상자, 페더레이션 경로 페이지](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로 페이지")</span><span class="sxs-lookup"><span data-stu-id="f992b-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="f992b-113">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="f992b-114">토폴로지 작성기의 Lync Server 2013 노드에서 **Standard edition Server** 또는 **Enterprise Edition 프런트 엔드 풀**로 이동 하 고 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="f992b-115">**연결**에서 **에지 풀 연결(미디어 구성 요소)** 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="f992b-116">목록에서 BackCompatSite에 대한 에지 서버 인터페이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="f992b-117">![속성 편집 대화 상자, 일반 페이지](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")</span><span class="sxs-lookup"><span data-stu-id="f992b-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="f992b-118">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="f992b-119">**토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="f992b-120">**동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="f992b-121">**게시 마법사**가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f992b-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

