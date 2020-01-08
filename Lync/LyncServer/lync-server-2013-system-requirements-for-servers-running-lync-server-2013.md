---
title: 'Lync Server 2013: Lync Server 2013을 실행하는 서버의 시스템 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="ad247-102">Lync Server 2013을 실행하는 서버의 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad247-102">System requirements for servers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad247-103">_**마지막으로 수정한 주제:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="ad247-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad247-104">하드웨어 요구 사항에 대 한 자세한 내용은 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013의 서버 하드웨어 플랫폼</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad247-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ad247-105">스탠더드 버전 및 Enterprise Edition 서버는 동일한 소프트웨어 요구 사항을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="ad247-106">Lync Server 2013, Enterprise Edition을 실행 하는 서버는 주요 조직 배포로 서 대규모 조직을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="ad247-107">Enterprise Edition server는 풀 당 약 8만 홈 사용자로 확장 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="ad247-108">Lync Server 2013, Standard Edition을 실행 하는 서버는 주요 조직 배포의 작은 조직 및 원격 위치를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="ad247-109">한 쌍의 Standard Edition 서버는 최대 5000 명의 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="ad247-110">스탠더드 버전 서버와 Enterprise Edition 서버 간의 차이점에 대 한 자세한 내용은 [Lync Server 2013에 대 한 배포 개요](lync-server-2013-deployment-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad247-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="ad247-111">운영 체제 설치</span><span class="sxs-lookup"><span data-stu-id="ad247-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad247-112">Lync Server 2013는 64 비트 버전 에서만 사용할 수 있으며, 64 비트 하드웨어와 64 비트 버전의 Windows Server 운영 체제를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="ad247-113">이 릴리스에서는 32 비트 버전의 Lync Server 2013을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="ad247-114">스탠더드 버전 및 Enterprise Edition 서버는 다음 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="ad247-115">Windows Server 2008 R2 SP1 또는 최신 서비스 팩</span><span class="sxs-lookup"><span data-stu-id="ad247-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="ad247-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ad247-116">Windows Server 2012</span></span>

  - <span data-ttu-id="ad247-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ad247-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="ad247-118">Standard Edition Server 또는 Enterprise Edition 프런트 엔드 서버에 운영 체제 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="ad247-119">운영 체제를 조직 표준에 맞게 최신 업데이트 및 필수 업데이트 수준으로 가져오기 위해 모든 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="ad247-120">운영 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad247-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad247-121">Windows Server 2012 R2에서 Lync Server 2013을 사용 하려면 Windows Server에서 레지스트리 키의 값을 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-121">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="ad247-122">이 변경은 인증서가 올바르게 작동 하 고 클라이언트가 Survivable Branch 기기에 등록 하는 데 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-122">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="ad247-123">자세한 내용은을 참조 <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="ad247-123">For more information, see <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="ad247-124">Lync Server 2013에 대 한 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="ad247-124">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="ad247-125">운영 체제에 필요한 업데이트 외에도 Lync Server 2013는 운영 체제 역할, 기능 및 소프트웨어가 작동 하도록 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-125">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="ad247-126">토폴로지를 게시 하 고 Lync Server 2013을 설치 하기 전에 설치 해야 하는 추가 소프트웨어에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에 대 한 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad247-126">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="ad247-127">모든 서버 역할에 필요한 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="ad247-127">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="ad247-128">모든 서버 역할에서 Windows PowerShell 명령줄 인터페이스 3.0 및 Microsoft .NET Framework 4.5이 설치 되어 있는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-128">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="ad247-129">또한 Lync Server 관리 도구를 실행 하는 컴퓨터에 Windows PowerShell 명령줄 인터페이스 3.0 및 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-129">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="ad247-130">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ad247-130">Windows PowerShell 3.0</span></span>

<span data-ttu-id="ad247-131">Lync Server 2013을 사용 하려면 Lync 서버 토폴로지에 참가 하는 각 컴퓨터에 Windows PowerShell 3.0을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-131">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="ad247-132">Windows PowerShell 3.0 설치에 대 한 자세한 내용은 [Lync Server 용 Windows powershell 3.0 설치 2013](lync-server-2013-installing-windows-powershell-3-0.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad247-132">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad247-133">Windows Server&nbsp;2008&nbsp;R2 SP1 사용 시 windows PowerShell 명령줄 인터페이스 3.0를 설치 하려면 Microsoft .net Framework 4.5을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-133">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="ad247-134">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ad247-134">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="ad247-135">Windows Server 2012 또는 Windows Server 2012 R2에서 Lync Server 2013를 실행 하는 서버에 Microsoft .NET Framework 4.5을 설치 하는 경우 하나의 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-135">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="ad247-136">.NET Framework 4.5가 설치 된 후에는 서버 관리자를 사용 하 여 HTTP 정품 인증을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-136">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="ad247-137">**Windows Server 2012 또는 Windows Server 2012 R2에 .NET 4.5 HTTP 정품 인증을 설치 하려면**</span><span class="sxs-lookup"><span data-stu-id="ad247-137">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="ad247-138">**시작** 메뉴에서 **프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **서버 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-138">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="ad247-139">서버 관리자의 **기능 요약**에서 **기능 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-139">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="ad247-140">**.Net Framework 4.5**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-140">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="ad247-141">아직 선택 하지 않은 경우 **WCF 정품 인증** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-141">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="ad247-142">그런 다음 **HTTP 활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-142">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="ad247-143">**다음** 을 클릭 하 고 화면의 지시에 따라 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad247-143">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

