---
title: 'Lync Server 2013: 응답 그룹에 대 한 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c9d43f6424a8d960ad5d0eee911b2f48455a39d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="ad94d-102">Lync Server 2013의 응답 그룹에 대 한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="ad94d-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad94d-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ad94d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="ad94d-104">다음 표에서는 용량 계획 요구 사항의 기반으로 사용할 수 있는 응답 그룹 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad94d-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad94d-p101">다음 표의 숫자는 모든 응답 그룹 오디오 파일에 대해 16kHz, 모노, 16비트 Wave(.wav) 파일을 사용하고 있다는 가정을 바탕으로 합니다. Windows Media 오디오(.wma) 등과 같은 다른 파일 형식을 사용하는 경우에는 숫자가 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad94d-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad94d-107">재해 복구 용량 계획을 위해 한 쌍으로구성된 풀의 각 풀은 두 풀에 있는 모든 응답 그룹의 작업을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad94d-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="ad94d-108">응답 그룹 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="ad94d-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad94d-109">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ad94d-109">Metric</span></span></th>
<th><span data-ttu-id="ad94d-110">Enterprise Edition 풀 (8 개의 프런트 엔드 서버 포함)</span><span class="sxs-lookup"><span data-stu-id="ad94d-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="ad94d-111">Standard Edition Server별</span><span class="sxs-lookup"><span data-stu-id="ad94d-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad94d-112">초당 걸려오는 전화 수</span><span class="sxs-lookup"><span data-stu-id="ad94d-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="ad94d-113">16 </span><span class="sxs-lookup"><span data-stu-id="ad94d-113">16</span></span></p></td>
<td><p><span data-ttu-id="ad94d-114">2</span><span class="sxs-lookup"><span data-stu-id="ad94d-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad94d-115">IVR 또는 MoH에 연결된 동시 통화 수</span><span class="sxs-lookup"><span data-stu-id="ad94d-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="ad94d-116">480</span><span class="sxs-lookup"><span data-stu-id="ad94d-116">480</span></span></p></td>
<td><p><span data-ttu-id="ad94d-117">60</span><span class="sxs-lookup"><span data-stu-id="ad94d-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad94d-118">동시 익명 세션 수(IM 포함 안 함)</span><span class="sxs-lookup"><span data-stu-id="ad94d-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="ad94d-119">224</span><span class="sxs-lookup"><span data-stu-id="ad94d-119">224</span></span></p></td>
<td><p><span data-ttu-id="ad94d-120">28@@</span><span class="sxs-lookup"><span data-stu-id="ad94d-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad94d-121">동시 익명 세션 수(IM 포함)</span><span class="sxs-lookup"><span data-stu-id="ad94d-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="ad94d-122">64</span><span class="sxs-lookup"><span data-stu-id="ad94d-122">64</span></span></p></td>
<td><p><span data-ttu-id="ad94d-123">8 </span><span class="sxs-lookup"><span data-stu-id="ad94d-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad94d-124">활성 에이전트(공식 및 비공식)</span><span class="sxs-lookup"><span data-stu-id="ad94d-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="ad94d-125">1200</span><span class="sxs-lookup"><span data-stu-id="ad94d-125">1200</span></span></p></td>
<td><p><span data-ttu-id="ad94d-126">1200</span><span class="sxs-lookup"><span data-stu-id="ad94d-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad94d-127">헌트 그룹 수</span><span class="sxs-lookup"><span data-stu-id="ad94d-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="ad94d-128">400</span><span class="sxs-lookup"><span data-stu-id="ad94d-128">400</span></span></p></td>
<td><p><span data-ttu-id="ad94d-129">400</span><span class="sxs-lookup"><span data-stu-id="ad94d-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad94d-130">IVR 그룹 수(음성 인식 사용)</span><span class="sxs-lookup"><span data-stu-id="ad94d-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="ad94d-131">200</span><span class="sxs-lookup"><span data-stu-id="ad94d-131">200</span></span></p></td>
<td><p><span data-ttu-id="ad94d-132">200</span><span class="sxs-lookup"><span data-stu-id="ad94d-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

