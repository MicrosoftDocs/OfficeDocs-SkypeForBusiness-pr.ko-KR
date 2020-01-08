---
title: 'Lync Server 2013: 그룹 채팅 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="d0a6b-102">Lync Server 2013에서 그룹 채팅 모니터링</span><span class="sxs-lookup"><span data-stu-id="d0a6b-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0a6b-103">_**마지막으로 수정한 주제:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="d0a6b-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="d0a6b-104">성능 향상을 위해 Microsoft 다운로드 센터에서 제공 하는 최신 [누적 서버 업데이트 설치 관리자](http://support.microsoft.com/kb/968802) 를 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="d0a6b-105">최신 누적 업데이트를 실행 하는 경우 메트릭 용 다음 스트레스 테스트 표를 사용 하 여 그룹 채팅 서버가 최적의 상태에서 실행 중인지 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="d0a6b-106">테스트 환경 및 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="d0a6b-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="d0a6b-107">그룹 채팅 풀에 있는 세 개의 그룹 채팅 서버 (각각 8gb 메모리 및 8 개 프로세서).</span><span class="sxs-lookup"><span data-stu-id="d0a6b-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a6b-108">두 개의 Lync Server 2013 프런트 엔드가 Enterprise Edition에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a6b-109">3 개의 그룹 채팅 서버에서 동시 사용자 6만.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a6b-110">그룹 채팅 풀이 호스트 하는 25000 채널.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a6b-111">채널 크기:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-112">작은 채널 크기: 30</span><span class="sxs-lookup"><span data-stu-id="d0a6b-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-113">중간 채널 크기: 150</span><span class="sxs-lookup"><span data-stu-id="d0a6b-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-114">큰 채널 크기: 2500</span><span class="sxs-lookup"><span data-stu-id="d0a6b-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a6b-115">채널 수:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-116">숫자 작은 채널: 24000</span><span class="sxs-lookup"><span data-stu-id="d0a6b-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-117">숫자 중간 채널 800</span><span class="sxs-lookup"><span data-stu-id="d0a6b-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-118">숫자 대형 채널 24</span><span class="sxs-lookup"><span data-stu-id="d0a6b-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-119">총 채널 24824</span><span class="sxs-lookup"><span data-stu-id="d0a6b-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a6b-120">채널 초대:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-121">채널의 절반은 초대 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a6b-122">사용자가 참가 하는 채널 수:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-123">작음: 12</span><span class="sxs-lookup"><span data-stu-id="d0a6b-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-124">보통: 2</span><span class="sxs-lookup"><span data-stu-id="d0a6b-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="d0a6b-125">큼: 1</span><span class="sxs-lookup"><span data-stu-id="d0a6b-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a6b-126">참가 속도:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-127">총 10 개/초, 3.33/초/서버 당</span><span class="sxs-lookup"><span data-stu-id="d0a6b-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a6b-128">로그 아웃 속도:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-129">총 10 개/초, 3.33/초/서버 당</span><span class="sxs-lookup"><span data-stu-id="d0a6b-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a6b-130">채팅 속도:</span><span class="sxs-lookup"><span data-stu-id="d0a6b-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0a6b-131">서버 당 총 20 개/초, 6.66/초</span><span class="sxs-lookup"><span data-stu-id="d0a6b-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0a6b-132">다음 성능 카운터 번호는 다양 한 하드웨어 사양 또는 사용자 프로필을 사용할 때 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6b-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="d0a6b-133">모니터링할 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="d0a6b-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0a6b-134">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="d0a6b-134">Performance Counter</span></span></th>
<th><span data-ttu-id="d0a6b-135">하나만</span><span class="sxs-lookup"><span data-stu-id="d0a6b-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0a6b-136">프로세스 (ChannelService)-&gt;% 프로세서 시간</span><span class="sxs-lookup"><span data-stu-id="d0a6b-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="d0a6b-137">Min: 0</span><span class="sxs-lookup"><span data-stu-id="d0a6b-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

