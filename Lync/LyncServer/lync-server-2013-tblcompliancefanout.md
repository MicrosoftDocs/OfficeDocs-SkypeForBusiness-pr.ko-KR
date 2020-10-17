---
title: 'Lync Server 2013: tblComplianceFanout'
description: 'Lync Server 2013: tblComplianceFanout.'
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
ms.openlocfilehash: 0cb94fff579c504598f027c8c68c7dde00a5a516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568574"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="9035a-103">Lync Server 2013의 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="9035a-103">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9035a-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9035a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9035a-105">tblComplianceFanout 테이블에는 준수 이벤트를 처리한 모든 서버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9035a-105">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="9035a-106">단</span><span class="sxs-lookup"><span data-stu-id="9035a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9035a-107">열</span><span class="sxs-lookup"><span data-stu-id="9035a-107">Column</span></span></th>
<th><span data-ttu-id="9035a-108">유형</span><span class="sxs-lookup"><span data-stu-id="9035a-108">Type</span></span></th>
<th><span data-ttu-id="9035a-109">설명</span><span class="sxs-lookup"><span data-stu-id="9035a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9035a-110">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="9035a-110">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="9035a-111">int</span><span class="sxs-lookup"><span data-stu-id="9035a-111">int</span></span></p></td>
<td><p><span data-ttu-id="9035a-112">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9035a-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9035a-113">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="9035a-113">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="9035a-114">int</span><span class="sxs-lookup"><span data-stu-id="9035a-114">int</span></span></p></td>
<td><p><span data-ttu-id="9035a-115">서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="9035a-115">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="9035a-116">키</span><span class="sxs-lookup"><span data-stu-id="9035a-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9035a-117">열</span><span class="sxs-lookup"><span data-stu-id="9035a-117">Column</span></span></th>
<th><span data-ttu-id="9035a-118">설명</span><span class="sxs-lookup"><span data-stu-id="9035a-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9035a-119">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="9035a-119">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="9035a-120">tblComplianceData.cmplEventID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9035a-120">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

