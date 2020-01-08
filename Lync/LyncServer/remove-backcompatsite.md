---
title: BackCompatSite 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="f2d0e-102">BackCompatSite 제거</span><span class="sxs-lookup"><span data-stu-id="f2d0e-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d0e-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f2d0e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f2d0e-104">모든 풀을 비활성화 하 고 모든 Edge 서버를 제거한 후에는 토폴로지 작성기 병합 마법사를 실행 하 여 **BackCompatSite**를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="f2d0e-105">토폴로지 작성기에서 백 호환성 사이트를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="f2d0e-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="f2d0e-106">토폴로지 작성기에서 기존 배포를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="f2d0e-107">**작업** 메뉴에서 **2007 R2 토폴로지 병합**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="f2d0e-108">계속하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="f2d0e-109">**레거시 Edge 지정** 페이지에서 Edge 서버 목록이 비어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="f2d0e-110">목록이 비어 있지 않으면 **제거** 단추를 사용 하 여 모든 레거시 Edge 서버를 제거 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="f2d0e-111">![토폴로지 병합 마법사, Edge 설정 페이지](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "병합 마법사 지정, Edge 설정 페이지로 지정")</span><span class="sxs-lookup"><span data-stu-id="f2d0e-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="f2d0e-112">**내부 SIP 포트 설정 지정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="f2d0e-113">**요약** 페이지에서 **다음** 을 클릭 하 여 기존 사이트 제거를 위해 토폴로지 병합을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="f2d0e-114">**상태** 열에서 값이 **성공적** 인지 확인 한 다음 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="f2d0e-115">토폴로지 작성기의 왼쪽 창에서 BackCompatSite를 확장 하 고 서버가 나열 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="f2d0e-116">**BackCompatSite**를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="f2d0e-117">**토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="f2d0e-118">**작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="f2d0e-119">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d0e-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

