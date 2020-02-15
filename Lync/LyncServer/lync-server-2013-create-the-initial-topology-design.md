---
title: 'Lync Server 2013: 초기 토폴로지 디자인 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed95696dc0acad9030615f8a031672f8abf3a136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="a251d-102">Lync Server 2013에 대 한 초기 토폴로지 디자인 만들기</span><span class="sxs-lookup"><span data-stu-id="a251d-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a251d-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a251d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a251d-104">Lync Server 2013, 계획 도구 설치가 완료 되 면 계획 도구를 시작 하 고 제안 된 Lync Server 2013 인프라 디자인을 시작할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a251d-105">계획 도구는 사이트 및 토폴로지를 디자인할 때 결정 과정을 안내 하는 자세한 가이드가 포함 된 마법사 기반 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="a251d-106">이 항목은 소모적인 가이드가 아니며, 디자인 세션에서 계획 도구를 사용 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="a251d-107">계획 도구 사용을 시작 하 고 초기 디자인을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a251d-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="a251d-108">Lync Server 2013, 계획 도구 시작: **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **계획 도구**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="a251d-109">계획 도구를 시작한 후 **에는 Microsoft Lync Server에 대 한 계획 도구 2013** 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="a251d-110">다음 옵션 중 하나를 선택 하 여 디자인을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="a251d-111">**옵션 1:**    **시작 단추를** 클릭 하면 기준을 정의 하기 위한 적절 한 선택과 관련 된 특정 일련의 인터뷰 질문이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="a251d-112">초기 면접 **시작** 인터뷰 섹션을 완료 한 후에는 사이트 아키텍처를 정의 하는 **디자인 사이트로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="a251d-113">이 옵션을 완료 하려면 3 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="a251d-114">**옵션 2: 디자인 사이트**   시작 페이지에서 **디자인 사이트** 를 클릭 하면 **시작** 섹션에 나와 있는 인터뷰 질문이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="a251d-115">**시작** 섹션의 인터뷰 질문에 응답 하 여 수집 된 정보는이 옵션을 사용 하 여 기본값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="a251d-116">**디자인 사이트**를 클릭 하면 숙련 된 디자이너가 초기 인터뷰를 우회 하 고 필요에 따라 **중앙 사이트** 시작 페이지에서 기본값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="a251d-117">이 옵션을 완료 하려면 3-5 단계를 건너뛰고 6 단계부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="a251d-118">**옵션 3: 저장 된 토폴로지**   표시 이전에 계획 도구를 사용 하 여 토폴로지를 완료 하 고 저장 한 경우에는 이러한 단계를 대부분 건너뛰고 토폴로지를 열고 표시 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="a251d-119">또한 토폴로지를 변경 하 고 업데이트 한 후 다시 저장 한 다음 Microsoft Excel 이나 Microsoft Visio로 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="a251d-120">이 옵션을 완료 하려면 3-12 단계를 건너뛰고 13 단계부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="a251d-121">**시작** 을 클릭 하 여 Lync Server 2013 토폴로지 디자인을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="a251d-122">디자인에 적합 한 조건을 선택 하 여 각 섹션에 응답 한 **후 다음을 클릭 하** 여 다음 마법사 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="a251d-123">이전 페이지를 변경 하려면 **뒤로** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a251d-124">각 페이지에는 선택 기준에 대 한 설명과 기본 설정 방법 및 용량 계획을 기반으로 하는 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="a251d-125">추가 정보가 필요한 경우에는 Microsoft TechNet 웹 사이트의 Lync Server 2013 계획 설명서에서 자세한 정보를 보려면 <STRONG>자세히를 참조</STRONG> 하세요.</span><span class="sxs-lookup"><span data-stu-id="a251d-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="a251d-126">Microsoft TechNet 웹 사이트에 액세스 하려면 인터넷에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="a251d-127">디자인에 적합 한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="a251d-128">초기 기준이 정의 된 후 페이지에는 기능 개요가 완료 된 것으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="a251d-129">**사이트 디자인** 을 클릭 하 여 중앙 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a251d-130">각 Lync Server 2013 토폴로지에는 하나 이상의 중앙 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="a251d-131">디자인에는 단일 중앙 사이트, 여러 분기 사이트가 포함 된 중앙 사이트, 여러 중앙 사이트, 각 중앙 사이트와 연결 된 분기 사이트의 여러 중앙 사이트가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="a251d-132">**사이트 이름**에이 중앙 사이트를 식별 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="a251d-133">**사이트 홈 사용자**에 게이 중앙 사이트에 있는 예상 온-프레미스 동시 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="a251d-134">**클라우드 홈 사용자**에 게이 중앙 사이트에 있는 예상 온라인 동시 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="a251d-135">필요에 따라 온라인 공동 작업, 사용자, 음성, 추가 배포 옵션 또는 서버 응용 프로그램에 대 한 선택 항목을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a251d-136">디자인의이 시점에서는 배포에 대 한 옵션만 선택 하거나 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="a251d-137">그러나 계획 도구의 이후 단계에서 더 많은 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="a251d-138">사용할 수 없으며 지울 수도 없는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="a251d-139">또한 다른 옵션을 선택 취소 하려면 하나를 선택 취소 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="a251d-140">예를 들어 Voice에서 <STRONG>Enterprise Voice</STRONG> 옵션을 지우면 서버 응용 프로그램의 <STRONG>응답 그룹</STRONG>, <STRONG>알림</STRONG>및 <STRONG>통화</STRONG> 대기 옵션 (모두 enterprise voice의 기능)도 선택 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="a251d-141">사이트 이름과 사용자 수를 정의한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="a251d-142">다음 페이지에서는 SIP 도메인, 회의 설정, 음성 설정 및 인프라, Exchange UM, 외부 사용자 액세스, 영구 채팅 설정, 클라이언트 설정, 배치 위치 옵션 및 분기 사이트에 대 한 정보를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="a251d-143">이러한 질문에 따라 적절 하 게 대답 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="a251d-144">마지막 질문에는 다른 중앙 사이트를 만들지 여부를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="a251d-145">**예**를 선택 하면 계획 도구가 중앙 사이트 페이지로 돌아옵니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="a251d-146">**아니요**를 선택 하는 경우 **다음**을 클릭 한 다음 **그리기** 를 클릭 하 여 높은 수준의 전역 토폴로지 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="a251d-147">기존 토폴로지를 보려면 **표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="a251d-148">이전에 저장 한 토폴로지를 나타내는 .xml 파일을 클릭 한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="a251d-149">계획 도구는 전역 토폴로지 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="a251d-150">이제 계획 도구에서 제공 되는 도구를 사용 하 여 토폴로지를 편집, 업데이트 또는 변경 하는 과정을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a251d-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a251d-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a251d-151">See Also</span></span>


[<span data-ttu-id="a251d-152">Lync Server 2013에서 디자인 편집</span><span class="sxs-lookup"><span data-stu-id="a251d-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

