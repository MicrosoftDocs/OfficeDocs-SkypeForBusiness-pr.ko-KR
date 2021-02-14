---
title: Microsoft Teams의 통화 품질 모니터링 및 개선
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: QoS(서비스 품질) 설정을 사용하여 Microsoft Teams에서 분석 및 통화 품질 대시보드를 호출합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 107bbf867c410a556e02d76eb991cf5f04730efa
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46587635"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="caef6-103">Microsoft Teams의 통화 품질 모니터링 및 개선</span><span class="sxs-lookup"><span data-stu-id="caef6-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="caef6-104">이 문서에서는 Microsoft Teams에서 통화 품질을 모니터링, 문제 해결, 관리 및 개선하는 데 사용할 수 있는 세 가지 주요 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="caef6-105">**CQD(통화** 품질 대시보드) : 전체적인 추세 또는 문제를 분석하기 위해 성능 향상을 주도합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="caef6-106">**통화 분석:** 개별 사용자의 통화 및 모임 품질을 분석하기 위해</span><span class="sxs-lookup"><span data-stu-id="caef6-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="caef6-107">**QoS(서비스 품질)**: 중요한 네트워크 트래픽의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="caef6-108">통화 품질 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caef6-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="caef6-109">사용자당 통화 분석  및 통화  품질 대시보드를 사용하여 진행 중 발생할 통화 품질 문제를 찾아서 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="caef6-110">이렇게 하면 네트워크 전체에서 성능 향상을 구동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="caef6-111">이러한 도구는 모두 Teams 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="caef6-112">**통화 분석은** Teams에서 각 사용자의 특정 통화 및  모임과 관련된 장치, 네트워크 및 연결에 대한 자세한 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="caef6-113">Teams 관리자 및 지원팀 상담원은 이 정보를 사용하여 특정 통화에서 통화 품질 및 연결 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="caef6-114">자세한 내용은 통화 [](set-up-call-analytics.md) 분석 설정 및 통화 분석을 사용하여 통화 품질 문제를 [해결하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="caef6-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="caef6-115">**CQD(통화** 품질 대시보드)는 조직 전체의 통화 품질에 대한 네트워크 전체 보기를 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="caef6-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="caef6-116">CQD 정보를 사용하여 문제를 식별하고 해결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="caef6-117">먼저 [CQD를 설정합니다.](turning-on-and-using-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="caef6-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="caef6-118">그런 다음 [Teams에서 통화 및 모임 품질 관리를 읽습니다.](quality-of-experience-review-guide.md)</span><span class="sxs-lookup"><span data-stu-id="caef6-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="caef6-119">호출 분석 및 CQD는 병렬로 실행하며 독립적으로 또는 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="caef6-120">예를 들어 통신 지원 전문가가 사용자의 통화 문제를 해결하는 데 도움이 더 필요하다고 판단하면 통화에 대한 추가 정보에 액세스할 수 있는 통신 지원 엔지니어에게 전화를 에스컬링합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="caef6-121">차례로 통신 지원 엔지니어는 네트워크 엔지니어에게 호출 분석에서 발견된 가능한 사이트 관련 문제로 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="caef6-122">네트워크 엔지니어는 CQD를 검사하여 전체 사이트 관련 문제가 사용자의 통화 문제의 원인일 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="caef6-123">QoS를 사용하여 중요한 네트워크 트래픽 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="caef6-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="caef6-124">사용자가 통화 및 모임에 Teams를 사용할 때 발신자 음성이 통화나 모임에서 끊기거나 끊어지거나 끊어지게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="caef6-125">공유 비디오는 중지 또는 픽셀화하거나 모두 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="caef6-126">이는 네트워크 정체가 발생하고 순서를 늦게 도착하거나 아치 않는 음성 및 비디오 트래픽을 나타내는 IP 패킷 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="caef6-127">이 경우(또는 처음에 발생하지 못하게) **QoS(서비스** 품질)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="caef6-128">QoS를 사용하면 지연에 민감한 네트워크 트래픽(예: 음성 또는 비디오 스트림)의 우선 순위를 지정하여 덜 민감하지 않은 트래픽(예: 다운로드할 추가 초가 큰 거래가 아닌 새 앱 다운로드)에서 "줄에서 잘라 내기"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="caef6-129">QoS는 Windows 그룹 정책 개체 및 포트 기반 Access Control Lists라는 라우팅 기능을 사용하여 실시간 스트림의 모든 패킷을 식별하고 표시합니다. 이 기능은 네트워크에서 자신의 전용 네트워크 대역폭을 공유하는 음성, 비디오 및 화면을 제공하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="caef6-130">이상적으로는 Teams를 롤아웃할 준비를 하면서 내부 네트워크에 QoS를 구현하지만 언제든지 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="caef6-131">충분히 작은 경우 QoS가 필요하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caef6-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="caef6-132">준비가 됐을 때 [Microsoft Teams에서 QoS(서비스 품질 구현)를 읽어 읽습니다.](QoS-in-Teams.md)</span><span class="sxs-lookup"><span data-stu-id="caef6-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="caef6-133">QoS를 사용하여 모임 트래픽을 관리하려는 경우 Teams 모임에 대한 실시간 미디어 트래픽을 처리하는 방법 [집합을 읽어 읽습니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span><span class="sxs-lookup"><span data-stu-id="caef6-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="caef6-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="caef6-134">Related Topics</span></span>

[<span data-ttu-id="caef6-135">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="caef6-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="caef6-136">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caef6-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="caef6-137">CQD 설정</span><span class="sxs-lookup"><span data-stu-id="caef6-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="caef6-138">Teams에서 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="caef6-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="caef6-139">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caef6-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

