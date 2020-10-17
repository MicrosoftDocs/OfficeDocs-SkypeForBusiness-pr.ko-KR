---
title: 'Lync Server 2013: 서버 및 도구 운영 체제 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 495ac4ba1b09b6a58a146882d54e17a8f3dd70bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510375"
---
# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="c474d-102">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="c474d-102">Server and tools operating system support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c474d-103">_**마지막으로 수정 된 항목:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="c474d-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="c474d-104">Lync Server 2013는 64 비트 에서만 사용할 수 있으며, 64 비트 하드웨어와 64 비트 버전의 Windows Server가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="c474d-105">즉, Lync Server 2013 관리 도구를 실행 하는 모든 서버 역할 및 컴퓨터가 64 비트 버전의 운영 체제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="c474d-106">서버 역할의 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c474d-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="c474d-107">Lync Server 2013에서는 Lync Server 2013의 모든 서버 역할에 대해 64 비트 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="c474d-108">Windows Server 2008 R2 SP1 (서비스 팩 1) Standard 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="c474d-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c474d-109">Windows Server 2008 R2 SP1 Enterprise 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="c474d-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c474d-110">Windows Server 2008 R2 SP1 Datacenter 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="c474d-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c474d-111">Windows Server 2012 Standard 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c474d-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="c474d-112">Windows Server 2012 Datacenter 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c474d-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="c474d-113">Windows Server 2012 R2 운영 체제는 Lync Server 2013에 대 한 누적 업데이트: 10 월 2013로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="c474d-114">Lync Server 2013는 다음에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="c474d-115">Windows Server 2008 R2 또는 Windows Server 2012의 Server Core 설치 옵션</span><span class="sxs-lookup"><span data-stu-id="c474d-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="c474d-116">Windows Web Server 2008 R2 운영 체제 또는 Windows Web Server 2012 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c474d-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="c474d-117">Windows Server 2008 R2 HPC 버전 또는 Windows Server 2012 HPC 버전</span><span class="sxs-lookup"><span data-stu-id="c474d-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="c474d-118">관리 도구의 추가 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c474d-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="c474d-119">Lync Server 2013 관리 도구는 Lync Server 2013를 실행 하는 서버에 기본적으로 설치 되지만, Windows 운영 체제를 실행 하는 다른 컴퓨터에 관리 도구를 별도로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="c474d-120">여기에는 다음 운영 체제의 64 비트 버전과 서버 역할을 배포 하는 데 지원 되는 운영 체제의 64 비트 버전 (이전 섹션에 설명 된 대로)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c474d-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="c474d-121">Windows 7 운영 체제 SP1 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="c474d-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c474d-122">Windows 8 운영 체제 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="c474d-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c474d-123">Windows 8.1 운영 체제 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="c474d-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="c474d-124">배포의 다른 서버에 대 한 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c474d-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="c474d-125">백 엔드 서버 및 기타 데이터베이스 서버에 대 한 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c474d-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="c474d-126">에 지 배포에 대 한 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 IIS 지원](lync-server-2013-iis-support.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c474d-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="c474d-127">인프라 및 가상화 지원을 포함 하 여 다른 소프트웨어 요구 사항에 대 한 자세한 내용은 [Lync server 2013의 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md)에서 다른 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c474d-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

