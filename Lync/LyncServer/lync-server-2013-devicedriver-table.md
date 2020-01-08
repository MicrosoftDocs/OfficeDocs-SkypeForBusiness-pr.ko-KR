---
title: 'Lync Server 2013: DeviceDriver 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea4ab9ad8b2eda5388791c98c1e1da90d9bd5c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="50438-102">Lync Server 2013의 DeviceDriver 테이블</span><span class="sxs-lookup"><span data-stu-id="50438-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50438-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="50438-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="50438-104">DeviceDriver 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="50438-104">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="50438-105">각 레코드는 캡처 장치 또는 렌더 장치에 사용 되는 드라이버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50438-105">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50438-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="50438-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="50438-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="50438-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="50438-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="50438-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="50438-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="50438-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50438-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="50438-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="50438-111">int</span><span class="sxs-lookup"><span data-stu-id="50438-111">int</span></span></p></td>
<td><p><span data-ttu-id="50438-112">주요한</span><span class="sxs-lookup"><span data-stu-id="50438-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="50438-113">이 장치 드라이버 레코드를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="50438-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50438-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="50438-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="50438-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="50438-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="50438-116">독특한</span><span class="sxs-lookup"><span data-stu-id="50438-116">unique</span></span></p></td>
<td><p><span data-ttu-id="50438-117">장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50438-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

