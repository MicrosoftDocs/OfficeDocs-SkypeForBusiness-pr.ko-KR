---
title: 'Lync Server 2013: tblSiopWhiteList'
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
ms.openlocfilehash: 86ffecf185ab0c32c45e910d1821a33cbcabaea3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="55408-102">Lync Server 2013의 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="55408-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55408-103">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="55408-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="55408-104">tblSiopWhiteList는 노드와 연결할 수 있는 등록된 추가 기능 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="55408-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="55408-105">단</span><span class="sxs-lookup"><span data-stu-id="55408-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55408-106">열</span><span class="sxs-lookup"><span data-stu-id="55408-106">Column</span></span></th>
<th><span data-ttu-id="55408-107">형식</span><span class="sxs-lookup"><span data-stu-id="55408-107">Type</span></span></th>
<th><span data-ttu-id="55408-108">설명</span><span class="sxs-lookup"><span data-stu-id="55408-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55408-109">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="55408-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="55408-110">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="55408-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="55408-111">추가 기능의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="55408-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55408-112">siopName</span><span class="sxs-lookup"><span data-stu-id="55408-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="55408-113">nvarchar(50), null이 아님</span><span class="sxs-lookup"><span data-stu-id="55408-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="55408-114">추가 기능의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55408-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55408-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="55408-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="55408-116">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="55408-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="55408-117">추가 기능의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="55408-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="55408-118">키</span><span class="sxs-lookup"><span data-stu-id="55408-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55408-119">열</span><span class="sxs-lookup"><span data-stu-id="55408-119">Column</span></span></th>
<th><span data-ttu-id="55408-120">설명</span><span class="sxs-lookup"><span data-stu-id="55408-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55408-121">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="55408-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="55408-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="55408-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

