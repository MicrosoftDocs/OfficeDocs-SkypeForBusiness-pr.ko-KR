---
title: 'Lync Server 2013: IP 전화 인벤토리 보고서'
description: 'Lync Server 2013: IP 전화 인벤토리 보고서'
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
ms.openlocfilehash: 3bc05017775ad64e0e18f876215aa2c6b3882bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575024"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="9473d-103">Lync Server 2013의 IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="9473d-103">IP Phone Inventory Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9473d-104">_**마지막으로 수정 된 항목:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="9473d-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="9473d-105">IP 전화 인벤토리 보고서는 조직에서 현재 사용 중인 IP 전화에 대 한 정보를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-105">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="9473d-106">IP 인벤토리 보고서에는 지정 된 보고 기간 동안 실제로 사용 된 IP 전화의 자세한 목록이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-106">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="9473d-107">무엇 보다도이 보고서를 통해 관리자는 기존에 사용 중인 오래 된 전화를 교체 해야 하는지 여부를 알 수 있습니다. 또한 조직에 거의 사용 되지 않는 고가의 전화가 있음을 관리자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-107">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="9473d-108">이러한 유형의 정보는 새 전화를 구입 하거나 기존 전화를 재배포할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-108">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="9473d-109">예를 들어 전화를 많이 사용 하는 사용자가 휴대폰을 자주 사용 하는 사용자와 휴대폰을 교체 하 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-109">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="9473d-110">이 보고서는 실제 인벤토리 보고서로 사용 될 때 몇 가지 제한 사항이 있음을 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-110">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="9473d-111">예를 들어 IP 전화 보고서에는 지정 된 기간 동안 Lync Server에 로그온 한 모든 전화가 마지막 로그온 시간을 기준으로 정렬 되어 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-111">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="9473d-112">지정 된 기간 동안 전화가 로그온 하지 않은 경우에는 해당 장치가 인벤토리 보고서에 나열 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-112">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="9473d-113">시작 하기 전에 로그온 하 여 지정 된 시간 간격 동안 계속 로그온 한 전화를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-113">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="9473d-114">예를 들어 2012 년 7 월의 모든 전화 인벤토리를 확인 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-114">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="9473d-115">또한 여러 전화가 Lync Server에 2012 년 6 월 30 일에 로그온 하 여 7 월 1 일부 터 계속 로그온 되어 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-115">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="9473d-116">해당 전화가 7 월 1 일에 대 한 인벤토리 보고서에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-116">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="9473d-117">또한 조직에서 더 이상 사용 하지 않는 전화가 인벤토리 보고서에 포함 될 수 있다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-117">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="9473d-118">예를 들어 시스템에 여러 Fabrikam 전화기가 2012 년 7 월 1 일에 로그온 했다고 가정 합니다. 5 일 후 조직에서 이러한 모든 Fabrikam 전화를 제거 하 고 새로운 Contoso 모델로 교체 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-118">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="9473d-119">Fabrikam 전화는 7 월 한 달 동안 시스템에 로그온 했기 때문에 "인벤터리" 보고서에 계속 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-119">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="9473d-120">또한 IP 전화 인벤토리 보고서에는 다양 한 유형의 휴대폰에 대 한 요약 합계가 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-120">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="9473d-121">예를 들어 105 Polycom CX600 휴대폰을 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-121">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="9473d-122">이 보고서에는 이러한 전화의 105이 있음을 알리는 메시지가 나타나지 않습니다. 대신, Polycom Cx600에 대해 105 별도의 항목을 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-122">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="9473d-123">Polycom Cx600에 대 한 항목의 수가 105 개 있다는 것을 확인 하는 유일한 방법은 이러한 각 항목의 수를 수동으로 계산 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-123">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9473d-124">또는 데이터를 내보낸 다음 Microsoft Excel 또는 Windows PowerShell을 사용 하 여 해당 횟수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-124">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="9473d-125">IP 전화 인벤토리 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="9473d-125">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="9473d-126">IP 전화 인벤토리 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-126">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="9473d-127">사용자 URI 메트릭을 클릭 하면 해당 사용자에 대 한 사용자 활동 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-127">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="9473d-128">피어 투 피어 통화에 대 한 마지막 활동 메트릭을 클릭 하면 피어 투 피어 세션 세부 정보 보고서로 이동 됩니다. 회의에 대해 같은 메트릭을 클릭 하면 전화 회의 정보 보고서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-128">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="9473d-129">IP 전화 인벤토리 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="9473d-129">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="9473d-130">특정 유형의 휴대폰에 대 한 사용 현황 정보에 관심이 있는 경우 (예: "Polycom CX600 휴대폰을 사용 하는 사용자는?") 해당 특정 유형의 전화를 필터링 하 여 IP 전화 인벤토리 보고서에서 해당 정보를 직접 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-130">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="9473d-131">그러나 모든 휴대폰에 대 한 요약 정보를 보려는 경우 (Polycom CX600을 LG-Nortel 사용 하는 사용자의 수는 몇 명), 이러한 유형의 분석을 수행 하려면 데이터를 내보내고 다른 응용 프로그램 (예: Windows PowerShell)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-131">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="9473d-132">예를 들어 데이터를 쉼표로 구분 된 값 파일 (C: \\ data \\ IP \_ 전화 \_ 인벤토리 \_Report.csv)으로 내보내야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-132">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="9473d-133">이 경우 다음 두 명령을 사용 하 여 모든 휴대폰에 대 한 요약 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-133">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="9473d-134">이 명령을 실행하면 다음과 같은 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-134">That will return data similar to this:</span></span>

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

<span data-ttu-id="9473d-135">마찬가지로, 이러한 두 명령은 시스템에 로그온 되어 있지만 실제로 통화를 수행 하는 데 사용 되지 않은 경우 (마지막 활동 메트릭 값이 비어 있는 경우 마지막 활동이 없음을 나타내는 경우)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-135">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="9473d-136">이는 사용 되지 않은 각 전화에 대해 다음과 비슷한 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-136">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="9473d-137">Ip 전화 인벤토리 보고서를 사용 하는 또 다른 흥미로운 방법은 다음과 같습니다. IP 전화의 MAC 주소가 있는 경우 MAC 주소 텍스트 상자에 해당 주소를 입력 하기만 하면 해당 전화를 마지막으로 사용한 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-137">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="9473d-138">그러면 IP 전화 인벤토리 보고서에서 이전에 해당 전화기로 로그온 한 사용자의 SIP 주소를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-138">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="9473d-139">또는 사용자 SIP 주소 (사용자 URI 접두사 상자)를 입력 하 여 해당 사용자가 사용 하는 모든 전화를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-139">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9473d-140">필터</span><span class="sxs-lookup"><span data-stu-id="9473d-140">Filters</span></span>

<span data-ttu-id="9473d-141">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-141">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="9473d-142">예를 들어 IP 전화 재고를 사용 하면 특정 회사에서 제조한 전화나 해당 휴대폰의 특정 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-142">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="9473d-143">또한 데이터의 그룹 지정 방식도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-143">You can also choose how data should be grouped.</span></span> <span data-ttu-id="9473d-144">이 경우 등록은 시, 일, 주 또는 월별로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-144">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9473d-145">다음 표에서는 IP 전화 인벤토리 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-145">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="9473d-146">IP 전화 인벤토리 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="9473d-146">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9473d-147">이름</span><span class="sxs-lookup"><span data-stu-id="9473d-147">Name</span></span></th>
<th><span data-ttu-id="9473d-148">설명</span><span class="sxs-lookup"><span data-stu-id="9473d-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9473d-149"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-p109">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9473d-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9473d-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9473d-p110">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9473d-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9473d-155">7/7/2012</span></span></p>
<p><span data-ttu-id="9473d-156">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9473d-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9473d-157">7/3/2012</span></span></p>
<p><span data-ttu-id="9473d-158">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-p111">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9473d-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9473d-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9473d-p112">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9473d-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9473d-165">7/7/2012</span></span></p>
<p><span data-ttu-id="9473d-166">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9473d-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9473d-167">7/3/2012</span></span></p>
<p><span data-ttu-id="9473d-168">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-169"><strong>회사</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-169"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-170">IP 전화를 제조한 회사의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-170">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="9473d-171">이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기반으로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-171">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-172"><strong>하드웨어 버전</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-172"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-173">IP 전화의 버전 번호입니다. 제조업체 및 하드웨어 버전 필터를 사용 하 여 특정 유형의 전화를 고유 하 게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-173">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="9473d-174">이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기반으로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-174">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-175"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-175"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-176">IP 전화에 사용 된 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-176">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="9473d-177">이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기반으로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-177">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-178"><strong>MAC 주소</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-178"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-179">IP 전화의 네트워크 인터페이스에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-179">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="9473d-180">MAC (미디어 액세스 제어) 주소는 일반적으로 전화기가 제조 되는 시점에 할당 되며 장치 하드웨어에 유선으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-180">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="9473d-181">특정 MAC 주소와 관련 된 레코드를 검색 하려면 해당 주소를 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-181">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="9473d-182">예제:</span><span class="sxs-lookup"><span data-stu-id="9473d-182">For example:</span></span></p>
<p><span data-ttu-id="9473d-183">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="9473d-183">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="9473d-184">전체 주소를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-184">You must enter the complete address.</span></span> <span data-ttu-id="9473d-185">일부 주소 (예: 00-08-5D)는 데이터를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-185">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-186"><strong>다음 일 이전의 마지막 활동</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-186"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-187">다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-187">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9473d-188">모든</span><span class="sxs-lookup"><span data-stu-id="9473d-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="9473d-189">10  </span><span class="sxs-lookup"><span data-stu-id="9473d-189">10</span></span></p></li>
<li><p><span data-ttu-id="9473d-190">20cm(8</span><span class="sxs-lookup"><span data-stu-id="9473d-190">20</span></span></p></li>
<li><p><span data-ttu-id="9473d-191">kb</span><span class="sxs-lookup"><span data-stu-id="9473d-191">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-192"><strong>다음 일 이전의 마지막 로그 오프 시간</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-192"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-193">다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-193">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9473d-194">모든</span><span class="sxs-lookup"><span data-stu-id="9473d-194">[All]</span></span></p></li>
<li><p><span data-ttu-id="9473d-195">10  </span><span class="sxs-lookup"><span data-stu-id="9473d-195">10</span></span></p></li>
<li><p><span data-ttu-id="9473d-196">20cm(8</span><span class="sxs-lookup"><span data-stu-id="9473d-196">20</span></span></p></li>
<li><p><span data-ttu-id="9473d-197">kb</span><span class="sxs-lookup"><span data-stu-id="9473d-197">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-198"><strong>사용자 URI 접두사</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-199">IP 전화를 사용한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-199">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9473d-200">메트릭</span><span class="sxs-lookup"><span data-stu-id="9473d-200">Metrics</span></span>

<span data-ttu-id="9473d-201">다음 표에서는 IP 전화 인벤토리 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-201">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="9473d-202">IP 전화 인벤토리 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="9473d-202">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9473d-203">이름</span><span class="sxs-lookup"><span data-stu-id="9473d-203">Name</span></span></th>
<th><span data-ttu-id="9473d-204">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="9473d-204">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9473d-205">설명</span><span class="sxs-lookup"><span data-stu-id="9473d-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9473d-206"><strong>회사</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-206"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-207">예</span><span class="sxs-lookup"><span data-stu-id="9473d-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-208">IP 전화를 제조한 회사의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-208">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-209"><strong>하드웨어 버전</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-209"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-210">예</span><span class="sxs-lookup"><span data-stu-id="9473d-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-211">IP 전화의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-211">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-212"><strong>MAC 주소</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-212"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-213">예</span><span class="sxs-lookup"><span data-stu-id="9473d-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-214">IP 전화의 네트워크 인터페이스에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-214">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="9473d-215">일반적으로 MAC 주소는 전화가 제조 되는 시점에 할당 되며 장치 하드웨어에 유선으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-215">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-216"><strong>사용자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-216"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-217">예</span><span class="sxs-lookup"><span data-stu-id="9473d-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-218">IP 전화를 사용한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-218">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-219"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-219"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-220">예</span><span class="sxs-lookup"><span data-stu-id="9473d-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-221">IP 전화에 사용 된 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-221">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-222"><strong>마지막 로그온 시간</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-222"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-223">예</span><span class="sxs-lookup"><span data-stu-id="9473d-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-224">IP 전화가 Lync Server에 마지막으로 로그온 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-224">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9473d-225"><strong>마지막 로그 오프 시간</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-225"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-226">예</span><span class="sxs-lookup"><span data-stu-id="9473d-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-227">IP 전화가 Lync Server에서 마지막으로 로그 오프 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-227">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9473d-228"><strong>마지막 활동</strong></span><span class="sxs-lookup"><span data-stu-id="9473d-228"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="9473d-229">예</span><span class="sxs-lookup"><span data-stu-id="9473d-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="9473d-230">IP 전화를 마지막으로 사용한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9473d-230">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

