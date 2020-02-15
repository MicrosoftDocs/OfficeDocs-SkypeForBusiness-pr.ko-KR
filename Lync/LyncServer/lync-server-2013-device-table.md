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
ms.openlocfilehash: 3d9281c3059d8fa234b8f62b6223eb601f38b119
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="430ae-102">Lync Server 2013의 장치 테이블</span><span class="sxs-lookup"><span data-stu-id="430ae-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="430ae-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="430ae-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="430ae-p101">Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="430ae-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="430ae-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="430ae-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="430ae-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="430ae-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="430ae-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="430ae-111">int</span><span class="sxs-lookup"><span data-stu-id="430ae-111">int</span></span></p></td>
<td><p><span data-ttu-id="430ae-112">Primary</span><span class="sxs-lookup"><span data-stu-id="430ae-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="430ae-113">이 장치를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="430ae-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="430ae-114"><strong>장치 이름</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="430ae-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="430ae-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="430ae-116">DeviceName + DeviceType은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="430ae-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="430ae-117">장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="430ae-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="430ae-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="430ae-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="430ae-119">비트만</span><span class="sxs-lookup"><span data-stu-id="430ae-119">bit</span></span></p></td>
<td><p><span data-ttu-id="430ae-120">DeviceName + DeviceType은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="430ae-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="430ae-p102">장치 유형입니다. 1은 캡처 장치이고 0은 렌더링 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="430ae-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

