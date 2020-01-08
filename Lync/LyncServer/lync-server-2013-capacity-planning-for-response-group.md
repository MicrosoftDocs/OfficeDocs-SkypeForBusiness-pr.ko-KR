---
title: 'Lync Server 2013: 응답 그룹 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="43970-102">Lync Server 2013의 응답 그룹 용량 계획</span><span class="sxs-lookup"><span data-stu-id="43970-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43970-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="43970-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="43970-104">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 응답 그룹 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="43970-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43970-105">다음 표의 숫자는 모든 응답 그룹 오디오 파일에 대해 16Khz, 모노, 16 비트 웨이브 (.wav) 파일을 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43970-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="43970-106">Windows Media 오디오 (.wma) 등의 다른 파일 형식을 사용 하는 경우 숫자는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43970-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43970-107">장애 복구 용량 계획의 경우 쌍으로 연결 된 풀의 각 풀은 두 풀의 모든 응답 그룹에 대 한 작업 부하를 처리할 수 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="43970-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="43970-108">응답 그룹 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="43970-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43970-109">미터</span><span class="sxs-lookup"><span data-stu-id="43970-109">Metric</span></span></th>
<th><span data-ttu-id="43970-110">엔터프라이즈 에디션 풀 (8 대의 프런트 엔드 서버 사용)</span><span class="sxs-lookup"><span data-stu-id="43970-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="43970-111">스탠더드 에디션 서버 당</span><span class="sxs-lookup"><span data-stu-id="43970-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43970-112">초당 수신 전화</span><span class="sxs-lookup"><span data-stu-id="43970-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="43970-113">16</span><span class="sxs-lookup"><span data-stu-id="43970-113">16</span></span></p></td>
<td><p><span data-ttu-id="43970-114">2</span><span class="sxs-lookup"><span data-stu-id="43970-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43970-115">IVR 또는 MoH에 연결 된 동시 통화</span><span class="sxs-lookup"><span data-stu-id="43970-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="43970-116">480</span><span class="sxs-lookup"><span data-stu-id="43970-116">480</span></span></p></td>
<td><p><span data-ttu-id="43970-117">60</span><span class="sxs-lookup"><span data-stu-id="43970-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43970-118">동시 익명 세션 (IM 제외)</span><span class="sxs-lookup"><span data-stu-id="43970-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="43970-119">224</span><span class="sxs-lookup"><span data-stu-id="43970-119">224</span></span></p></td>
<td><p><span data-ttu-id="43970-120">일까</span><span class="sxs-lookup"><span data-stu-id="43970-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43970-121">동시 익명 세션 (IM 포함)</span><span class="sxs-lookup"><span data-stu-id="43970-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="43970-122">64</span><span class="sxs-lookup"><span data-stu-id="43970-122">64</span></span></p></td>
<td><p><span data-ttu-id="43970-123">20cm(8</span><span class="sxs-lookup"><span data-stu-id="43970-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43970-124">활성 에이전트 (형식 및 비공식적인)</span><span class="sxs-lookup"><span data-stu-id="43970-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="43970-125">1200</span><span class="sxs-lookup"><span data-stu-id="43970-125">1200</span></span></p></td>
<td><p><span data-ttu-id="43970-126">1200</span><span class="sxs-lookup"><span data-stu-id="43970-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43970-127">헌트 그룹 수</span><span class="sxs-lookup"><span data-stu-id="43970-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="43970-128">400</span><span class="sxs-lookup"><span data-stu-id="43970-128">400</span></span></p></td>
<td><p><span data-ttu-id="43970-129">400</span><span class="sxs-lookup"><span data-stu-id="43970-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43970-130">IVR 그룹 수 (음성 인식 사용)</span><span class="sxs-lookup"><span data-stu-id="43970-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="43970-131">200</span><span class="sxs-lookup"><span data-stu-id="43970-131">200</span></span></p></td>
<td><p><span data-ttu-id="43970-132">200</span><span class="sxs-lookup"><span data-stu-id="43970-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

