---
title: Lync Server 2013 회의의 구성 요소 및 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="0e8ec-102">Lync Server 2013의 회의의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="0e8ec-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e8ec-103">_**마지막으로 수정한 주제:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="0e8ec-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="0e8ec-104">토폴로지 작성기에서 회의를 선택 하면 회의가 프런트 엔드 서버 또는 Standard Edition 서버의 일부로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="0e8ec-105">전화 접속 회의 및 PowerPoint 공유에는 추가 구성 요소 및 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="0e8ec-106">다음 섹션에서는 웹 회의, A/V 회의 및 전화 접속 회의에 지원 되는 구성 요소와 토폴로지에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="0e8ec-107">지원 되는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0e8ec-107">Supported Components</span></span>

<span data-ttu-id="0e8ec-108">유일한 구성 요소인 웹 회의와 A/V 회의는 조직의 프런트 엔드 서버 또는 Standard Edition 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="0e8ec-109">프런트 엔드 서버 및 Standard Edition 서버에 대 한 하드웨어 및 소프트웨어 요구 사항 목록은 lync server [2013의 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 및 [lync Server 2013의 서버 소프트웨어 및 인프라 지원을](lync-server-2013-server-software-and-infrastructure-support.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="0e8ec-110">Lync Server 2013는 Office Web Apps 및 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션 공유 및 렌더링을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="0e8ec-111">Office Web Apps 서버를 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="0e8ec-112">전화 접속 회의는 웹 회의와 A/V 회의에 대 한 요구 사항 외에도 다음과 같은 Lync Server 2013 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="0e8ec-113">**응용 프로그램 서비스**   응용 프로그램 서비스는 통합 커뮤니케이션 (UC) 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="0e8ec-114">전화 접속 회의는 응용 프로그램 서비스가 필요한 두 개의 UC 응용 프로그램 (회의 수행자 및 회의 알림)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="0e8ec-115">응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 사용자가 회의 작업 부하를 배포 하 고 전화 접속 회의 옵션을 선택할 때 모든 Standard Edition 서버에 기본적으로 설치 및 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="0e8ec-116">**회의 수행자 응용**   프로그램 회의 수행자 응용 프로그램은 공용 전환 통신 네트워크 (PSTN) 통화를 수락 하 고, 메시지를 재생 하 고, 전화를 a/V 회의에 연결 하는 통합 커뮤니케이션 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="0e8ec-117">회의 작업 부하를 배포 하 고 전화 접속 회의 옵션을 선택할 때 회의 수행자 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="0e8ec-118">**회의 알림**   응용 프로그램 회의 알림 응용 프로그램은 참가자가 회의에 참가 하거나 탈퇴할 때, 참가자가 음소거 또는 음소거 됨 경우, 다른 사용자가 컨퍼런스 로비에 들어가거나 회의가 잠겨 있거나 잠금이 해제 되는 등의 특정 작업을 수행 하는 통합 커뮤니케이션 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="0e8ec-119">회의 알림 응용 프로그램은 또한 휴대폰 키패드의 DTMF (multifrequency) 명령을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="0e8ec-120">회의 작업 부하를 배포 하 고 전화 접속 회의 옵션을 선택할 때 회의 알림 응용 프로그램이 기본적으로 자동으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="0e8ec-121">**전화 접속 회의 설정 페이지**   전화 접속 회의 설정 페이지에 사용 가능한 언어와 전화 회의 전화 접속 번호가 표시 되 고, 회의 정보 (예약할 필요가 없는 모임의 경우), 전화 회의 DTMF 컨트롤 및 PIN (개인 식별 번호) 및 지정 된 회의 정보 관리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="0e8ec-122">전화 접속 회의 설정 페이지는 웹 서비스의 일부로 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="0e8ec-123">**Lync server 2013, 중재 서버 및 pstn 게이트웨이**   전화 회의에는 lync server 2013와 pstn 게이트웨이 간의 신호 (및 미디어)를 변환 하는 조정 서버가 필요 하며, 조정 서버와 pstn 게이트웨이 간에 신호 및 미디어를 번역 하는 PSTN 게이트웨이를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="0e8ec-124">전화 접속 회의의 경우 하나 이상의 중재 서버와 다음 중 하나 이상을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="0e8ec-125">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="0e8ec-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="0e8ec-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="0e8ec-126">IP-PBX</span></span>
    
      - <span data-ttu-id="0e8ec-127">SBC (세션 경계 컨트롤러) (SIP 트렁크 구성으로 연결 되는 인터넷 전화 통신 서비스 공급자의 경우)</span><span class="sxs-lookup"><span data-stu-id="0e8ec-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e8ec-128">또한 엔터프라이즈 음성을 배포 하는 경우 중재 서버 및 PSTN 게이트웨이는 엔터프라이즈 음성 배포의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="0e8ec-129">엔터프라이즈 음성을 배포 하지 않는 경우에는 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이, IP-PBX 또는 전화 접속 회의를 위한 SBC를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="0e8ec-130">**파일 저장소**   파일 저장소는 기록 된 이름 오디오 파일에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="0e8ec-131">파일 저장소는 모든 Enterprise Edition 또는 Standard Edition 배포의 표준 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="0e8ec-132">**사용자 스토어**   사용자 저장소는 사용자 Lync Server 2013 pin을 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="0e8ec-133">핀이 해시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-133">PINs are hashed.</span></span> <span data-ttu-id="0e8ec-134">사용자 저장소는 모든 Enterprise Edition 또는 Standard Edition 배포의 표준 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="0e8ec-135">**Lync server 제어판**   일부 전화 접속 설정은 lync server 제어판을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="0e8ec-136">**Lync server 관리 셸**   모든 전화 접속 설정은 Lync server management shell cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="0e8ec-137">Lync Server 관리 셸 cmdlet은 회의 수행자 응용 프로그램 및 회의 알림 신청 배포, 구성, 실행, 모니터링, 문제 해결에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="0e8ec-138">특정 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="0e8ec-139">지원 되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="0e8ec-139">Supported Topologies</span></span>

<span data-ttu-id="0e8ec-140">Lync Server 2013에서 회의 서비스를 실행 하는 서버는 항상 프런트 엔드 서버 또는 Standard Edition 서버와 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="0e8ec-141">초기 배포 중에 토폴로지 작성기는 토폴로지에 회의를 포함 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="0e8ec-142">토폴로지 작성기를 사용 하 여 기존 배포에 회의를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="0e8ec-143">자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="0e8ec-144">전화 회의 Toplogies</span><span class="sxs-lookup"><span data-stu-id="0e8ec-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="0e8ec-145">전화 접속 회의는 다음 토폴로지와 구성으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="0e8ec-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0e8ec-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="0e8ec-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0e8ec-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="0e8ec-148">기업 음성이 있거나 없는 경우</span><span class="sxs-lookup"><span data-stu-id="0e8ec-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="0e8ec-149">중앙 사이트에는 응용 프로그램 서비스, 회의 수행자 응용 프로그램, 회의 알림 응용 프로그램을 배포할 수 있지만 분기 사이트에 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e8ec-150">전화 접속 회의를 배포 하는 경우 Lync Server 2013 회의를 배포 하는 모든 풀에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="0e8ec-151">모든 풀에 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 회의 기능을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="0e8ec-152">이 요구 사항은 사용자가 한 풀의 액세스 번호를 호출 하 여 다른 풀의 Lync Server 2013 컨퍼런스에 참가 하는 경우 기록 된 이름 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="0e8ec-153">Lync Server 2013 및 Office Web Apps에서 지원 되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="0e8ec-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="0e8ec-154">Lync Server 2013에서는 다음과 같은 방법으로 Office Web Apps 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="0e8ec-155">필요 사항에 따라 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="0e8ec-156">**조직의 방화벽 및 동일한 네트워크 영역에 Lync Server 2013 및 Office Web Apps 서버를 모두 설치 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e8ec-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="0e8ec-157">이 토폴로지에서는 역방향 프록시 서버를 통해 Office Web Apps 서버에 대 한 외부 액세스가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="0e8ec-158">Lync Server 2013과 Office Web apps 서버 (또는 Office Web Apps 서버 팜)는 모두 온-프레미스와 조직의 방화벽 뒤에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="0e8ec-159">Lync Server와 동일한 네트워크 영역에 Office Web Apps 서버를 설치 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="0e8ec-160">외부 Lync 클라이언트는 인터넷에서 요청을 받아서 내부 네트워크에 전달 하는 서버 인 리버스 프록시 서버를 사용 하 여 Lync Server 2013 및 Office Web Apps 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="0e8ec-161">(내부 클라이언트는 Office Web Apps 서버에 직접 연결할 수 있기 때문에 역방향 프록시 서버를 사용할 필요가 없습니다.) 이 토폴로지는 Lync Server 2013에서 사용 하는 전용 Office Web Apps 서버 팜을 사용 하려는 경우에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="0e8ec-162">**외부에서 배포 된 Office Web Apps 서버 사용**</span><span class="sxs-lookup"><span data-stu-id="0e8ec-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="0e8ec-163">이 토폴로지에서는 Lync Server 2013를 온-프레미스에 배포 하 고 Lync Server 네트워크 영역 외부에 배포 된 Office Web Apps 서버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="0e8ec-164">이 문제는 Office Web Apps 서버를 회사의 여러 응용 프로그램에서 공유 하 고 Lync Server에서 Office Web Apps 서버의 외부 인터페이스를 사용 하 고 그 반대의 경우를 위해 네트워크에 배포 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="0e8ec-165">역방향 프록시 서버를 설치할 필요는 없습니다. 대신, Office Web Apps 서버에서 Lync Server 2013 까지의 모든 요청이 Edge 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="0e8ec-166">내부 및 외부 Lync 클라이언트 모두 외부 URL을 사용 하 여 Office Web Apps 서버에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="0e8ec-167">Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버가 토폴로지 작성기에서 외부 네트워크 (즉, 외곽/인터넷)에 배포 됨** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="0e8ec-168">자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="0e8ec-169">선택 하는 토폴로지에 관계 없이 올바른 방화벽 포트를 열어야 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="0e8ec-170">Office Web Apps 서버, 부하 분산 장치 또는 Lync 서버의 방화벽에서 DNS 이름, IP 주소 및 포트가 차단 되지 않았는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e8ec-171">Office Web Apps 서버에 대 한 외부 액세스를 제공 하는 또 다른 옵션은 주변 네트워크에 서버를 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="0e8ec-172">이 작업을 수행 하는 경우 Office Web Apps 서버를 설치 하려면 서버 컴퓨터가 Active Directory 도메인의 구성원 이어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="0e8ec-173">네트워크 정책에서 주변 네트워크의 컴퓨터를 Active Directory 도메인 구성원으로 사용할 수 있도록 허용 하지 않는 한 주변 네트워크에 Office Web Apps 서버를 설치 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="0e8ec-174">대신 내부 네트워크에 Office Web Apps 서버를 설치 하 고 리버스 프록시 서버를 통해 외부 사용자 액세스를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e8ec-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

