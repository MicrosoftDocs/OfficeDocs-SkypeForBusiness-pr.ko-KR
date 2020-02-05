---
title: 'Lync Server 2013: IP 전화 인벤토리 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb9bb9a3ae48c8bf2fc9a5122e1b8004e0f6019
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="4c575-102">Lync Server 2013의 IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="4c575-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c575-103">_**마지막으로 수정한 주제:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="4c575-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="4c575-104">IP 전화 재고 보고서는 조직에서 현재 사용 중인 IP 전화에 대 한 정보를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-104">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="4c575-105">IP 인벤토리 보고서는 지정 된 보고 기간 동안 실제로 사용 된 IP 전화의 세부 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-105">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="4c575-106">그 외에,이 보고서를 통해 이전에는 오래 된 구형 전화기를 사용 하 고 있거나 교체 해야 하는지 여부를 관리자에 게 알릴 수 있습니다. 또한 거의 사용 하지 않는 조직에 부담이 큰 전화가 있다는 사실을 관리자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-106">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="4c575-107">이러한 종류의 정보는 새 전화를 구입 하거나 기존 전화를 재배포할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-107">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="4c575-108">(예를 들어, 휴대폰을 거의 사용 하지 않는 사용자가 전화기를 자주 사용 하는 사용자와 다른 사람으로 전환 하 라는 메시지가 표시 될 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="4c575-108">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="4c575-109">실제 인벤토리 보고서로 사용 되는 경우에는이 보고서에 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="4c575-110">한 가지 방법으로 IP 전화 보고서는 지정 된 기간 동안 Lync Server에 로그온 한 모든 전화기를 마지막 로그온 시간을 기준으로 정렬 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="4c575-111">지정 된 기간에 휴대폰에서 로그온 하지 않은 경우에는 목록 보고서에 해당 시간이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="4c575-112">이는 시작 하기 전에 로그온 하 고 지정 된 시간 간격 동안 계속 로그온 한 전화를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="4c575-113">예를 들어 2012 년 7 월부터 모든 전화 인벤터리를 보고 싶을 때</span><span class="sxs-lookup"><span data-stu-id="4c575-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="4c575-114">또한 여러 전화기가 2012 년 6 월 30 일에 Lync Server에 로그온 했 고, 7 월 1 일부로 계속 로그온 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="4c575-115">해당 전화는 7 월 1 일의 인벤터리 보고서에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="4c575-116">또한 인벤터리 보고서에는 조직에서 더 이상 사용 하지 않는 전화가 포함 될 수 있다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="4c575-117">예를 들어, 2012 년 7 월 1 일에 시스템에 로그온 한 Fabrikam 전화가 여러 개 있다고 가정 합니다. 5 일 후에 조직에서 해당 Fabrikam 전화를 모두 제거 하 고 최신 Contoso 모델로 바꿨습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="4c575-118">Fabrikam 전화는 7 월 동안 시스템에 로그온 했기 때문에 "인벤터리" 보고서에 계속 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="4c575-119">또한 IP 전화 인벤터리 보고서에는 다양 한 유형의 휴대폰에 대 한 요약 합계가 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-119">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="4c575-120">예를 들어 105 Polycom CX600 휴대폰을 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-120">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="4c575-121">이 보고서는 귀하에 게 이러한 전화의 105 있다는 사실을 알려 주지 않습니다. 대신 Polycom Cx600에 대 한 105 별도의 항목만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-121">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="4c575-122">Polycom Cx600에 대 한 105 항목이 있는지 확인 하는 유일한 방법은 각 항목의 수를 수동으로 계산 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-122">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4c575-123">또는 데이터를 내보내고 Microsoft Excel 또는 Windows PowerShell을 사용 하 여 해당 횟수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="4c575-124">IP 전화 인벤토리 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="4c575-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="4c575-125">모니터링 보고서 홈 페이지에서 IP 전화 인벤터리 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-125">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4c575-126">사용자 URI 메트릭을 클릭 하면 해당 사용자의 사용자 활동 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-126">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="4c575-127">피어 투 피어 통화에 대 한 마지막 활동 메트릭을 클릭 하면 피어 투 피어 세션 세부 정보 보고서로 이동 합니다. 회의에 대해 동일한 메트릭을 클릭 하면 회의 세부 정보 보고서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-127">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="4c575-128">IP 전화 인벤토리 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="4c575-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="4c575-129">특정 종류의 휴대폰에 대 한 사용 현황 정보에 관심이 있는 경우 (예: "Polycom CX600 휴대폰을 사용 하는 사용자는 빈도") 해당 특정 유형의 휴대폰을 기준으로 필터링 하 여 해당 정보를 IP 전화 재고 보고서에서 직접 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="4c575-130">그러나 모든 휴대폰에 대 한 요약 정보를 원하는 경우 (Polycom CX600를 사용 하는 사용자 수), LG-Nortel IP8540 등을 사용 하는 경우, 데이터를 내보내고 다른 응용 프로그램 (예: Windows PowerShell)을 사용 하 여 해당 유형의 작업을 수행 해야 합니다. 분석.</span><span class="sxs-lookup"><span data-stu-id="4c575-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="4c575-131">예를 들어 데이터를 쉼표로 구분 된 값 파일 (\\C: data\\IP\_Phone\_의\_보고서 .csv)로 내보내야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="4c575-132">이 경우 다음 두 명령을 사용 하 여 모든 휴대폰에 대 한 요약 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="4c575-133">이는 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="4c575-134">마찬가지로,이 두 명령어는 시스템에 로그온 했지만 실제로는 전화를 거는 데 사용 되지 않은 것을 알려 줍니다 (마지막 활동 메트릭의 값이 비어 있는 경우 마지막 작업이 없음을 나타냄).</span><span class="sxs-lookup"><span data-stu-id="4c575-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="4c575-135">이것은 사용 되지 않은 각 전화기에 대해 다음과 비슷한 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="4c575-136">Ip 휴대폰의 MAC 주소를 사용 하는 또 다른 흥미로운 방법은 MAC 주소 텍스트 상자에 해당 주소를 입력 하 여 해당 전화기를 마지막으로 사용한 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="4c575-137">그러면 IP 전화 목록 보고서가 해당 전화기로 마지막으로 로그인 한 사용자의 SIP 주소를 다시 보고 합니다 (다른 항목 중).</span><span class="sxs-lookup"><span data-stu-id="4c575-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="4c575-138">또는 사용자의 SIP 주소 (사용자 URI 접두사 상자)를 입력 하 여 해당 사용자가 사용한 모든 전화를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4c575-139">필터가</span><span class="sxs-lookup"><span data-stu-id="4c575-139">Filters</span></span>

<span data-ttu-id="4c575-140">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4c575-141">예를 들어 IP 전화 인벤터리를 사용 하 여 특정 회사 또는 특정 버전의 휴대폰으로 제조 된 전화만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-141">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="4c575-142">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="4c575-143">이 경우, 등록은 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-143">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4c575-144">다음 표에는 IP 전화 인벤토리 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="4c575-145">IP 전화 인벤터리 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="4c575-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c575-146">이름</span><span class="sxs-lookup"><span data-stu-id="4c575-146">Name</span></span></th>
<th><span data-ttu-id="4c575-147">설명</span><span class="sxs-lookup"><span data-stu-id="4c575-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c575-148"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-149">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-149">Start date/time for the time range.</span></span> <span data-ttu-id="4c575-150">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-150">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4c575-151">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="4c575-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4c575-152">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-152">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4c575-153">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-153">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4c575-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4c575-154">7/7/2012</span></span></p>
<p><span data-ttu-id="4c575-155">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="4c575-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4c575-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4c575-156">7/3/2012</span></span></p>
<p><span data-ttu-id="4c575-157">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-158"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-159">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-159">End date/time for the time range.</span></span> <span data-ttu-id="4c575-160">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-160">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4c575-161">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="4c575-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4c575-162">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-162">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4c575-163">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-163">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4c575-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4c575-164">7/7/2012</span></span></p>
<p><span data-ttu-id="4c575-165">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="4c575-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4c575-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4c575-166">7/3/2012</span></span></p>
<p><span data-ttu-id="4c575-167">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-168"><strong>제조업체</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-169">IP 전화기를 제조 하는 회사의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-169">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="4c575-170">이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기준으로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-170">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-171"><strong>하드웨어 버전</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-172">IP 전화의 버전 번호입니다. 제조업체 및 하드웨어 버전 필터를 사용 하 여 특정 유형의 휴대폰을 고유 하 게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="4c575-173">이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기준으로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-174"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-175">IP 휴대폰에서 사용 하는 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-175">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="4c575-176">이 필터에 대 한 값은 현재 데이터베이스에 있는 IP 전화를 기준으로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-176">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-177"><strong>MAC 주소</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-178">IP 휴대폰의 네트워크 인터페이스에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-178">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="4c575-179">MAC (미디어 액세스 제어) 주소는 일반적으로 휴대폰을 제조 하 고 디바이스 하드웨어에 하드 연결 되어 있는 시점에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-179">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="4c575-180">특정 MAC 주소와 관련 된 레코드를 검색 하려면 해당 주소를 입력 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-180">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="4c575-181">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-181">For example:</span></span></p>
<p><span data-ttu-id="4c575-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="4c575-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="4c575-183">전체 주소를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-183">You must enter the complete address.</span></span> <span data-ttu-id="4c575-184">일부 주소 (예: 00-08-5D)는 데이터를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-184">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-185"><strong>일 전 마지막 활동</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-186">다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c575-187">모든</span><span class="sxs-lookup"><span data-stu-id="4c575-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c575-188">1천만</span><span class="sxs-lookup"><span data-stu-id="4c575-188">10</span></span></p></li>
<li><p><span data-ttu-id="4c575-189">명</span><span class="sxs-lookup"><span data-stu-id="4c575-189">20</span></span></p></li>
<li><p><span data-ttu-id="4c575-190">30</span><span class="sxs-lookup"><span data-stu-id="4c575-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-191"><strong>마지막 로그 인 날짜 이전 시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-192">다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c575-193">모든</span><span class="sxs-lookup"><span data-stu-id="4c575-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c575-194">1천만</span><span class="sxs-lookup"><span data-stu-id="4c575-194">10</span></span></p></li>
<li><p><span data-ttu-id="4c575-195">명</span><span class="sxs-lookup"><span data-stu-id="4c575-195">20</span></span></p></li>
<li><p><span data-ttu-id="4c575-196">30</span><span class="sxs-lookup"><span data-stu-id="4c575-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-197"><strong>사용자 URI 접두사</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-198">IP 전화를 사용한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4c575-199">매트릭스</span><span class="sxs-lookup"><span data-stu-id="4c575-199">Metrics</span></span>

<span data-ttu-id="4c575-200">다음 표에는 IP 전화 인벤토리 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="4c575-201">IP 전화 인벤토리 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c575-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c575-202">이름</span><span class="sxs-lookup"><span data-stu-id="4c575-202">Name</span></span></th>
<th><span data-ttu-id="4c575-203">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="4c575-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c575-204">설명</span><span class="sxs-lookup"><span data-stu-id="4c575-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c575-205"><strong>제조업체</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-206">예</span><span class="sxs-lookup"><span data-stu-id="4c575-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-207">IP 전화기를 제조 하는 회사의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-208"><strong>하드웨어 버전</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-209">예</span><span class="sxs-lookup"><span data-stu-id="4c575-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-210">IP 전화기의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-211"><strong>MAC 주소</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-212">예</span><span class="sxs-lookup"><span data-stu-id="4c575-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-213">IP 휴대폰의 네트워크 인터페이스에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-213">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="4c575-214">MAC 주소는 일반적으로 휴대폰을 제조할 때 할당 되며 디바이스 하드웨어에 하드 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-214">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-215"><strong>사용자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-216">예</span><span class="sxs-lookup"><span data-stu-id="4c575-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-217">IP 전화를 사용한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-218"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-219">예</span><span class="sxs-lookup"><span data-stu-id="4c575-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-220">IP 휴대폰에서 사용 하는 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-221"><strong>마지막 로그온 시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-222">예</span><span class="sxs-lookup"><span data-stu-id="4c575-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-223">IP 전화가 Lync Server에 마지막으로 로그인 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c575-224"><strong>마지막 로그 인 시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-225">예</span><span class="sxs-lookup"><span data-stu-id="4c575-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-226">IP 전화가 Lync Server에서 마지막으로 로그 오프 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c575-227"><strong>마지막 활동</strong></span><span class="sxs-lookup"><span data-stu-id="4c575-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="4c575-228">예</span><span class="sxs-lookup"><span data-stu-id="4c575-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c575-229">IP 전화기를 마지막으로 사용한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c575-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

