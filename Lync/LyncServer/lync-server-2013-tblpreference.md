---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="3fbe9-102">Lync Server 2013의 tblPreference</span><span class="sxs-lookup"><span data-stu-id="3fbe9-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fbe9-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="3fbe9-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="3fbe9-104">tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe9-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="3fbe9-105">이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe9-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="3fbe9-106">열</span><span class="sxs-lookup"><span data-stu-id="3fbe9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fbe9-107">열</span><span class="sxs-lookup"><span data-stu-id="3fbe9-107">Column</span></span></th>
<th><span data-ttu-id="3fbe9-108">유형</span><span class="sxs-lookup"><span data-stu-id="3fbe9-108">Type</span></span></th>
<th><span data-ttu-id="3fbe9-109">설명</span><span class="sxs-lookup"><span data-stu-id="3fbe9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="3fbe9-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-111">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="3fbe9-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-112">레이블이 " &lt;사용자 sip uri&gt;| 사용자 이름"과 같은 형식입니다. &lt;기본 설정&gt;집합</span><span class="sxs-lookup"><span data-stu-id="3fbe9-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="3fbe9-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-114">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="3fbe9-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-115">버전 관리 목적에 대 한 순차 번호 (레이블 당).</span><span class="sxs-lookup"><span data-stu-id="3fbe9-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="3fbe9-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3fbe9-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-118">인코딩된 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="3fbe9-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="3fbe9-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-120">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="3fbe9-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-121">기본 설정을 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe9-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="3fbe9-122">키</span><span class="sxs-lookup"><span data-stu-id="3fbe9-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fbe9-123">열</span><span class="sxs-lookup"><span data-stu-id="3fbe9-123">Column</span></span></th>
<th><span data-ttu-id="3fbe9-124">설명</span><span class="sxs-lookup"><span data-stu-id="3fbe9-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="3fbe9-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe9-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

