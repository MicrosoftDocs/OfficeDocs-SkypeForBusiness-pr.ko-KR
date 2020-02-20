---
title: 'Lync Server 2013: Devices 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1270557e5d02fd1764957d75441ecc33ad11588c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="acf6d-102">Lync Server 2013의 Devices 테이블</span><span class="sxs-lookup"><span data-stu-id="acf6d-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acf6d-103">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="acf6d-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="acf6d-p101">Devices 테이블은 지원 테이블입니다. 각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf6d-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acf6d-106">열</span><span class="sxs-lookup"><span data-stu-id="acf6d-106">Column</span></span></th>
<th><span data-ttu-id="acf6d-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="acf6d-107">Data Type</span></span></th>
<th><span data-ttu-id="acf6d-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="acf6d-108">Key/Index</span></span></th>
<th><span data-ttu-id="acf6d-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="acf6d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acf6d-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="acf6d-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="acf6d-111">int</span><span class="sxs-lookup"><span data-stu-id="acf6d-111">int</span></span></p></td>
<td><p><span data-ttu-id="acf6d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="acf6d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="acf6d-113">이 하드웨어 버전을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="acf6d-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acf6d-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="acf6d-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="acf6d-115">int</span><span class="sxs-lookup"><span data-stu-id="acf6d-115">int</span></span></p></td>
<td><p><span data-ttu-id="acf6d-116">외부</span><span class="sxs-lookup"><span data-stu-id="acf6d-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="acf6d-117">이 장치의 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="acf6d-117">Manufacturer of this device.</span></span> <span data-ttu-id="acf6d-118">자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf6d-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acf6d-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="acf6d-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="acf6d-120">int</span><span class="sxs-lookup"><span data-stu-id="acf6d-120">int</span></span></p></td>
<td><p><span data-ttu-id="acf6d-121">외부</span><span class="sxs-lookup"><span data-stu-id="acf6d-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="acf6d-122">이 장치의 하드웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="acf6d-122">Hardware version of this device.</span></span> <span data-ttu-id="acf6d-123">자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf6d-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acf6d-124"><strong>Mac</strong></span><span class="sxs-lookup"><span data-stu-id="acf6d-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="acf6d-125">bigint</span><span class="sxs-lookup"><span data-stu-id="acf6d-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="acf6d-126">MAC 주소</span><span class="sxs-lookup"><span data-stu-id="acf6d-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

