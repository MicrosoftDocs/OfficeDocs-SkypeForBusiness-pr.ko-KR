---
title: 'Lync Server 2013: 추가 소프트웨어 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="a20ce-102">Lync Server 2013에 대한 추가 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a20ce-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a20ce-103">_**마지막으로 수정한 주제:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="a20ce-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="a20ce-104">Lync Server 2013에는 서버 플랫폼의 하드웨어 및 운영 체제 요구 사항 외에도 배포 하는 서버에 추가 소프트웨어를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a20ce-105">Lync Server를 실행 하는 서버에 대 한 플랫폼 요구 사항에 대 한 자세한 내용은 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013의 서버 하드웨어 플랫폼</A> 및 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013의 서버 및 도구 운영 체제 지원</A>에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="a20ce-106">클라이언트 컴퓨터 및 장치에 대 한 시스템 요구 사항에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013에서 클라이언트 및 장치 계획</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="a20ce-107">관리 도구의 소프트웨어 요구 사항에 대 한 자세한 내용은 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013의 관리 도구 소프트웨어 요구</A>사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="a20ce-108">모든 내부 서버 역할에 필요한 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a20ce-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="a20ce-109">이 섹션에서는 모든 내부 서버 역할 (예를 들어, Edge 서버를 제외한 모든 Lync Server 서버 역할)에 필요한 소프트웨어를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="a20ce-110">Edge 서버 및 Edge 풀에 대 한 요구 사항은이 항목의 뒷부분에 있는 **Edge 서버의 추가 소프트웨어**에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="a20ce-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a20ce-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="a20ce-112">Lync Server 2013을 실행 하는 각 서버에는 올바른 Windows PowerShell 3.0 버전이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="a20ce-113">자세한 내용은 [Lync Server 2013 용 Windows PowerShell 3.0 설치](lync-server-2013-installing-windows-powershell-3-0.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="a20ce-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a20ce-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="a20ce-115">Lync Server에는 모든 내부 서버 역할 및 Lync Server 관리 도구 또는 Microsoft Lync Server 2013, 계획 도구를 실행 하는 모든 컴퓨터에 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="a20ce-116">Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="a20ce-117">수동으로 설치 하려면 Microsoft 다운로드 센터에서 Microsoft .NET 4.5 프레임 워크를 다운로드 하세요.[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="a20ce-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="a20ce-118">Windows Server 2012를 실행 하는 서버에 Microsoft .NET Framework 4.5 설치</span><span class="sxs-lookup"><span data-stu-id="a20ce-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="a20ce-119">Lync Server 2013 및 Windows Server 2012를 실행 하는 서버에 Microsoft .NET Framework 4.5을 설치 하는 경우 하나의 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="a20ce-120">.NET Framework 4.5가 설치 된 후에는 서버 관리자를 사용 하 여 HTTP 정품 인증을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="a20ce-121">**Windows Server 2012에서 .NET 4.5 HTTP 정품 인증을 설치 하려면**</span><span class="sxs-lookup"><span data-stu-id="a20ce-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="a20ce-122">**시작** 메뉴에서 **프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **서버 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="a20ce-123">서버 관리자의 **기능 요약**에서 **기능 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="a20ce-124">**.Net Framework 4.5**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="a20ce-125">아직 선택 하지 않은 경우 **WCF 정품 인증** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="a20ce-126">그런 다음 **HTTP 활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="a20ce-127">**다음** 을 클릭 하 고 화면의 지시에 따라 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="a20ce-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="a20ce-128">Windows Identity Foundation</span></span>

<span data-ttu-id="a20ce-129">Lync Server 2013의 **Windows Identity foundation** 에서는 서버에서 서버 인증 시나리오를 지원 하기 위해 Windows identity foundation을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="a20ce-130">Windows Server 2008 R2 및 Windows Server 2012에는 Windows 식별 토대를 설치 하는 데 다른 절차가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="a20ce-131">다음 목록에서 해당 서버 운영 체제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="a20ce-132">Windows Server 2008 R2 For Windows Server 2008 R2의 경우 컴퓨터에 이미 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="a20ce-133">이렇게 하려면 **프로그램 추가/제거**, **설치 된 업데이트 보기**, **Windows** 에서 **KB974405 (windows Identity Foundation**입력 항목)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="a20ce-134">Windows Id 파운데이션을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="a20ce-135">Windows server 2012 For Windows Server 2012에서는 **서버 관리자** 를 사용 하 여 Windows Identity Foundation을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="a20ce-136">서버 관리자 **역할 및 기능 추가 마법사**에서 **기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="a20ce-137">목록에서 **Windows Id 파운데이션 3.5** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="a20ce-138">**다음**을 클릭 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="a20ce-139">모든 프런트 엔드 서버 및 Standard Edition 서버에 대 한 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a20ce-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="a20ce-140">또한 모든 프런트 엔드 서버와 스탠더드 버전 서버는 특정 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="a20ce-141">또한, 회의, 통화 공원 응용 프로그램, 공지 사항 또는 응답 그룹을 배포 하는 모든 프런트 엔드 서버와 Standard Edition 서버는 Windows Media 형식 런타임을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="a20ce-142">IIS (인터넷 정보 서비스)</span><span class="sxs-lookup"><span data-stu-id="a20ce-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="a20ce-143">프런트 엔드 서버와 Standard Edition 서버는 다음 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="a20ce-144">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a20ce-144">Static Content</span></span>

  - <span data-ttu-id="a20ce-145">기본 문서</span><span class="sxs-lookup"><span data-stu-id="a20ce-145">Default Document</span></span>

  - <span data-ttu-id="a20ce-146">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="a20ce-146">HTTP Errors</span></span>

  - <span data-ttu-id="a20ce-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a20ce-147">ASP.NET</span></span>

  - <span data-ttu-id="a20ce-148">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="a20ce-148">.NET Extensibility</span></span>

  - <span data-ttu-id="a20ce-149">ISAPI (인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="a20ce-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a20ce-150">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="a20ce-150">ISAPI Filters</span></span>

  - <span data-ttu-id="a20ce-151">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="a20ce-151">HTTP Logging</span></span>

  - <span data-ttu-id="a20ce-152">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="a20ce-152">Logging Tools</span></span>

  - <span data-ttu-id="a20ce-153">추적할</span><span class="sxs-lookup"><span data-stu-id="a20ce-153">Tracing</span></span>

  - <span data-ttu-id="a20ce-154">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="a20ce-154">Windows Authentication</span></span>

  - <span data-ttu-id="a20ce-155">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="a20ce-155">Request Filtering</span></span>

  - <span data-ttu-id="a20ce-156">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="a20ce-156">Static Content Compression</span></span>

  - <span data-ttu-id="a20ce-157">동적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="a20ce-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="a20ce-158">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="a20ce-158">IIS Management Console</span></span>

  - <span data-ttu-id="a20ce-159">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="a20ce-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a20ce-160">익명 인증 (IIS가 설치 되 면 기본적으로 설치 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a20ce-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="a20ce-161">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="a20ce-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="a20ce-162">Windows Media 형식 런타임 및 Windows 데스크톱 환경</span><span class="sxs-lookup"><span data-stu-id="a20ce-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="a20ce-163">**Windows 데스크톱 환경** 회의를 배포할 모든 프런트 엔드 서버 및 Standard Edition 서버에는 windows Media 형식 런타임이 설치 되어 있어야 하며,이는 windows Server 2012을 Windows 데스크톱 환경의 일부로 설치 되어 있는 경우를 제외 하 고,</span><span class="sxs-lookup"><span data-stu-id="a20ce-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="a20ce-164">Windows Server 2012에는 Microsoft Media Foundation이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="a20ce-165">Windows Media 형식 런타임은 통화 공원, 알림 및 응답 그룹 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows Media 오디오 (.wma) 파일을 실행 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="a20ce-166">Lync Server 2013을 설치 하기 전에 Windows 데스크톱 환경을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="a20ce-167">Lync Server 2013에서 서버에이 소프트웨어를 찾을 수 없는 경우 설치 하 라는 메시지가 표시 되 고 설치를 완료 하려면 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="a20ce-168">프런트 엔드 서버용 추가 소프트웨어 및 Windows Server 2012에서 실행 되는 스탠더드 버전 서버</span><span class="sxs-lookup"><span data-stu-id="a20ce-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="a20ce-169">프런트 엔드 서버에는 Windows Server 2012에 기본적으로 설치 되지 않는 .NET 3.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="a20ce-170">설치 하려면 Windows Server 2012 설치 미디어를 D 드라이브에 입력 하 고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="a20ce-171">Windows Server 2012를 실행 하는 서버에 .NET 3.5을 설치 하는 방법에 대 한 자세한 내용은의 <https://go.microsoft.com/fwlink/p/?linkid=275032>"Microsoft .net Framework 3.5 배포 고려 사항"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="a20ce-172">디렉터 용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a20ce-172">Additional Software for Directors</span></span>

<span data-ttu-id="a20ce-173">디렉터는 다음 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="a20ce-174">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a20ce-174">Static Content</span></span>

  - <span data-ttu-id="a20ce-175">기본 문서</span><span class="sxs-lookup"><span data-stu-id="a20ce-175">Default Document</span></span>

  - <span data-ttu-id="a20ce-176">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="a20ce-176">HTTP Errors</span></span>

  - <span data-ttu-id="a20ce-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a20ce-177">ASP.NET</span></span>

  - <span data-ttu-id="a20ce-178">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="a20ce-178">.NET Extensibility</span></span>

  - <span data-ttu-id="a20ce-179">ISAPI (인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="a20ce-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a20ce-180">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="a20ce-180">ISAPI Filters</span></span>

  - <span data-ttu-id="a20ce-181">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="a20ce-181">HTTP Logging</span></span>

  - <span data-ttu-id="a20ce-182">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="a20ce-182">Logging Tools</span></span>

  - <span data-ttu-id="a20ce-183">추적할</span><span class="sxs-lookup"><span data-stu-id="a20ce-183">Tracing</span></span>

  - <span data-ttu-id="a20ce-184">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="a20ce-184">Windows Authentication</span></span>

  - <span data-ttu-id="a20ce-185">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="a20ce-185">Request Filtering</span></span>

  - <span data-ttu-id="a20ce-186">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="a20ce-186">Static Content Compression</span></span>

  - <span data-ttu-id="a20ce-187">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="a20ce-187">IIS Management Console</span></span>

  - <span data-ttu-id="a20ce-188">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="a20ce-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a20ce-189">익명 인증 (IIS가 설치 되 면 기본적으로 설치 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a20ce-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="a20ce-190">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="a20ce-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="a20ce-191">영구 채팅 프런트 엔드 서버용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a20ce-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="a20ce-192">영구 채팅 프런트 엔드 서버는 Windows Server의 구성 요소인 메시지 대기열 (MSMQ 라고도 함)을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="a20ce-193">MSMQ를 사용 하는 방법에 대 한 자세한 내용은 [여기를 클릭 하세요.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="a20ce-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="a20ce-194">Edge 서버용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a20ce-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="a20ce-195">Edge 서버에는 다음 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="a20ce-196">Lync Server 2013을 실행 하는 각 서버에는 올바른 Windows PowerShell 3.0 버전이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="a20ce-197">자세한 내용은 [Lync Server 2013 용 Windows PowerShell 3.0 설치](lync-server-2013-installing-windows-powershell-3-0.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="a20ce-198">Lync Server에는 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="a20ce-199">Windows Server 2008 R2에 설치 된 Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="a20ce-200">수동으로 설치 하려면 Microsoft 다운로드 센터에서 Microsoft .NET 4.5 프레임 워크를 다운로드 하세요.[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="a20ce-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="a20ce-201">Lync Server 2013의 **Windows Identity foundation** 에서는 서버에서 서버 인증 시나리오를 지원 하기 위해 Windows identity foundation을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="a20ce-202">Windows Server 2008 R2 및 Windows Server 2012에는 Windows 식별 토대를 설치 하는 데 다른 절차가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="a20ce-203">다음 목록에서 해당 서버 운영 체제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="a20ce-204">Windows Server 2008 R2 For Windows Server 2008 R2의 경우 컴퓨터에 이미 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="a20ce-205">이렇게 하려면 **프로그램 추가/제거**, **설치 된 업데이트 보기**, **Windows** 에서 **KB974405 (windows Identity Foundation**입력 항목)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="a20ce-206">Windows Id 파운데이션을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="a20ce-207">Windows server 2012 For Windows Server 2012에서는 **서버 관리자** 를 사용 하 여 Windows Identity Foundation을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="a20ce-208">서버 관리자 **역할 및 기능 추가 마법사**에서 **기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="a20ce-209">목록에서 **Windows Id 파운데이션 3.5** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="a20ce-210">**다음**을 클릭 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="a20ce-211">미디어 서버에 계층화 된 소켓 공급자 설치 안 함</span><span class="sxs-lookup"><span data-stu-id="a20ce-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="a20ce-212">모든 프런트 엔드 서버 또는 독립 실행형 중재 서버에는 Microsoft 인터넷 보안 및 가속 (ISA) 서버 클라이언트 소프트웨어 또는 다른 모든 Winsock 계층화 된 서비스 공급자 (LSP) 소프트웨어를 설치 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a20ce-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="a20ce-213">이 소프트웨어를 설치 하면 미디어 트래픽 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a20ce-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a20ce-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a20ce-214">See Also</span></span>


[<span data-ttu-id="a20ce-215">Lync Server 2013의 관리 도구 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a20ce-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

