---
title: 'Lync Server 2013: 모니터링 보고서 사용'
description: 'Lync Server 2013: 모니터링 보고서를 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e19b266e0580a89b814e80982c5f4ff2146ec01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580314"
---
# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="c6f65-103">Lync Server 2013에서 모니터링 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="c6f65-103">Using Monitoring Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6f65-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c6f65-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c6f65-105">Lync Server 2013에는 Microsoft SQL Server Reporting Service에서 게시 한 표준 보고서 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-105">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="c6f65-106">웹 브라우저를 통해 액세스할 수 있는 이러한 보고서는 모두 CDR 및 QoE 데이터베이스에 저장된 CDR(통화 정보 기록) 및 QoE(체감 품질) 레코드를 기반으로 사용, 통화 진단 정보 및 미디어 품질 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="c6f65-107">이러한 보고서를 사용 하려면 SQL Server 인스턴스를 실행 하는 컴퓨터에 모니터링 보고서를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-107">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6f65-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c6f65-108">In This Section</span></span>

  - <span data-ttu-id="c6f65-109">[Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)     에서 모니터링 대시보드 사용 관리자에 게 시스템 상태 및 시스템 사용에 대 한 간략 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-109">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="c6f65-110">[Lync Server 2013](lync-server-2013-system-usage-reports.md)     의 시스템 사용 현황 보고서 Lync Server에서 수집한 CDR 데이터를 기반으로 시스템 사용 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-110">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="c6f65-111">[Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)     의 사용자 당 통화 진단 보고서 실패 한 피어 투 피어 및 회의 세션에 대 한 사용자별 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-111">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="c6f65-112">[Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)     의 통화 진단 보고서 실패 한 피어 투 피어 및 회의 세션에 대 한 요약 정보 및 진단 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-112">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="c6f65-113">[Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)     의 미디어 품질 진단 보고서 통화 품질에 대 한 정보 및 실패 한 통화에 대 한 진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-113">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="c6f65-114">레코드 찾기</span><span class="sxs-lookup"><span data-stu-id="c6f65-114">Locating Records</span></span>

<span data-ttu-id="c6f65-p102">모니터링 보고서에는 특정 시점에 화면에 있는 제한 수의 레코드만 표시됩니다. 화면에 표시된 실제 레코드 수는 보고서에 따라 달라집니다. 현재 화면에 표시되지 않은 레코드를 보려면 페이지에서 데이터를 탐색할 수 있게 해주는 표준 앞으로 및 뒤로 컨트롤(각 보고서의 도구 모음에 있음)을 사용하면 됩니다. 또한 데이터 집합의 첫 번째 페이지나 마지막 페이지로 빠르게 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="c6f65-119">앞으로 및 뒤로 컨트롤을 사용하는 것 외에도 **현재 페이지** 상자에 페이지 번호를 입력해서 데이터 집합의 특정 페이지로 바로 이동하고 Enter 키를 누를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="c6f65-p103">페이지에서 데이터를 탐색하는 기능을 제공하는 것 외에도 각 보고서에는 레코드를 찾을 수 있는 제한된 기능이 포함됩니다. 특정 값에 따라 레코드를 찾으려면 **찾기** 상자에 값을 입력한 후 **찾기**를 클릭합니다. 보고서에서 데이터 검색을 시작하고 **찾기** 상자에 입력한 값의 첫 번째 인스턴스가 발견되면 검색을 중지합니다. 검색 조건에 맞는 다음 레코드를 찾으려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="c6f65-p104">앞에서 설명한 것처럼 모니터링 보고서에는 가장 기본적인 검색 기능만 제공됩니다. 예를 들어 필드별로 값을 검색하도록 지정할 수는 없습니다. 검색 메커니즘에서는 모든 필드의 모든 레코드에서 일치하는 값을 자동으로 검색합니다. 검색에 와일드카드를 사용할 수 없으며 모든 검색은 부분 값 검색으로 수행됩니다. 즉, 111을 검색할 경우 값 111뿐만 아니라 값 11100, 811, 3112, 611A5B도 반환되며 해당 필드에 값 111이 포함된 다른 모든 필드에서도 검색이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="c6f65-p105">각 보고서는 기본 레코드 집합을 표시하도록 구성됩니다. 예를 들어 사용자 등록 보고서에는 기본적으로 지난 주의 사용자 등록 활동이 표시됩니다. 일부 경우에는 이로 인해 보고서에서 레코드가 반환되지 않을 수 있습니다. 이 경우 지난 주에 발생한 사용자 등록이 없음을 의미합니다. "보고서 필터와 일치하는 결과가 없습니다." 메시지가 표시되면 필터 값을 변경하고(예: 시간 기간을 지난 주가 아닌 지난 달로 변경) 쿼리를 다시 실행해보십시오. 자세한 내용은 이 항목의 뒷부분에 나오는 "데이터 필터링" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="c6f65-135">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="c6f65-135">Filtering Data</span></span>

<span data-ttu-id="c6f65-p106">레코드의 하위 집합만 조사하려는 경우도 있습니다. 예를 들어 피어 투 피어 세션 및 회의 세션을 모두 조사하는 대신 피어 투 피어 세션만 조사할 수도 있습니다. 마찬가지로 반환되는 레코드 수를 줄여야 할 수도 있습니다. 기본적으로 보고서에 데이터 집합의 처음 1,000개 레코드만 표시할 수 있습니다. 이러한 문제를 해결하기 위해 대부분의 보고서에는 여러 필터링 옵션이 포함됩니다. 예를 들어 2011년 1월 1일부터 2011년 1월 15일까지 기간 동안의 레코드만 보려는 경우 **시작** 상자에 2011년 1월 1일을 입력하고 **종료** 상자에 2011년 1월 15일을 입력할 수 있습니다. 그런 다음 **보고서 보기**를 클릭하면 반환되는 데이터가 2011년 1월 1일부터 2011년 1월 15일까지 발생한 활동으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="c6f65-p107">사용 가능한 필터는 보고 있는 보고서에 따라 달라집니다. 특정 보고서에 대한 자세한 내용은 해당 보고서에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="c6f65-145">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="c6f65-145">Exporting Data</span></span>

<span data-ttu-id="c6f65-p108">모니터링 보고서에서는 보고서에 포함된 데이터를 내보낼 수 있는 최소 두 가지 이상의 방법을 제공합니다. 각 보고서의 맨 위에 표시되는 도구 모음의 **내보내기** 옵션을 사용할 수 있습니다. 이 옵션을 사용할 경우 먼저 **형식 선택** 드롭다운 목록에서 원하는 내보내기 형식을 선택합니다. 사용 가능한 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="c6f65-150">보고서 데이터를 포함하는 XML 파일</span><span class="sxs-lookup"><span data-stu-id="c6f65-150">XML file with report data</span></span>

  - <span data-ttu-id="c6f65-151">CSV(쉼표로 구분)</span><span class="sxs-lookup"><span data-stu-id="c6f65-151">CSV (comma delimited)</span></span>

  - <span data-ttu-id="c6f65-152">Acrobat(PDF) 파일</span><span class="sxs-lookup"><span data-stu-id="c6f65-152">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="c6f65-153">MHTML(웹 보관)</span><span class="sxs-lookup"><span data-stu-id="c6f65-153">MHTML (web archive)</span></span>

  - <span data-ttu-id="c6f65-154">Excel</span><span class="sxs-lookup"><span data-stu-id="c6f65-154">Excel</span></span>

  - <span data-ttu-id="c6f65-155">TIFF 파일</span><span class="sxs-lookup"><span data-stu-id="c6f65-155">TIFF file</span></span>

  - <span data-ttu-id="c6f65-156">Word</span><span class="sxs-lookup"><span data-stu-id="c6f65-156">Word</span></span>

<span data-ttu-id="c6f65-p109">형식을 선택한 후 **내보내기**를 클릭합니다. **파일 다운로드** 대화 상자가 표시되면 **저장**을 클릭합니다. **다른 이름으로 저장** 대화 상자에서 대상 폴더를 선택하고, 파일 이름을 입력한 후 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="c6f65-p110">Microsoft OneNote가 설치된 경우 보고서 데이터를 OneNote로 복사할 수도 있습니다. 이렇게 하려면 도구 모음에서 **보고서 보기** 단추를 마우스 오른쪽 단추로 클릭합니다. **OneNote에서 위치 선택** 대화 상자에서 데이터를 복사하려는 OneNote의 섹션을 선택한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f65-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

