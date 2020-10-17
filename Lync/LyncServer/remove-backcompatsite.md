---
title: BackCompatSite 제거
description: BackCompatSite을 제거 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570274"
---
# <a name="remove-backcompatsite"></a><span data-ttu-id="1e29e-103">BackCompatSite 제거</span><span class="sxs-lookup"><span data-stu-id="1e29e-103">Remove BackCompatSite</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e29e-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1e29e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1e29e-105">모든 풀이 비활성화되고 모든 에지 서버가 제거된 후 토폴로지 작성기 병합 마법사를 실행하여 **BackCompatSite**를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-105">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="1e29e-106">토폴로지 작성기에서 BackCompat 사이트를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="1e29e-106">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="1e29e-107">토폴로지 작성기에서 기존 배포를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-107">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="1e29e-108">**동작** 메뉴에서 **2007 R2 토폴로지 병합**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-108">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="1e29e-109">계속하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-109">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="1e29e-p101">**레거시 에지 지정** 페이지에서 에지 서버의 목록이 비어 있는지 확인합니다. 목록이 비어 있지 않으면 **제거** 단추를 사용하여 모든 레거시 에지 서버를 제거한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="1e29e-112">![토폴로지 병합 마법사,에 지 설정 지정 페이지](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "토폴로지 병합 마법사,에 지 설정 지정 페이지")</span><span class="sxs-lookup"><span data-stu-id="1e29e-112">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="1e29e-113">**내부 SIP 포트 설정 지정** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-113">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="1e29e-114">**요약** 페이지에서 **다음** 을 클릭 하 여 토폴로지 병합을 시작 하 고 레거시 사이트를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-114">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="1e29e-115">**상태** 열에서 값이 **성공**인지 확인한 다음 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-115">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="1e29e-116">토폴로지 작성기의 왼쪽 창에서 BackCompatSite를 확장하고 나열된 서버가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-116">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="1e29e-117">**BackCompatSite**를 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-117">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="1e29e-118">**토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-118">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="1e29e-119">**동작** 메뉴에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-119">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="1e29e-120">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e29e-120">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

