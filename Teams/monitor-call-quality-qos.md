---
title: Microsoft 팀의 통화 품질 모니터링 및 개선
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: QoS (서비스 품질) 설정을 사용한 다음 Microsoft 팀에서 분석 및 통화 품질 대시보드를 호출 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085943"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="7660c-103">Microsoft 팀의 통화 품질 모니터링 및 개선</span><span class="sxs-lookup"><span data-stu-id="7660c-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="7660c-104">이 문서에서는 Microsoft 팀에서 통화 품질을 모니터링, 문제 해결, 관리 및 개선 하는 데 사용할 수 있는 세 가지 주요 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="7660c-105">**CQD (통화 품질 대시보드)**: 조직 전체에 걸친 추세 또는 문제를 분석 하는 데 드라이브 성능이 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="7660c-106">**통화 분석**: 개별 사용자의 통화 및 모임 품질을 분석 하는 방법</span><span class="sxs-lookup"><span data-stu-id="7660c-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="7660c-107">**QoS (서비스 품질)**: 중요 한 네트워크 트래픽 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="7660c-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="7660c-108">통화 음질 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7660c-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="7660c-109">사용자 단위 **통화 분석** 및 **통화 품질 대시보드** 를 사용 하 여 진행 중인 작업 중에 발생 하는 통화 품질 문제를 찾고 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="7660c-110">이렇게 하면 네트워크에서 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="7660c-111">이러한 도구는 모두 팀 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="7660c-112">**통화 분석** 은 팀의 각 사용자에 대 한 ***특정 통화 및 모임*** 과 관련 된 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="7660c-113">팀 관리자 및 헬프데스크 상담원은이 정보를 사용 하 여 특정 전화의 통화 품질 및 연결 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="7660c-114">자세한 내용은 통화 [분석 설정](set-up-call-analytics.md) 및 통화 [분석을 사용 하 여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="7660c-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="7660c-115">**CQD (통화 품질 대시보드)** 는 조직의 ***네트워크 전체*** 에 걸친 통화 품질 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="7660c-116">모든 문제를 식별 하 고 해결 하는 데 도움이 되는 CQD 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="7660c-117">먼저 [CQD를 설정](turning-on-and-using-call-quality-dashboard.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="7660c-118">그런 다음 [팀에서 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="7660c-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="7660c-119">통화 분석 및 CQD는 병렬로 실행 되며 독립적으로 또는 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="7660c-120">예를 들어 통신 지원 전문가에 게 사용자의 통화 문제 해결에 대 한 추가 지원이 필요한 것으로 판단 되는 경우 통화를 통신 지원 엔지니어에 게 전달 하 고, 사용자는 통화에 대 한 자세한 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="7660c-121">그러면 통신 지원 엔지니어가 전화 분석에서 발견 되는 사이트 관련 문제에 대 한 네트워크 엔지니어를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="7660c-122">네트워크 엔지니어는 전체 사이트 관련 문제가 사용자의 통화 문제를 일으킬 수 있는지 확인 하기 위해 CQD를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="7660c-123">QoS를 사용 하 여 중요 한 네트워크 트래픽 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="7660c-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="7660c-124">사용자가 팀을 사용 하 여 통화 및 모임을 시작 하면 통화 또는 모임에서 발신자의 음성이 발생 하거나 절삭 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="7660c-125">공유 비디오가 중지 또는 pixelate 수도 있고 모두 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="7660c-126">이는 네트워크 혼잡이 발생 하 고 순서에 도달 하지 않은 음성 및 비디오 트래픽을 나타내는 IP 패킷으로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="7660c-127">이 문제가 발생 하는 경우 (또는 처음에이를 발생 하지 않도록 하려면) **서비스 품질 (QoS)** 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="7660c-128">QoS를 사용 하는 경우에는 지연 되는 네트워크 트래픽 (예: 음성 또는 비디오 스트림)의 우선 순위를 지정 하 여 중요 하지 않은 트래픽 앞 (즉, 다운로드가 시작 되는 추가 초가 큰 문제가 아닌 경우 새 앱 다운로드)에 "줄에서 잘라내기"를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="7660c-129">QoS는 실시간 스트림의 모든 패킷을 식별 하 고 표시 하며, Windows 그룹 정책 개체와 포트 기반 액세스 제어 목록 이라는 라우팅 기능을 사용 하 여 네트워크에 음성, 비디오, 화면 공유를 제공 하 여 자신의 전용 네트워크 대역폭을 공유할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="7660c-130">이상적으로는 팀 롤아웃을 준비 하는 동안 내부 네트워크에 QoS를 구현 하지만 언제 든 지이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="7660c-131">충분히 작은 경우 QoS가 필요 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="7660c-132">준비가 되 면 [Microsoft 팀에서 QoS (서비스 품질)](QoS-in-Teams.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="7660c-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="7660c-133">QoS를 사용 하 여 모임 트래픽을 관리 하려면 [팀 모임에 대 한 실시간 미디어 트래픽을 처리 하는 방법 설정을](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7660c-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="7660c-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7660c-134">Related Topics</span></span>

[<span data-ttu-id="7660c-135">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="7660c-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="7660c-136">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7660c-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="7660c-137">CQD 설정</span><span class="sxs-lookup"><span data-stu-id="7660c-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="7660c-138">팀에서 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="7660c-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="7660c-139">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7660c-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

