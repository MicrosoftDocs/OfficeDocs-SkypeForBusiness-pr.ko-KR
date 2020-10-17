---
title: 'Lync Server 2013: SIPResponseMetaData 테이블'
description: 'Lync Server 2013: SIPResponseMetaData 테이블'
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
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558984"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="4d88c-103">Lync Server 2013의 SIPResponseMetaData 테이블</span><span class="sxs-lookup"><span data-stu-id="4d88c-103">SIPResponseMetaData table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d88c-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4d88c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4d88c-105">SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="4d88c-106">이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치에서 요청을 할 때 생성 되지만 서버에서 해당 요청을 사용 하는 것을 거절 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="4d88c-107">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d88c-108">열</span><span class="sxs-lookup"><span data-stu-id="4d88c-108">Column</span></span></th>
<th><span data-ttu-id="4d88c-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4d88c-109">Data Type</span></span></th>
<th><span data-ttu-id="4d88c-110">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="4d88c-110">Key/Index</span></span></th>
<th><span data-ttu-id="4d88c-111">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4d88c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d88c-112"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="4d88c-112"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4d88c-113">int</span><span class="sxs-lookup"><span data-stu-id="4d88c-113">int</span></span></p></td>
<td><p><span data-ttu-id="4d88c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="4d88c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4d88c-115">SIP 응답 코드를 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-115">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d88c-116"><strong>클래스</strong></span><span class="sxs-lookup"><span data-stu-id="4d88c-116"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="4d88c-117">int</span><span class="sxs-lookup"><span data-stu-id="4d88c-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4d88c-118">응답 코드에 대 한 일반 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-118">General classification for the response code.</span></span> <span data-ttu-id="4d88c-119">분류에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-119">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d88c-120">1 – 정보 응답</span><span class="sxs-lookup"><span data-stu-id="4d88c-120">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="4d88c-121">2-성공적인 응답</span><span class="sxs-lookup"><span data-stu-id="4d88c-121">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="4d88c-122">3 – 리디렉션 응답</span><span class="sxs-lookup"><span data-stu-id="4d88c-122">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="4d88c-123">4-클라이언트 오류 응답</span><span class="sxs-lookup"><span data-stu-id="4d88c-123">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="4d88c-124">5--서버 오류 응답</span><span class="sxs-lookup"><span data-stu-id="4d88c-124">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="4d88c-125">6 – 전역 오류 응답</span><span class="sxs-lookup"><span data-stu-id="4d88c-125">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d88c-126"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="4d88c-126"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="4d88c-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4d88c-127">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4d88c-128">SIP 응답 코드에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-128">Description of the SIP response code.</span></span> <span data-ttu-id="4d88c-129">예를 들어, 응답 코드 181에는 다음 설명이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d88c-129">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="4d88c-130">착신 전환 중</span><span class="sxs-lookup"><span data-stu-id="4d88c-130">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

