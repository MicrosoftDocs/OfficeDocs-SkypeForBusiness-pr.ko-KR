---
title: 'Lync Server 2013: 통화 대기에 대한 용량 계획'
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
ms.openlocfilehash: dd4cc9d10a3a3562c035c7bc2f64f551b70cc5da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="1565b-102">Lync Server 2013의 통화 대기에 대한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="1565b-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1565b-103">_**마지막으로 수정한 주제:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="1565b-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="1565b-104">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 통화 공원 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1565b-105">재해 복구 용량 계획을 위해 쌍으로 연결 된 풀의 각 풀은 두 풀의 통화 파킹 서비스에 대 한 작업 부하를 처리할 수 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="1565b-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="1565b-106">통화 공원 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="1565b-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1565b-107">미터</span><span class="sxs-lookup"><span data-stu-id="1565b-107">Metric</span></span></th>
<th><span data-ttu-id="1565b-108">프런트 엔드 풀 단위 (프런트 엔드 서버 8 개)</span><span class="sxs-lookup"><span data-stu-id="1565b-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="1565b-109">스탠더드 에디션 서버 당</span><span class="sxs-lookup"><span data-stu-id="1565b-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1565b-110">공원 요금</span><span class="sxs-lookup"><span data-stu-id="1565b-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="1565b-111">분당 8</span><span class="sxs-lookup"><span data-stu-id="1565b-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="1565b-112">분당 1</span><span class="sxs-lookup"><span data-stu-id="1565b-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1565b-113">파킹 통화 속도 검색</span><span class="sxs-lookup"><span data-stu-id="1565b-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="1565b-114">분당 8</span><span class="sxs-lookup"><span data-stu-id="1565b-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="1565b-115">분당 1</span><span class="sxs-lookup"><span data-stu-id="1565b-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1565b-116">평균 공원 기간</span><span class="sxs-lookup"><span data-stu-id="1565b-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="1565b-117">60 초</span><span class="sxs-lookup"><span data-stu-id="1565b-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="1565b-118">60 초</span><span class="sxs-lookup"><span data-stu-id="1565b-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

