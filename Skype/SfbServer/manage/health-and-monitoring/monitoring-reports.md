---
title: 비즈니스용 Skype 서버에서 모니터링 보고서 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: '요약: 비즈니스용 Skype 서버에서 보고서 모니터링에 대해 자세히 알아보세요.'
ms.openlocfilehash: 1468a012501753a720807f1b1ec609ff187ffc1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817807"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a><span data-ttu-id="86ee6-103">비즈니스용 Skype 서버에서 모니터링 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="86ee6-103">Using Monitoring Reports in Skype for Business Server</span></span> 
 
<span data-ttu-id="86ee6-104">**요약:** 비즈니스용 Skype 서버에서 보고서 모니터링에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="86ee6-104">**Summary:** Learn about Monitoring Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="86ee6-105">비즈니스용 Skype Server에는 Microsoft SQL Server Reporting 서비스에 의해 게시 되는 표준 보고서 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-105">Skype for Business Server includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="86ee6-106">웹 브라우저를 사용 하 여 액세스할 수 있는 이러한 보고서에는 CDR 및 체감 품질 데이터베이스에 저장 된 CDR (통화 정보 기록) 및 체감 품질 (사용 품질) 레코드를 기준으로 하는 사용량, 호출 진단 정보 및 미디어 품질 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>
  
<span data-ttu-id="86ee6-107">이러한 보고서를 사용 하려면 SQL Server의 인스턴스를 실행 하는 컴퓨터에 모니터링 보고서를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-107">To use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="86ee6-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="86ee6-108">In This Section</span></span>

- <span data-ttu-id="86ee6-109">[비즈니스용 Skype 서버에서 모니터링 대시보드 사용](monitoring-dashboard.md) 관리자에 게 시스템 상태 및 시스템 사용량에 대 한 간략 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-109">[Using the Monitoring Dashboard in Skype for Business Server](monitoring-dashboard.md) Provides administrators with a quick overview of their system health and system usage.</span></span>
    
- <span data-ttu-id="86ee6-110">[비즈니스용 Skype 서버의 시스템 사용 보고서](system-usage-reports.md) 비즈니스용 Skype 서버에서 수집한 CDR 데이터를 기반으로 시스템 사용 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-110">[System usage reports in Skype for Business Server](system-usage-reports.md) Provides system usage information based on CDR data collected by Skype for Business Server.</span></span>
    
- <span data-ttu-id="86ee6-111">[비즈니스용 Skype 서버에서 사용자 당 전화 진단 보고서](call-diagnostic-reports-per-user.md) 실패 한 피어 투 피어 및 회의 세션에 대 한 사용자별 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-111">[Call Diagnostic Reports (per user) in Skype for Business Server](call-diagnostic-reports-per-user.md) Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="86ee6-112">[비즈니스용 Skype 서버에서 진단 보고서로 전화 걸기](call-diagnostic-reports.md) 실패 한 피어 투 피어 및 회의 세션에 대 한 요약 정보 및 진단 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-112">[Call Diagnostic Reports in Skype for Business Server](call-diagnostic-reports.md) Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="86ee6-113">[비즈니스용 Skype 서버의 미디어 품질 진단 보고서](media-quality-diagnostic-reports.md) 통화 음질 및 실패 한 통화에 대 한 진단 및 문제 해결 정보에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-113">[Media Quality Diagnostic Reports in Skype for Business Server](media-quality-diagnostic-reports.md) Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>
    
## <a name="locating-records"></a><span data-ttu-id="86ee6-114">레코드 찾기</span><span class="sxs-lookup"><span data-stu-id="86ee6-114">Locating Records</span></span>

<span data-ttu-id="86ee6-115">모니터링 보고서에는 한 번에 제한 된 수의 레코드만 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-115">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="86ee6-116">화면에 표시 되는 실제 레코드 수는 보고서에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-116">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="86ee6-117">현재 화면에 표시 되지 않은 레코드를 보려면 각 보고서의 도구 모음에 있는 표준 앞으로 및 뒤로 컨트롤을 사용 하 여 데이터를 페이징 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-117">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report's toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="86ee6-118">데이터 집합의 첫 번째 페이지 또는 마지막 페이지로 빠르게 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-118">You can also quickly jump to the first page or the last page of the dataset.</span></span>
  
<span data-ttu-id="86ee6-119">앞으로 및 뒤로 컨트롤을 사용 하는 것 외에도 **현재 페이지** 상자에 페이지 번호를 입력 하 고 enter 키를 눌러 데이터 집합의 페이지로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>
  
<span data-ttu-id="86ee6-120">각 보고서에는 데이터를 페이징 하는 기능을 제공 하는 것 외에도 레코드를 찾는 제한 된 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-120">In addition to providing the ability to page through the data, each report also includes the limited ability to find records.</span></span> <span data-ttu-id="86ee6-121">지정 된 값을 기준으로 레코드를 찾으려면 **찾기** 상자에 해당 값을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-121">To find records based on a given value, type that value into the **Find** box, and then click **Find**.</span></span> <span data-ttu-id="86ee6-122">보고서에서 데이터를 검색 하기 시작 하 고 **찾기** 상자에 입력 한 값의 첫 번째 인스턴스에서 멈춥니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-122">The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box.</span></span> <span data-ttu-id="86ee6-123">검색 조건을 충족 하는 다음 레코드를 찾으려면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-123">To find the next record that meets the search criteria, click **Next**.</span></span>
  
<span data-ttu-id="86ee6-124">참고로, 모니터링 보고서는 가장 기본적인 검색 기능만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-124">As noted, the Monitoring Reports provide only the most basic search functions.</span></span> <span data-ttu-id="86ee6-125">예를 들어 값을 찾을 필드를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-125">For example, you cannot specify which field the value should be found in.</span></span> <span data-ttu-id="86ee6-126">검색 메커니즘은 모든 레코드의 모든 필드에서 일치 하는 값을 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-126">The search mechanism automatically searches for matching values in every field in every record.</span></span> <span data-ttu-id="86ee6-127">검색에 와일드 카드를 사용할 수 없으며 모든 검색에서 부분 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-127">You cannot use wildcards in your searches, and all searches look for partial values.</span></span> <span data-ttu-id="86ee6-128">즉, 111을 검색 하면 값 11100 111, 811, 3112, 611A5B, 그리고 해당 필드 내의 아무 곳에 나 값을 포함 하는 다른 모든 필드를 검색 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-128">That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>
  
<span data-ttu-id="86ee6-129">각 보고서는 기본 레코드 집합을 표시 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-129">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="86ee6-130">예를 들어 사용자 등록 보고서에는 기본적으로 지난 주에 대 한 사용자 등록 활동이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-130">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="86ee6-131">어떤 경우에는이로 인해 보고서를 반환 하는 레코드가 표시 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-131">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="86ee6-132">이 경우 지난 주에 사용자 등록이 수행 되지 않았음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-132">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="86ee6-133">"보고서 필터와 일치 하는 결과가 없습니다" 라는 메시지가 표시 되는 경우 필터 값을 변경 하 고 (예: 기간을 지난 주가 아닌 지난 달로 변경) 쿼리를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-133">If you see the message "No results match the report filters," try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="86ee6-134">자세한 내용은이 항목의 뒷부분에 나오는 "데이터 필터링" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86ee6-134">For details, see the "Filtering Data" section later in this topic.</span></span>
  
## <a name="filtering-data"></a><span data-ttu-id="86ee6-135">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="86ee6-135">Filtering Data</span></span>

<span data-ttu-id="86ee6-136">레코드의 하위 집합을 보기만 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-136">There will likely be times when you want to look at only a subset of records.</span></span> <span data-ttu-id="86ee6-137">예를 들어 피어 투 피어 세션 및 회의 세션과는 달리 피어 투 피어 세션만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-137">For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="86ee6-138">마찬가지로 반환 되는 레코드 수를 줄여야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-138">Likewise, there will be times when you need to reduce the number of records that are returned.</span></span> <span data-ttu-id="86ee6-139">기본적으로 보고서에는 데이터 집합의 첫 번째 1000 레코드만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-139">By default, a report can only display the first 1,000 records in a data set.</span></span> <span data-ttu-id="86ee6-140">이러한 문제를 해결 하기 위해 대부분의 보고서에는 여러 필터링 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-140">To address these issues, most reports include a number of filtering options.</span></span> <span data-ttu-id="86ee6-141">예를 들어 2 월 1 일에서 2011 년 1 월 15 2011 일 사이의 레코드만 표시 하려면 **보낸 사람** 상자에 2011 1, 15, 01, 시작 **날짜 상자에** 2011을 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-141">For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box.</span></span> <span data-ttu-id="86ee6-142">그런 다음 **보고서 보기**를 클릭 하면 반환 되는 데이터가 2011 년 1 월 1 일에서 2011 년 1 월 15 일 사이에 발생 하는 작업으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-142">If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>
  
<span data-ttu-id="86ee6-143">사용할 수 있는 필터는 보고 있는 보고서에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-143">The filters available to you vary depending on the report that you are viewing.</span></span> <span data-ttu-id="86ee6-144">특정 보고서에 대 한 자세한 내용은 해당 보고서에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86ee6-144">For details about a specific report, see the help topic for that report.</span></span>
  
## <a name="exporting-data"></a><span data-ttu-id="86ee6-145">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="86ee6-145">Exporting Data</span></span>

<span data-ttu-id="86ee6-146">모니터링 보고서는 두 가지 이상의 방법을 제공 하 여 보고서에 포함 된 데이터를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-146">The Monitoring Reports provide at least two different ways to export the data included in a report.</span></span> <span data-ttu-id="86ee6-147">각 보고서의 맨 위에 표시 되는 도구 모음에서 **내보내기** 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-147">You can use the **Export** option in the toolbar that appears at the top of each report.</span></span> <span data-ttu-id="86ee6-148">이 옵션을 사용 하려면 **형식 선택** 드롭다운 목록에서 원하는 내보내기 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-148">To use this option, select the desired export format from the **Select a format** drop-down list.</span></span> <span data-ttu-id="86ee6-149">다음과 같은 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-149">The following formats are available to you:</span></span>
  
- <span data-ttu-id="86ee6-150">보고서 데이터를 포함 하는 XML 파일</span><span class="sxs-lookup"><span data-stu-id="86ee6-150">XML file with report data</span></span>
    
- <span data-ttu-id="86ee6-151">CSV (쉼표로 분리)</span><span class="sxs-lookup"><span data-stu-id="86ee6-151">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="86ee6-152">Acrobat (PDF) 파일</span><span class="sxs-lookup"><span data-stu-id="86ee6-152">Acrobat (PDF) file</span></span>
    
- <span data-ttu-id="86ee6-153">MHTML (웹 보관)</span><span class="sxs-lookup"><span data-stu-id="86ee6-153">MHTML (web archive)</span></span>
    
- <span data-ttu-id="86ee6-154">0:excel}</span><span class="sxs-lookup"><span data-stu-id="86ee6-154">Excel</span></span>
    
- <span data-ttu-id="86ee6-155">TIFF 파일</span><span class="sxs-lookup"><span data-stu-id="86ee6-155">TIFF file</span></span>
    
- <span data-ttu-id="86ee6-156">이면</span><span class="sxs-lookup"><span data-stu-id="86ee6-156">Word</span></span>
    
<span data-ttu-id="86ee6-157">형식을 선택한 후 **내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-157">After selecting a format, click **Export**.</span></span> <span data-ttu-id="86ee6-158">**파일 다운로드** 대화 상자가 표시 되 면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-158">When the **File Download** dialog box appears, click **Save**.</span></span> <span data-ttu-id="86ee6-159">**다른 이름으로 저장** 대화 상자에서 대상 폴더를 선택 하 고 파일 이름을 입력 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-159">In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>
  
<span data-ttu-id="86ee6-160">Microsoft OneNote가 설치 되어 있는 경우 보고서 데이터를 OneNote에 복사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-160">If you have Microsoft OneNote installed, you can also copy the report data to OneNote.</span></span> <span data-ttu-id="86ee6-161">이렇게 하려면 도구 모음에서 **보고서 보기** 단추를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-161">To do this, right-click the **View Report** button on the toolbar.</span></span> <span data-ttu-id="86ee6-162">**Onenote에서 위치 선택** 대화 상자에서 데이터를 복사 하려는 onenote 섹션을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86ee6-162">In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>
  

