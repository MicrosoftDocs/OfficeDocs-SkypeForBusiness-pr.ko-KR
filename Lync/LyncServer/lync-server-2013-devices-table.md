---
title: 'Lync Server 2013: Devices 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="ff047-102">Lync Server 2013의 Devices 테이블</span><span class="sxs-lookup"><span data-stu-id="ff047-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff047-103">_**마지막으로 수정한 주제:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ff047-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ff047-104">장치 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ff047-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="ff047-105">각 레코드는 한 장치 (일반 전화기)에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff047-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff047-106">열</span><span class="sxs-lookup"><span data-stu-id="ff047-106">Column</span></span></th>
<th><span data-ttu-id="ff047-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ff047-107">Data Type</span></span></th>
<th><span data-ttu-id="ff047-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="ff047-108">Key/Index</span></span></th>
<th><span data-ttu-id="ff047-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="ff047-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff047-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="ff047-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff047-111">int</span><span class="sxs-lookup"><span data-stu-id="ff047-111">int</span></span></p></td>
<td><p><span data-ttu-id="ff047-112">주요한</span><span class="sxs-lookup"><span data-stu-id="ff047-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff047-113">이 하드웨어 버전을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ff047-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff047-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="ff047-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff047-115">int</span><span class="sxs-lookup"><span data-stu-id="ff047-115">int</span></span></p></td>
<td><p><span data-ttu-id="ff047-116">외부</span><span class="sxs-lookup"><span data-stu-id="ff047-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff047-117">이 장치에 대 한 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="ff047-117">Manufacturer of this device.</span></span> <span data-ttu-id="ff047-118">자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff047-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff047-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ff047-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff047-120">int</span><span class="sxs-lookup"><span data-stu-id="ff047-120">int</span></span></p></td>
<td><p><span data-ttu-id="ff047-121">외부</span><span class="sxs-lookup"><span data-stu-id="ff047-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff047-122">이 장치에 대 한 하드웨어 버전.</span><span class="sxs-lookup"><span data-stu-id="ff047-122">Hardware version of this device.</span></span> <span data-ttu-id="ff047-123">자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff047-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff047-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="ff047-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ff047-125">bigint</span><span class="sxs-lookup"><span data-stu-id="ff047-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff047-126">MAC 주소</span><span class="sxs-lookup"><span data-stu-id="ff047-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

