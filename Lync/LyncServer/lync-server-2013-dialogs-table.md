---
title: 'Lync Server 2013: Dialogs 테이블'
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
ms.openlocfilehash: 4782c8de23daa16bc43f40ac3e4bbf62c06c5e3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="365e9-102">Lync Server 2013의 Dialogs 테이블</span><span class="sxs-lookup"><span data-stu-id="365e9-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="365e9-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="365e9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="365e9-104">Dialogs 테이블은 피어 투 피어 세션에 대 한의 dialogids에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="365e9-105">열</span><span class="sxs-lookup"><span data-stu-id="365e9-105">Column</span></span></th>
<th><span data-ttu-id="365e9-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="365e9-106">Data Type</span></span></th>
<th><span data-ttu-id="365e9-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="365e9-107">Key/Index</span></span></th>
<th><span data-ttu-id="365e9-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="365e9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="365e9-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="365e9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="365e9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="365e9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="365e9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="365e9-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="365e9-112">세션 요청 시간 SessionIDSeq와 함께 사용 되어 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="365e9-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="365e9-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="365e9-114">int</span><span class="sxs-lookup"><span data-stu-id="365e9-114">int</span></span></p></td>
<td><p><span data-ttu-id="365e9-115">Primary</span><span class="sxs-lookup"><span data-stu-id="365e9-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="365e9-116">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-116">ID number to identify the session.</span></span> <span data-ttu-id="365e9-117">SessionIDTime과 함께 세션을 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="365e9-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="365e9-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="365e9-119">int</span><span class="sxs-lookup"><span data-stu-id="365e9-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="365e9-120">ExternalID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="365e9-121">이 필드는 데이터베이스 검색 속도를 높이는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="365e9-122"><strong>externalId</strong></span><span class="sxs-lookup"><span data-stu-id="365e9-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="365e9-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="365e9-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="365e9-124">이진로 저장 된 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="365e9-125">이진 파일의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="365e9-126">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="365e9-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="365e9-127">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="365e9-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

