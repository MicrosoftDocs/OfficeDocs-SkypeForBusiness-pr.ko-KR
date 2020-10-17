---
title: 'Lync Server 2013: 새로운 클라이언트 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6103c6cd8ae762402a94412a56eda107f43a58fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518205"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="9798e-102">Lync Server 2013의 새로운 클라이언트 기능</span><span class="sxs-lookup"><span data-stu-id="9798e-102">What's new for clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9798e-103">_**마지막으로 수정 된 항목:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9798e-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="9798e-104">Microsoft Lync 2013에는 새롭게 디자인 된 사용자 인터페이스와 중요 한 새로운 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="9798e-105">관리자는 이제 Office 설치 프로그램에 클라이언트를 포함 하 여 조직에서 Office를 배포 하 고 클라이언트를 사용자 지정 하는 보다 효율적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9798e-106">Lync 2013 사용자 인터페이스 업데이트의 설명 보기에 대 한 자세한 내용은 "Lync 2013의 새로운 기능"을 참조 하십시오 <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> .</span><span class="sxs-lookup"><span data-stu-id="9798e-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="9798e-107">Office 설치 프로그램과의 통합</span><span class="sxs-lookup"><span data-stu-id="9798e-107">Integration with Office Setup</span></span>

<span data-ttu-id="9798e-108">Outlook 메시징 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 lync 2013 용 Lync 2013 클라이언트와 온라인 모임 추가 기능은 이제 Office 2013 설치 프로그램에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="9798e-109">이전 버전의 Lync 및 Office Communicator에서는 Windows Installer 속성을 사용 하 여 Office 설치를 사용자 지정 하 고 제어할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="9798e-110">Lync 2013는 Office 설치 프로그램에 통합 되었기 때문에 다음 방법을 사용 하 여 Lync 2013 설치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="9798e-111">OST(Office 사용자 지정 도구) 사용</span><span class="sxs-lookup"><span data-stu-id="9798e-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="9798e-112">Config.xml을 사용하여 설치 작업 수행</span><span class="sxs-lookup"><span data-stu-id="9798e-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="9798e-113">설치 프로그램 명령줄 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="9798e-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9798e-114">Lync 2013 설치 프로그램은 이전 버전의 Lync 또는 Office Communicator를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="9798e-115">Lync 2013 클라이언트는 다른 Lync 또는 Office Communicator 클라이언트와 함께 나란히 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="9798e-116">자세한 내용은 lync [Server 2013에서 lync 클라이언트 배포](lync-server-2013-deploying-lync-clients.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9798e-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="9798e-117">그룹 정책 배포</span><span class="sxs-lookup"><span data-stu-id="9798e-117">Group Policy Deployment</span></span>

<span data-ttu-id="9798e-118">Lync 2013는 이제 Office 설치에 포함 되어 있으므로 Lync 그룹 정책 설정을 배포 하는 방법이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="9798e-119">이전 버전의 Lync 및 Office Communicator에서는 ADML를 사용 하 여 그룹 정책 설정을 정의할 수 있지만 Lync 2013에서는 이제 Office 그룹 정책 관리 템플릿과 함께 제공 되는 Lync ADMX 및 관리 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="9798e-120">자세한 내용은 [Lync 2013에 대 한 그룹 정책 설정을](lync-server-2013-group-policy-settings-for-lync-2013.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9798e-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="9798e-121">Outlook 예약 추가 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="9798e-122">Lync 2013 용 온라인 모임 추가 기능에는 모임 초대 사용자 지정 및 새 모임 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="9798e-123">관리자는 사용자 지정 로고, 지원 URL, 법적 고지 사항 URL 또는 사용자 지정 바닥글 텍스트를 추가하여 조직의 모임 초대를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="9798e-124">자세한 내용은 [Lync Server 2013에서 온라인 모임 추가 기능 사용자 지정](lync-server-2013-customizing-the-online-meeting-add-in.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9798e-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="9798e-125">새로운 참석자 음소거 제어를 통해서는 모임 이끌이가 기본적으로 참석자의 오디오 및 비디오가 음소거된 상태로 회의를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="9798e-126">Virtual Desktop Infrastructure 플러그인</span><span class="sxs-lookup"><span data-stu-id="9798e-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="9798e-127">Lync 2013 클라이언트는 이제 VDI (가상 데스크톱 인프라) 환경에서 오디오 및 비디오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="9798e-128">사용자는 오디오 또는 비디오 장치(예: 헤드셋 또는 카메라)를 로컬 컴퓨터(예: 씬 클라이언트 또는 용도가 다시 설정된 컴퓨터)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="9798e-129">사용자가 가상 컴퓨터에 연결 하 고, 가상 컴퓨터에서 실행 중인 Lync 2013 클라이언트에 로그인 하 고, 클라이언트가 로컬로 실행 되는 것 처럼 실시간 오디오 및 비디오 통신에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="9798e-130">다음은 가상 데스크톱 환경에서 지원 되는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="9798e-131">다음을 포함한 오디오 및 비디오에 대한 장치 통합:</span><span class="sxs-lookup"><span data-stu-id="9798e-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="9798e-132">장치에서 통화 제어</span><span class="sxs-lookup"><span data-stu-id="9798e-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="9798e-133">장치에 현재 상태 통합</span><span class="sxs-lookup"><span data-stu-id="9798e-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="9798e-134">다중 HID(휴먼 인터페이스 장치) 지원</span><span class="sxs-lookup"><span data-stu-id="9798e-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="9798e-135">위치 및 긴급 서비스 지원</span><span class="sxs-lookup"><span data-stu-id="9798e-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="9798e-136">IM, 오디오, 비디오, 응용 프로그램 공유, 데스크톱 공유, PowerPoint 공유, 화이트 보드, 파일 전송 등 모든 Lync 형식 지원</span><span class="sxs-lookup"><span data-stu-id="9798e-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="9798e-137">일대일 통화 및 회의 통화에서 오디오 및 비디오 지원</span><span class="sxs-lookup"><span data-stu-id="9798e-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="9798e-138">VDI 플러그 인을 배포 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 LYNC VDI 플러그 인 배포](lync-server-2013-deploying-the-lync-vdi-plug-in.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9798e-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="9798e-139">향상된 비디오 기능</span><span class="sxs-lookup"><span data-stu-id="9798e-139">Video Enhancements</span></span>

<span data-ttu-id="9798e-140">일부 새로운 기능으로 회의 참가자의 비디오 환경이 크게 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="9798e-141">참가자의 비디오에 참가자가 계속해서 화면 가운데에 표시되도록 하는 얼굴 인식 및 스마트 프레이밍 기술로 비디오 기능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="9798e-p107">두 사용자간 통화 및 단체 회의에서 이제 고해상도 비디오가 지원됩니다. 사용자는 최대 HD 1080P까지 향상된 해상도를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="9798e-144">참가자는 다양한 모임 레이아웃 중에서 선택할 수 있습니다. 갤러리 보기에는 모든 참가자의 사진 또는 비디오가 표시되고, 발표자 보기에는 모임 콘텐츠 및 현재 발표자의 비디오 또는 사진만 표시되고, 프레젠테이션 보기에는 모임 콘텐츠만 표시되며, 간단히 보기에는 모임 컨트롤만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="9798e-p108">새로운 갤러리 기능으로 참가자는 여러 개의 비디오 피드를 동시에 확인할 수 있습니다. 회의가 5명 이상의 참가자로 구성된 경우 가장 활동적인 참가의 비디오 피드가 위쪽에 표시되고 다른 참가자는 사진이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="9798e-147">참가자는 비디오 고정 기능을 사용해서 항상 표시할 비디오 피드 중 하나 이상을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="9798e-148">발표자는 비디오 스포트라이트 기능을 사용해서 한 사람의 비디오 피드를 선택하여 모든 회의 참가자가 해당 참가자만 볼 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="9798e-149">채팅방 통합</span><span class="sxs-lookup"><span data-stu-id="9798e-149">Chat Room Integration</span></span>

<span data-ttu-id="9798e-150">Lync 2013는 이제 Lync 2010 그룹 채팅에서 이전에 제공 된 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="9798e-151">개별 그룹 채팅 클라이언트가 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="9798e-152">Lync 2013 내에서 사용자는 채팅방을 검색 하 고, 대화 상대를 연락처에 추가 하 고, 대화방 활동을 모니터링 하 고, 메시지를 읽고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="9798e-153">사용자는 항목 피드를 만들어서 채팅방에 포함된 사용자가 특정 키워드가 포함된 게시물을 추가할 때 이에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="9798e-154">새로운 **영구 채팅** 옵션 페이지에서는 사용자가 자신의 채팅방에 메시지를 게시할 때 적용할 알림 경고 및 사운드를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="9798e-155">Lync Web App 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-155">Lync Web App Updates</span></span>

<span data-ttu-id="9798e-156">Lync Web App은 Lync Server 2013 모임에 대 한 웹 기반 회의 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="9798e-157">이 릴리스에서는 컴퓨터 오디오 및 비디오를 Lync Web App에 추가 하 여 Lync 클라이언트를 로컬로 설치 하지 않은 모든 사용자에 게 전체 모임 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="9798e-158">모임 참가자가 모든 공동 작업 및 공유 기능과 발표자 모임 컨트롤에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="9798e-159">사용자가 모임에 참가 하려고 하지만 로컬로 설치 된 클라이언트는 없는 경우 Lync Web App이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="9798e-160">모임 참가에 대 한 추가 옵션을 허용 하려는 경우 모임 참가 페이지를 구성할 수 있습니다. 배포 설명서에서 [Lync Server 2013의 모임 참가 페이지 구성을](lync-server-2013-configuring-the-meeting-join-page.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9798e-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="9798e-161">Lync Web App에 대 한 개선 사항으로 인해 Lync Server 2013에서는 업데이트 된 버전의 참석자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="9798e-162">Lync Web App은 조직 외부의 참가자가 선택할 수 있는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="9798e-163">오디오, 비디오 및 공유 기능을 사용하기 위해서는 처음에 사용할 때 플러그인을 설치해야 하지만 로컬 클라이언트를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="9798e-164">모바일 클라이언트용 Lync 2013 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="9798e-165">향상 된 현재 상태, 연락처 및 IM 기능 외에도 Lync 2013 모바일 클라이언트는 인터넷 및 셀룰러 데이터 연결을 통해 음성 및 화상 통화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="9798e-166">일정 항목에서 모임 링크를 한 번 탭 하면 모바일 사용자는 Lync 음성 및 비디오 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="9798e-167">Lync 2013 모바일 클라이언트에 대 한 자세한 내용은 [Lync Server 2013에서 모바일 클라이언트 계획](lync-server-2013-planning-for-mobile-clients.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9798e-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="9798e-168">Lync 2013 사용자 인터페이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="9798e-169">내게 필요한 옵션 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-169">Accessibility Updates</span></span>

<span data-ttu-id="9798e-170">Lync 2013는 몇 가지 새로운 내게 필요한 옵션 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="9798e-171">Lync 2013는 높은 DPI 해상도를 지원 하므로 사용자가 125%와 150% dpi의 텍스트 및 그래픽 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="9798e-172">Lync에서는 Windows에서 고대비 테마와 함께 사용 하는 경우 사용자 인터페이스를 완전히 작동할 수 있도록 대비가 높은 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="9798e-173">Lync에서는 사용자가 마우스 없이 중요 한 기능에 액세스할 수 있도록 바로 가기 키를 100 개 이상 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="9798e-174">예를 들어 사용자는 Tab을 옮기거나 포커스를 설정하지 않아도 Alt+C를 눌러서 통화를 수락하거나 Alt + I를 눌러서 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="9798e-175">Alt+Q를 누르면 통화가 종료되고 Ctrl+N을 누르면 OneNote가 시작되며, Alt+T를 누르면 도구 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="9798e-176">Lync 2013의 광범위 한 화면 판독기를 지원 하기 때문에 화면 판독기를 사용 하는 경우 모든 알림, 들어오는 요청 및 인스턴트 메시지를 소리내어 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="9798e-177">공유 중 현재 상태</span><span class="sxs-lookup"><span data-stu-id="9798e-177">Presence While Sharing</span></span>

<span data-ttu-id="9798e-178">Lync에서 사용자가 공유 중인 것을 감지 하면 Lync에서 현재 상태를 표시 하는 사용자에 게 자동으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="9798e-179">이 상태는 보낸 사람이 작업 그룹 정보 공개 범위에 지정되지 않은 한 모든 들어오는 통신을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="9798e-180">사용자가 보조 모니터에서 공유 기능을 완전히 사용 하는 경우 Lync에서 현재 상태를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="9798e-181">대화 창 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-181">Conversation Window Updates</span></span>

<span data-ttu-id="9798e-182">새롭게 디자인된 대화 창에서는 중요한 기능에 대한 빠른 액세스 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="9798e-p116">새로운 대화 탭 기능으로 사용자는 이제 모든 IM 및 채팅방을 하나의 대화 창에 유지할 수 있습니다. 대화 창 왼쪽에 표시되는 탭을 이용해서 모든 활성 대화 간에 쉽게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="9798e-p117">사용자는 개별 대화를 다른 분리된 창으로 빼내고 창 크기를 조절할 수 있습니다. 또한 창을 다시 기본 대화 창에 넣을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="9798e-187">Lync 2013는 사용자가 로그 아웃 하 고 Lync에 다시 로그인 할 때 사용자의 대화를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="9798e-188">사용자는 어느 대화에도 IM, 비디오, 프로그램 공유, 데스크톱 공유 또는 웹 회의 도구(화이트보드, 모임 메모, 공유 전자 필기장 및 첨부 파일을 신속하게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="9798e-189">비디오 또는 콘텐츠를 공유 중인 모임에서는 사용자가 모임 비디오 또는 공유 콘텐츠를 빼내서 창 크기를 조절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="9798e-190">Lync 주 창 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-190">Lync Main Window Updates</span></span>

<span data-ttu-id="9798e-191">새롭게 효율화된 화면 모양에 **새로운 소식** 메모 필드, 상태 선택기 및 **내 위치 설정** 선택기와 같은 익숙한 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="9798e-192">대화방을 사용 하도록 설정 하면 기본 Lync 페이지에 **새 채팅방** 아이콘이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="9798e-193">**채팅방** 아이콘을 사용해서는 자신의 채팅방 및 필터에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="9798e-194">사용자는 보기 아이콘을 클릭해서 **연락처** 보기, **채팅방** 보기, **대화** 보기 또는 **전화** 보기로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="9798e-195">사용자가 Exchange 2013로 마이그레이션된 경우 고해상도 그림을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="9798e-196">연락처 보기 및 대화 상대 카드 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="9798e-197">Lync 2013에서는 사용자가 **대화 상대** 보기에서 연락처 및 그룹을 볼 수 있는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="9798e-198">새 통합 연락처 저장소를 사용 하 여 사용자의 Lync 대화 상대를 Exchange 2013로 마이그레이션한 후 사용자가 Lync 2013, Outlook 또는 Outlook Web App에서 연락처에 액세스 하 고이를 관리할 수 있으며, 즐겨찾기는 동기화 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="9798e-199">예를 들어 사용자가 Outlook의 즐겨찾기에 연락처를 추가 하는 경우 Lync 2013의 즐겨찾기 그룹에 해당 연락처가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="9798e-200">XMPP 프록시 및 XMPP 게이트웨이를 추가하고 구성한 경우에는 사용자가 인스턴트 메시징 및 현재 상태를 위해 XMPP 기반 파트너에서 연락처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="9798e-201">새로운 **내 조직 외부의 대화 상대 추가** 기능을 통해서는 조직 외부에 있는 사용자를 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="9798e-202">새로운 **즐겨찾기** 그룹을 통해서는 자주 사용하는 사용자를 더 빠르게 액세스할 수 있도록 사용자 목록으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="9798e-p120">사용자는 새로운 **대화 상대 목록** 옵션 페이지를 사용해서 사용자를 정렬하고 연락처를 표시하는 방법을 선택할 수 있습니다. 대화 상대의 사진이 표시된 확장된 2행 보기를 선택하거나 간결한 1행 보기를 선택할 수 있습니다. 또한 연락처를 알파벳 또는 상태별로 정렬할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="9798e-206">회의 업데이트</span><span class="sxs-lookup"><span data-stu-id="9798e-206">Conferencing Updates</span></span>

<span data-ttu-id="9798e-207">Lync 2013에서는 회의 기능이 몇 가지 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="9798e-p121">모임 유형에 따라 사용자는 이제 모임을 예약할 때 모든 사용자를 음소거하거나 비디오 공유를 차단할 수 있습니다. 이러한 옵션은 **모임 옵션** 페이지에서 사용할 수 있으며 참가자 20명 이상인 대규모 모임에서 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="9798e-210">모임 방에서 오디오 컨트롤을 쉽게 사용할 수 있으므로 음소거, 음소거 해제, 장치 변경 등의 오디오 옵션을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="9798e-211">프로그램을 공유할 때는 두 개 이상의 프로그램을 사용해야 하는 경우 여러 개의 프로그램을 공유하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="9798e-212">이제는 비디오 클립이 포함된 프레젠테이션을 업로드할 수 있습니다. PowerPoint 파일을 업로드하고 마우스를 슬라이드 위로 이동하면 재생, 일시 정지와 같은 비디오 컨트롤과 오디오 컨트롤을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="9798e-213">모임 중에는 **다른 옵션**(**...**) 메뉴에서 **이 호출을 다음으로 병합**을 사용해서 열려 있는 다른 대화를 현재 모임에 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="9798e-214">참가자의 이름을 보기 위해서는 **참가자 보기** 단추 위로 마우스를 가져가거나 **참가자 목록 표시**를 클릭하여 패널을 모임에 도킹하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="9798e-215">모임 유형에 따라 사용자는 여러 콘텐츠 및 참가자 보기 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="9798e-p122">모임 기록은 Windows Media Player(MP4)에서 재생되는 형식으로 자동으로 저장됩니다. 사용자는 이 파일을 다른 사용자와 쉽게 공유하거나 기록 관리자에서 **게시**를 사용하여 공유 위치에 기록을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="9798e-p123">OneNote는 모임에서 공동 작업할 수 있는 새로운 방법들을 지원합니다. 모임 중 사용자는 모임 후 개인 목적으로 사용하기 위해 OneNote를 사용해서 메모를 작성하거나 공유 전자 필기장을 사용하고 실시간으로 모임 참가자들과 같이 편집할 수 있습니다. 모든 팀 구성원이 공유 전자 필기장에 액세스해서 정보를 나누거나, 생각을 브레인스토밍하거나, 전자 필기장 페이지를 가상의 화이트보드처럼 사용할 수 있습니다. 모임에서 공유되는 콘텐츠 및 사용자는 자동으로 해당 전자 필기장에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="9798e-p124">사용자는 모임 방 아래의 **공유 콘텐츠 및 선행 모임 작업**을 사용해서 콘텐츠 형식 간에 전환할 수 있습니다. 또한 **프레젠테이션 가능 콘텐츠 관리** 메뉴를 사용해서 공유하려는 콘텐츠를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9798e-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9798e-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9798e-224">See Also</span></span>


[<span data-ttu-id="9798e-225">Lync Server 2013의 클라이언트 계획</span><span class="sxs-lookup"><span data-stu-id="9798e-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

