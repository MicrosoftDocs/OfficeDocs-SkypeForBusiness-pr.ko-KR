---
title: 통화 품질 모니터링 및 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: QoS(서비스 품질) 설정을 사용하여 분석 및 통화 품질 대시보드를 Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162694"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="1a5a5-103">통화 품질 모니터링 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a5a5-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="1a5a5-104">이 문서에서는 통화 품질을 모니터링, 문제 해결, 관리 및 개선하는 데 사용할 수 있는 세 가지 주요 도구를 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="1a5a5-105">**CQD(품질 대시보드)** 호출 : 전체 추세 또는 문제를 분석하기 위해 성능 향상을 주도합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="1a5a5-106">**통화 분석**: 개별 사용자의 통화 및 모임 품질을 분석하기 위해</span><span class="sxs-lookup"><span data-stu-id="1a5a5-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="1a5a5-107">**QoS(서비스 품질)**: 중요한 네트워크 트래픽의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="1a5a5-108">통화 품질 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1a5a5-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="1a5a5-109">사용자당 통화 분석  및 통화 **품질** 대시보드를 사용하여 진행 중 발생할 호출 품질 문제를 찾고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="1a5a5-110">이렇게 하면 네트워크 전체에서 성능 향상을 구동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="1a5a5-111">이러한 두 도구는 모두 Teams 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="1a5a5-112">**통화 분석은** 각 사용자에 대한 특정 호출 및 \*\*\*\* 모임과 관련된 디바이스, 네트워크 및 연결에 대한 자세한 Teams.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  **_specific calls and meetings_** for each user in Teams.</span></span> <span data-ttu-id="1a5a5-113">Teams 및 헬프데스크 에이전트는 이 정보를 사용하여 특정 통화에서 통화 품질 및 연결 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="1a5a5-114">자세한 내용은 통화 [](set-up-call-analytics.md) 분석 설정 및 통화 분석 사용 을 읽고 통화 품질이 좋지 않은 [문제를 해결합니다.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="1a5a5-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="1a5a5-115">**CQD(통화** 품질 대시보드)는 조직 전체에서 통화 품질에 대한 네트워크 전체 보기를 제공합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1a5a5-115">**Call Quality Dashboard (CQD)** gives you a **_network-wide view_** of call quality across your organization.</span></span> <span data-ttu-id="1a5a5-116">CQD 정보를 사용하여 문제를 식별하고 해결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="1a5a5-117">먼저 [CQD를 설정합니다.](turning-on-and-using-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="1a5a5-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="1a5a5-118">그런 다음 에서 통화 및 모임 품질 [관리를 Teams.](quality-of-experience-review-guide.md)</span><span class="sxs-lookup"><span data-stu-id="1a5a5-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="1a5a5-119">호출 분석 및 CQD 실행을 병렬로 실행하고 독립적으로 또는 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="1a5a5-120">예를 들어 통신 지원 전문가가 사용자의 통화 문제를 해결하는 데 도움이 더 필요하다고 판단하면 통화에 대한 추가 정보에 액세스할 수 있는 통신 지원 엔지니어에게 전화를 에스컬레이터합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="1a5a5-121">통신 지원 엔지니어는 통화 분석에서 발견한 가능한 사이트 관련 문제를 네트워크 엔지니어에게 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="1a5a5-122">네트워크 엔지니어는 CQD를 검사하여 전체 사이트 관련 문제가 사용자의 호출 문제의 원인일 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="1a5a5-123">QoS를 사용하여 중요한 네트워크 트래픽 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="1a5a5-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="1a5a5-124">사용자가 통화 및 Teams 사용이 시작될 때 발신자 음성이 통화 또는 모임에서 깨지거나 끊어지거나 끊어지게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="1a5a5-125">공유 비디오는 동결되거나 픽셀화되거나 모두 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="1a5a5-126">이는 음성 및 비디오 트래픽이 네트워크 혼잡을 발생하고 순서가 늦거나 아는 경우를 나타내는 IP 패킷에 기인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="1a5a5-127">이 경우(또는 처음에 발생하는 것을 방지하기 위해) **QoS(서비스** 품질)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="1a5a5-128">QoS를 사용하면 지연에 민감한 네트워크 트래픽(예: 음성 또는 비디오 스트림)의 우선 순위를 지정하여 덜 민감하지 않은 트래픽 앞에서 "줄을 끊습니다"(새 앱 다운로드와 같이 다운로드할 추가 초가 큰 중요하지 않은 경우)를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="1a5a5-129">QoS는 그룹 정책 개체 및 포트 기반 액세스 제어 목록이라는 라우팅 Windows 사용하여 실시간 스트림에서 모든 패킷을 식별하고 표시합니다. 이 기능은 네트워크에서 자신의 전용 네트워크 대역폭을 공유하는 음성, 비디오 및 화면 공유를 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="1a5a5-130">이상적으로는 내부 네트워크에서 QoS를 구현하면서 롤아웃할 준비를 Teams 있지만 언제든지 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="1a5a5-131">충분히 작은 경우 QoS가 필요하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5a5-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="1a5a5-132">준비가되면 에서 [QoS(서비스 품질 구현)를 Microsoft Teams.](QoS-in-Teams.md)</span><span class="sxs-lookup"><span data-stu-id="1a5a5-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="1a5a5-133">QoS를 사용하여 모임 트래픽을 관리하기 위해 모임에 대한 실시간 미디어 트래픽을 처리하는 방법 Teams [를 읽습니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span><span class="sxs-lookup"><span data-stu-id="1a5a5-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="1a5a5-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1a5a5-134">Related Topics</span></span>

[<span data-ttu-id="1a5a5-135">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="1a5a5-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="1a5a5-136">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1a5a5-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="1a5a5-137">CQD 설정</span><span class="sxs-lookup"><span data-stu-id="1a5a5-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="1a5a5-138">통화 및 모임 품질 관리 Teams</span><span class="sxs-lookup"><span data-stu-id="1a5a5-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="1a5a5-139">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1a5a5-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)