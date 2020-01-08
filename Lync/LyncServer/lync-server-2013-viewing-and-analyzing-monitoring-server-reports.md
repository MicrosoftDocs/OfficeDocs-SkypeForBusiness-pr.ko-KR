---
title: 'Lync Server 2013: 모니터링 서버 보고서 보기 및 분석'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="2b964-102">Lync Server 2013에서 모니터링 서버 보고서 보기 및 분석</span><span class="sxs-lookup"><span data-stu-id="2b964-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b964-103">_**마지막으로 수정한 주제:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="2b964-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="2b964-104">모니터링 서버 보고서는 최종 사용자에 게 제공 되는 체감 품질 모니터링 하는 다양 한 음성 품질 측정값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="2b964-105">또한 모니터링 서버에는 조직에서 사용 및 미디어 품질 추세를 시청 하 고 발생 하는 미디어 품질 문제를 해결할 수 있는 몇 가지 기본 제공 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="2b964-106">매일 및 매주 작동 하는 모니터링 서버 보고서를 유지 하는 주요 부분은 특히 다음과 같이 미디어 품질 보고서를 보고 분석 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="2b964-107">체감 품질 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="2b964-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="2b964-108">체감 품질 성과 보고서</span><span class="sxs-lookup"><span data-stu-id="2b964-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="2b964-109">모니터링 서버에서 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="2b964-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="2b964-110">웹 브라우저에서 SQL reporting services를 호스트 하는 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="2b964-111">브라우저 화면에서 필요한 보고서를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="2b964-112">) 내보내기 옵션과 필요한 출력 형식을 선택 하 여 보고서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="2b964-113">CDR (통화 정보 기록) 구성</span><span class="sxs-lookup"><span data-stu-id="2b964-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="2b964-114">RTCUniversalServerAdmins 그룹의 구성원 이거나 동등한 권한이 있거나 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 Lync Server 2013을 배포한 네트워크의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2b964-115">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2b964-116">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="2b964-117">**통화 정보 기록** 페이지에서 표의 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="2b964-118">제거를 설정 하려면 **서버 모니터링을 위해 제거 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="2b964-119">**최대 기간 (일) 동안 통화 정보 기록 유지:** 통화 정보 기록을 보존 해야 하는 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="2b964-120">**최대 기간 (일)에 대 한 오류 보고 데이터 유지:** 오류 보고서를 유지 해야 하는 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="2b964-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="2b964-122">체감 품질 구성</span><span class="sxs-lookup"><span data-stu-id="2b964-122">Configure QoE</span></span>

1.  <span data-ttu-id="2b964-123">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2b964-124">자세한 내용은 대리인 설정 사용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b964-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="2b964-125">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2b964-126">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="2b964-127">**경력 데이터** 페이지의 테이블에서 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="2b964-128">제거를 설정 하려면 **서버 모니터링을 위해 제거 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="2b964-129">**최대 기간 (일) 동안 통화 정보 기록 유지:** 체감 품질 데이터를 유지할 최대 일 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="2b964-130">커밋을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="2b964-131">보관 정책 변경</span><span class="sxs-lookup"><span data-stu-id="2b964-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="2b964-132">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b964-133">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2b964-134">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="2b964-135">정책 목록에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2b964-136">**보관 정책 편집-전역**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="2b964-137">배포에 대 한 내부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="2b964-138">배포에 대해 외부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="2b964-139">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="2b964-140">사용자에 게 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="2b964-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="2b964-141">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b964-142">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2b964-143">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="2b964-144">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2b964-145">**보관 정책**에서 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="2b964-146">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b964-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b964-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b964-147">See Also</span></span>


[<span data-ttu-id="2b964-148">Lync Server 2013에서 모니터링 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="2b964-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="2b964-149">Lync Server 2013의 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="2b964-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="2b964-150">Lync Server 2013의 미디어 품질 비교 보고서</span><span class="sxs-lookup"><span data-stu-id="2b964-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

