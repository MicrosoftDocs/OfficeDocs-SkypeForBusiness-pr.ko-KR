---
title: 'Lync Server 2013: 모범 사례 분석기에서 만든 보고서 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376b35a250ae1be9574cfa93debe154d94ca589f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="47a68-102">Lync Server 2013의 모범 사례 분석기에서 만든 보고서 이해</span><span class="sxs-lookup"><span data-stu-id="47a68-102">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a68-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="47a68-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="47a68-p101">모범 사례 분석기는 문제를 원활하게 분석 및 확인할 수 있도록 구성된 다양한 유형의 보고서를 제공합니다. 모범 사례 문석기는 오류, 경고, 기타 정보 등의 문제를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-p101">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues. Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="47a68-106">보고서</span><span class="sxs-lookup"><span data-stu-id="47a68-106">Reports</span></span>

<span data-ttu-id="47a68-107">다음의 각 보고서를 표시하면 검색 결과에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-107">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="47a68-108">**목록 보고서**   목록 보고서는 특정 기준으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-108">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="47a68-109">결과를 클래스, 심각도 또는 문제별로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-109">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="47a68-110">예를 들어 결과를 클래스별로 구성하는 경우 디렉터 관련 문제는 보고서의 디렉터 섹션에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-110">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="47a68-111">모든 문제를 볼 수도 있고 정보 항목만 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-111">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="47a68-112">목록 보고서에서는 메모리 등의 특정 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-112">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="47a68-113">보고서를 인쇄하거나 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-113">You can also print the report or export it.</span></span>

  - <span data-ttu-id="47a68-114">**트리 보고서**   트리 보고서는 검색을 실행 하는 데 사용 되는 규칙 및 검색을 실행할 때 지정한 기타 옵션으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-114">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="47a68-115">예를 들어 테스트 토폴로지 규칙과 관련된 문제는 보고서의 테스트 토폴로지 섹션에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-115">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="47a68-116">모든 문제의 세부 정보를 볼 수도 있고 문제 요약만 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-116">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="47a68-117">트리 보고서에서는 메모리 등의 특정 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-117">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="47a68-118">보고서를 인쇄하거나 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-118">You can also print the report or export it.</span></span>

  - <span data-ttu-id="47a68-119">**기타**   보고서 다른 보고서의 항목에는 검색에 포함 된 작업의 런타임 로그가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-119">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="47a68-120">기타 보고서의 항목에서는 메모리 등의 특정 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-120">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="47a68-121">보고서를 인쇄하거나 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-121">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="47a68-122">발행</span><span class="sxs-lookup"><span data-stu-id="47a68-122">Issues</span></span>

<span data-ttu-id="47a68-123">모범 사례 분석기에서 생성하는 보고서는 환경 검색 중에 식별된 특정 문제를 보여 주며, 여기에는 다음과 같은 유형의 문제가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-123">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="47a68-124">\*\*\*\*   작업 환경에서 변경 해야 하는 중요 한 문제에 대해 오류를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-124">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="47a68-125">예를 들어 Lync Server 2013 핵심 구성 요소가 설치 되어 있지 않은 경우 오류가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-125">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>

    <span data-ttu-id="47a68-p106">오류로 분류된 문제는 보고서에서 빨간색 X 기호로 표시됩니다. 오류는 **목록 보고서** 보기의 경우 **모든 문제** 탭에 표시되고, **트리 보고서** 보기의 경우 **자세히 보기** 및 **요약 보기** 탭에 표시됩니다. 보고서에서 특정 오류를 표시하지 않으려면 보고서에서 해당 오류의 단일 인스턴스 또는 모든 인스턴스에 대해 오류를 표시하지 않도록 지정할 수 있습니다. 이 경우 설정을 변경하여 보고서에 오류가 표시되도록 지정하지 않으면 오류는 **기타 보고서** 보기의 **숨겨진 항목** 탭에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-p106">Issues that are classified as errors are identified in the report by a red X symbol. Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="47a68-130">\*\*\*\*   모범 사례 구현과 일치 하지 않는 경고 문제</span><span class="sxs-lookup"><span data-stu-id="47a68-130">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="47a68-131">환경을 변경해야 할 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-131">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="47a68-132">즉, 변경할 필요가 없는 특정 설정과 관련된 알려진 문제일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-132">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="47a68-133">예를 들어 서버에서 시작되지 않는 서비스는 경고로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-133">For example, services that are not started on a server are logged as warnings.</span></span>

    <span data-ttu-id="47a68-p108">경고로 분류된 문제는 보고서에서 노란색 삼각형 경고 기호로 표시됩니다. 경고는 **목록 보고서** 보기의 경우 **모든 문제** 탭에 표시되고, **트리 보고서** 보기의 경우 **자세히 보기** 및 **요약 보기** 탭에 표시됩니다. 보고서에서 특정 오류를 표시하지 않으려면 보고서에서 해당 오류의 단일 인스턴스 또는 모든 인스턴스에 대해 오류를 표시하지 않도록 지정할 수 있습니다. 이 경우 설정을 변경하여 보고서에 경고가 표시되도록 지정하지 않으면 경고는 **기타 보고서** 보기의 **숨겨진 항목** 탭에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-p108">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol. Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="47a68-138">**정보**   에 오류 또는 경고로 분류 되지 않는 모든 문제가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-138">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="47a68-139">예를 들어 Active Directory 도메인 서비스의 Lync Server 2013 Standard Edition Server 개체 수는 정보 문제로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-139">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>

    <span data-ttu-id="47a68-140">정보 문제는 **목록 보고서** 보기의 경우 **모든 문제** 탭에 표시되고, **트리 보고서** 보기의 경우 **자세히 보기** 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-140">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="47a68-141">Lync Server 2013, 모범 사례 분석기는 문제를 해결 하기 위해 환경을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-141">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="47a68-142">검색에서는 잠재적 문제만 검색하여 각 문제를 해결하는 방법에 대한 정보가 포함된 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-142">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="47a68-p111">문제를 클릭하면 설명과 몇 가지 옵션이 특정 문제에 대해 표시됩니다. 그러면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-p111">If you click an issue, an explanation and some options are displayed for specific issues. Then, you can do any of the following:</span></span>

  - <span data-ttu-id="47a68-145">문제에 대한 자세한 정보 및 문제 해결 방법 찾기</span><span class="sxs-lookup"><span data-stu-id="47a68-145">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="47a68-146">보고서에 문제가 표시되지 않도록 지정</span><span class="sxs-lookup"><span data-stu-id="47a68-146">Stop showing issues in reports:</span></span>

      - <span data-ttu-id="47a68-147">선택한 인스턴스에 대한 문제 표시 중지</span><span class="sxs-lookup"><span data-stu-id="47a68-147">Stop showing issues for the selected instance.</span></span>

      - <span data-ttu-id="47a68-148">해당 문제의 모든 인스턴스에 대해 문제 표시 중지</span><span class="sxs-lookup"><span data-stu-id="47a68-148">Stop showing issues for all instances of that issue.</span></span>

    <span data-ttu-id="47a68-p112">보고서에서 표시되지 않도록 지정한 문제를 확인하려면 **기타 보고서** 보기의 **숨겨진 항목** 탭으로 이동합니다. 이 탭에서 보고서에 문제가 다시 표시되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a68-p112">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view. From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="47a68-151">특정 문제를 해결 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 모범 사례 분석기에서 식별 한 문제 분석 및 해결](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47a68-151">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
