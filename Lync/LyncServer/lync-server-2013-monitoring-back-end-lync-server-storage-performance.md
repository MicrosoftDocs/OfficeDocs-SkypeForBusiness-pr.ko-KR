---
title: 'Lync Server 2013: 백 엔드 Lync Server 저장소 성능 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4d3741564cd0228213400d7ee1fbb7271c4ddd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="b677e-102">다시 종료 Lync Server 2013 저장소 성능 모니터링</span><span class="sxs-lookup"><span data-stu-id="b677e-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b677e-103">_**마지막으로 수정한 주제:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="b677e-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="b677e-104">Lync Server 2013 백 엔드 데이터베이스는 Lync Server 2013 배포에서 매우 중요 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="b677e-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b677e-105">Lync Server 2013 백 엔드가 최적으로 수행 되 고 있는지 확인 하는 데 도움이 되도록 데이터베이스 및 해당 트랜잭션 로그를 지속적으로 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b677e-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="b677e-106">다음 표에서는 저장소 성능에 대 한 정보를 확인 하기 위해 모니터링 해야 하는 성능 카운터를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b677e-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="b677e-107">시스템 성능이 저하 될 때 성능 변화를 이해 하기 위해 이러한 카운터의 초기 계획 값을 먼저 결정 해야 합니다 (시스템의 정상적인 경우 부하가 예상 되는 경우).</span><span class="sxs-lookup"><span data-stu-id="b677e-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="b677e-108">모니터링할 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="b677e-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b677e-109">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="b677e-109">Performance Counter</span></span></th>
<th><span data-ttu-id="b677e-110">기준 임계값</span><span class="sxs-lookup"><span data-stu-id="b677e-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b677e-111">트랜잭션/초 (RTC)</span><span class="sxs-lookup"><span data-stu-id="b677e-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b677e-112">Rtcdyn (트랜잭션/초)</span><span class="sxs-lookup"><span data-stu-id="b677e-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b677e-113">트랜잭션/초 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="b677e-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b677e-114">로그 플러시/초 (RTC)</span><span class="sxs-lookup"><span data-stu-id="b677e-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b677e-115">로그 플러시/초 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="b677e-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b677e-116">로그 플러시/초 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="b677e-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b677e-117">Disk 전송/초 (읽기 + 쓰기)-RTC db</span><span class="sxs-lookup"><span data-stu-id="b677e-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b677e-118">Disk 전송/초-RTC 로그</span><span class="sxs-lookup"><span data-stu-id="b677e-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b677e-119">Disk 전송/초-rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="b677e-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b677e-120">디스크 전송/초-rtcdyn 로그</span><span class="sxs-lookup"><span data-stu-id="b677e-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

