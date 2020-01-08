---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5db403431c182e3f5bb8e7a3fabaa04cd2a94d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="fbe79-102">Lync Server 2013의 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="fbe79-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe79-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fbe79-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fbe79-104">tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbe79-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="fbe79-105">열</span><span class="sxs-lookup"><span data-stu-id="fbe79-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe79-106">열</span><span class="sxs-lookup"><span data-stu-id="fbe79-106">Column</span></span></th>
<th><span data-ttu-id="fbe79-107">유형</span><span class="sxs-lookup"><span data-stu-id="fbe79-107">Type</span></span></th>
<th><span data-ttu-id="fbe79-108">설명</span><span class="sxs-lookup"><span data-stu-id="fbe79-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe79-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="fbe79-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="fbe79-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="fbe79-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="fbe79-111">변경 된 그룹의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe79-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe79-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="fbe79-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="fbe79-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbe79-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="fbe79-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe79-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe79-115">memberRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="fbe79-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="fbe79-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fbe79-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fbe79-117">구성원이 추가 된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe79-117">False if the member was added.</span></span> <span data-ttu-id="fbe79-118">구성원이 제거 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe79-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="fbe79-119">키</span><span class="sxs-lookup"><span data-stu-id="fbe79-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe79-120">열</span><span class="sxs-lookup"><span data-stu-id="fbe79-120">Column</span></span></th>
<th><span data-ttu-id="fbe79-121">설명</span><span class="sxs-lookup"><span data-stu-id="fbe79-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe79-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="fbe79-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="fbe79-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe79-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

