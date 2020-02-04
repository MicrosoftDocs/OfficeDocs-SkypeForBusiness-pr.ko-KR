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
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="166be-102">Lync Server 2013의 새로운 클라이언트 기능</span><span class="sxs-lookup"><span data-stu-id="166be-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="166be-103">_**마지막으로 수정한 주제:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="166be-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="166be-104">Microsoft Lync 2013에는 새롭게 디자인 된 사용자 인터페이스와 중요 한 새 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="166be-105">관리자는 이제 Office 설치 프로그램에 클라이언트를 포함 하 여 Office를 배포 하 고 조직의 클라이언트를 사용자 지정 하는 보다 효율적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="166be-106">Lync 2013 사용자 인터페이스 업데이트의 설명 보기는 "Lync 2013의 새로운 기능"을 참조 하세요 <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span><span class="sxs-lookup"><span data-stu-id="166be-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="166be-107">Office 설치 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="166be-107">Integration with Office Setup</span></span>

<span data-ttu-id="166be-108">Outlook messaging 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 lync 2013 용 Lync 2013 클라이언트와 온라인 모임 추가 기능이 이제 Office 2013 설치 프로그램에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="166be-109">이전 버전의 Lync 및 Office Communicator에서는 Windows Installer 속성을 사용 하 여 Office 설치를 사용자 지정 하 고 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="166be-110">Lync 2013는 Office 설치 프로그램과 통합 되므로 다음 방법을 사용 하 여 Lync 2013 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="166be-111">Office 사용자 지정 도구(OCT) 사용</span><span class="sxs-lookup"><span data-stu-id="166be-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="166be-112">Config.xml을 사용 하 여 설치 작업 수행</span><span class="sxs-lookup"><span data-stu-id="166be-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="166be-113">설치 명령줄 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="166be-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="166be-114">Lync 2013 설치 프로그램이 이전 버전의 Lync 또는 Office Communicator를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="166be-115">Lync 2013 클라이언트는 다른 Lync 또는 Office Communicator 클라이언트와 나란히 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="166be-116">자세한 내용은 [Lync Server 2013에서 lync 클라이언트 배포](lync-server-2013-deploying-lync-clients.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="166be-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="166be-117">그룹 정책 배포</span><span class="sxs-lookup"><span data-stu-id="166be-117">Group Policy Deployment</span></span>

<span data-ttu-id="166be-118">Lync 2013이 Office 설치에 포함 되어 있기 때문에 Lync 그룹 정책 설정을 배포 하는 방법이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="166be-119">이전 버전의 Lync 및 Office Communicator에서는 Communicator를 사용 하 여 그룹 정책 설정을 정의할 수 있지만, Lync 2013에서 Office 그룹 정책과 함께 제공 되는 Lync ADMX 및 ADML 관리 서식 파일을 사용 하면 됩니다. 관리 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="166be-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="166be-120">자세한 내용은 [Lync 2013에 대 한 그룹 정책 설정을](lync-server-2013-group-policy-settings-for-lync-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="166be-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="166be-121">Outlook 일정 추가 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="166be-122">Lync 2013의 온라인 모임 추가 기능에는 모임 초대 사용자 지정 및 새 모임 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="166be-123">관리자는 사용자 지정 로고, 지원 URL, 법적 고 지 사항 URL 또는 사용자 지정 바닥글 텍스트를 추가 하 여 조직의 모임 초대를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="166be-124">자세한 내용은 [Lync Server 2013에서 온라인 모임 추가 기능 사용자 지정](lync-server-2013-customizing-the-online-meeting-add-in.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="166be-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="166be-125">새 참석자 음소거 컨트롤을 사용 하면 모임 이끌이가 기본적으로 참석자 오디오와 비디오가 음소거 된 회의를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="166be-126">가상 데스크톱 인프라 플러그 인</span><span class="sxs-lookup"><span data-stu-id="166be-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="166be-127">Lync 2013 클라이언트는 이제 VDI (가상 데스크톱 인프라) 환경에서 오디오 및 비디오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="166be-128">사용자는 오디오 또는 비디오 장치 (예: 헤드셋 또는 카메라)를 로컬 컴퓨터 (예: 씬 클라이언트 또는 컴퓨터 시스템)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="166be-129">사용자는 가상 컴퓨터에 연결 하 고, 가상 컴퓨터에서 실행 중인 Lync 2013 클라이언트에 로그인 하 고, 클라이언트가 로컬로 실행 되는 것 처럼 실시간 오디오 및 비디오 통신에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="166be-130">가상 데스크톱 환경에서 지원 되는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="166be-131">오디오 및 비디오에 대 한 장치 통합에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="166be-132">장치에서 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="166be-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="166be-133">디바이스의 현재 상태 통합</span><span class="sxs-lookup"><span data-stu-id="166be-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="166be-134">여러 HID (휴먼 인터페이스 장치) 지원</span><span class="sxs-lookup"><span data-stu-id="166be-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="166be-135">위치 및 응급 서비스 지원.</span><span class="sxs-lookup"><span data-stu-id="166be-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="166be-136">메신저, 오디오, 비디오, 응용 프로그램 공유, 데스크톱 공유, PowerPoint 공유, 화이트 보드, 파일 전송 등 모든 Lync 형식을 지원</span><span class="sxs-lookup"><span data-stu-id="166be-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="166be-137">사용자 간 통화 및 전화 회의 통화에서 오디오 및 비디오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="166be-138">VDI 플러그 인을 배포 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 LYNC VDI 플러그 인 배포](lync-server-2013-deploying-the-lync-vdi-plug-in.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="166be-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="166be-139">비디오 향상</span><span class="sxs-lookup"><span data-stu-id="166be-139">Video Enhancements</span></span>

<span data-ttu-id="166be-140">몇 가지 새로운 기능은 컨퍼런스 참가자의 비디오 환경을 크게 개선 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="166be-141">얼굴 감지 및 스마트 프레이밍을 사용 하 여 비디오를 향상 시킬 수 있으므로 참가자의 비디오가 프레임의 중앙을 유지 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="166be-142">타사 통화와 단체 회의에서는 이제 고화질 비디오가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="166be-143">사용자는 HD 1080P로 해상도를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="166be-144">참가자는 다른 모임 레이아웃에서 선택할 수 있습니다. 갤러리 보기에는 모든 참가자의 그림 또는 비디오가 표시 됩니다. 발표자 보기에는 모임 콘텐츠 및 현재 발표자의 비디오 또는 그림만 표시 됩니다. 프레젠테이션 보기에는 모임 콘텐츠만 표시 됩니다. 간단히 보기에는 모임 컨트롤만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="166be-145">새 갤러리 기능을 사용 하면 참가자가 동시에 여러 비디오 피드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="166be-146">회의에 다섯 명 이상의 참가자가 있는 경우 가장 활발 한 참가자의 비디오만 맨 위쪽 행에 표시 되 고 다른 참가자에 게 사진이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="166be-147">참가자는 비디오 고정을 사용 하 여 항상 표시할 수 있는 비디오 피드를 한 개 이상 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="166be-148">발표자는 비디오 스포트라이트 기능을 사용 하 여 한 사용자의 비디오 피드를 선택 하 여 모임의 모든 참가자가 해당 참가자만 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="166be-149">채팅방 통합</span><span class="sxs-lookup"><span data-stu-id="166be-149">Chat Room Integration</span></span>

<span data-ttu-id="166be-150">Lync 2013는 이제 Lync 2010 그룹 채팅에서 제공 하 던 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="166be-151">별도의 그룹 채팅 클라이언트는 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="166be-152">Lync 2013 내에서 사용자는 채팅방을 검색 하 고, 연락처에 채팅방을 추가 하 고, 채팅방 활동을 모니터링 하 고, 메시지를 읽고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="166be-153">사용자는 대화방 중 하나에서 특정 키워드가 포함 된 게시물을 추가 하는 경우 알림을 받도록 주제 피드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="166be-154">새로운 **영구 채팅** 옵션 페이지를 사용 하면 사용자가 대화방에 메시지를 게시할 때 적용 되는 알림 알림과 소리를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="166be-155">Lync Web App 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-155">Lync Web App Updates</span></span>

<span data-ttu-id="166be-156">Lync Web App은 Lync Server 2013 모임에 대 한 웹 기반 회의 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="166be-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="166be-157">이번 릴리스에서는 컴퓨터 오디오 및 비디오를 Lync Web App에 추가 하 여 Lync 클라이언트가 로컬로 설치 되어 있지 않은 모든 사용자에 게 전체 모임 중 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="166be-158">모임 참가자는 모든 공동 작업 및 공유 기능 및 발표자 모임 컨트롤에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="166be-159">사용자가 모임에 참가 하려고 하지만 로컬로 설치 된 클라이언트가 없는 경우 Lync Web App이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="166be-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="166be-160">모임 참가에 대 한 추가 옵션을 허용 하려는 경우 모임 참가 페이지를 구성할 수 있습니다. 배포 설명서의 [Lync Server 2013에서 모임 참가 페이지 구성을](lync-server-2013-configuring-the-meeting-join-page.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="166be-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="166be-161">Lync Web App의 향상 된 기능으로 인해 Lync Server 2013의 업데이트 된 버전의 참석자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="166be-162">Lync Web App은 조직 외부의 참가자가 선택할 수 있는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="166be-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="166be-163">로컬 클라이언트 설치는 필요 하지 않지만, 오디오, 비디오, 공유 기능을 처음 사용할 때에는 플러그 인을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="166be-164">모바일 클라이언트 업데이트를 위한 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="166be-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="166be-165">향상 된 현재 상태, 연락처 및 IM 기능 외에도 Lync 2013 모바일 클라이언트는 인터넷 및 셀룰러 데이터 연결을 통해 음성 및 영상 통화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="166be-166">일정 항목에서 모임 링크를 한 번 탭 하면 모바일 사용자가 Lync 음성 및 비디오 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="166be-167">Lync 2013 모바일 클라이언트에 대 한 자세한 내용은 [Lync Server 2013의 모바일 클라이언트 계획](lync-server-2013-planning-for-mobile-clients.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="166be-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="166be-168">Lync 2013 사용자 인터페이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="166be-169">접근성 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-169">Accessibility Updates</span></span>

<span data-ttu-id="166be-170">Lync 2013에는 여러 가지 새로운 접근성 기능이 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="166be-171">Lync 2013는 높은 DPI 해상도를 지원 하 여 사용자가 125% 및 150% dpi의 텍스트와 그래픽을 확장할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="166be-172">Lync는 Windows에서 고대비 테마를 사용 하는 경우 사용자 인터페이스가 완전히 작동할 수 있도록 고대비 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="166be-173">Lync는 사용자가 마우스 없이 중요 한 기능에 액세스할 수 있도록 100 개 이상의 바로 가기 키를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="166be-174">예를 들어 사용자는 Alt + C를 눌러 통화를 수락 하거나, Alt + I를 눌러 포커스를 탭 하거나 설정할 필요 없이이를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="166be-175">(Alt + Q)를 누르면 통화가 종료 되 고 (Ctrl + N) OneNote가 시작 되며 (Alt + T) 도구 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="166be-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="166be-176">Lync 2013의 광범위 한 화면 읽기 지원 기능을 통해 화면 읽기 프로그램을 사용 하는 경우 모든 알림, 수신 요청 및 인스턴트 메시지가 소리내어 읽도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="166be-177">공유 하는 동안 현재 상태</span><span class="sxs-lookup"><span data-stu-id="166be-177">Presence While Sharing</span></span>

<span data-ttu-id="166be-178">Lync에서 사용자가 공유 중인 것을 감지 하면 Lync는 사용자에 게 현재 상태를 표시 하는 자동으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="166be-179">이 상태는 보낸 사람이 작업 그룹 정보 공개 범위에 할당 된 경우를 제외 하 고 모든 수신 통신을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="166be-180">사용자가 보조 모니터에서 완전히 공유 기능을 사용 하는 경우 Lync에서 현재 상태를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="166be-181">대화 창 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-181">Conversation Window Updates</span></span>

<span data-ttu-id="166be-182">다시 디자인 된 대화 창을 통해 중요 한 기능에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="166be-183">새로운 탭이 있는 대화 기능을 사용 하면 사용자가 모든 Im을 유지 하 고 대화방을 하나의 대화 창에 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="166be-184">대화 창의 왼쪽에 있는 탭을 통해 사용자는 모든 활성 대화에서 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="166be-185">사용자는 개별 대화를 별도의 창에 팝 한 다음 창의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="166be-186">또한 창을 다시 주 대화 창으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="166be-187">Lync 2013는 사용자가 로그 아웃 하 고 Lync에 다시 로그인 할 때 사용자의 대화를 다시 열립니다.</span><span class="sxs-lookup"><span data-stu-id="166be-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="166be-188">사용자는 모든 대화에 메신저, 비디오, 프로그램 공유, 데스크톱 공유 또는 웹 회의 도구 (화이트 보드, 모임 메모, 공유 전자 필기장 및 첨부 파일)를 빠르게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="166be-189">비디오 또는 콘텐츠를 공유 하는 모임에서 사용자가 모임 비디오 또는 공유 콘텐츠를 팝 한 다음 창의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="166be-190">Lync 주 창 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-190">Lync Main Window Updates</span></span>

<span data-ttu-id="166be-191">새로운 간소화 된 모양에는 **현재 진행 중인 작업** : 메모 필드, 상태 선택기, **위치 선택기 설정** 등의 친숙 한 기능이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="166be-192">채팅방을 사용할 수 있게 되 면 사용자는 기본 Lync 페이지에 새 **채팅방** 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="166be-193">**채팅방 아이콘을** 사용 하면 사용자가 채팅방과 필터에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="166be-194">사용자는 보기 아이콘을 클릭 하 여 **대화 상대** 보기, **채팅방** 보기, **대화** 보기 또는 **전화** 보기로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="166be-195">사용자가 Exchange 2013으로 마이그레이션한 경우 고해상도 그림을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="166be-196">연락처 보기 및 대화 상대 카드 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="166be-197">Lync 2013에서는 사용자가 **대화 상대** 보기에서 연락처 및 그룹을 보는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="166be-198">새로운 통합 된 연락처 저장소에서 사용자의 Lync 대화 상대를 Exchange 2013으로 마이그레이션한 후 사용자는 Lync 2013, Outlook 또는 Outlook Web App에서 연락처에 액세스 하 고 관리할 수 있으며, 즐겨찾기는 동기화 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="166be-199">예를 들어 사용자가 Outlook에서 즐겨찾기에 연락처를 추가 하는 경우 Lync 2013의 즐겨찾기 그룹에 해당 연락처가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="166be-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="166be-200">XMPP 프록시 및 XMPP 게이트웨이를 추가 하 고 구성한 경우 사용자는 인스턴트 메시지 및 현재 상태에 대해 XMPP 기반 파트너에서 연락처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="166be-201">조직 외부에 있는 사용자를 추가 하는 방법을 사용자에 게 제공 하는 **조직의 새 연락처 추가** 기능을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="166be-202">새로운 **즐겨찾기** 그룹을 사용 하면 사용자가 가장 자주 연락 하는 사용자 목록을 만들어 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="166be-203">사용자는 새 **연락처 목록** 옵션 페이지를 사용 하 여 사용자가 대화 상대를 정렬 하 고 표시 하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="166be-204">사용자는 연락처의 그림을 표시 하는 두 줄 보기를 선택 하거나 한 줄 보기를 압축 하 여 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="166be-205">사용자는 알파벳순 또는 상태별로 연락처를 정렬할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="166be-206">회의 업데이트</span><span class="sxs-lookup"><span data-stu-id="166be-206">Conferencing Updates</span></span>

<span data-ttu-id="166be-207">Lync 2013는 여러 향상 된 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="166be-208">모임 유형에 따라 이제 사용자가 청중을 음소거 하 고 모임을 예약할 때 비디오 공유를 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="166be-209">이러한 옵션은 **모임 옵션** 페이지에서 사용할 수 있으며 참가자가 20 명 이상인 대규모 모임에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="166be-210">회의실의 오디오 컨트롤을 사용 하면 사용자가 음소거, 음소거 해제, 장치 변경 등과 같은 오디오 옵션을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="166be-211">프로그램을 공유 하는 경우 사용자가 여러 프로그램을 사용 해야 하는 경우 공유할 프로그램을 하나 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="166be-212">이제 PowerPoint 파일을 업로드 하 고 슬라이드를 마우스로 가리켜 재생, 일시 중지, 오디오 컨트롤 등의 비디오 컨트롤을 표시 하 여 비디오 클립을 포함 하는 프레젠테이션을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="166be-213">모임 중에는 사용자가 **추가 옵션** (**...**) 메뉴에서 **이 통화를 다음으로 병합** 을 사용 하 여 열려 있는 다른 대화를 모임에 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="166be-214">참가자의 이름을 보려면 **참가자 보기** 단추를 마우스로 가리키거나 **참가자 목록 표시** 를 클릭 하 여 모임에서 패널을 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="166be-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="166be-215">모임 유형에 따라 사용자는 여러 다른 콘텐츠 및 참가자 보기에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="166be-216">모임 녹음/녹화는 Windows Media Player (MP4)에서 재생 되는 형식으로 자동 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="166be-217">사용자가 쉽게 파일을 공유 하거나 기록 관리자의 **게시** 기능을 사용 하 여 공유 위치에 녹음/녹화를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="166be-218">OneNote를 사용 하면 모임에서 공동 작업할 수 있는 새로운 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="166be-219">모임 중에는 OneNote를 사용 하 여 모임 이후 개인에 게 노트를 기록 하거나 공유 전자 필기장을 사용 하거나 모임 참가자와 실시간으로 공동 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="166be-220">모든 팀 구성원은 공유 메모에 액세스 하 여 정보를 제공 하거나, 아이디어를 토론 하거나, 전자 필기장 페이지를 가상 화이트 보드로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="166be-221">모임에서 공유 되는 사용자와 콘텐츠가 노트에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="166be-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="166be-222">사용자는 회의실의 맨 아래에 있는 **콘텐츠 공유 및 선행 모임 활동** 을 사용 하 여 콘텐츠 형식을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="166be-223">사용자는 **프레젠테이션 가능 콘텐츠 관리** 메뉴를 사용 하 여 공유할 콘텐츠를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166be-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="166be-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="166be-224">See Also</span></span>


[<span data-ttu-id="166be-225">Lync Server 2013의 클라이언트 계획</span><span class="sxs-lookup"><span data-stu-id="166be-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

