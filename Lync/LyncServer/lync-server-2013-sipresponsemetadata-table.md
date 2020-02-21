---
title: 'Lync Server 2013: SIPResponseMetaData 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0143bdd74b955f2cba5f68540be7c969f748aa47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="42134-102">Lync Server 2013의 SIPResponseMetaData 테이블</span><span class="sxs-lookup"><span data-stu-id="42134-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42134-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="42134-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="42134-104">SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42134-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="42134-105">이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치에서 요청을 할 때 생성 되지만 서버에서 해당 요청을 사용 하는 것을 거절 합니다.</span><span class="sxs-lookup"><span data-stu-id="42134-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="42134-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42134-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42134-107">열</span><span class="sxs-lookup"><span data-stu-id="42134-107">Column</span></span></th>
<th><span data-ttu-id="42134-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="42134-108">Data Type</span></span></th>
<th><span data-ttu-id="42134-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="42134-109">Key/Index</span></span></th>
<th><span data-ttu-id="42134-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="42134-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42134-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="42134-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="42134-112">int</span><span class="sxs-lookup"><span data-stu-id="42134-112">int</span></span></p></td>
<td><p><span data-ttu-id="42134-113">Primary</span><span class="sxs-lookup"><span data-stu-id="42134-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="42134-114">SIP 응답 코드를 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="42134-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42134-115"><strong>클래스</strong></span><span class="sxs-lookup"><span data-stu-id="42134-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="42134-116">int</span><span class="sxs-lookup"><span data-stu-id="42134-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42134-117">응답 코드에 대 한 일반 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="42134-117">General classification for the response code.</span></span> <span data-ttu-id="42134-118">분류에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42134-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="42134-119">1 – 정보 응답</span><span class="sxs-lookup"><span data-stu-id="42134-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="42134-120">2-성공적인 응답</span><span class="sxs-lookup"><span data-stu-id="42134-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="42134-121">3 – 리디렉션 응답</span><span class="sxs-lookup"><span data-stu-id="42134-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="42134-122">4-클라이언트 오류 응답</span><span class="sxs-lookup"><span data-stu-id="42134-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="42134-123">5--서버 오류 응답</span><span class="sxs-lookup"><span data-stu-id="42134-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="42134-124">6 – 전역 오류 응답</span><span class="sxs-lookup"><span data-stu-id="42134-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42134-125"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="42134-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="42134-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42134-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42134-127">SIP 응답 코드에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="42134-127">Description of the SIP response code.</span></span> <span data-ttu-id="42134-128">예를 들어, 응답 코드 181에는 다음 설명이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42134-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="42134-129">착신 전환 중</span><span class="sxs-lookup"><span data-stu-id="42134-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

