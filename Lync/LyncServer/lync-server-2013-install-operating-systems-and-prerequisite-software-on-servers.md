---
title: 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c41147d33dce792f88b30f72b36201ddb6c7d62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="66b1f-102">Lync Server 2013의 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="66b1f-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66b1f-103">_**마지막으로 수정한 주제:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="66b1f-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="66b1f-104">하드웨어 및 시스템 인프라를 설정한 후에는 배포 하는 각 서버의 모든 다른 필수 구성 요소와 함께 적절 한 Windows 운영 체제와 업데이트를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="66b1f-105">여기에는 각 Lync Server 2013 서버 역할 및 추가 인프라 서버와 함께 배포에 필요한 SQL Server를 실행 하는 서버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="66b1f-106">이 섹션에서는 내부 서버용 운영 체제와 필수 구성 요소를 설치 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="66b1f-107">외부 사용자 액세스를 지원 하도록 Edge 서버를 배포 하는 경우에는 Edge 서버 및 리버스 프록시 서버를 포함 하 여 해당 서버에 대 한 운영 체제 및 필수 구성 요소 소프트웨어만 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="66b1f-108">외부 사용자 액세스를 지원 하기 위해 서버를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 경계 네트워크에서 서버 설치 준비</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="66b1f-109">서버에 Windows 운영 체제 설치</span><span class="sxs-lookup"><span data-stu-id="66b1f-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="66b1f-110">배포 하는 각 서버에서 다음과 같이 적절 한 Windows 운영 체제를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="66b1f-111">**Lync server 2013**   를 실행 하는 서버 lync server 2013를 실행 하는 서버의 운영 체제 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [lync server 2013에서 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="66b1f-112">**데이터베이스 서버**   백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스를 비롯 한 데이터베이스 서버의 운영 체제 요구 사항에 대 한 자세한 내용은 SQL Server 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="66b1f-113">SQL Server 2012의 경우에서 [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)sql Server 2012 온라인 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="66b1f-114">Windows Server&nbsp;2008&nbsp;R2 SP1을 사용 하 여 Lync Server 2013을 설치 하는 경우 먼저 Microsoft 기술 자료 문서 2646886 "FIX: 모듈에서 IIS 7.5"의 insertentitybody 메서드를 호출할 때, at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>에 설명 된 업데이트를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="66b1f-115">KB 문서, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">이벤트 id 32402, 61045는 Windows Server 2012 R2에 설치 된 Lync Server 2013 프런트 엔드 서버에 기록</A>된 대로 레지스트리를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-115">You must also modify the registry as described in the KB article, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="66b1f-116">서버에 Windows 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="66b1f-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="66b1f-117">각 서버의 Windows Update에서 다음 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="66b1f-118">**Lync server 2013**   를 실행 하는 서버에 대 한 windows 업데이트 lync server 2013를 실행 하는 서버에 필요한 windows 업데이트 업데이트에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="66b1f-119">**데이터베이스 서버**   백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스를 포함 하 여 데이터베이스 서버에 필요한 Windows 업데이트 업데이트에 대 한 자세한 내용은 SQL Server 2012 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="66b1f-120">SQL Server 2012의 경우에서 [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)sql Server 2012 온라인 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="66b1f-121">서버에 다른 필수 구성 요소 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="66b1f-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="66b1f-122">Lync Server 2013에는 서버에 다음과 같은 추가 소프트웨어를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="66b1f-123">**Lync server 2013**   을 실행 하는 서버의 필수 구성 요소 소프트웨어 lync server 2013를 실행 하는 서버의 추가 소프트웨어 필수 구성 요소는 배포 되는 서버 역할에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="66b1f-124">각 서버의 특정 소프트웨어 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에 대 한 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="66b1f-125">**Windows identity foundation**   Lync Server 2013에는 서버에서 서버 간 인증 시나리오를 지원 하기 위해 windows identity foundation을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="66b1f-126">컴퓨터에 이미 설치 되어 있는지 확인 하려면 제어판에서 **프로그램 및 기능**을 클릭 하 고 **설치 된 업데이트를 확인**한 다음 **Microsoft Windows**를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="66b1f-127">Windows Id 파운데이션을 설치 하는 방법에 [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66b1f-127">For details about installing Windows Identity Foundation, see [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="66b1f-128">**Microsoft .net framework 4.5**   는 Lync Server 2013에 64 비트 버전의 microsoft .net framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="66b1f-129">**데이터베이스 서버용**   필수 구성 요소 소프트웨어 백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스를 포함 하 여 데이터베이스 서버에 필요한 Windows 업데이트에 대 한 자세한 내용은 SQL Server 2012 설명서를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span><span class="sxs-lookup"><span data-stu-id="66b1f-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="66b1f-130">Lync Server 2013는 각 스탠더드 버전 서버와 로컬 구성 저장소가 있는 Lync Server 2013를 실행 하는 각 서버에 Microsoft SQL Server 2012 Express를 자동으로 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="66b1f-131">**Windows media 형식 런타임**   회의를 배포할 모든 프런트 엔드 서버와 Standard Edition 서버는 windows Media 형식 런타임을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="66b1f-132">Windows Media 형식 런타임은 통화 공원, 알림 및 응답 그룹 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows Media 오디오 (.wma) 파일을 실행 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="66b1f-133">Windows Server 2012 및 Windows Server 2012 R2의 경우 Windows Media 형식 런타임이 Microsoft 미디어 파운데이션을 사용 하 여 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="66b1f-134">Windows Server&nbsp;2008 및 windows server&nbsp;2008&nbsp;R2의 경우 Windows Media 형식 런타임이 windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="66b1f-135">Lync Server 2013을 설치 하기 전에 Windows 데스크톱 환경을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="66b1f-136">Lync Server 2013에서 서버에이 소프트웨어를 찾을 수 없는 경우 설치 하 라는 메시지가 표시 되 고 설치를 완료 하려면 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b1f-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

