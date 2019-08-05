---
title: Microsoft 팀에서 QoS를 구현 하 고 통화 분석을 모니터링
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jambirk
description: QoS (서비스 품질) 설정을 사용한 다음 Microsoft 팀에서 분석 및 통화 품질 대시보드를 호출 합니다.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77730db17e900951f0fe1a60b7c0ae2ccdbfbc5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181247"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="d1151-103">Microsoft 팀에서 QoS를 구현 하 고 통화 품질을 모니터링</span><span class="sxs-lookup"><span data-stu-id="d1151-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="d1151-104">시작 하기</span><span class="sxs-lookup"><span data-stu-id="d1151-104">Get Started</span></span>

<span data-ttu-id="d1151-105">사용자가 전화를 걸고 모임에 참가 하기 위해 팀을 사용 하기 시작 하면 통화 또는 모임에서 발신자의 음성이 발생 하거나 chopping 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-105">As your users start using Teams for making calls and holding meetings, they may experience a caller's voice breaking up or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="d1151-106">공유 비디오가 중지 또는 pixelate 수도 있고 모두 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-106">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="d1151-107">이는 네트워크 혼잡이 발생 하 고 순서에 도달 하지 않은 음성 및 비디오 트래픽을 나타내는 IP 패킷으로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="d1151-108">이러한 문제를 처리 하 고 반환 하는 것을 방지 하는 방법 (주로 QoS (서비스 품질)을 확인할 수 있는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-108">There are ways to identify these problems when they surface and prevent their return, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="d1151-109">**QoS (서비스 품질)** 는 네트워크 지연과 같은 중요 한 네트워크 트래픽 (예: 새 앱 다운로드 (예: 다운로드에 추가 초)을 사용 하는 것이 좋습니다. "음성 또는 비디오 스트림")을 "회선에서 잘라내기" 하는 것을 허용 하는 방법입니다. 큰 노력이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-109">**Quality of Service (QoS)** is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="d1151-110">QoS는 Windows 그룹 정책 개체와 포트 기반 액세스 제어 목록 이라는 라우팅 기능을 사용 하 여 실시간 스트림의 모든 패킷을 식별 하 고 표시 하며, 이렇게 하면 네트워크에서 음성, 비디오 및 화면 공유를 통해 자신의 전용 부분을 쉽게 전달할 수 있습니다. 네트워크 대역폭.</span><span class="sxs-lookup"><span data-stu-id="d1151-110">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which then helps your network to give voice, video, and screen share streams their own dedicated portions of network bandwidth.</span></span>

 <span data-ttu-id="d1151-111">전자 메일을 통해 편지를 보내는 것과 같은 기능을 제공 하는 것이 좋습니다. 책 요금을 전송 하는 경우에는 시간이 매우 오래 걸릴 수 있으며, 첫 번째 수업을 보내는 것이 훨씬 더 빠르기 때문에 우선 순위 메일을 보내는 경우에도 마찬가지입니다. 2 일 이내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-111">For now, we'll just say that it's a lot like sending a letter through the mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="d1151-112">많은 양의 네트워크는 메일 보다 빠르게 실행 되지만, 일부 응용 프로그램에 대해 속도가 중요 하 고 다른 사용자에 게는 중요 하지 않은 경우에도 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-112">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="d1151-113">이 주제는 본질적으로 기본적으로 자세 하 고 이해 하기 힘든 반면, 시간과 에너지 선행에 투자 하는 것이 가능 하도록 사용자 환경에 큰 차이를 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-113">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span> <span data-ttu-id="d1151-114">자세한 내용은 [Microsoft 팀에서 서비스 품질 구현 (QoS)](QoS-in-Teams.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1151-114">Read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) for a more detailed discussion.</span></span>

<span data-ttu-id="d1151-115">이상적으로는 팀을 설정 하는 동안 내부 네트워크에 QoS를 구현할 수 있지만,이 경우 선택 사항으로 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-115">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="d1151-116">이렇게 하면 지연 되는 음성 및 비디오 트래픽이 다른 트래픽에 대 한 우선 순위를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-116">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="d1151-117">모든 [클라이언트 장치](QoS-in-Teams-clients.md), [Microsoft 팀 관리 센터](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)및 네트워크의 스위치와 라우터에서이 우선 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-117">You'd do this prioritization on all the [client devices](QoS-in-Teams-clients.md), in the [Microsoft Teams admin center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="d1151-118">[**통화 분석 및 통화 품질 대시보드**](difference-between-call-analytics-and-call-quality-dashboard.md) 는 진행 중인 작업 중 발생 하는 문제를 찾아서 해결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-118">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="d1151-119">**통화 분석** 에서는 Microsoft 팀 또는 비즈니스용 Skype 계정의 각 사용자에 대 한 ***특정 통화 및 모임*** 과 관련 된 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-119">**Call Analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="d1151-120">Office 365 관리자는 통화 분석을 사용 하 여 특정 통화에서 발생 하는 통화 품질 및 연결 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-120">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="d1151-121">이는 문제를 식별 하 고 제거 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-121">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="d1151-122">**콜 품질 대시보드 (CQD)** 는 관리자와 네트워크 엔지니어가 ***네트워크***를 최적화 하 고 단일 통화를 분석 하 고 문제를 해결할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-122">**Call Quality Dashboard (CQD)** is designed to help admins and network engineers optimize their ***network***, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="d1151-123">CQD는 특정 사용자 로부터 포커스를 이동 하 여 전체 조직에 대 한 집계 된 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-123">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="d1151-124">또한 문제를 식별 하 고 제거 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1151-124">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1151-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d1151-125">Related Topics</span></span>

[<span data-ttu-id="d1151-126">Microsoft 팀에서 QoS (서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="d1151-126">Implement Quality of Service (QoS) in Microsoft Teams</span></span>](QoS-in-Teams.md)

[<span data-ttu-id="d1151-127">비디오: 통화 품질 개요</span><span class="sxs-lookup"><span data-stu-id="d1151-127">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="d1151-128">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="d1151-128">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="d1151-129">통화 분석을 사용 하 여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d1151-129">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="d1151-130">통화 품질 대시보드 켜기 및 사용</span><span class="sxs-lookup"><span data-stu-id="d1151-130">Turning on and using Call Quality Dashboard</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="d1151-131">통화 품질 대시보드에서 사용할 수 있는 크기 및 측정값</span><span class="sxs-lookup"><span data-stu-id="d1151-131">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="d1151-132">통화 품질 대시보드의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="d1151-132">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)