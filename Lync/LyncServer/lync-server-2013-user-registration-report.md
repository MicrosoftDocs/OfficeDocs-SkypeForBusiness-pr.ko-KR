---
title: 'Lync Server 2013: 사용자 등록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716d8324fba8346fa1326da2ed253dfa07bc3915
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="43aac-102">Lync Server 2013의 사용자 등록 보고서</span><span class="sxs-lookup"><span data-stu-id="43aac-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43aac-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="43aac-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="43aac-104">사용자 등록 보고서는 지정 된 기간 (매시간, 매일, 매주, 매월) 동안 Microsoft Lync Server 2013에 로그온 한 사용자 수에 대 한 정보를 사용자 로그온 작업에 대 한 개요로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="43aac-105">이 보고서에는 로그온한 사용자의 수만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="43aac-106">즉, *누가* 로그온했는지는 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="43aac-107">모니터링 보고서는 어떤 사용자가 Lync Server 2013를 사용 하 고 있는지와 어떤 것이 아닌 경우에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="43aac-108">그러나 사용자 활동 보고서를 사용하면 대략적인 사용자 정보를 파악할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="43aac-109">사용자 등록 보고서는 사용자 로그온에 대한 정보를 제공할 때 두 가지 주요 기준을 사용하여 정보를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="43aac-110">첫째로, 이 보고서에서는 로그온이 두 가지 기본 범주(내부 로그온/외부 로그온)로 구별됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="43aac-111">내부 로그온은 회사 네트워크에 연결되어 있는 동안 조직 방화벽 내에서 로그온한 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="43aac-112">외부 로그온은에 지 서버를 통해 방화벽 외부에서 로그온 한 사용자 (예: 인터넷에서 로그온 한 사용자가 외부 로그온으로 café)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="43aac-113">방화벽 외부에서 로그온하는 사용자 수를 확인해야 하는 경우 사용자 등록 보고서에서 해당 정보를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="43aac-114">사용자 등록 보고서는 지정된 기간 동안의 *활성* 사용자 수에 대한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="43aac-115">활성 사용자는 IM (인스턴트 메시징) 세션에 참여 하거나, Lync 모임에 참가 하거나, 전화를 걸거나 받거나, 아니면 해당 기간 동안 Lync Server를 사용 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="43aac-116">활성 사용자는 로그온하기는 했지만 시스템을 실제로 사용한 적은 없는 사용자와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="43aac-117">사용자 등록 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="43aac-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="43aac-p104">사용자 등록 보고서는 모니터링 보고서 홈 페이지에서만 액세스할 수 있습니다. 이 보고서는 다른 보고서에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="43aac-120">효율적인 사용자 등록 보고서 활용</span><span class="sxs-lookup"><span data-stu-id="43aac-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="43aac-121">Lync Server를 배포한 후에는 사용자가이 새로운 기술을 실제로 사용 하는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="43aac-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="43aac-122">이와 관련하여 몇 가지 제한이 있기는 하지만, 사용자 등록 보고서를 사용하면 해당 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="43aac-123">사용자가 Lync Server를 사용 하 고 있는지 여부를 확인 하려면 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="43aac-124">먼저 사용자 등록 보고서에서 고유 로그온 사용자 메트릭 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="43aac-125">이 값은 Lync Server에 로그온 한 개별 개별 사용자의 수를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="43aac-126">비교를 통해 총 로그온 메트릭은 모든 사용자가 Lync Server에 로그온 한 총 시간 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="43aac-127">예를 들어 Ken Myer가 하루에 여러 번 Lync Server에 로그온 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="43aac-128">이 경우 Ken Myer의 로그온은 총 로그온 메트릭에서는 5회의 개별 로그온 세션으로 계산되지만 고유 로그온 사용자 메트릭에서는 단일 로그온 사용자로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="43aac-129">마찬가지로, 사용자가 여러 장치나 여러 위치에서 로그온하는 경우도 흔합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="43aac-130">예를 들어 사용자는 데스크톱 컴퓨터의 랩톱 컴퓨터를 사용 하 여 로그온 할 수 있으며 Lync Server에 자동으로 로그온 하는 IP 전화가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="43aac-131">이 예제의 경우 로그온 횟수는 3회이지만 고유 사용자는 1명입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="43aac-132">총 로그온과 고유 로그온 간의 차이를 보다 자세하게 파악하려면 아래 표에 나와 있는 지정된 기간 동안의 로그온을 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="43aac-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43aac-133">사용자</span><span class="sxs-lookup"><span data-stu-id="43aac-133">User</span></span></th>
<th><span data-ttu-id="43aac-134">로그온 시간</span><span class="sxs-lookup"><span data-stu-id="43aac-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43aac-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="43aac-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="43aac-136">2012/7/7 오전 8:45</span><span class="sxs-lookup"><span data-stu-id="43aac-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="43aac-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="43aac-138">2012/7/7 오전 8:46</span><span class="sxs-lookup"><span data-stu-id="43aac-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43aac-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="43aac-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="43aac-140">2012/7/7 오전 9:17</span><span class="sxs-lookup"><span data-stu-id="43aac-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="43aac-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="43aac-142">2012/7/7 오전 9:22</span><span class="sxs-lookup"><span data-stu-id="43aac-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43aac-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="43aac-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="43aac-144">2012/7/7 오전 9:31</span><span class="sxs-lookup"><span data-stu-id="43aac-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="43aac-p107">이 경우 총 로그온 횟수는 5회이지만 고유 로그온 사용자는 2명(3회 로그온한 Ken Myer, 2회 로그온한 Pilar Ackerman)입니다. 이처럼 로그온 횟수와 고유 로그온 사용자 수는 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="43aac-147">고유한 로그온 수를 아는 것 외에도 Lync Server에 대해 사용 하도록 설정 된 총 사용자 수를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="43aac-148">Lync Server 2013 관리 셸을 열고 다음 Windows PowerShell 명령을 실행 하 여이 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="43aac-149">위의 명령이 값 1236을 반환 하 고 고유 로그온 사용자 메트릭이 평균 값 667를 반환 하는 경우, 사용자가 Lync에 대해 거의 모든 부분을 사용 하도록 설정 하는 것은 실제로 매일 시스템에 로그온 하는 것을 제안 합니다 (즉, 667은 1236으로 구분 됨). ,이는 대략 54%입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="43aac-150">로그온 메트릭은 지정된 기간 동안 실제로 로그온한 사용자를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="43aac-151">그러나 시스템에 이미 로그온되어 있는 사용자는 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="43aac-152">예를 들어 고유 로그온 사용자 메트릭에서 로그온 667회를 표시하는데 사용자 수는 1,236명이면 사용자 중 절반 정도가 시스템에 로그온함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="43aac-153">그러나 로그온 데이터 확인을 시작한 시간에 사용자 300명이 시스템에 이미 로그온한 상태라고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="43aac-154">이는 실제로 거의 1000 사용자가 Lync Server에 로그온 했을 것 이며,이는 사용자의 80%에 가까울수록 더 가까이 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="43aac-155">고유 로그온 사용자 값은 고유 활성 사용자 메트릭과도 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="43aac-156">고유한 활성 사용자 메트릭은 Lync Server에 실제로 사용 된 고유한 사용자 수, 즉 전화를 걸거나 Lync 모임에 참가 했거나 IM 세션에 참가 했음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="43aac-157">이는 사용자가 Windows를 시작할 때마다 자동으로 시작 되도록 Microsoft Lync 2013을 구성할 수 있기 때문에 유용한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="43aac-158">따라서 매일 Windows에 로그온 할 때 Lync에 자동으로 로그온 하는 사용자가 많고이 기간 동안에는 실제로 Lync Server를 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="43aac-159">또한 고유한 활성 사용자 메트릭은 사용자가 대개 하루 종일 Windows를 로그 오프 하지 않는 조직에서 더 의미 있는 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="43aac-160">대신 컴퓨터를 잠그고 Windows 및 Lync를 실행 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="43aac-161">이러한 상황에서는 사용자가 로그온한 상태를 며칠씩 유지하고 로그오프하지는 않기 때문에 일별 로그온 수가 매우 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="43aac-162">그러나 고유한 활성 사용자는 사용자가 Lync 또는 다른 Lync Server 클라이언트를 사용 중인지 여부를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="43aac-163">필터</span><span class="sxs-lookup"><span data-stu-id="43aac-163">Filters</span></span>

<span data-ttu-id="43aac-164">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="43aac-165">예를 들어 사용자 등록 보고서를 사용 하면 모든 등록자 풀 및에 지 서버에 대 한 데이터를 보거나 개별 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="43aac-166">또한 데이터의 그룹 지정 방식도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="43aac-167">이 경우 등록은 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="43aac-168">다음 표에서는 사용자 등록 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="43aac-169">사용자 등록 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="43aac-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43aac-170">이름</span><span class="sxs-lookup"><span data-stu-id="43aac-170">Name</span></span></th>
<th><span data-ttu-id="43aac-171">설명</span><span class="sxs-lookup"><span data-stu-id="43aac-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43aac-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-p113">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="43aac-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="43aac-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="43aac-p114">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="43aac-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="43aac-178">7/7/2012</span></span></p>
<p><span data-ttu-id="43aac-179">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="43aac-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="43aac-180">7/3/2012</span></span></p>
<p><span data-ttu-id="43aac-181">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-p115">시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="43aac-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="43aac-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="43aac-p116">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="43aac-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="43aac-188">7/7/2012</span></span></p>
<p><span data-ttu-id="43aac-189">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="43aac-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="43aac-190">7/3/2012</span></span></p>
<p><span data-ttu-id="43aac-191">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43aac-192"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-p117">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="43aac-195">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="43aac-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="43aac-196">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="43aac-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="43aac-197">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="43aac-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="43aac-198">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="43aac-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="43aac-p118">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-201"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-202">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="43aac-203">개별 풀을 선택하거나 <strong>[모두]</strong>를 선택하여 모든 풀에 대한 데이터를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="43aac-204">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="43aac-205">선별한</span><span class="sxs-lookup"><span data-stu-id="43aac-205">Metrics</span></span>

<span data-ttu-id="43aac-206">다음 표에서는 사용자 등록 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="43aac-207">사용자 등록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="43aac-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43aac-208">이름</span><span class="sxs-lookup"><span data-stu-id="43aac-208">Name</span></span></th>
<th><span data-ttu-id="43aac-209">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="43aac-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="43aac-210">설명</span><span class="sxs-lookup"><span data-stu-id="43aac-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43aac-211"><strong>매시간</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="43aac-212"><strong>매일</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="43aac-213"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="43aac-214"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-215">아니요</span><span class="sxs-lookup"><span data-stu-id="43aac-215">No</span></span></p></td>
<td><p><span data-ttu-id="43aac-p120">필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 세부 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 2012/7/7을 클릭하면 해당 날짜의 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-219"><strong>총 로그온</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-220">아니요</span><span class="sxs-lookup"><span data-stu-id="43aac-220">No</span></span></p></td>
<td><p><span data-ttu-id="43aac-221">성공한 로그온 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43aac-222"><strong>내부 로그온</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-223">아니요</span><span class="sxs-lookup"><span data-stu-id="43aac-223">No</span></span></p></td>
<td><p><span data-ttu-id="43aac-224">내부 네트워크 내의 총 로그온 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-225"><strong>외부 로그온</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-226">아니요</span><span class="sxs-lookup"><span data-stu-id="43aac-226">No</span></span></p></td>
<td><p><span data-ttu-id="43aac-227">에지 서버를 사용하는 내부 네트워크 외부에서의 총 로그온 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43aac-228"><strong>고유 로그온 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-229">아니요</span><span class="sxs-lookup"><span data-stu-id="43aac-229">No</span></span></p></td>
<td><p><span data-ttu-id="43aac-p121">로그온 세션이 하나 이상 포함된 총 사용자 수입니다. 로그온 세션을 여러 개 갖고 있는 사용자도 한 명의 사용자로 계산되며 단일 로그온 세션을 갖고 있는 사용자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aac-232"><strong>고유 활성 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="43aac-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="43aac-233">아니요</span><span class="sxs-lookup"><span data-stu-id="43aac-233">No</span></span></p></td>
<td><p><span data-ttu-id="43aac-p122">피어 투 피어 또는 회의 세션에 포함된 총 사용자 수입니다. 세션을 여러 개 갖고 있는 사용자도 한 명의 사용자로 계산되며 단일 세션을 갖고 있는 사용자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="43aac-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

