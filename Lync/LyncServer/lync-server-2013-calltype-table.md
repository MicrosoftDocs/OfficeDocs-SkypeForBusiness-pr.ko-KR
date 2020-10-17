---
title: 'Lync Server 2013: CallType 테이블'
description: 'Lync Server 2013: CallType 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565174"
---
# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="10a41-103">Lync Server 2013의 CallType 테이블</span><span class="sxs-lookup"><span data-stu-id="10a41-103">CallType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10a41-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="10a41-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="10a41-105">CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="10a41-105">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10a41-106">열</span><span class="sxs-lookup"><span data-stu-id="10a41-106">Column</span></span></th>
<th><span data-ttu-id="10a41-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="10a41-107">Data Type</span></span></th>
<th><span data-ttu-id="10a41-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="10a41-108">Key/Index</span></span></th>
<th><span data-ttu-id="10a41-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="10a41-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10a41-110"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="10a41-110"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="10a41-111">int</span><span class="sxs-lookup"><span data-stu-id="10a41-111">int</span></span></p></td>
<td><p><span data-ttu-id="10a41-112">Primary</span><span class="sxs-lookup"><span data-stu-id="10a41-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10a41-113"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="10a41-113"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="10a41-114">varchar</span><span class="sxs-lookup"><span data-stu-id="10a41-114">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10a41-115">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10a41-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="10a41-116">0 -- 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="10a41-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="10a41-117">1 -- 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="10a41-117">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="10a41-118">2--응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="10a41-118">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="10a41-119">3 -- 오디오</span><span class="sxs-lookup"><span data-stu-id="10a41-119">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="10a41-120">4 -- 오디오 및 비디오</span><span class="sxs-lookup"><span data-stu-id="10a41-120">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="10a41-121">5 -- 파일 전송</span><span class="sxs-lookup"><span data-stu-id="10a41-121">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

