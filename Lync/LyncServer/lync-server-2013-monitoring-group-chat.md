---
title: 'Lync Server 2013: 그룹 채팅 모니터링'
description: 'Lync Server 2013: 그룹 채팅 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562034"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="e4c6a-103">Lync Server 2013의 모니터링 그룹 채팅</span><span class="sxs-lookup"><span data-stu-id="e4c6a-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4c6a-104">_**마지막으로 수정 된 항목:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="e4c6a-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="e4c6a-105">성능을 개선 하기 위해 Microsoft 다운로드 센터에서 제공 하는 최신 [누적 서버 업데이트 설치 관리자](https://support.microsoft.com/kb/968802) 를 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4c6a-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="e4c6a-106">최신 누적 업데이트를 실행 중인 경우 메트릭 용으로 다음 스트레스 테스트 테이블을 사용 하 여 그룹 채팅 서버가 최적의 상태에서 실행 되 고 있는지 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4c6a-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="e4c6a-107">테스트 환경 및 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="e4c6a-107">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-108">그룹 채팅 풀에 있는 세 개의 그룹 채팅 서버 (각각 8gb 메모리 및 8 개의 프로세서 포함)</span><span class="sxs-lookup"><span data-stu-id="e4c6a-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c6a-109">Enterprise Edition에서 두 Lync Server 2013 프런트 엔드가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4c6a-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-110">3 개의 그룹 채팅 서버에 걸친 동시 사용자 6만</span><span class="sxs-lookup"><span data-stu-id="e4c6a-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c6a-111">그룹 채팅 풀이 호스트 하는 25000 채널</span><span class="sxs-lookup"><span data-stu-id="e4c6a-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-112">채널 크기:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-113">작은 채널 크기: 30</span><span class="sxs-lookup"><span data-stu-id="e4c6a-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-114">중간 규모 채널 크기: 150</span><span class="sxs-lookup"><span data-stu-id="e4c6a-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-115">큰 채널 크기: 2500</span><span class="sxs-lookup"><span data-stu-id="e4c6a-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c6a-116">채널 수:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-117">작은 채널 수: 24000</span><span class="sxs-lookup"><span data-stu-id="e4c6a-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-118">중간 규모 채널 800</span><span class="sxs-lookup"><span data-stu-id="e4c6a-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-119">큰 채널 24 개</span><span class="sxs-lookup"><span data-stu-id="e4c6a-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-120">총 채널 24824</span><span class="sxs-lookup"><span data-stu-id="e4c6a-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-121">초대 채널:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-122">채널의 절반은 초대 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="e4c6a-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c6a-123">사용자가 참가 하는 채널 수:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-124">작음: 12</span><span class="sxs-lookup"><span data-stu-id="e4c6a-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-125">중간: 2</span><span class="sxs-lookup"><span data-stu-id="e4c6a-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="e4c6a-126">큼: 1</span><span class="sxs-lookup"><span data-stu-id="e4c6a-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-127">조인 비율:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-128">초당 10 개 합계/초, 3.33/초당 서버 당</span><span class="sxs-lookup"><span data-stu-id="e4c6a-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c6a-129">로그 아웃 비율:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-130">초당 10 개 합계/초, 3.33/초당 서버 당</span><span class="sxs-lookup"><span data-stu-id="e4c6a-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-131">채팅 속도:</span><span class="sxs-lookup"><span data-stu-id="e4c6a-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4c6a-132">서버당 초당 20 개, 초당 6.66/초</span><span class="sxs-lookup"><span data-stu-id="e4c6a-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4c6a-133">다음 성능 카운터 번호는 서로 다른 하드웨어 사양 또는 사용자 프로필을 사용할 때 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4c6a-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="e4c6a-134">모니터링할 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="e4c6a-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4c6a-135">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="e4c6a-135">Performance Counter</span></span></th>
<th><span data-ttu-id="e4c6a-136">임계값</span><span class="sxs-lookup"><span data-stu-id="e4c6a-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4c6a-137">프로세스 (ChannelService)- &gt; % 프로세서 시간</span><span class="sxs-lookup"><span data-stu-id="e4c6a-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="e4c6a-138">최소값: 0</span><span class="sxs-lookup"><span data-stu-id="e4c6a-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

