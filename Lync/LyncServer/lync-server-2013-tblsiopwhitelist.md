---
title: 'Lync Server 2013: tblSiopWhiteList'
description: 'Lync Server 2013: tblSiopWhiteList.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbb58c0818a6f36959732f210b8eb53bbfe223d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563864"
---
# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="0fd29-103">Lync Server 2013의 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="0fd29-103">tblSiopWhiteList in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fd29-104">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="0fd29-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="0fd29-105">tblSiopWhiteList는 노드와 연결할 수 있는 등록된 추가 기능 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd29-105">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="0fd29-106">단</span><span class="sxs-lookup"><span data-stu-id="0fd29-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fd29-107">열</span><span class="sxs-lookup"><span data-stu-id="0fd29-107">Column</span></span></th>
<th><span data-ttu-id="0fd29-108">유형</span><span class="sxs-lookup"><span data-stu-id="0fd29-108">Type</span></span></th>
<th><span data-ttu-id="0fd29-109">설명</span><span class="sxs-lookup"><span data-stu-id="0fd29-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fd29-110">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="0fd29-110">siopID</span></span></p></td>
<td><p><span data-ttu-id="0fd29-111">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fd29-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="0fd29-112">추가 기능의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd29-112">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fd29-113">siopName</span><span class="sxs-lookup"><span data-stu-id="0fd29-113">siopName</span></span></p></td>
<td><p><span data-ttu-id="0fd29-114">nvarchar(50), null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fd29-114">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="0fd29-115">추가 기능의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd29-115">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fd29-116">siopUrl</span><span class="sxs-lookup"><span data-stu-id="0fd29-116">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="0fd29-117">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fd29-117">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="0fd29-118">추가 기능의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd29-118">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0fd29-119">키</span><span class="sxs-lookup"><span data-stu-id="0fd29-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fd29-120">열</span><span class="sxs-lookup"><span data-stu-id="0fd29-120">Column</span></span></th>
<th><span data-ttu-id="0fd29-121">설명</span><span class="sxs-lookup"><span data-stu-id="0fd29-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fd29-122">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="0fd29-122">siopID</span></span></p></td>
<td><p><span data-ttu-id="0fd29-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd29-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

