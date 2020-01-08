---
title: 'Lync Server 2013: 모범 사례 분석기에서 만든 보고서 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0903c3bafc4017d5455c188c66de3e1f2cf0b178
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="46e16-102">Lync Server 2013에서 모범 사례 분석기에서 만든 보고서 이해</span><span class="sxs-lookup"><span data-stu-id="46e16-102">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e16-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="46e16-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="46e16-104">모범 사례 분석기에서는 문제의 분석 및 해결을 돕기 위해 구성 된 여러 유형의 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-104">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues.</span></span> <span data-ttu-id="46e16-105">모범 사례 분석기는 오류, 경고 및 기타 정보와 같은 문제를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-105">Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="46e16-106">보고서</span><span class="sxs-lookup"><span data-stu-id="46e16-106">Reports</span></span>

<span data-ttu-id="46e16-107">다음과 같은 각 보고서를 보고 검색 결과에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-107">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="46e16-108">**목록 보고서**   목록 보고서는 특정 조건으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-108">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="46e16-109">결과를 수업, 심각도 또는 문제점과 같이 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-109">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="46e16-110">예를 들어 수업 별로 결과를 구성 하는 경우, 이사회 관련 문제는 보고서의 디렉터 섹션에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-110">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="46e16-111">모든 문제점을 보거나 정보 항목 으로만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-111">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="46e16-112">목록 보고서에서 메모리와 같은 특정 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-112">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="46e16-113">보고서를 인쇄 하거나 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-113">You can also print the report or export it.</span></span>

  - <span data-ttu-id="46e16-114">**트리 보고서**   트리 보고서는 검사를 실행 하는 데 사용 되는 규칙 및 스캔을 실행할 때 지정한 기타 옵션으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-114">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="46e16-115">예를 들어 테스트 토폴로지 규칙과 관련 된 문제는 보고서의 테스트 토폴로지 섹션에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-115">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="46e16-116">모든 문제에 대 한 세부 정보 또는 문제 요약만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-116">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="46e16-117">트리 보고서에서 메모리와 같은 특정 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-117">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="46e16-118">보고서를 인쇄 하거나 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-118">You can also print the report or export it.</span></span>

  - <span data-ttu-id="46e16-119">\*\*\*\*   다른 보고서의 기타 보고서 항목에는 스캔에 포함 된 작업의 런타임 로그가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-119">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="46e16-120">다른 보고서에서 메모리와 같은 특정 항목에 대 한 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-120">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="46e16-121">보고서를 인쇄 하거나 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-121">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="46e16-122">사항</span><span class="sxs-lookup"><span data-stu-id="46e16-122">Issues</span></span>

<span data-ttu-id="46e16-123">모범 사례 분석기에서 생성 된 보고서는 다음 유형의 문제를 포함 하 여 사용자 환경을 검색 하는 동안 식별 되는 특정 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-123">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="46e16-124">\*\*\*\*   환경에서 변경 해야 하는 중요 한 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-124">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="46e16-125">예를 들어 Lync Server 2013 주요 구성 요소가 설치 되어 있지 않으면 오류가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-125">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>
    
    <span data-ttu-id="46e16-126">오류로 분류 된 문제는 보고서에서 빨간색 X 기호로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-126">Issues that are classified as errors are identified in the report by a red X symbol.</span></span> <span data-ttu-id="46e16-127">오류는 **목록 보고서** 보기의 **모든 문제** 탭과 **트리 보고서** 보기의 **자세히 보기** 탭 및 **요약 보기** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-127">Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view.</span></span> <span data-ttu-id="46e16-128">보고서에 특정 오류를 표시 하지 않으려는 경우 단일 인스턴스 또는 해당 오류의 모든 인스턴스에 대해 오류가 표시 되지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-128">If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report.</span></span> <span data-ttu-id="46e16-129">그런 다음 설정을 변경 하 고 보고서에 오류가 표시 되도록 지정 하지 않는 한 **다른 보고서** 보기의 **숨겨진 항목** 탭에 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-129">The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="46e16-130">\*\*\*\*   모범 사례 구현과 일관 되지 않는 경고 문제</span><span class="sxs-lookup"><span data-stu-id="46e16-130">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="46e16-131">이는 사용자 환경의 변경 필요성을 나타내지는 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-131">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="46e16-132">이 문제는 변경 하지 않아도 되는 특정 설정의 알려진 문제일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-132">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="46e16-133">예를 들어 서버에서 시작 되지 않은 서비스는 경고로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-133">For example, services that are not started on a server are logged as warnings.</span></span>
    
    <span data-ttu-id="46e16-134">경고로 분류 된 문제는 노란색 삼각형 경고 기호를 기준으로 보고서에서 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-134">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol.</span></span> <span data-ttu-id="46e16-135">경고는 **목록 보고서** 보기의 **모든 문제** 탭과 **트리 보고서** 보기의 **자세히 보기** 탭과 **요약 보기** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-135">Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view.</span></span> <span data-ttu-id="46e16-136">보고서에 특정 오류를 표시 하지 않으려는 경우 단일 인스턴스 또는 해당 오류의 모든 인스턴스에 대해 오류가 표시 되지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-136">If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report.</span></span> <span data-ttu-id="46e16-137">그런 다음 설정을 변경 하 고 보고서에 경고가 표시 되도록 지정 하지 않는 한 **다른 보고서** 보기의 **숨겨진 항목** 탭에만 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-137">The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="46e16-138">**정보**   에는 오류 또는 경고로 분류 되지 않는 모든 문제가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-138">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="46e16-139">예를 들어 Active Directory 도메인 서비스의 Lync Server 2013 Standard Edition Server 개체 수는 정보 문제로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-139">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>
    
    <span data-ttu-id="46e16-140">정보 문제는 **목록 보고서** 보기의 **모든 문제** 탭과 **트리 보고서** 보기의 **자세히 보기** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-140">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="46e16-141">Lync Server 2013, 모범 사례 분석기는 문제를 해결 하기 위해 환경을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-141">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="46e16-142">이 검사는 잠재적인 문제만 감지 하 고 각 문제를 해결 하는 방법에 대 한 정보가 포함 된 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-142">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="46e16-143">문제를 클릭 하면 특정 문제에 대 한 설명 및 일부 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-143">If you click an issue, an explanation and some options are displayed for specific issues.</span></span> <span data-ttu-id="46e16-144">그러면 다음 중 하나를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-144">Then, you can do any of the following:</span></span>

  - <span data-ttu-id="46e16-145">문제 및 해결 방법에 대 한 자세한 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="46e16-145">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="46e16-146">보고서의 문제 표시를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-146">Stop showing issues in reports:</span></span>
    
      - <span data-ttu-id="46e16-147">선택한 인스턴스에 대 한 문제의 표시를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-147">Stop showing issues for the selected instance.</span></span>
    
      - <span data-ttu-id="46e16-148">해당 문제의 모든 인스턴스에 대 한 문제의 표시를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-148">Stop showing issues for all instances of that issue.</span></span>
    
    <span data-ttu-id="46e16-149">보고서에 표시를 중지 한 문제를 확인 하려면 **다른 보고서** 보기의 **숨겨진 항목** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-149">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view.</span></span> <span data-ttu-id="46e16-150">여기서 보고서의 문제 표시를 다시 시작 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e16-150">From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="46e16-151">특정 문제 해결에 대 한 자세한 내용은 [Lync Server 2013에서 모범 사례 분석기에서 식별 된 문제 분석 및 해결](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46e16-151">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

