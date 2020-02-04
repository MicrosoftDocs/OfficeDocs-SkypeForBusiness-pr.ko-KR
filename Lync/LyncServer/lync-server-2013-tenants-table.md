---
title: 'Lync Server 2013: Tenants 테이블'
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
ms.openlocfilehash: de776adeb8c280c5216b35cc8236a0834c14aa13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="a6089-102">Lync Server 2013의 Tenants 테이블</span><span class="sxs-lookup"><span data-stu-id="a6089-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6089-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a6089-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a6089-104">테 넌 트 테이블은 다양 한 테 넌 트 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="a6089-104">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="a6089-105">테이블의 각 레코드는 하나의 테 넌 트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6089-105">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6089-106">온-프레미스 배포에서 CDR는 빌드에 테 넌 트 ID를 사용 하 여 공용 IM 연결, 페더레이션 및 익명 등의 다른 인증 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6089-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="a6089-107">열</span><span class="sxs-lookup"><span data-stu-id="a6089-107">Column</span></span></th>
<th><span data-ttu-id="a6089-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a6089-108">Data Type</span></span></th>
<th><span data-ttu-id="a6089-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="a6089-109">Key/Index</span></span></th>
<th><span data-ttu-id="a6089-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="a6089-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6089-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="a6089-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6089-112">int</span><span class="sxs-lookup"><span data-stu-id="a6089-112">int</span></span></p></td>
<td><p><span data-ttu-id="a6089-113">주요한</span><span class="sxs-lookup"><span data-stu-id="a6089-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6089-114">이 테 넌 트 ID를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a6089-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6089-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="a6089-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a6089-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a6089-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6089-117">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="a6089-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a6089-118">00000000-0000-0000-0000-000000000000 – 엔터프라이즈</span><span class="sxs-lookup"><span data-stu-id="a6089-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="a6089-119">00000000-0000-0000-0000-000000000001-페더레이션</span><span class="sxs-lookup"><span data-stu-id="a6089-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="a6089-120">00000000-0000-0000-0000-000000000002 – 익명</span><span class="sxs-lookup"><span data-stu-id="a6089-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="a6089-121">00000000-0000-0000-0000-000000000003-공용 메신저 연결</span><span class="sxs-lookup"><span data-stu-id="a6089-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

