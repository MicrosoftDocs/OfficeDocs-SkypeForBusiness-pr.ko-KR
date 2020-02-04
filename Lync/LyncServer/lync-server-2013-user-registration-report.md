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
ms.openlocfilehash: 079e6cb96a9401d909be4f459d7bbe7c3f6d4ed6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="ffc85-102">Lync Server 2013의 사용자 등록 보고서</span><span class="sxs-lookup"><span data-stu-id="ffc85-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc85-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ffc85-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ffc85-104">사용자 등록 보고서는 지정 된 기간 (매시간, 매일, 매주, 매월) 동안 Microsoft Lync Server 2013에 로그온 한 사용자 수에 대 한 정보를 사용자 로그온 활동에 대 한 개요로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="ffc85-105">보고서는 로그인 한 사용자 수만 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="ffc85-106">로그온 한 사용자에 게 *는* 알려 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="ffc85-107">모니터링 보고서는 특정 사용자가 Lync Server 2013를 사용 하 고 있는지 여부에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="ffc85-108">그러나 사용자 활동 보고서를 사용 하 여 대략적인 예측 한 사용자 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="ffc85-109">사용자 로그온에 대 한 정보를 제공할 때 사용자 등록 보고서는 두 가지 중요 한 차이점을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="ffc85-110">먼저, 로그온을 두 가지 기본 범주인 내부 로그온 및 외부 로그온으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="ffc85-111">내부 로그온은 조직의 방화벽 (즉, 회사 네트워크에 연결 된 상태) 내부에서 로그온 한 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="ffc85-112">외부 로그온은 Edge 서버를 통해 방화벽 외부에서 로그온 한 사용자를 나타냅니다 (예를 들어 인터넷 카페에서 로그온 한 사용자가 외부 로그인으로 간주).</span><span class="sxs-lookup"><span data-stu-id="ffc85-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="ffc85-113">사용자가 방화벽 외부에서 로그온 하는 횟수를 알아야 하는 경우 사용자 등록 보고서에이 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="ffc85-114">또한 사용자 등록 보고서에는 특정 기간 동안 발생 한 *활성* 사용자 수가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="ffc85-115">활성 사용자는 IM (인스턴트 메시징) 세션을 진행 하거나, Lync 모임에 참가 하거나, 전화를 걸거나 받거나, 그 기간 동안 Lync Server를 사용 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="ffc85-116">이는 로그온 한 사용자와 다르며, 실제로 시스템을 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="ffc85-117">사용자 등록 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="ffc85-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="ffc85-118">모니터링 보고서 홈 페이지 에서만 사용자 등록 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-118">You access the User Registration Report only from the Monitoring Reports home page.</span></span> <span data-ttu-id="ffc85-119">사용자 등록 보고서는 다른 보고서에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-119">The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="ffc85-120">사용자 등록 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="ffc85-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="ffc85-121">Lync Server를 배포한 후에는 다음을 수행 합니다. 사용자가 실제로이 새로운 기술을 사용 하 고 있는지 어떻게 알 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="ffc85-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="ffc85-122">여기에는 몇 가지 제한 사항이 있지만,이 질문에 대 한 답은 사용자 등록 보고서를 통해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="ffc85-123">사용자가 Lync Server를 사용 하 고 있는지 여부를 확인 하려면 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="ffc85-124">먼저, 사용자 등록 보고서에서 고유한 로그온 사용자 메트릭의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="ffc85-125">이 값을 통해 Lync Server에 로그온 한 개별 사용자의 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="ffc85-126">비교 하 여 총 로그온 메트릭은 사용자가 Lync Server에 로그온 한 총 시간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="ffc85-127">예를 들어 한 날에: 진구 Myer에서 Lync Server 5 개를 서로 다른 시간으로 로그온 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="ffc85-128">이 경우: 진구 Myer는 총 로그온 메트릭에 대해 5 개의 개별 로그온 세션으로 계산 되지만, 고유한 로그온 사용자 메트릭에 대해 하나의 로그온 사용자만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="ffc85-129">마찬가지로 사용자가 여러 장치 또는 여러 위치에서 로그온 하는 것은 드문 일입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="ffc85-130">예를 들어 사용자는 데스크톱 컴퓨터, 랩톱 컴퓨터를 사용 하 여 로그온 할 수 있으며 Lync Server에 자동으로 로그인 하는 IP 전화를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="ffc85-131">이 예제에는 세 개의 로그온이 있는 하나의 고유 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="ffc85-132">총 로그온과 고유 로그온 간의 차이에 대 한 자세한 설명을 보려면 다음 표의 지정 된 기간에 대 한 로그온을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="ffc85-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc85-133">사용자</span><span class="sxs-lookup"><span data-stu-id="ffc85-133">User</span></span></th>
<th><span data-ttu-id="ffc85-134">로그온 시간</span><span class="sxs-lookup"><span data-stu-id="ffc85-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-135">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="ffc85-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="ffc85-136">오전 7/7/2012 8:45</span><span class="sxs-lookup"><span data-stu-id="ffc85-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-137">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="ffc85-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="ffc85-138">오전 7/7/2012 8:46</span><span class="sxs-lookup"><span data-stu-id="ffc85-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="ffc85-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="ffc85-140">오전 7/7/2012 9:17</span><span class="sxs-lookup"><span data-stu-id="ffc85-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-141">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="ffc85-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="ffc85-142">오전 7/7/2012 9:22</span><span class="sxs-lookup"><span data-stu-id="ffc85-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="ffc85-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="ffc85-144">오전 7/7/2012 9:31</span><span class="sxs-lookup"><span data-stu-id="ffc85-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ffc85-145">총 5 개의 로그온이 있다는 점에 유의 하십시오. 그러나: 진구 Myer (3 번 로그온 한 경우) 및 Pilar Ackerman (두 번 로그인 한)에는 두 가지 고유한 로그온 사용자만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-145">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice).</span></span> <span data-ttu-id="ffc85-146">이는 로그온과 고유 로그온 사용자 간의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-146">That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="ffc85-147">고유한 로그온 횟수를 아는 것 외에도 Lync Server에 대해 사용 하도록 설정 된 총 사용자 수를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="ffc85-148">이 값은 Lync Server 2013 관리 셸을 열고 다음 Windows PowerShell 명령을 실행 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="ffc85-149">앞의 명령이 1236 및 고유 로그온 사용자 메트릭을 반환 하는 경우 사용자가 Lync에 대해 거의 매일 시스템에 로그인 하는 것을 제안 하는 평균값 667 (즉, 667을 1236로 나눈 값이 설정 됨)이 반환 됩니다. ,이는 대략 54%입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ffc85-150">로그온 메트릭은 지정 된 기간에 실제로 로그온 한 사용자를 기록 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ffc85-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="ffc85-151">시스템에 이미 로그온 한 사용자를 추적 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="ffc85-152">예를 들어 고유한 로그온 사용자 메트릭이 667 로그온을 표시 하 고 1236 사용자가 있는 경우 사용자가 시스템에 로그온 하 고 있다는 것을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="ffc85-153">그러나 300 사용자가 로그온 데이터를 확인 하기 시작 했을 때 이미 시스템에 로그온 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="ffc85-154">이것은 실제로 거의 1000 사용자가 Lync Server에 로그인 한 것을 의미 하는데,이는 사용자의 80%에 가까운 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="ffc85-155">또한 고유한 로그온 사용자 값을 고유 활성 사용자 메트릭의 값과 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="ffc85-156">고유한 활성 사용자 메트릭은 Lync Server를 사용 하 여 사용자에 게 전화를 걸거나 Lync 모임에 참가 했거나 메신저 대화 세션에 참가 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="ffc85-157">이는 사용자가 Windows를 시작할 때마다 자동으로 시작 되도록 Microsoft Lync 2013을 구성할 수 있기 때문에 유용한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="ffc85-158">이 때문에 하루에 Windows에 로그온 할 때 Lync에 자동으로 로그인 하는 사용자 수가 많을 수 있지만,이 기간 동안에는 실제로 Lync Server를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="ffc85-159">또한 고유한 활성 사용자 메트릭은 사용자가 일반적으로 일이 끝날 때 창을 로그 오프 하지 않는 조직에서 보다 의미 있는 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="ffc85-160">대신 컴퓨터를 잠그고 Windows 및 Lync가 실행 되는 것을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="ffc85-161">이러한 상황에서는 사용자가 며칠 전에 로그인 하 고 로그 오프할 수 없기 때문에 하루에 몇 번의 로그온이 끝날 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="ffc85-162">그러나 고유한 활성 사용자는 사용자가 현재 Lync 또는 다른 Lync Server 클라이언트를 사용 중인지 여부를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ffc85-163">필터가</span><span class="sxs-lookup"><span data-stu-id="ffc85-163">Filters</span></span>

<span data-ttu-id="ffc85-164">필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="ffc85-165">예를 들어 사용자 등록 보고서를 사용 하면 모든 등록자 풀 및 Edge 서버의 데이터를 보거나 개별 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="ffc85-166">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="ffc85-167">이 경우, 등록은 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ffc85-168">다음 표에는 사용자 등록 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="ffc85-169">사용자 등록 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="ffc85-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc85-170">이름</span><span class="sxs-lookup"><span data-stu-id="ffc85-170">Name</span></span></th>
<th><span data-ttu-id="ffc85-171">설명</span><span class="sxs-lookup"><span data-stu-id="ffc85-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-172"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-173">시간 범위에 대 한 시작 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-173">Start date and time for the time range.</span></span> <span data-ttu-id="ffc85-174">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-174">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ffc85-175">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="ffc85-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ffc85-176">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-176">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="ffc85-177">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-177">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ffc85-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ffc85-178">7/7/2012</span></span></p>
<p><span data-ttu-id="ffc85-179">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="ffc85-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ffc85-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ffc85-180">7/3/2012</span></span></p>
<p><span data-ttu-id="ffc85-181">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-182"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-183">시간 범위의 종료 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-183">End date and time for the time range.</span></span> <span data-ttu-id="ffc85-184">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-184">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ffc85-185">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="ffc85-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ffc85-186">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-186">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="ffc85-187">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-187">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ffc85-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ffc85-188">7/7/2012</span></span></p>
<p><span data-ttu-id="ffc85-189">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="ffc85-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ffc85-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ffc85-190">7/3/2012</span></span></p>
<p><span data-ttu-id="ffc85-191">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-192"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-193">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="ffc85-193">Time interval.</span></span> <span data-ttu-id="ffc85-194">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-194">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ffc85-195">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="ffc85-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ffc85-196">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="ffc85-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ffc85-197">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="ffc85-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ffc85-198">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="ffc85-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ffc85-199">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값의 수만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-199">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="ffc85-200">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-200">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-201"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-202">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="ffc85-203">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 선택 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="ffc85-204">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ffc85-205">매트릭스</span><span class="sxs-lookup"><span data-stu-id="ffc85-205">Metrics</span></span>

<span data-ttu-id="ffc85-206">다음 표에는 사용자 등록 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="ffc85-207">사용자 등록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="ffc85-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc85-208">이름</span><span class="sxs-lookup"><span data-stu-id="ffc85-208">Name</span></span></th>
<th><span data-ttu-id="ffc85-209">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ffc85-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ffc85-210">설명</span><span class="sxs-lookup"><span data-stu-id="ffc85-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-211"><strong>마다</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="ffc85-212"><strong>Daily</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="ffc85-213"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="ffc85-214"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-215">아니요</span><span class="sxs-lookup"><span data-stu-id="ffc85-215">No</span></span></p></td>
<td><p><span data-ttu-id="ffc85-216">필터 도구 모음에서 선택한 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-216">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="ffc85-217">해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="ffc85-218">예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-219"><strong>총 로그온 횟수</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-220">아니요</span><span class="sxs-lookup"><span data-stu-id="ffc85-220">No</span></span></p></td>
<td><p><span data-ttu-id="ffc85-221">성공한 로그온 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-222"><strong>내부 로그온</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-223">아니요</span><span class="sxs-lookup"><span data-stu-id="ffc85-223">No</span></span></p></td>
<td><p><span data-ttu-id="ffc85-224">내부 네트워크 내의 총 로그온 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-225"><strong>외부 로그온</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-226">아니요</span><span class="sxs-lookup"><span data-stu-id="ffc85-226">No</span></span></p></td>
<td><p><span data-ttu-id="ffc85-227">Edge 서버를 사용 하는 내부 네트워크 외부의 총 로그온 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc85-228"><strong>고유한 로그온 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-229">아니요</span><span class="sxs-lookup"><span data-stu-id="ffc85-229">No</span></span></p></td>
<td><p><span data-ttu-id="ffc85-230">하나 이상의 로그온 세션이 있는 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-230">Total number of users who had at least one logon session.</span></span> <span data-ttu-id="ffc85-231">여러 로그온 세션이 있는 사용자는 단일 로그온 세션만 갖는 사람과 같은 사용자로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-231">A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc85-232"><strong>고유한 활성 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="ffc85-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="ffc85-233">아니요</span><span class="sxs-lookup"><span data-stu-id="ffc85-233">No</span></span></p></td>
<td><p><span data-ttu-id="ffc85-234">피어 투 피어 또는 회의 세션에 참여 한 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-234">Total number of users who were involved in a peer-to-peer or conferencing session.</span></span> <span data-ttu-id="ffc85-235">여러 세션이 있는 사용자는 단일 세션을 소유한 사람과 같은 사용자로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc85-235">A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

