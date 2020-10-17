---
title: 'Lync Server 2013: tblSystemRevision'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSystemRevision
ms:assetid: 95b8e307-117c-4fb0-bd52-bc5a5b9ade55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615019(v=OCS.15)
ms:contentKeyID: 48184901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f30248bb39d24e5fd24deb5d4ee2afb938ef7c24
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497315"
---
# <a name="tblsystemrevision-in-lync-server-2013"></a><span data-ttu-id="d24ae-102">Lync Server 2013의 tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="d24ae-102">tblSystemRevision in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d24ae-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d24ae-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d24ae-104">tblSystemRevision에는 여러 관리자 클라이언트 간에 일관성을 유지하기 위해서 tblAdminLock 테이블에서 사용되는 수정 버전 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24ae-104">tblSystemRevision contains the revision number that is used with the tblAdminLock table to achieve consistency across multiple administrator clients.</span></span>

### <a name="columns"></a><span data-ttu-id="d24ae-105">단</span><span class="sxs-lookup"><span data-stu-id="d24ae-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d24ae-106">열</span><span class="sxs-lookup"><span data-stu-id="d24ae-106">Column</span></span></th>
<th><span data-ttu-id="d24ae-107">유형</span><span class="sxs-lookup"><span data-stu-id="d24ae-107">Type</span></span></th>
<th><span data-ttu-id="d24ae-108">설명</span><span class="sxs-lookup"><span data-stu-id="d24ae-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d24ae-109">sysRevision</span><span class="sxs-lookup"><span data-stu-id="d24ae-109">sysRevision</span></span></p></td>
<td><p><span data-ttu-id="d24ae-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d24ae-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d24ae-111">수정 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d24ae-111">Revision number.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

