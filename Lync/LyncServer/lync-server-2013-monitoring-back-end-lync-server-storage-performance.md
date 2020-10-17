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
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531955"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="814c6-102">모니터링 백 엔드 Lync Server 2013 저장소 성능</span><span class="sxs-lookup"><span data-stu-id="814c6-102">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="814c6-103">_**마지막으로 수정 된 항목:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="814c6-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="814c6-104">Lync Server 2013 백 엔드 데이터베이스는 Lync Server 2013 배포에서 매우 중요 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="814c6-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="814c6-105">Lync Server 2013 백 엔드를 최적으로 수행 하 고 있는지 확인 하는 데 도움이 되도록 데이터베이스 및 각 트랜잭션 로그를 지속적으로 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="814c6-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="814c6-106">다음 표에는 저장소 성능에 대 한 정보를 파악 하기 위해 모니터링 해야 하는 성능 카운터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814c6-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="814c6-107">시스템이 스트레스를 받을 때 성능 변경을 이해 하기 위해 이러한 카운터의 초기 계획 값을 먼저 결정 해야 합니다 (시스템이 정상, 예상 되는 부하).</span><span class="sxs-lookup"><span data-stu-id="814c6-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="814c6-108">모니터링할 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="814c6-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="814c6-109">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="814c6-109">Performance Counter</span></span></th>
<th><span data-ttu-id="814c6-110">기준 임계값</span><span class="sxs-lookup"><span data-stu-id="814c6-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="814c6-111">초당 트랜잭션 (RTC)</span><span class="sxs-lookup"><span data-stu-id="814c6-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814c6-112">초당 트랜잭션 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="814c6-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814c6-113">초당 트랜잭션 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="814c6-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814c6-114">로그 플러시/초 (RTC)</span><span class="sxs-lookup"><span data-stu-id="814c6-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814c6-115">로그 플러시/초 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="814c6-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814c6-116">로그 플러시/초 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="814c6-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814c6-117">초당 디스크 전송-RTC db</span><span class="sxs-lookup"><span data-stu-id="814c6-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814c6-118">초당 디스크 전송-RTC 로그</span><span class="sxs-lookup"><span data-stu-id="814c6-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814c6-119">초당 디스크 전송 rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="814c6-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814c6-120">초당 디스크 전송 rtcdyn 로그</span><span class="sxs-lookup"><span data-stu-id="814c6-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

