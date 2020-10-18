---
title: 'Lync Server 2013: tblADCookie'
description: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573724"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="5e569-103">Lync Server 2013의 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="5e569-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e569-104">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="5e569-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="5e569-105">tblADCookie에는 현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="5e569-106">단</span><span class="sxs-lookup"><span data-stu-id="5e569-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e569-107">열</span><span class="sxs-lookup"><span data-stu-id="5e569-107">Column</span></span></th>
<th><span data-ttu-id="5e569-108">유형</span><span class="sxs-lookup"><span data-stu-id="5e569-108">Type</span></span></th>
<th><span data-ttu-id="5e569-109">설명</span><span class="sxs-lookup"><span data-stu-id="5e569-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e569-110">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="5e569-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="5e569-111">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e569-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5e569-112">모니터링 중인 도메인의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e569-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="5e569-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="5e569-114">nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="5e569-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="5e569-115">Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e569-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="5e569-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="5e569-117">image(바이너리)</span><span class="sxs-lookup"><span data-stu-id="5e569-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="5e569-118">Active Directory 동기화 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e569-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="5e569-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="5e569-120">datetime</span><span class="sxs-lookup"><span data-stu-id="5e569-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e569-121">행 업데이트 시간이 포함된 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e569-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="5e569-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="5e569-123">datetime</span><span class="sxs-lookup"><span data-stu-id="5e569-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e569-p101">변경할 수 없도록 행이 잠길 때까지의 시간입니다. 이 방식은 한 번에 하나의 채팅 서비스만 Active Directory 동기화를 수행할 수 있도록 보장하는 소프트웨어 내부 잠금 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5e569-126">키</span><span class="sxs-lookup"><span data-stu-id="5e569-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e569-127">열 (s)</span><span class="sxs-lookup"><span data-stu-id="5e569-127">Column(s)</span></span></th>
<th><span data-ttu-id="5e569-128">설명</span><span class="sxs-lookup"><span data-stu-id="5e569-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e569-129">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="5e569-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="5e569-130">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e569-131">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="5e569-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="5e569-132">Principal.prinGuid 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5e569-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

