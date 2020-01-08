---
title: 'Lync Server 2013: 서버 및 도구 운영 체제 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19ae4b69eb261a9d23d767dcd3847d8986847b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="ac8ac-102">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="ac8ac-102">Server and tools operating system support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac8ac-103">_**마지막으로 수정한 주제:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="ac8ac-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="ac8ac-104">Lync Server 2013는 64 비트 에서만 사용할 수 있으며, 64 비트 하드웨어와 64 비트 버전의 Windows Server가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="ac8ac-105">즉, Lync Server 2013 관리 도구를 실행 하는 모든 서버 역할 및 컴퓨터는 64 비트 버전의 운영 체제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="ac8ac-106">서버 역할에 대 한 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ac8ac-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="ac8ac-107">Lync Server 2013는 Lync Server 2013의 모든 서버 역할에 대해 다음 운영 체제의 64 비트 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="ac8ac-108">Windows Server 2008 R2 SP1(서비스 팩 1) 표준 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="ac8ac-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="ac8ac-109">Windows Server 2008 R2 SP1 엔터프라이즈 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="ac8ac-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="ac8ac-110">Windows Server 2008 R2 SP1 데이터 센터 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="ac8ac-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="ac8ac-111">Windows Server 2012 표준 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ac8ac-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="ac8ac-112">Windows Server 2012 데이터 센터 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ac8ac-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="ac8ac-113">Windows Server 2012 R2 운영 체제는 Lync Server 2013:10 월 2013에 대 한 누적 업데이트에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="ac8ac-114">Lync Server 2013는 다음에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="ac8ac-115">Windows Server 2008 R2 또는 Windows Server 2012의 Server Core 설치 옵션</span><span class="sxs-lookup"><span data-stu-id="ac8ac-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="ac8ac-116">Windows Web Server 2008 R2 운영 체제 또는 Windows Web Server 2012 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ac8ac-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="ac8ac-117">Windows Server 2008 R2 HPC 버전 또는 Windows Server 2012 HPC 에디션</span><span class="sxs-lookup"><span data-stu-id="ac8ac-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="ac8ac-118">관리 도구에 대 한 추가 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ac8ac-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="ac8ac-119">Lync Server 2013 관리 도구는 Lync Server 2013를 실행 하는 서버에 기본적으로 설치 되지만, Windows 운영 체제를 실행 하는 다른 컴퓨터에 관리 도구를 별도로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="ac8ac-120">여기에는 다음 운영 체제의 64 비트 버전이 포함 되며, 앞 섹션에서 설명한 대로 서버 역할 배포에 지원 되는 운영 체제의 64 비트 버전 외에도 다음과 같이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="ac8ac-121">Windows 7 운영 체제 SP1 운영 체제 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="ac8ac-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="ac8ac-122">Windows 8 운영 체제 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="ac8ac-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="ac8ac-123">Windows 8.1 운영 체제 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="ac8ac-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="ac8ac-124">배포의 다른 서버에 대 한 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ac8ac-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="ac8ac-125">백 엔드 서버 및 기타 데이터베이스 서버에 대 한 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="ac8ac-126">역방향 프록시 서버에 대 한 요구 사항에 대 한 자세한 내용은 (Edge 배포의 경우) [Lync Server 2013에서 IIS 지원을](lync-server-2013-iis-support.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="ac8ac-127">인프라 및 가상화 지원 등의 다른 소프트웨어 요구 사항에 대 한 자세한 내용은 [Lync server 2013의 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md)의 다른 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8ac-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

