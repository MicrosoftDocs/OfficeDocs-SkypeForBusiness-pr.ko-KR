---
title: 'Lync Server 2013: tblPreference 설정'
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
ms.openlocfilehash: ef0ee11cd780037410ea1d7e0d94c83e139d8418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523775"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="601df-102">Lync Server 2013의 tblPreference 설정</span><span class="sxs-lookup"><span data-stu-id="601df-102">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="601df-103">_**마지막으로 수정 된 항목:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="601df-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="601df-104">tblPreference에는 사용자의 클라이언트 기본 설정이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="601df-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="601df-105">이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="601df-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="601df-106">단</span><span class="sxs-lookup"><span data-stu-id="601df-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="601df-107">열</span><span class="sxs-lookup"><span data-stu-id="601df-107">Column</span></span></th>
<th><span data-ttu-id="601df-108">유형</span><span class="sxs-lookup"><span data-stu-id="601df-108">Type</span></span></th>
<th><span data-ttu-id="601df-109">설명</span><span class="sxs-lookup"><span data-stu-id="601df-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="601df-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="601df-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="601df-111">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="601df-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="601df-112">&lt;사용자 sip uri &gt; | 사용자 이름 &lt; 등의 형식을 사용 하는 레이블입니다. 기본 설정 &gt;</span><span class="sxs-lookup"><span data-stu-id="601df-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="601df-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="601df-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="601df-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="601df-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="601df-115">버전 관리 목적의 일련 번호(레이블당)입니다.</span><span class="sxs-lookup"><span data-stu-id="601df-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="601df-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="601df-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="601df-117">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="601df-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="601df-118">인코딩된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="601df-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="601df-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="601df-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="601df-120">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="601df-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="601df-121">기본 설정을 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="601df-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="601df-122">키</span><span class="sxs-lookup"><span data-stu-id="601df-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="601df-123">열</span><span class="sxs-lookup"><span data-stu-id="601df-123">Column</span></span></th>
<th><span data-ttu-id="601df-124">설명</span><span class="sxs-lookup"><span data-stu-id="601df-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="601df-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="601df-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="601df-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="601df-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

