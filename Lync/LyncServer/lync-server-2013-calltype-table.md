---
title: 'Lync Server 2013: CallType 테이블'
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
ms.openlocfilehash: d369243bd8083191d4956896acbdbc1c7e575bf8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512915"
---
# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="9ad65-102">Lync Server 2013의 CallType 테이블</span><span class="sxs-lookup"><span data-stu-id="9ad65-102">CallType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ad65-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9ad65-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9ad65-104">CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad65-104">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ad65-105">열</span><span class="sxs-lookup"><span data-stu-id="9ad65-105">Column</span></span></th>
<th><span data-ttu-id="9ad65-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ad65-106">Data Type</span></span></th>
<th><span data-ttu-id="9ad65-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="9ad65-107">Key/Index</span></span></th>
<th><span data-ttu-id="9ad65-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9ad65-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ad65-109"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9ad65-109"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ad65-110">int</span><span class="sxs-lookup"><span data-stu-id="9ad65-110">int</span></span></p></td>
<td><p><span data-ttu-id="9ad65-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9ad65-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ad65-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="9ad65-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ad65-113">varchar</span><span class="sxs-lookup"><span data-stu-id="9ad65-113">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ad65-114">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad65-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9ad65-115">0 -- 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="9ad65-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="9ad65-116">1 -- 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="9ad65-116">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="9ad65-117">2--응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="9ad65-117">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="9ad65-118">3 -- 오디오</span><span class="sxs-lookup"><span data-stu-id="9ad65-118">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="9ad65-119">4 -- 오디오 및 비디오</span><span class="sxs-lookup"><span data-stu-id="9ad65-119">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="9ad65-120">5 -- 파일 전송</span><span class="sxs-lookup"><span data-stu-id="9ad65-120">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

