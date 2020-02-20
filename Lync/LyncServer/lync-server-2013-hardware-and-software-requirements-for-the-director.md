---
title: 'Lync Server 2013: 디렉터에 대 한 하드웨어 및 소프트웨어 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff5e28b21e06cc438c7eb092515443579f5c004
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="969b7-102">Lync Server 2013의 디렉터에 대 한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="969b7-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="969b7-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="969b7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="969b7-104">이 섹션에서는 디렉터에 대 한 하드웨어 및 소프트웨어 요구 사항과 디렉터에 대해 지원 되는 배치 시나리오에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="969b7-105">디렉터에 대한 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="969b7-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="969b7-106">다음 표에는 디렉터에 대 한 하드웨어 요구 사항이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="969b7-107">디렉터에 대한 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="969b7-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="969b7-108">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="969b7-108">Hardware component</span></span></th>
<th><span data-ttu-id="969b7-109">최소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="969b7-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="969b7-110">CPU</span><span class="sxs-lookup"><span data-stu-id="969b7-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="969b7-111">64비트 프로세서, 쿼드 코어, 2.0GHz 이상</span><span class="sxs-lookup"><span data-stu-id="969b7-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="969b7-112">64비트 듀얼 프로세서, 듀얼 코어, 2.0GHz 이상</span><span class="sxs-lookup"><span data-stu-id="969b7-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="969b7-113">메모리</span><span class="sxs-lookup"><span data-stu-id="969b7-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="969b7-114">4GB(기가바이트)</span><span class="sxs-lookup"><span data-stu-id="969b7-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="969b7-115">공간이</span><span class="sxs-lookup"><span data-stu-id="969b7-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="969b7-116">10K RPM HDD(하드 디스크 드라이브)</span><span class="sxs-lookup"><span data-stu-id="969b7-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="969b7-117">성능이 10K RPM HDD 이상인 고성능 SDD(반도체 드라이브)</span><span class="sxs-lookup"><span data-stu-id="969b7-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="969b7-118">2x RAID 10(스트라이프 및 미러) 15K RPM 디스크(데이터베이스 데이터 파일용)</span><span class="sxs-lookup"><span data-stu-id="969b7-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="969b7-119">네트워크</span><span class="sxs-lookup"><span data-stu-id="969b7-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="969b7-120">1Gbps(초당 기가비트) 네트워크 어댑터 2개(권장)</span><span class="sxs-lookup"><span data-stu-id="969b7-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="969b7-121">1Gbps 네트워크 어댑터 1개(지원)</span><span class="sxs-lookup"><span data-stu-id="969b7-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="969b7-122">디렉터에 대 한 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="969b7-122">Software Requirements for the Director</span></span>

<span data-ttu-id="969b7-123">디렉터 역할은 Lync Server 2013 Enterprise Edition을 실행 하는 서버에만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="969b7-124">디렉터에는 다음과 같은 64 비트 운영 체제 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="969b7-125">Windows Server 2008 R2 Standard 운영 체제 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="969b7-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="969b7-126">Windows Server 2008 R2 Enterprise 운영 체제 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="969b7-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="969b7-127">서비스 팩 1이 포함 된 Windows Server 2008 R2 Datacenter 운영 체제</span><span class="sxs-lookup"><span data-stu-id="969b7-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="969b7-128">Windows Server 2012 Standard 운영 체제</span><span class="sxs-lookup"><span data-stu-id="969b7-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="969b7-129">Windows Server 2012 Datacenter 운영 체제</span><span class="sxs-lookup"><span data-stu-id="969b7-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="969b7-130">또한 lync Server 2013에서는 [추가 서버 지원 및 Lync server 2013의 요구 사항](lync-server-2013-additional-server-support-and-requirements.md)항목에 설명 된 대로 다음 프로그램 및 업데이트를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="969b7-131">지원되는 배치</span><span class="sxs-lookup"><span data-stu-id="969b7-131">Supported Collocation</span></span>

<span data-ttu-id="969b7-132">Lync Server 2013의 다른 서버 역할을 사용 하 여 디렉터 서버 역할을 배치 된 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="969b7-133">그러나 디렉터를 배포 하지 않으면 프런트 엔드 서버에서이 역할을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="969b7-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

