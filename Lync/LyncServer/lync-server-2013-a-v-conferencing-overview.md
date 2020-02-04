---
title: Lync Server 2013 A/V 회의 개요
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 405d44f9128ef4c8120a6a8389f8d566b6880b2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="a746e-102">Lync Server 2013의 A/V 회의 개요</span><span class="sxs-lookup"><span data-stu-id="a746e-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a746e-103">_**마지막으로 수정한 주제:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="a746e-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="a746e-104">A/V 회의는 사용자 간 실시간 오디오 및 비디오 통신을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="a746e-105">회의를 배포 하는 경우 웹 회의 및 A/V 회의를 사용 하도록 설정 하 고 사용 하거나 웹 회의만을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="a746e-106">A/V 회의를 계획 하려면 조직에 필요한 회의 미디어 유형에 필요한 네트워크 대역폭을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="a746e-107">여기에는 오디오, 비디오, 파노라마 비디오가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="a746e-108">A/V 회의에 대 한 사용자를 활성화 하기 전에 네트워크가 결과 로드를 처리할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="a746e-109">네트워크 대역폭이 충분 하지 않으면 사용자 환경이 심각 하 게 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="a746e-110">CAC (호출 허용 제어)를 사용 하 여 A/V 회의에 사용 되는 네트워크 대역폭을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="a746e-111">이는 중앙 사이트와 지점 간 제한 된 대역폭 연결과 같은 제한 네트워크에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="a746e-112">자세한 내용은 [Lync Server 2013에서 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a746e-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="a746e-113">미디어 대역폭 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항을](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a746e-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="a746e-114">네트워크에 오디오 회의를 배포 하는 경우 헤드셋과 같은 오디오 장치가 있어야 오디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="a746e-115">비디오 회의를 배포 하는 경우 사용자 용 웹캠 등의 비디오 장치를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="a746e-116">최적의 사용자 환경을 위해 Microsoft에서 모든 디바이스 유형에 대해 인증 하는 UC (통합 통신) 장치를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="a746e-117">UC 인증 장치에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)"Lync 용 전화 및 장치"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a746e-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="a746e-118">오디오 또는 비디오 장치, 장치 배포, 사용자 교육 등을 위해 고려해 야 할 중요 한 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="a746e-119">다음 섹션에서는 대역폭 관리 및 적절 한 클라이언트 선택에 대 한 정보를 포함 하 여 오디오 및 비디오 회의 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="a746e-120">오디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="a746e-120">Audio Conferencing Features</span></span>

<span data-ttu-id="a746e-121">Lync Server 2013는 다음을 포함 하 여 사용자에 대 한 오디오 회의 환경을 구성 하는 데 사용할 수 있는 몇 가지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="a746e-122">**청중 음소거**   발표자는이 설정을 사용 하 여 전화 회의의 모든 오디오 참가자를 음소거 하 고 발표자 이외의 사용자는 음소거를 해제할 수 없는 상태에 회의를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="a746e-123">**회의 시작/종료 알림**   전화 접속 회의를 사용 하도록 설정한 경우 발표자는이 설정을 사용 하 여 알림 기능을 설정 하거나 해제 하 여 회의가 진행 되는 동안 혼란을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="a746e-124">\*\*\*\*   사용 권한이 부여 된 발표자 및 참석자에 게 전화를 걸어 사용자를 추가 하면, 회의에 PSTN 번호를 추가 하 고 해당 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="a746e-125">비디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="a746e-125">Video Conferencing Features</span></span>

<span data-ttu-id="a746e-126">Lync Server 2013는 다음을 포함 하 여 사용자에 대 한 비디오 회의 환경을 구성 하는 데 사용할 수 있는 몇 가지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="a746e-127">**갤러리 보기**   두 명 이상이 있는 비디오 회의에서 사용자는 자동으로 회의의 모든 사람을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="a746e-128">회의에 다섯 명 이상의 참가자가 있는 경우 가장 활발 한 참가자의 비디오가 맨 위쪽 행에 나타나고 다른 참가자를 위한 사진만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="a746e-129">단체 비디오는 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="a746e-130">단체 비디오의 구성 또는 해제에 대 한 자세한 내용은 [Lync Server 2013에서 비디오 대역폭 구성을](lync-server-2013-configuring-video-bandwidth.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a746e-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="a746e-131">**파노라마 비디오**   RoundTable 영상 회의 장치가 회의실에 설치 되어 있는 경우이 기능은 회의실에 대 한 전체 360도 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="a746e-132">파노라마 비디오 스트립은 RoundTable 장치 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="a746e-133">**발표자 전용 비디오 모드**   발표자는 발표자의 비디오만 표시 되도록 모임을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="a746e-134">이렇게 하면 여러 비디오 스트림을 사용할 수 있으며 다양 한 원본으로 잠길 때 대규모 모임에서 혼란을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="a746e-135">이 모드는 RoundTable 디바이스에서 캡처하고 제공 하는 비디오에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="a746e-136">**Hd 영상**   사용자는 2-파티 통화와 단체 회의에서 hd 1080p로 해상도를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="a746e-137">**비디오 스포트라이트**   발표자는 선택한 참가자가 비디오 원본에 있는 비디오만 회의의 다른 참가자에 게 표시 되도록 모임을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="a746e-138">이 모드는 파노라마 비디오의 RoundTable 장치에서 캡처한 후 제공 하는 비디오에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a746e-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

