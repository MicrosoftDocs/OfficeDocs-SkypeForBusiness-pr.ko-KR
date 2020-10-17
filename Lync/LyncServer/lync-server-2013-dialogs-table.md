---
title: 'Lync Server 2013: Dialogs 테이블'
description: 'Lync Server 2013: Dialogs 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559704"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="35532-103">Lync Server 2013의 Dialogs 테이블</span><span class="sxs-lookup"><span data-stu-id="35532-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35532-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="35532-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="35532-105">Dialogs 테이블은 피어 투 피어 세션에 대 한의 dialogids에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="35532-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35532-106">열</span><span class="sxs-lookup"><span data-stu-id="35532-106">Column</span></span></th>
<th><span data-ttu-id="35532-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35532-107">Data Type</span></span></th>
<th><span data-ttu-id="35532-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="35532-108">Key/Index</span></span></th>
<th><span data-ttu-id="35532-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="35532-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35532-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="35532-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35532-111">datetime</span><span class="sxs-lookup"><span data-stu-id="35532-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="35532-112">Primary</span><span class="sxs-lookup"><span data-stu-id="35532-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="35532-113">세션 요청 시간 SessionIDSeq와 함께 사용 되어 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="35532-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35532-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="35532-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="35532-115">int</span><span class="sxs-lookup"><span data-stu-id="35532-115">int</span></span></p></td>
<td><p><span data-ttu-id="35532-116">Primary</span><span class="sxs-lookup"><span data-stu-id="35532-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="35532-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="35532-117">ID number to identify the session.</span></span> <span data-ttu-id="35532-118">SessionIDTime과 함께 세션을 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35532-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35532-119"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="35532-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="35532-120">int</span><span class="sxs-lookup"><span data-stu-id="35532-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="35532-121">ExternalID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="35532-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="35532-122">이 필드는 데이터베이스 검색 속도를 높이는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35532-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35532-123"><strong>externalId</strong></span><span class="sxs-lookup"><span data-stu-id="35532-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="35532-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="35532-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="35532-125">이진로 저장 된 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35532-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="35532-126">이진 파일의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35532-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="35532-127">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="35532-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="35532-128">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35532-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

