---
title: 'Lync Server 2013: tblConfig'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 399d4e794b45f549aed86838463091db437b286f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="15e10-102">Lync Server 2013의 tblConfig</span><span class="sxs-lookup"><span data-stu-id="15e10-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e10-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="15e10-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="15e10-104">tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15e10-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="15e10-105">단</span><span class="sxs-lookup"><span data-stu-id="15e10-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15e10-106">열</span><span class="sxs-lookup"><span data-stu-id="15e10-106">Column</span></span></th>
<th><span data-ttu-id="15e10-107">형식</span><span class="sxs-lookup"><span data-stu-id="15e10-107">Type</span></span></th>
<th><span data-ttu-id="15e10-108">설명</span><span class="sxs-lookup"><span data-stu-id="15e10-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15e10-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="15e10-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="15e10-110">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="15e10-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="15e10-111">풀 &quot;을 포함 합니다.&quot;</span><span class="sxs-lookup"><span data-stu-id="15e10-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e10-112">configContent</span><span class="sxs-lookup"><span data-stu-id="15e10-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="15e10-113">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="15e10-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="15e10-114">구성 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="15e10-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e10-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="15e10-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="15e10-116">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="15e10-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="15e10-117">데이터베이스 인스턴스의 고유한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15e10-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="15e10-118">키</span><span class="sxs-lookup"><span data-stu-id="15e10-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15e10-119">열</span><span class="sxs-lookup"><span data-stu-id="15e10-119">Column</span></span></th>
<th><span data-ttu-id="15e10-120">설명</span><span class="sxs-lookup"><span data-stu-id="15e10-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15e10-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="15e10-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="15e10-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="15e10-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

