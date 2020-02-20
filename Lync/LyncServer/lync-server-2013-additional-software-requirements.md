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
ms.openlocfilehash: e725c4c425492316d13b4a1f5957e37199f1521f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="18b47-102">Lync Server 2013의 추가 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="18b47-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18b47-103">_**마지막으로 수정 된 항목:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="18b47-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="18b47-104">Lync Server 2013에서는 서버 플랫폼의 하드웨어 및 운영 체제 요구 사항 외에도 배포 하는 서버에 추가 소프트웨어를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18b47-105">Lync Server를 실행 하는 서버의 플랫폼 요구 사항에 대 한 자세한 내용은 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013에 대 한 서버 하드웨어 플랫폼</A> 및 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013의 서버 및 도구 운영 체제 지원을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18b47-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="18b47-106">클라이언트 컴퓨터 및 장치에 대 한 시스템 요구 사항에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013의 클라이언트 및 장치에 대 한 계획</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18b47-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="18b47-107">관리 도구에 대 한 소프트웨어 요구 사항에 대 한 자세한 내용은 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013의 관리 도구 소프트웨어 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18b47-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="18b47-108">모든 내부 서버 역할에 필요한 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="18b47-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="18b47-109">이 섹션에는 모든 내부 서버 역할 (에 지 서버를 제외한 모든 Lync Server 서버 역할)에 필요한 소프트웨어가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="18b47-110">에 지 서버 및에 지 풀에 대 한 요구 사항은이 항목의 뒷부분에 있는 **추가 소프트웨어의에 지 서버에**나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="18b47-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="18b47-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="18b47-112">Lync Server 2013을 실행 하는 각 서버에 올바른 버전의 Windows PowerShell 3.0이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="18b47-113">자세한 내용은 [설치 Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18b47-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="18b47-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="18b47-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="18b47-115">Lync Server에는 모든 내부 서버 역할 및 Lync Server 관리 도구 또는 Microsoft Lync Server 2013, 계획 도구를 실행 하는 모든 컴퓨터에 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="18b47-116">Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="18b47-117">이를 수동으로 설치 하려면 Microsoft 다운로드 센터에서 Microsoft .NET 4.5 Framework를 다운로드 하세요.[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="18b47-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="18b47-118">Windows Server 2012를 실행 하는 서버에 Microsoft .NET Framework 4.5 설치</span><span class="sxs-lookup"><span data-stu-id="18b47-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="18b47-119">Lync Server 2013 및 Windows Server 2012을 실행할 서버에 Microsoft .NET Framework 4.5을 설치 하는 경우에는 하나의 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="18b47-120">.NET Framework 4.5이 설치 되 면 서버 관리자를 사용 하 여 HTTP 정품 인증을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="18b47-121">**Windows Server 2012에서 .NET 4.5 HTTP 정품 인증을 설치 하려면**</span><span class="sxs-lookup"><span data-stu-id="18b47-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="18b47-122">**시작** 메뉴에서 **프로그램**, **관리 도구**를 차례로 클릭 한 다음 **서버 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="18b47-123">서버 관리자의 **기능 요약**에서 **기능 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="18b47-124">**.Net Framework 4.5**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="18b47-125">**WCF 활성화** 가 아직 선택 되어 있지 않으면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="18b47-126">그런 다음 **HTTP 정품 인증**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="18b47-127">**다음** 을 클릭 하 고 화면의 지시에 따라 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="18b47-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="18b47-128">Windows Identity Foundation</span></span>

<span data-ttu-id="18b47-129">Lync Server 2013의 **Windows Identity foundation** 을 사용 하려면 서버 간 인증 시나리오를 지원 하기 위해 Windows identity foundation을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="18b47-130">Windows Server 2008 R2 및 Windows Server 2012을 설치 하려면 다른 절차가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="18b47-131">다음 목록에서 서버 운영 체제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="18b47-132">Windows server 2008 r 2의 경우 컴퓨터에 이미 설치 되어 있는지 확인 합니다. 2008</span><span class="sxs-lookup"><span data-stu-id="18b47-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="18b47-133">이렇게 하려면 **프로그램 추가/제거**, **설치 된 업데이트 보기**및 **windows** 에서 windows **Identity Foundation (KB974405)** 항목을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="18b47-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="18b47-134">Windows Identity Foundation을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18b47-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="18b47-135">Windows server 2012 For Windows Server 2012의 경우 **서버 관리자** 를 사용 하 여 Windows Identity Foundation을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="18b47-136">서버 관리자 **역할 및 기능 추가 마법사**에서 **기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="18b47-137">목록에서 **Windows Identity Foundation 3.5** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="18b47-138">**다음**을 클릭 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="18b47-139">모든 프런트 엔드 서버 및 Standard Edition Server에 대 한 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="18b47-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="18b47-140">또한 모든 프런트 엔드 서버 및 Standard Edition 서버에서 특정 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="18b47-141">또한 회의, 통화 대기 응용 프로그램, 알림 또는 응답 그룹이 배포 되는 모든 프런트 엔드 서버 및 Standard Edition 서버는 Windows Media 형식 런타임을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="18b47-142">IIS(인터넷 정보 서비스)</span><span class="sxs-lookup"><span data-stu-id="18b47-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="18b47-143">프런트 엔드 서버 및 Standard Edition 서버는 다음 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="18b47-144">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="18b47-144">Static Content</span></span>

  - <span data-ttu-id="18b47-145">기본 문서</span><span class="sxs-lookup"><span data-stu-id="18b47-145">Default Document</span></span>

  - <span data-ttu-id="18b47-146">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="18b47-146">HTTP Errors</span></span>

  - <span data-ttu-id="18b47-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18b47-147">ASP.NET</span></span>

  - <span data-ttu-id="18b47-148">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="18b47-148">.NET Extensibility</span></span>

  - <span data-ttu-id="18b47-149">ISAPI(인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="18b47-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="18b47-150">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="18b47-150">ISAPI Filters</span></span>

  - <span data-ttu-id="18b47-151">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="18b47-151">HTTP Logging</span></span>

  - <span data-ttu-id="18b47-152">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="18b47-152">Logging Tools</span></span>

  - <span data-ttu-id="18b47-153">추적은</span><span class="sxs-lookup"><span data-stu-id="18b47-153">Tracing</span></span>

  - <span data-ttu-id="18b47-154">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="18b47-154">Windows Authentication</span></span>

  - <span data-ttu-id="18b47-155">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="18b47-155">Request Filtering</span></span>

  - <span data-ttu-id="18b47-156">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="18b47-156">Static Content Compression</span></span>

  - <span data-ttu-id="18b47-157">동적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="18b47-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="18b47-158">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="18b47-158">IIS Management Console</span></span>

  - <span data-ttu-id="18b47-159">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="18b47-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="18b47-160">익명 인증 (IIS가 설치 될 때 기본적으로 설치 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="18b47-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="18b47-161">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="18b47-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="18b47-162">Windows Media 형식 런타임 및 Windows 데스크톱 환경</span><span class="sxs-lookup"><span data-stu-id="18b47-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="18b47-163">**Windows 데스크톱 환경** 회의를 배포할 모든 프런트 엔드 서버 및 Standard Edition 서버에 windows Media 형식 런타임이 설치 되어 있어야 하며,이는 windows Server 2012를 제외 하 고 windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="18b47-164">Windows Server 2012에는 Microsoft Media Foundation이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="18b47-165">Windows Media 형식 런타임은 통화 대기, 알림 및 응답 그룹 응용 프로그램에서 알림 및 음악에 대해 재생하는 Windows Media Audio(.wma) 파일을 실행하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="18b47-166">Lync Server 2013을 설치 하기 전에 Windows 데스크톱 환경을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="18b47-167">Lync Server 2013이 서버에서이 소프트웨어를 찾지 못하는 경우 설치 하 라는 메시지가 표시 되 고 서버를 다시 시작 하 여 설치를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="18b47-168">Windows Server 2012에서 실행 되는 프런트 엔드 서버 및 Standard Edition Server 용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="18b47-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="18b47-169">프런트 엔드 서버에는 Windows Server 2012에 기본적으로 설치 되지 않는 .NET 3.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="18b47-170">설치 하려면 Windows Server 2012 설치 미디어를 D 드라이브에 넣고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="18b47-171">Windows Server 2012을 실행 하는 서버에 .NET 3.5을 설치 하는 방법에 대 한 자세한 내용은의 " <https://go.microsoft.com/fwlink/p/?linkid=275032>Microsoft .net Framework 3.5 배포 고려 사항"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18b47-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="18b47-172">디렉터용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="18b47-172">Additional Software for Directors</span></span>

<span data-ttu-id="18b47-173">디렉터는 다음 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="18b47-174">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="18b47-174">Static Content</span></span>

  - <span data-ttu-id="18b47-175">기본 문서</span><span class="sxs-lookup"><span data-stu-id="18b47-175">Default Document</span></span>

  - <span data-ttu-id="18b47-176">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="18b47-176">HTTP Errors</span></span>

  - <span data-ttu-id="18b47-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18b47-177">ASP.NET</span></span>

  - <span data-ttu-id="18b47-178">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="18b47-178">.NET Extensibility</span></span>

  - <span data-ttu-id="18b47-179">ISAPI(인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="18b47-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="18b47-180">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="18b47-180">ISAPI Filters</span></span>

  - <span data-ttu-id="18b47-181">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="18b47-181">HTTP Logging</span></span>

  - <span data-ttu-id="18b47-182">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="18b47-182">Logging Tools</span></span>

  - <span data-ttu-id="18b47-183">추적은</span><span class="sxs-lookup"><span data-stu-id="18b47-183">Tracing</span></span>

  - <span data-ttu-id="18b47-184">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="18b47-184">Windows Authentication</span></span>

  - <span data-ttu-id="18b47-185">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="18b47-185">Request Filtering</span></span>

  - <span data-ttu-id="18b47-186">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="18b47-186">Static Content Compression</span></span>

  - <span data-ttu-id="18b47-187">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="18b47-187">IIS Management Console</span></span>

  - <span data-ttu-id="18b47-188">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="18b47-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="18b47-189">익명 인증(IIS 설치 시 기본적으로 설치됨)</span><span class="sxs-lookup"><span data-stu-id="18b47-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="18b47-190">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="18b47-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="18b47-191">영구 채팅 프런트 엔드 서버용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="18b47-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="18b47-192">영구 채팅 프런트 엔드 서버는 Windows Server의 구성 요소인 메시지 큐 (MSMQ 라고도 함)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="18b47-193">MSMQ 사용에 대 한 자세한 내용은 [여기를 클릭 하세요.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="18b47-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="18b47-194">에 지 서버용 추가 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="18b47-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="18b47-195">에 지 서버에는 다음 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="18b47-196">Lync Server 2013을 실행 하는 각 서버에 올바른 버전의 Windows PowerShell 3.0이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="18b47-197">자세한 내용은 [설치 Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18b47-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="18b47-198">Lync Server에는 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="18b47-199">Windows Server 2008 r 2에 설치 된 Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="18b47-200">이를 수동으로 설치 하려면 Microsoft 다운로드 센터에서 Microsoft .NET 4.5 Framework를 다운로드 하세요.[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="18b47-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="18b47-201">Lync Server 2013의 **Windows Identity foundation** 을 사용 하려면 서버 간 인증 시나리오를 지원 하기 위해 Windows identity foundation을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="18b47-202">Windows Server 2008 R2 및 Windows Server 2012을 설치 하려면 다른 절차가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="18b47-203">다음 목록에서 서버 운영 체제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="18b47-204">Windows server 2008 r 2의 경우 컴퓨터에 이미 설치 되어 있는지 확인 합니다. 2008</span><span class="sxs-lookup"><span data-stu-id="18b47-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="18b47-205">이렇게 하려면 **프로그램 추가/제거**, **설치 된 업데이트 보기**및 **windows** 에서 windows **Identity Foundation (KB974405)** 항목을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="18b47-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="18b47-206">Windows Identity Foundation을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18b47-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="18b47-207">Windows server 2012 For Windows Server 2012의 경우 **서버 관리자** 를 사용 하 여 Windows Identity Foundation을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="18b47-208">서버 관리자 **역할 및 기능 추가 마법사**에서 **기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="18b47-209">목록에서 **Windows Identity Foundation 3.5** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="18b47-210">**다음**을 클릭 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="18b47-211">미디어 서버에 LSP(Layered Service Provider) 설치 금지</span><span class="sxs-lookup"><span data-stu-id="18b47-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="18b47-212">모든 프런트 엔드 서버 또는 독립 실행형 중재 서버에는 Microsoft Internet Security and 가속이 (ISA) 서버 클라이언트 소프트웨어 또는 기타 모든 Winsock 계층화 된 서비스 공급자 (LSP) 소프트웨어를 설치 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="18b47-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="18b47-213">이 소프트웨어를 설치 하면 미디어 트래픽 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b47-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18b47-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18b47-214">See Also</span></span>


[<span data-ttu-id="18b47-215">Lync Server 2013의 관리 도구 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="18b47-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

