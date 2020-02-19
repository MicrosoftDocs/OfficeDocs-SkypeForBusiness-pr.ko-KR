---
title: 'Lync Server 2013: 전화 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cf680ddd7e980cbcbd1437657d4a6ef87e17e46
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="78520-102">Lync Server 2013의 전화 테이블</span><span class="sxs-lookup"><span data-stu-id="78520-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78520-103">_**마지막으로 수정 된 항목:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="78520-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="78520-104">전화 테이블이 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="78520-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="78520-105">테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 VoIP 통화와 관련 된 하나의 전화 번호에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78520-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78520-106">열</span><span class="sxs-lookup"><span data-stu-id="78520-106">Column</span></span></th>
<th><span data-ttu-id="78520-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="78520-107">Data Type</span></span></th>
<th><span data-ttu-id="78520-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="78520-108">Key/Index</span></span></th>
<th><span data-ttu-id="78520-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="78520-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78520-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="78520-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="78520-111">int</span><span class="sxs-lookup"><span data-stu-id="78520-111">int</span></span></p></td>
<td><p><span data-ttu-id="78520-112">Primary</span><span class="sxs-lookup"><span data-stu-id="78520-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="78520-113">이 전화를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="78520-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78520-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="78520-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="78520-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="78520-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="78520-116">전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="78520-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78520-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="78520-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="78520-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="78520-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78520-119">타임 스탬프입니다 (내부 전용).</span><span class="sxs-lookup"><span data-stu-id="78520-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="78520-120">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78520-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

