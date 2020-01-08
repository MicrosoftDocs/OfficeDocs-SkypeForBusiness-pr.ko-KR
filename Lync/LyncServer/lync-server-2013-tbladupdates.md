---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="88e7d-102">Lync Server 2013의 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="88e7d-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e7d-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="88e7d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="88e7d-104">tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="88e7d-105">열</span><span class="sxs-lookup"><span data-stu-id="88e7d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88e7d-106">열</span><span class="sxs-lookup"><span data-stu-id="88e7d-106">Column</span></span></th>
<th><span data-ttu-id="88e7d-107">유형</span><span class="sxs-lookup"><span data-stu-id="88e7d-107">Type</span></span></th>
<th><span data-ttu-id="88e7d-108">설명</span><span class="sxs-lookup"><span data-stu-id="88e7d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88e7d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="88e7d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="88e7d-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="88e7d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-111">변경 된 개체의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e7d-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="88e7d-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="88e7d-113">nvarchar (384), null 아님</span><span class="sxs-lookup"><span data-stu-id="88e7d-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-114">개체의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e7d-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="88e7d-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="88e7d-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="88e7d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-117">개체의 특성이 하나 이상 변경 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e7d-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="88e7d-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="88e7d-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="88e7d-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-120">구성원 자격이 변경 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e7d-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="88e7d-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="88e7d-122">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="88e7d-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-123">사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e7d-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="88e7d-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="88e7d-125">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="88e7d-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-126">개체가 삭제 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e7d-127">lastUpdated 됨</span><span class="sxs-lookup"><span data-stu-id="88e7d-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="88e7d-128">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="88e7d-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="88e7d-129">행이 삽입 된 시간의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="88e7d-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

