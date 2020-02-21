---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051f9929c7728db4b1e6e55b061098211bbc11ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="206ae-102">Lync Server 2013의 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="206ae-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="206ae-103">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="206ae-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="206ae-104">tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206ae-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="206ae-105">단</span><span class="sxs-lookup"><span data-stu-id="206ae-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="206ae-106">열</span><span class="sxs-lookup"><span data-stu-id="206ae-106">Column</span></span></th>
<th><span data-ttu-id="206ae-107">형식</span><span class="sxs-lookup"><span data-stu-id="206ae-107">Type</span></span></th>
<th><span data-ttu-id="206ae-108">설명</span><span class="sxs-lookup"><span data-stu-id="206ae-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="206ae-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="206ae-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="206ae-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="206ae-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="206ae-111">마지막으로 처리 된 준수 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="206ae-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="206ae-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="206ae-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="206ae-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="206ae-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="206ae-114">데이터베이스에 대 한 단독 잠금을 보유 하는 준수 서버의 ID 이거나, 없는 경우-1입니다.</span><span class="sxs-lookup"><span data-stu-id="206ae-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="206ae-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="206ae-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="206ae-116">datetime2, null이 아님</span><span class="sxs-lookup"><span data-stu-id="206ae-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="206ae-117">잠금 만료 시간 (activeServerID이-1이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="206ae-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

