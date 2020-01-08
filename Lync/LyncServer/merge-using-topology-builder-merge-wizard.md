---
title: 토폴로지 작성기 병합 마법사를 사용 하 여 병합
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="899c8-102">토폴로지 작성기 병합 마법사를 사용 하 여 병합</span><span class="sxs-lookup"><span data-stu-id="899c8-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="899c8-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="899c8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="899c8-104">토폴로지 작성기를 사용 하 여 기존 배포를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="899c8-105">**작업** 메뉴에서 **Office Communications Server 2007 R2 병합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="899c8-106">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-106">Click **Next**.</span></span>

4.  <span data-ttu-id="899c8-107">**Edge 설정 지정**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="899c8-108">![토폴로지 병합 마법사, Edge 설정 페이지](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "병합 마법사 지정, Edge 설정 페이지로 지정")</span><span class="sxs-lookup"><span data-stu-id="899c8-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="899c8-109">**Edge 유형 지정**에서 edge 서버 구성의 유형을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="899c8-110">이 예제에서는 **단일 Edge 서버** 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="899c8-111"><STRONG>확장 된 Edge 배포</STRONG> 는 지원 되지 않는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="899c8-112"><STRONG>확장 된 Edge 서버</STRONG> 는 먼저 <STRONG>단일 Edge 서버</STRONG> 또는 <STRONG>부하가 분산 된 통합 Edge</STRONG> 서버로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="899c8-113">**내부에 지 설정 지정** 에서 필요에 따라 Edge 풀의 내부 FQDN 및 포트에 대 한 관련 정보를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="899c8-114">![내부에 지 설정 대화 상자](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "내부에 지") 설정 대화 상자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="899c8-115">**외부에 지 지정**에서 edge 서버의 웹 회의 FQDN 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="899c8-116"><STRONG>Next (다음</STRONG>)를 클릭 하기 전에이 절차의 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="899c8-117">이 단계를 놓치지 않도록 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="899c8-118">페더레이션에 레거시 Office 통신 서버 2007 R2 Edge 서버를 사용 하려는 경우 **이 Edge 풀을 페더레이션 및 공용 메신저 연결에 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="899c8-119">여러 개의 Edge 서버가 배포 된 경우 페더레이션에 대 한 서버 중 하나만 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="899c8-120">이 확인란을 선택 하지 않고 나중에 페더레이션을 사용 하기로 결정 한 경우에는 토폴로지 작성기 병합 마법사를 실행 하 고 토폴로지를 다시 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="899c8-121">![Edge 서버 대화 상자, 외부 edge 페이지]에(images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "지 서버 대화 상자 지정, 외부에 지 페이지 지정")</span><span class="sxs-lookup"><span data-stu-id="899c8-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="899c8-122">**다음 홉 지정**에서 환경에 다음 홉 위치의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="899c8-123">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="899c8-124">![Edge 서버 대화 상자, 다음 홉 페이지에](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "지 서버 대화 상자 지정, 다음 홉 페이지 지정")</span><span class="sxs-lookup"><span data-stu-id="899c8-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="899c8-125">**Edge 설정 지정**에서 모든 Office 통신 서버 2007 R2 Edge 서버가 추가 된 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="899c8-126">추가 하려는 Office Communications Server 2007 R2 Edge 서버가 더 있으면 4 단계부터이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="899c8-127">**내부 sip 포트 지정** 에서 기본 설정 (기본 sip 포트를 수정 하지 않은 경우)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="899c8-128">5061의 기본 포트를 사용 하 고 있지 않은 경우 적절 하 게 변경 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="899c8-129">**요약**에서 **다음** 을 클릭 하 여 토폴로지 병합을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="899c8-130">마법사 페이지에서 토폴로지가 성공적으로 병합 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="899c8-131">**상태** 열에서 값이 **성공**인지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="899c8-132">토폴로지 작성기의 왼쪽 창에 Office Communications Server 2007 R2 환경이 Lync Server 2013과 통합 되었음을 나타내는 **BackCompatSite**이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="899c8-133">(images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "병합 된 토폴로지를 표시") 하는 ![병합 된 토폴로지 토폴로지 작성기를 보여 주는 토폴로지 작성기]</span><span class="sxs-lookup"><span data-stu-id="899c8-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="899c8-134">**작업** 메뉴에서 **토폴로지 게시**를 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="899c8-135">**게시 마법사** 가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="899c8-136">레거시 정책 설정을 Lync Server 2013으로 가져오도록 다음 항목인 <A href="import-policies-and-settings.md">정책 및 설정 가져오기</A>를 완료 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="899c8-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

