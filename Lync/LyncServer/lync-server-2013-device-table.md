---
title: 'Lync Server 2013: Device 테이블'
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
ms.openlocfilehash: 7fd06db1bd429526826962d5c3ad098642a3a42d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="c3be5-102">Lync Server 2013의 Device 테이블</span><span class="sxs-lookup"><span data-stu-id="c3be5-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3be5-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c3be5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c3be5-104">장치 테이블은 다양 한 캡처 또는 렌더링 장치에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="c3be5-105">테이블의 각 레코드는 하나의 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3be5-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c3be5-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c3be5-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c3be5-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3be5-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c3be5-111">int</span><span class="sxs-lookup"><span data-stu-id="c3be5-111">int</span></span></p></td>
<td><p><span data-ttu-id="c3be5-112">주요한</span><span class="sxs-lookup"><span data-stu-id="c3be5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c3be5-113">이 장치를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3be5-114"><strong>이름</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="c3be5-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c3be5-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c3be5-116">장치 이름 + DeviceType는 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="c3be5-117">장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3be5-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="c3be5-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="c3be5-119">다소</span><span class="sxs-lookup"><span data-stu-id="c3be5-119">bit</span></span></p></td>
<td><p><span data-ttu-id="c3be5-120">장치 이름 + DeviceType는 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="c3be5-121">장치 유형.</span><span class="sxs-lookup"><span data-stu-id="c3be5-121">Device type.</span></span> <span data-ttu-id="c3be5-122">1은 캡처 장치이 고 0은 렌더링 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="c3be5-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

