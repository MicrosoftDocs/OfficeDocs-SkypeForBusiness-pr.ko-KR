---
title: 'Lync Server 2013: 장치 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd5b62059329d9a2277e28f1a2ae08c25384bde
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522435"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="e519f-102">Lync Server 2013의 장치 테이블</span><span class="sxs-lookup"><span data-stu-id="e519f-102">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e519f-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e519f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e519f-p101">Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e519f-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e519f-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e519f-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e519f-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e519f-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e519f-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e519f-111">int</span><span class="sxs-lookup"><span data-stu-id="e519f-111">int</span></span></p></td>
<td><p><span data-ttu-id="e519f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e519f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e519f-113">이 장치를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e519f-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e519f-114"><strong>장치 이름</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="e519f-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e519f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e519f-116">DeviceName + DeviceType은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="e519f-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="e519f-117">장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e519f-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e519f-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="e519f-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="e519f-119">비트만</span><span class="sxs-lookup"><span data-stu-id="e519f-119">bit</span></span></p></td>
<td><p><span data-ttu-id="e519f-120">DeviceName + DeviceType은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="e519f-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="e519f-p102">장치 유형입니다. 1은 캡처 장치이고 0은 렌더링 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="e519f-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

