---
title: 'Lync Server 2013: tblPreference 설정'
description: 'Lync Server 2013: tblPreference 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547514"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="4398c-103">Lync Server 2013의 tblPreference 설정</span><span class="sxs-lookup"><span data-stu-id="4398c-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4398c-104">_**마지막으로 수정 된 항목:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="4398c-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="4398c-105">tblPreference에는 사용자의 클라이언트 기본 설정이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4398c-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="4398c-106">이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4398c-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="4398c-107">단</span><span class="sxs-lookup"><span data-stu-id="4398c-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4398c-108">열</span><span class="sxs-lookup"><span data-stu-id="4398c-108">Column</span></span></th>
<th><span data-ttu-id="4398c-109">유형</span><span class="sxs-lookup"><span data-stu-id="4398c-109">Type</span></span></th>
<th><span data-ttu-id="4398c-110">설명</span><span class="sxs-lookup"><span data-stu-id="4398c-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4398c-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="4398c-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="4398c-112">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="4398c-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="4398c-113">&lt;사용자 sip uri &gt; | 사용자 이름 &lt; 등의 형식을 사용 하는 레이블입니다. 기본 설정 &gt;</span><span class="sxs-lookup"><span data-stu-id="4398c-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4398c-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="4398c-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="4398c-115">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4398c-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4398c-116">버전 관리 목적의 일련 번호(레이블당)입니다.</span><span class="sxs-lookup"><span data-stu-id="4398c-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4398c-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="4398c-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="4398c-118">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="4398c-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="4398c-119">인코딩된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="4398c-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4398c-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="4398c-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="4398c-121">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4398c-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4398c-122">기본 설정을 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4398c-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4398c-123">키</span><span class="sxs-lookup"><span data-stu-id="4398c-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4398c-124">열</span><span class="sxs-lookup"><span data-stu-id="4398c-124">Column</span></span></th>
<th><span data-ttu-id="4398c-125">설명</span><span class="sxs-lookup"><span data-stu-id="4398c-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4398c-126">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="4398c-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="4398c-127">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4398c-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

