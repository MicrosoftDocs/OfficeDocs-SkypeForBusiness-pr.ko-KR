---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fce70f05b317ac7467fd17306d6933c66087e5e6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="d80b3-102">Lync Server 2013의 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="d80b3-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80b3-103">_**마지막으로 수정한 주제:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d80b3-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d80b3-104">tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80b3-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="d80b3-105">열</span><span class="sxs-lookup"><span data-stu-id="d80b3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d80b3-106">열</span><span class="sxs-lookup"><span data-stu-id="d80b3-106">Column</span></span></th>
<th><span data-ttu-id="d80b3-107">유형</span><span class="sxs-lookup"><span data-stu-id="d80b3-107">Type</span></span></th>
<th><span data-ttu-id="d80b3-108">설명</span><span class="sxs-lookup"><span data-stu-id="d80b3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d80b3-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="d80b3-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="d80b3-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d80b3-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d80b3-111">최근 처리 된 준수 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80b3-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d80b3-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="d80b3-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="d80b3-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="d80b3-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d80b3-114">데이터베이스에 대 한 단독 잠금을 보유 하는 규정 준수 서버의 ID 이거나, 없으면-1입니다.</span><span class="sxs-lookup"><span data-stu-id="d80b3-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d80b3-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="d80b3-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="d80b3-116">datetime2, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d80b3-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="d80b3-117">잠금 만료 시간 (activeServerID가-1이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="d80b3-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

