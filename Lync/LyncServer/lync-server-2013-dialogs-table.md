---
title: 'Lync Server 2013: Dialogs 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a25ae1d298f1cf5908c4669a78485491fadd617d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="b4261-102">Lync Server 2013의 Dialogs 테이블</span><span class="sxs-lookup"><span data-stu-id="b4261-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4261-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b4261-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b4261-104">Dialogs 테이블은 피어 투 피어 세션에 대 한 DialogIDs에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4261-105">열</span><span class="sxs-lookup"><span data-stu-id="b4261-105">Column</span></span></th>
<th><span data-ttu-id="b4261-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b4261-106">Data Type</span></span></th>
<th><span data-ttu-id="b4261-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="b4261-107">Key/Index</span></span></th>
<th><span data-ttu-id="b4261-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="b4261-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4261-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b4261-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b4261-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="b4261-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b4261-111">주요한</span><span class="sxs-lookup"><span data-stu-id="b4261-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4261-112">세션 요청 시간 세션을 고유 하 게 식별 하는 SessionIDSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4261-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b4261-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b4261-114">int</span><span class="sxs-lookup"><span data-stu-id="b4261-114">int</span></span></p></td>
<td><p><span data-ttu-id="b4261-115">주요한</span><span class="sxs-lookup"><span data-stu-id="b4261-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4261-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-116">ID number to identify the session.</span></span> <span data-ttu-id="b4261-117">세션을 고유 하 게 식별 하는 SessionIDTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4261-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="b4261-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="b4261-119">int</span><span class="sxs-lookup"><span data-stu-id="b4261-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b4261-120">ExternalID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="b4261-121">이 필드는 데이터베이스 검색 속도를 높이는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4261-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="b4261-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="b4261-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="b4261-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b4261-124">이진으로 저장 된 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="b4261-125">이진 파일의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="b4261-126">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="b4261-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="b4261-127">이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4261-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

