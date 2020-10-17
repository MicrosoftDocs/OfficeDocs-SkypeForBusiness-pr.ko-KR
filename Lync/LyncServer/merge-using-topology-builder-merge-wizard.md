---
title: 토폴로지 작성기 병합 마법사를 사용 하 여 병합
description: 토폴로지 작성기 병합 마법사를 사용 하 여 병합 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d71a63eef95e3e36802dedfa9fbc1a173d283b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544564"
---
# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="b94ea-103">토폴로지 작성기 병합 마법사를 사용 하 여 병합</span><span class="sxs-lookup"><span data-stu-id="b94ea-103">Merge using Topology Builder Merge wizard</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b94ea-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b94ea-104">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="b94ea-105">토폴로지 작성기를 사용하여 기존 배포를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-105">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="b94ea-106">**동작** 메뉴에서 **Office Communications Server 2007 R2 병합**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-106">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="b94ea-107">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-107">Click **Next**.</span></span>

4.  <span data-ttu-id="b94ea-108">**에지 설정 지정**에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-108">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="b94ea-109">![토폴로지 병합 마법사,에 지 설정 지정 페이지](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "토폴로지 병합 마법사,에 지 설정 지정 페이지")</span><span class="sxs-lookup"><span data-stu-id="b94ea-109">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="b94ea-p101">**에지 유형 지정**에서 에지 서버 구성 유형을 입력하고 **다음**을 클릭합니다. 이 예에서는 **단일 에지 서버** 옵션이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-p101">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b94ea-p102"><STRONG>확장된 에지 배포</STRONG>는 지원되는 구성이 아닙니다. <STRONG>확장된 에지 서버</STRONG>가 먼저 <STRONG>단일 에지 서버</STRONG> 또는 <STRONG>부하 분산 통합 에지</STRONG> 서버로 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-p102"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="b94ea-114">**내부에 지 설정 지정** 에서 필요에 따라에 지 풀의 내부 FQDN 및 포트에 대 한 관련 정보를 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-114">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="b94ea-115">![내부에 지 설정 지정 대화 상자](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "내부에 지 설정 지정 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="b94ea-115">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="b94ea-116">**외부 에지 지정**에서 에지 서버에 대한 웹 회의 FQDN 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-116">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b94ea-p103"><STRONG>다음</STRONG>을 클릭하기 전에 이 절차의 다음 단계를 수행합니다. 이 단계를 결코 건너뛰어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-p103">Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="b94ea-119">페더레이션을 위해 레거시 Office Communications Server 2007 R2에 지 서버를 사용 하려는 경우 **이에 지 풀은 페더레이션 및 공용 IM 연결에 사용 됩니다** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-119">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="b94ea-120">여러 에지 서버를 배포한 경우 그중 한 에지 서버만 페더레이션에 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-120">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="b94ea-121">이 확인란을 선택하지 않았는데 나중에 페더레이션을 사용할 것을 결정하는 경우 토폴로지 작성기 병합 마법사를 실행하여 토폴로지를 다시 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-121">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="b94ea-122">![에 지 서버 대화 상자, 외부에 지 지정 페이지](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "에 지 서버 대화 상자, 외부에 지 지정 페이지")</span><span class="sxs-lookup"><span data-stu-id="b94ea-122">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="b94ea-123">**다음 홉 지정**에서 환경의 다음 홉 위치에 대한 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-123">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="b94ea-124">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-124">Click **Finish**.</span></span>
    
    <span data-ttu-id="b94ea-125">![에 지 서버 대화 상자, 다음 홉 지정 페이지](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "에 지 서버 대화 상자, 다음 홉 지정 페이지")</span><span class="sxs-lookup"><span data-stu-id="b94ea-125">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="b94ea-126">에 **지 설정 지정**에서 모든 Office Communications Server 2007 R2에 지 서버를 추가한 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-126">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="b94ea-127">추가할 Office Communications Server 2007 R2에 지 서버가 더 있는 경우 4 단계부터이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-127">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="b94ea-128">**내부 sip 포트 지정** 에서 기본 설정 (기본 sip 포트를 수정 하지 않은 경우)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-128">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="b94ea-129">기본 포트 5061을 사용하지 않는 경우 포트를 적절히 변경하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-129">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="b94ea-130">**요약**에서 **다음**을 클릭하여 토폴로지 병합을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-130">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="b94ea-131">마법사 페이지에서 토폴로지가 성공적으로 병합되었는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-131">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="b94ea-132">**상태** 열에서 값이 **성공**인지 확인한 후 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-132">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="b94ea-133">토폴로지 작성기의 왼쪽 창에 Office Communications Server 2007 R2 환경이 Lync Server 2013과 병합 되었음을 나타내는 **BackCompatSite**가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-133">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="b94ea-134">![병합 된 토폴로지를 보여 주는 토폴로지 작성기](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "병합 된 토폴로지를 보여 주는 토폴로지 작성기")</span><span class="sxs-lookup"><span data-stu-id="b94ea-134">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="b94ea-135">**동작** 메뉴에서 **토폴로지 게시**를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-135">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="b94ea-136">**게시 마법사**가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-136">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b94ea-137">기존 정책 설정을 Lync Server 2013로 가져오려면 다음 항목인 <A href="import-policies-and-settings.md">정책 및 설정 가져오기</A>를 완료 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b94ea-137">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

