---
title: 'Lync Server 2013: Phones 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920454a5db71c1e6f3cd2ea2ae1134d149b4f297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="15713-102">Lync Server 2013의 Phones 테이블</span><span class="sxs-lookup"><span data-stu-id="15713-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15713-103">_**마지막으로 수정한 주제:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="15713-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="15713-104">전화 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="15713-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="15713-105">표의 각 레코드에는 데이터베이스의 레코드를 포함 하는 VoIP 통화와 관련 된 하나의 전화 번호에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15713-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15713-106">열</span><span class="sxs-lookup"><span data-stu-id="15713-106">Column</span></span></th>
<th><span data-ttu-id="15713-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="15713-107">Data Type</span></span></th>
<th><span data-ttu-id="15713-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="15713-108">Key/Index</span></span></th>
<th><span data-ttu-id="15713-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="15713-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15713-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="15713-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="15713-111">int</span><span class="sxs-lookup"><span data-stu-id="15713-111">int</span></span></p></td>
<td><p><span data-ttu-id="15713-112">주요한</span><span class="sxs-lookup"><span data-stu-id="15713-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="15713-113">이 전화를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="15713-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15713-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="15713-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="15713-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="15713-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15713-116">전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="15713-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15713-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="15713-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="15713-118">Dmtf</span><span class="sxs-lookup"><span data-stu-id="15713-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15713-119">타임 스탬프 (내부용).</span><span class="sxs-lookup"><span data-stu-id="15713-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="15713-120">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="15713-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

