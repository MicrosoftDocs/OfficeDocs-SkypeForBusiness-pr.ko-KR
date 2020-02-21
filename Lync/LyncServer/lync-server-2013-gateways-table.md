---
title: 'Lync Server 2013: 게이트웨이 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddb3a0e781b5f505cb5a63d36eda73b98629e19b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="85500-102">Lync Server 2013의 게이트웨이 테이블</span><span class="sxs-lookup"><span data-stu-id="85500-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85500-103">_**마지막으로 수정 된 항목:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="85500-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="85500-104">게이트웨이 테이블이 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85500-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="85500-105">각 레코드는 데이터베이스의 레코드를 포함 하는 공중 전화망 (PSTN) 통화와 관련 된 하나의 게이트웨이에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="85500-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85500-106">열</span><span class="sxs-lookup"><span data-stu-id="85500-106">Column</span></span></th>
<th><span data-ttu-id="85500-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="85500-107">Data Type</span></span></th>
<th><span data-ttu-id="85500-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="85500-108">Key/Index</span></span></th>
<th><span data-ttu-id="85500-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="85500-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85500-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="85500-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="85500-111">int</span><span class="sxs-lookup"><span data-stu-id="85500-111">int</span></span></p></td>
<td><p><span data-ttu-id="85500-112">Primary</span><span class="sxs-lookup"><span data-stu-id="85500-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="85500-113">이 게이트웨이를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="85500-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85500-114"><strong>게이트웨이</strong></span><span class="sxs-lookup"><span data-stu-id="85500-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="85500-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="85500-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="85500-116">게이트웨이 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="85500-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

