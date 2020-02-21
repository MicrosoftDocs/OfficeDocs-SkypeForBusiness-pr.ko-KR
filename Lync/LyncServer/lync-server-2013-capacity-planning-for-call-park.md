---
title: 'Lync Server 2013: 통화 대기에 대 한 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dd9ba479fff51491c1240ec42941615f7c476da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="435f6-102">Lync Server 2013의 통화 대기에 대 한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="435f6-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="435f6-103">_**마지막으로 수정 된 항목:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="435f6-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="435f6-104">다음 표에서는 용량 계획 요구 사항의 기반으로 사용할 수 있는 통화 대기 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="435f6-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="435f6-105">재해 복구 용량 계획을 위해 연결 된 풀의 각 풀은 두 풀에서 통화 대기 서비스의 작업을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="435f6-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="435f6-106">통화 대기 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="435f6-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="435f6-107">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="435f6-107">Metric</span></span></th>
<th><span data-ttu-id="435f6-108">프런트 엔드 풀 당 (8 개의 프런트 엔드 서버 포함)</span><span class="sxs-lookup"><span data-stu-id="435f6-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="435f6-109">Standard Edition Server별</span><span class="sxs-lookup"><span data-stu-id="435f6-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="435f6-110">대기 속도</span><span class="sxs-lookup"><span data-stu-id="435f6-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="435f6-111">분당 8개</span><span class="sxs-lookup"><span data-stu-id="435f6-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="435f6-112">분당 1개</span><span class="sxs-lookup"><span data-stu-id="435f6-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="435f6-113">대기 중인 통화 재개 속도</span><span class="sxs-lookup"><span data-stu-id="435f6-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="435f6-114">분당 8개</span><span class="sxs-lookup"><span data-stu-id="435f6-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="435f6-115">분당 1개</span><span class="sxs-lookup"><span data-stu-id="435f6-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="435f6-116">평균 대기 시간</span><span class="sxs-lookup"><span data-stu-id="435f6-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="435f6-117">60초</span><span class="sxs-lookup"><span data-stu-id="435f6-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="435f6-118">60초</span><span class="sxs-lookup"><span data-stu-id="435f6-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

