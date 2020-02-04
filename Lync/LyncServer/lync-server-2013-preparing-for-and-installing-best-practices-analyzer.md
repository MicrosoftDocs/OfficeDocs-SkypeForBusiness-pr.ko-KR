---
title: 'Lync Server 2013: 모범 사례 분석기 준비 및 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="48157-102">Lync Server 2013에서 모범 사례 분석기 준비 및 설치</span><span class="sxs-lookup"><span data-stu-id="48157-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48157-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="48157-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="48157-104">이 항목에서 설명 하는 작업을 수행 하려면 관리자 그룹의 구성원으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48157-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="48157-105">모범 사례 분석기 설치에 대 한 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="48157-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="48157-106">Lync Server 2013, 모범 사례 분석기를 실행 하 여 환경을 검색 하려면 컴퓨터에서 다음 운영 체제 중 하나의 64 비트 버전을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48157-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="48157-107">Windows Server 2008 R2 SP1 (Service Pack 1) 표준 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="48157-108">Windows Server 2008 R2 SP1 엔터프라이즈 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="48157-109">Windows Server 2008 R2 SP1 데이터 센터 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="48157-110">Windows Server 2012 데이터 센터 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="48157-111">Windows Server 2012 표준 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="48157-112">Windows Server 2012 엔터프라이즈 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="48157-113">Windows Server 2012 R2 Datacenter 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="48157-114">Windows Server 2012 R2 표준 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="48157-115">Windows Server 2012 R2 엔터프라이즈 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="48157-116">Windows 8 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="48157-117">Windows 7 운영 체제</span><span class="sxs-lookup"><span data-stu-id="48157-117">Windows 7 operating system</span></span>

<span data-ttu-id="48157-118">또한 컴퓨터는 다음을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48157-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="48157-119">Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="48157-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="48157-120">Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48157-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="48157-121">Lync Server 2013, Core 구성 요소.</span><span class="sxs-lookup"><span data-stu-id="48157-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="48157-122">WMI 이전 버전과의 호환성 패키지.</span><span class="sxs-lookup"><span data-stu-id="48157-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="48157-123">자세한 내용은 마이그레이션 설명서에서 [WMI 이전 버전과 호환성 패키지 설치](install-wmi-backward-compatibility-package.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48157-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="48157-124">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="48157-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="48157-125">자세한 내용은 배포 설명서에서 [Lync Server 2013 용 Windows PowerShell 3.0 설치](lync-server-2013-installing-windows-powershell-3-0.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48157-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="48157-126">Lync Server 2013, Core 구성 요소 또는 WMI 이전 버전과의 호환성 패키지를 실행 하 고 있지 않은 지원 되는 운영 체제를 사용 하는 컴퓨터에 모범 사례 분석기를 설치할 수 있지만, 해당 컴퓨터에 대 한 모범 사례 분석기를 사용 하 여 보고서를 볼 수는 없습니다. 스캔을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48157-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="48157-127">설치할 컴퓨터 선택</span><span class="sxs-lookup"><span data-stu-id="48157-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="48157-128">Lync server 2013 관리 전용 컴퓨터에 Lync Server 2013, 모범 사례 분석기를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48157-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="48157-129">Lync Server 2013를 실행 하는 서버 또는 Lync Server 2013 관리 도구를 실행 하는 관리 컴퓨터에이 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48157-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="48157-130">Lync Server를 실행 하는 서버에이 도구를 설치 하는 경우 도구를 사용 하 여 해당 서버만 검색 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48157-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="48157-131">모범 사례 분석기 설치</span><span class="sxs-lookup"><span data-stu-id="48157-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="48157-132">Lync Server 2013에 대 한 모범 사례 분석기를 다운로드할 수 [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)있습니다.</span><span class="sxs-lookup"><span data-stu-id="48157-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="48157-133">모범 사례 분석기를 설치 하려면 도구를 설치 하려는 컴퓨터에서 Microsoft 설치 관리자 파일인 RtcBPA를 시작 하 고 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="48157-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="48157-134">프로그램 파일을 설치 하는 기본 위치는 \<시스템 드라이브\>\\프로그램 파일\\입니다. Lync\\Server 2013 BPA.</span><span class="sxs-lookup"><span data-stu-id="48157-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

