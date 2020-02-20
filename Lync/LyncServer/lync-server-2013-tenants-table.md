---
title: 'Lync Server 2013: 테 넌 트 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47c447d18589f8e0cd86c007df74a21287be949f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="d0333-102">Lync Server 2013의 테 넌 트 테이블</span><span class="sxs-lookup"><span data-stu-id="d0333-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0333-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d0333-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d0333-p101">Tenants 테이블은 다양한 테넌트 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 테넌트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0333-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0333-106">온-프레미스 배포의 경우 CDR은 기본 제공되는 테넌트 ID를 사용하여 공용 IM 연결, 페더레이션 및 익명과 같은 서로 다른 인증 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0333-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0333-107">열</span><span class="sxs-lookup"><span data-stu-id="d0333-107">Column</span></span></th>
<th><span data-ttu-id="d0333-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0333-108">Data Type</span></span></th>
<th><span data-ttu-id="d0333-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="d0333-109">Key/Index</span></span></th>
<th><span data-ttu-id="d0333-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d0333-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0333-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="d0333-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0333-112">int</span><span class="sxs-lookup"><span data-stu-id="d0333-112">int</span></span></p></td>
<td><p><span data-ttu-id="d0333-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d0333-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0333-114">이 테넌트 ID를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d0333-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0333-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="d0333-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d0333-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d0333-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0333-117">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0333-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0333-118">00000000-0000-0000-0000-000000000000 - 엔터프라이즈</span><span class="sxs-lookup"><span data-stu-id="d0333-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="d0333-119">00000000-0000-0000-0000-000000000001 - 페더레이션</span><span class="sxs-lookup"><span data-stu-id="d0333-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="d0333-120">00000000-0000-0000-0000-000000000002 - 익명</span><span class="sxs-lookup"><span data-stu-id="d0333-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="d0333-121">00000000-0000-0000-0000-000000000003 - 익명 IM 연결</span><span class="sxs-lookup"><span data-stu-id="d0333-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

