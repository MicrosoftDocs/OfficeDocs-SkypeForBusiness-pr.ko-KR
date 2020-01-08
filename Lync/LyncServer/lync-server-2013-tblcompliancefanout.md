---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6edae4c6e37f5abb6714e7c6863c80b7a6e7756b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="bdf01-102">Lync Server 2013의 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="bdf01-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdf01-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bdf01-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bdf01-104">tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf01-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="bdf01-105">열</span><span class="sxs-lookup"><span data-stu-id="bdf01-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdf01-106">열</span><span class="sxs-lookup"><span data-stu-id="bdf01-106">Column</span></span></th>
<th><span data-ttu-id="bdf01-107">유형</span><span class="sxs-lookup"><span data-stu-id="bdf01-107">Type</span></span></th>
<th><span data-ttu-id="bdf01-108">설명</span><span class="sxs-lookup"><span data-stu-id="bdf01-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdf01-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="bdf01-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="bdf01-110">int</span><span class="sxs-lookup"><span data-stu-id="bdf01-110">int</span></span></p></td>
<td><p><span data-ttu-id="bdf01-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf01-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdf01-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="bdf01-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="bdf01-113">int</span><span class="sxs-lookup"><span data-stu-id="bdf01-113">int</span></span></p></td>
<td><p><span data-ttu-id="bdf01-114">서버 id (tblServerIdentity. serverID 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="bdf01-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bdf01-115">키</span><span class="sxs-lookup"><span data-stu-id="bdf01-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdf01-116">열</span><span class="sxs-lookup"><span data-stu-id="bdf01-116">Column</span></span></th>
<th><span data-ttu-id="bdf01-117">설명</span><span class="sxs-lookup"><span data-stu-id="bdf01-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdf01-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="bdf01-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="bdf01-119">TblComplianceData에서 조회를 사용 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf01-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

