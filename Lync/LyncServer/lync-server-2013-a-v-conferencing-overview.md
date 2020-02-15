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
ms.openlocfilehash: dd73e1356e42aca8dc4159143287371dd66f0688
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="252c7-102">Lync Server 2013의 A/V 회의 개요</span><span class="sxs-lookup"><span data-stu-id="252c7-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="252c7-103">_**마지막으로 수정 된 항목:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="252c7-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="252c7-p101">A/V 회의를 사용하면 사용자 간의 실시간 음성 통신 및 화상 통신이 가능합니다. 회의를 배포할 때는 웹 회의와 A/V 회의를 둘 다 사용하도록 설정하고 사용할지, 아니면 웹 회의만 사용하도록 설정하고 사용할지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-p101">A/V conferencing enables real-time audio and video communications between your users. When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="252c7-p102">A/V 회의를 계획하려면 조직에서 사용할 회의 미디어 유형에 필요한 네트워크 대역폭을 이해해야 합니다. 이러한 미디어 유형으로는 오디오, 비디오, 파노라마 비디오 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-p102">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires. This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="252c7-108">사용자가 A/V 회의를 사용할 수 있도록 설정하기 전에 네트워크에서 결과 부하를 처리할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="252c7-109">네트워크 대역폭이 부족하면 최종 사용자의 환경이 크게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="252c7-110">CAC(통화 허용 제어)를 사용하여 A/V 회의에 사용되는 네트워크 대역폭을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="252c7-111">이것은 중앙 사이트와 분기 사이트 간 제한된 대역폭 링크와 같은 제한적인 네트워크에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="252c7-112">자세한 내용은 [Lync Server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="252c7-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="252c7-113">미디어 대역폭 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항을](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="252c7-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="252c7-114">오디오 회의를 네트워크에 배포한 경우 사용자는 헤드셋과 같은 오디오 장치가 있어야 오디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="252c7-115">또한 비디오 회의를 배포한 경우 사용자를 위해 웹캠과 같은 비디오 장치를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="252c7-116">모든 장치 유형에 대해 Microsoft에서 인증 한 UC (통합 통신) 장치를 사용 하 여 최적의 사용자 환경을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="252c7-117">UC 인증 장치에 대 한 자세한 내용은 "Lync 용 전화 및 장치"를 참조 [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)하세요.</span><span class="sxs-lookup"><span data-stu-id="252c7-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="252c7-118">오디오 또는 비디오 장치의 경우 장치 배포 및 사용자 교육을 고려하고 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="252c7-119">다음 섹션에서는 대역폭 관리와 적절한 클라이언트 선택에 대한 정보를 비롯하여 오디오 회의 및 비디오 회의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="252c7-120">오디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="252c7-120">Audio Conferencing Features</span></span>

<span data-ttu-id="252c7-121">Lync Server 2013에서는 다음을 비롯 하 여 사용자에 대 한 오디오 회의 환경을 구성 하는 데 사용할 수 있는 몇 가지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="252c7-122">**대상 그룹 음소거**   발표자는이 설정을 사용 하 여 전화 회의의 모든 오디오 참가자를 음소거 하 고 발표자 이외에는 자신을 음소거 해제할 수 없는 상태로 회의를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="252c7-123">**회의 입장/종료 알림**   전화 접속 회의를 사용 하도록 설정한 경우 발표자는이 설정을 사용 하 여 입력 및 종료 알림을 설정 하거나 해제 하 여 회의가 진행 되는 동안 혼란을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="252c7-124">**전화 걸기를 통해 사용자 추가**   권한이 부여 된 발표자와 참석자는 회의에 PSTN 번호를 추가 하 고 해당 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="252c7-125">비디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="252c7-125">Video Conferencing Features</span></span>

<span data-ttu-id="252c7-126">Lync Server 2013에서는 다음을 비롯 하 여 사용자에 대 한 비디오 회의 환경을 구성 하는 데 사용할 수 있는 몇 가지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="252c7-127">**갤러리 보기**   두 명 이상의 사용자가 포함 된 비디오 회의에서는 사용자가 자동으로 전화 회의에서 모든 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="252c7-128">비디오 회의의 참가자가 6명 이상인 경우 가장 열심히 참여하는 참가자가 제일 위 행에 나타나고 나머지 참가자는 사진만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="252c7-129">단체 비디오 기능은 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="252c7-130">단체 비디오를 구성 또는 해제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 비디오 대역폭 구성을](lync-server-2013-configuring-video-bandwidth.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="252c7-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="252c7-131">**파노라마 비디오**   회의 대화방에 RoundTable 비디오 회의 장치가 설치 되어 있는 경우이 기능은 회의실에 대 한 전체 360도 보기로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="252c7-132">파노라마 비디오 스트립은 RoundTable 장치를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="252c7-133">**발표자 전용 비디오 모드**   발표자는 발표자의 비디오만 표시 되도록 모임을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="252c7-134">이를 통해 여러 비디오 스트림이 제공되고 다양한 원본으로 잠기는 대규모 모임에서 주의 분산을 막을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="252c7-135">또한 이 모드는 RoundTable 장치로 캡처 및 제공되는 비디오에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="252c7-136">**Hd video**   사용자는 두 회사 전화 및 단체 회의에서 hd 1080p까지 해상도를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="252c7-137">**비디오 스포트라이트**   발표자는 회의의 다른 참가자가 비디오 원본에 해당 하는 선택 된 참가자의 비디오만 표시 되도록 모임을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="252c7-138">이 모드 역시 파노라마 비디오를 위해 RoundTable 장치로 캡처 및 제공되는 비디오에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="252c7-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

