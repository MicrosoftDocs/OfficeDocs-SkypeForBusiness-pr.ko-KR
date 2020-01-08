---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="658f1-102">Lync Server 2013의 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="658f1-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="658f1-103">_**마지막으로 수정한 주제:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="658f1-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="658f1-104">tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="658f1-105">열</span><span class="sxs-lookup"><span data-stu-id="658f1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="658f1-106">열</span><span class="sxs-lookup"><span data-stu-id="658f1-106">Column</span></span></th>
<th><span data-ttu-id="658f1-107">유형</span><span class="sxs-lookup"><span data-stu-id="658f1-107">Type</span></span></th>
<th><span data-ttu-id="658f1-108">설명</span><span class="sxs-lookup"><span data-stu-id="658f1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="658f1-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="658f1-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="658f1-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="658f1-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="658f1-111">모니터링 중인 도메인의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="658f1-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="658f1-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="658f1-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="658f1-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="658f1-114">Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="658f1-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="658f1-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="658f1-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="658f1-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="658f1-117">Active Directory 동기화 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="658f1-118">lastUpdated 됨</span><span class="sxs-lookup"><span data-stu-id="658f1-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="658f1-119">dmtf</span><span class="sxs-lookup"><span data-stu-id="658f1-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="658f1-120">행 업데이트 시간이 포함 된 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="658f1-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="658f1-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="658f1-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="658f1-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="658f1-123">행이 변경 내용에 맞게 잠길 때 까지의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="658f1-124">이는 채팅 서비스 중 하나만 Active Directory Sync를 한 번에 수행 하도록 하는 소프트웨어 연동 메커니즘의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="658f1-125">핵심</span><span class="sxs-lookup"><span data-stu-id="658f1-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="658f1-126">개 열</span><span class="sxs-lookup"><span data-stu-id="658f1-126">Column(s)</span></span></th>
<th><span data-ttu-id="658f1-127">설명</span><span class="sxs-lookup"><span data-stu-id="658f1-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="658f1-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="658f1-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="658f1-129">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="658f1-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="658f1-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="658f1-131">PrinGuid 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="658f1-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

