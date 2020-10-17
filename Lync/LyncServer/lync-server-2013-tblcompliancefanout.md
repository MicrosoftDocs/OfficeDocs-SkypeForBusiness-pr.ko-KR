---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df687926940aa98f3bf803f9a991527f19fa58f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509445"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="e299e-102">Lync Server 2013의 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="e299e-102">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e299e-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e299e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e299e-104">tblComplianceFanout 테이블에는 준수 이벤트를 처리한 모든 서버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e299e-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="e299e-105">단</span><span class="sxs-lookup"><span data-stu-id="e299e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e299e-106">열</span><span class="sxs-lookup"><span data-stu-id="e299e-106">Column</span></span></th>
<th><span data-ttu-id="e299e-107">유형</span><span class="sxs-lookup"><span data-stu-id="e299e-107">Type</span></span></th>
<th><span data-ttu-id="e299e-108">설명</span><span class="sxs-lookup"><span data-stu-id="e299e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e299e-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="e299e-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="e299e-110">int</span><span class="sxs-lookup"><span data-stu-id="e299e-110">int</span></span></p></td>
<td><p><span data-ttu-id="e299e-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e299e-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e299e-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="e299e-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="e299e-113">int</span><span class="sxs-lookup"><span data-stu-id="e299e-113">int</span></span></p></td>
<td><p><span data-ttu-id="e299e-114">서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="e299e-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e299e-115">키</span><span class="sxs-lookup"><span data-stu-id="e299e-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e299e-116">열</span><span class="sxs-lookup"><span data-stu-id="e299e-116">Column</span></span></th>
<th><span data-ttu-id="e299e-117">설명</span><span class="sxs-lookup"><span data-stu-id="e299e-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e299e-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="e299e-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="e299e-119">tblComplianceData.cmplEventID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e299e-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

