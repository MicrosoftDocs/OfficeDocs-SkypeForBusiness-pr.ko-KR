---
title: 통화 대기열 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 인사말 메시지, 음악 보관, 착신 전환, 기타 기능을 제공 하는 Microsoft 팀과 통화 큐에 대 한 전화 시스템을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 8365761f25ff981cd13770f23a27f4ef8a589b25
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220306"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="80a7a-103">통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="80a7a-103">Create a call queue</span></span>

<span data-ttu-id="80a7a-104">통화 큐는 특정 문제 또는 질문에 대 한 도움을 얻을 수 있는 조직의 사용자에 게 발신자를 라우팅하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="80a7a-105">통화는 큐에 있는 사람에 게 한 번에 하나씩 분배 됩니다 ( *상담원*이라고 함).</span><span class="sxs-lookup"><span data-stu-id="80a7a-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="80a7a-106">통화 대기열은 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-106">Call queues provide:</span></span>

- <span data-ttu-id="80a7a-107">인사말 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-107">A greeting message.</span></span>

- <span data-ttu-id="80a7a-108">다른 사용자가 대기 중에 음악을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-108">Music while people are waiting on hold.</span></span>

- <span data-ttu-id="80a7a-109">전화 접속 *-선입 선출 (FIFO* ) 주문부터 상담원을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="80a7a-110">큐 오버플로 및 시간 초과에 대 한 처리 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="80a7a-111">이 문서의 절차를 따르기 전에 [팀 자동 전화 교환 및 통화 대기열에 대 한 요금제](plan-auto-attendant-call-queue.md) 를 확인 하 고 [시작 단계](plan-auto-attendant-call-queue.md#getting-started) 를 팔 로우 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="80a7a-112">통화 대기열을 설정 하려면 팀 관리 센터에서 **음성을**확장 하 고 **통화 대기열**을 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="80a7a-113">리소스 계정 및 언어</span><span class="sxs-lookup"><span data-stu-id="80a7a-113">Resource account and language</span></span>

![](media/call-queue-name-language.png)

1. <span data-ttu-id="80a7a-114">통화 대기열의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-114">Type a name for the call queue.</span></span> <span data-ttu-id="80a7a-115">상담원은 대기열에서 수신 전화를 받을 때이 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-115">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="80a7a-116">**계정 추가**를 클릭 하 고이 통화 큐와 함께 사용 하려는 리소스 계정을 검색 한 다음 **추가**를 클릭 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="80a7a-117">언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-117">Choose a language.</span></span> <span data-ttu-id="80a7a-118">이 언어는 시스템에서 생성 하는 음성 메시지 및 음성 메일에 사용 됩니다 (사용 하도록 설정한 경우).</span><span class="sxs-lookup"><span data-stu-id="80a7a-118">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and--hold-music"></a><span data-ttu-id="80a7a-119">인사말 및 음악 보류</span><span class="sxs-lookup"><span data-stu-id="80a7a-119">Greetings and  hold music</span></span>

<span data-ttu-id="80a7a-120">큐에 도착할 때 전화를 받을 때 인사말을 재생할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-120">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="80a7a-121">재생 하려는 인사말이 포함 된 MP3, WAV 또는 WMA 파일을 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-121">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="80a7a-122">팀은 보류 중인 호출자에 게 기본 음악을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-122">Teams provides default music to callers while they are on hold.</span></span> <span data-ttu-id="80a7a-123">특정 오디오 파일을 재생 하려면 **오디오 파일 재생** 을 선택 하 고 MP3, WAV 또는 WMA 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-123">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="80a7a-124">업로드 된 기록은 5mb 보다 클 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-124">The uploaded recording can be no larger than 5 MB..</span></span>

## <a name="call-agents"></a><span data-ttu-id="80a7a-125">통화 에이전트</span><span class="sxs-lookup"><span data-stu-id="80a7a-125">Call agents</span></span>

<span data-ttu-id="80a7a-126">선택한 통화 에이전트는 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-126">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="80a7a-127">전화 시스템 라이선스 및 Enterprise Voice가 설정 된 온라인 사용자</span><span class="sxs-lookup"><span data-stu-id="80a7a-127">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="80a7a-128">통화 요금제를 사용 하는 온라인 사용자</span><span class="sxs-lookup"><span data-stu-id="80a7a-128">Online users with a Calling Plan</span></span>
- <span data-ttu-id="80a7a-129">온-프레미스 비즈니스용 Skype 서버 사용자</span><span class="sxs-lookup"><span data-stu-id="80a7a-129">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="80a7a-130">상담원은 통화 대기열 통화를 위해 Microsoft 팀 앱을 사용 하 고 있는 경우에는 TeamsOnly 모드에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-130">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![](media/call-queue-users-groups.png)

<span data-ttu-id="80a7a-131">최대 20 명의 에이전트를 개별적으로 추가 하거나 그룹을 통해 최대 200 에이전트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-131">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="80a7a-132">큐에 사용자를 추가 하려면 사용자 **추가**, 사용자 검색을 차례로 클릭 하 고 **추가**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-132">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="80a7a-133">큐에 그룹을 추가 하려면 그룹 **추가**를 클릭 하 고 그룹을 검색 한 다음 **추가**를 클릭 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-133">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="80a7a-134">배포 목록, 보안 그룹, Microsoft 365 그룹 또는 Microsoft 팀 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-134">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="80a7a-135">그룹에 추가 된 새 사용자는 첫 번째 통화가 도착 하는 데 8 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-135">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="80a7a-136">통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="80a7a-136">Call routing</span></span>

![](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="80a7a-137">**회의 모드** 는 에이전트가 통화를 수락 한 후 호출자가 에이전트에 연결 하는 데 걸리는 시간을 크게 줄여줍니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="80a7a-138">회의 모드가 작동 하려면 통화 큐의 상담원은 다음 클라이언트 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="80a7a-139">최신 버전의 Microsoft 팀 데스크톱 클라이언트, Android 앱 또는 iOS 앱</span><span class="sxs-lookup"><span data-stu-id="80a7a-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="80a7a-140">Microsoft 팀 전화 버전 1449/1.0.94.2020051601 이상</span><span class="sxs-lookup"><span data-stu-id="80a7a-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="80a7a-141">에이전트 팀 계정은 팀 전용 모드로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="80a7a-142">요구 사항에 맞지 않는 상담원은 통화 라우팅 목록에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="80a7a-143">에이전트가 호환 되는 클라이언트를 사용 하는 경우에는 통화 큐에 대해 회의 모드를 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="80a7a-144">다른 용무 중 통화 모드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="80a7a-145">현재 상태 기반 라우팅이 활성화 되어 있지 않은 경우 통화 대기열 호출이 계속 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="80a7a-146">**라우팅 메서드** 는 에이전트가 대기열에서 전화를 받는 순서를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="80a7a-147">다음 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-147">Choose from these options:</span></span>

- <span data-ttu-id="80a7a-148">**수행자 라우팅은** 동시에 대기열의 모든 에이전트를 울릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="80a7a-149">통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="80a7a-150">**Serial 라우팅은** 모든 통화 에이전트를 **통화 에이전트** 목록에 지정 된 순서 대로 하나씩 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="80a7a-151">에이전트가 전화를 걸거나 받지 못하는 경우 통화는 다음 에이전트로 연결 되며, 모든 에이전트가 선택 되거나 시간 초과 될 때까지 시도 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="80a7a-152">**라운드 로빈** 에서는 각 호출 에이전트가 대기열에서 같은 수의 호출을 받을 수 있도록 들어오는 호출의 라우팅을 분산 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="80a7a-153">이는 모든 통화 에이전트 간에 동일한 기회를 보장 하기 위해 인바운드 영업 환경에서 바람직 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="80a7a-154">**가장 긴 유휴** 시간은 오랫동안 유휴 상태에 있는 에이전트로 각 호출을 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="80a7a-155">현재 상태를 사용할 수 있거나 해당 사용자의 현재 상태가 10 분 미만으로 떨어져 있는 경우 에이전트가 유휴 상태인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="80a7a-156">현재 상태가 10 분 이상인 에이전트는 유휴 상태로 간주 되지 않으며 현재 상태를 사용할 수 있는 것으로 변경 될 때까지 통화를 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![](media/call-queue-presence-agents-time.png)


<span data-ttu-id="80a7a-157">**현재 상태 기반 라우팅은** 통화 에이전트의 가용성 상태를 사용 하 여 선택한 라우팅 메서드의 호출 라우팅 목록에 에이전트가 포함 되어야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-157">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="80a7a-158">가용성 상태가 **사용 가능** 으로 설정 된 통화 에이전트는 통화 라우팅 목록에 포함 되며 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-158">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="80a7a-159">가용성 상태가 다른 상태로 설정 된 에이전트는 통화 라우팅 목록에서 제외 되며, 해당 사용 가능 상태가 다시 **사용 가능**으로 변경 될 때까지 통화를 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-159">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="80a7a-160">라우팅 메서드를 사용 하 여 현재 상태 기반 통화 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-160">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="80a7a-161">에이전트가 전화를 opts 경우 사용 가능한 상태에 관계 없이 통화 라우팅 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-161">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="80a7a-162">현재 상태 기반 라우팅이 사용 되는 경우 비즈니스용 Skype 클라이언트를 사용 하는 에이전트가 통화 라우팅 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-162">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="80a7a-163">비즈니스용 Skype를 사용 하는 에이전트가 있는 경우 현재 상태 기반 통화 회람을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="80a7a-163">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="80a7a-164">**에이전트 알림 시간** 대기열이 다음 에이전트로 호출을 리디렉션하는 동안 에이전트의 전화가 연결 되는 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-164">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="80a7a-165">대용량 큐의 경우 다음 설정을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-165">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="80a7a-166">**자동** **전화 회의 모드**</span><span class="sxs-lookup"><span data-stu-id="80a7a-166">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="80a7a-167">**전화 교환 라우팅** **메서드** 라우팅</span><span class="sxs-lookup"><span data-stu-id="80a7a-167">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="80a7a-168">**현재 상태 기반 라우팅** **On**</span><span class="sxs-lookup"><span data-stu-id="80a7a-168">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="80a7a-169">**에이전트 알림 시간:** **20 초**</span><span class="sxs-lookup"><span data-stu-id="80a7a-169">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="80a7a-170">통화 오버플로 처리</span><span class="sxs-lookup"><span data-stu-id="80a7a-170">Call overflow handling</span></span>

![](media/call-queue-overflow-handling.png)

<span data-ttu-id="80a7a-171">**큐의 최대 통화** 는 주어진 시간에 큐에서 대기할 수 있는 최대 호출 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-171">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="80a7a-172">기본값은 50 이지만, 0에서 200 까지의 범위에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-172">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="80a7a-173">이 제한에 도달 하면 **최대 통화 수** 설정에 도달 하는 경우에 지정 된 대로 통화가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-173">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="80a7a-174">통화 연결을 끊거나 통화 라우팅 대상 중 하나로 리디렉션하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-174">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="80a7a-175">예를 들어 호출자가 큐의 에이전트에 대 한 보이스 메일을 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-175">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

> [!NOTE]
> <span data-ttu-id="80a7a-176">최대 통화 수가 0으로 설정 되 면 인사말 메시지가 재생 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-176">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="80a7a-177">통화 시간 제한 처리</span><span class="sxs-lookup"><span data-stu-id="80a7a-177">Call timeout handling</span></span>

![](media/call-queue-timeout-handling.png)

<span data-ttu-id="80a7a-178">**통화 시간 제한: 최대 대기 시간은** 대기 또는 연결 해제 하기 전에 큐에서 통화 대기를 대기할 수 있는 최대 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-178">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="80a7a-179">15 초에서 45 분 까지의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-179">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="80a7a-180">통화 연결을 끊거나 통화 라우팅 대상 중 하나로 리디렉션하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-180">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="80a7a-181">예를 들어 호출자가 큐의 에이전트에 대 한 보이스 메일을 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-181">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="80a7a-182">전화 걸기 제한 옵션을 선택한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-182">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="80a7a-183">발신 전화의 발신자 ID</span><span class="sxs-lookup"><span data-stu-id="80a7a-183">Caller ID for outbound calls</span></span>

<span data-ttu-id="80a7a-184">통화 대기열의 상담원은 고객 전화를 반환 하기 위해 전화를 걸 수 있으므로, 통화 대기열의 구성원에 대 한 발신자 ID를 적절 한 자동 전화 교환의 서비스 번호로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-184">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="80a7a-185">자세한 내용은 [Microsoft 팀의 발신자 ID 정책 관리](caller-id-policies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80a7a-185">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="80a7a-186">지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="80a7a-186">Supported clients</span></span>

- <span data-ttu-id="80a7a-187">통화 대기열의 통화 에이전트에 대해 다음 클라이언트가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-187">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="80a7a-188">비즈니스용 Skype 데스크톱 클라이언트 2016 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="80a7a-188">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="80a7a-189">Lync 데스크톱 클라이언트 2013 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="80a7a-189">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="80a7a-190">Microsoft 팀에서 지원 되는 모든 IP 전화 모델</span><span class="sxs-lookup"><span data-stu-id="80a7a-190">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="80a7a-191">[비즈니스용 Skype Online 전화 받기를](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80a7a-191">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="80a7a-192">Mac 비즈니스용 Skype 클라이언트 (버전 16.8.196 이상)</span><span class="sxs-lookup"><span data-stu-id="80a7a-192">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="80a7a-193">Android 비즈니스용 Skype 클라이언트 (버전 6.16.0.9 이상)</span><span class="sxs-lookup"><span data-stu-id="80a7a-193">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="80a7a-194">iPhone 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="80a7a-194">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="80a7a-195">iPad 용 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="80a7a-195">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="80a7a-196">Microsoft 팀 Windows 클라이언트 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="80a7a-196">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="80a7a-197">Microsoft 팀 Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="80a7a-197">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="80a7a-198">Microsoft 팀 iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="80a7a-198">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="80a7a-199">Microsoft 팀 Android 앱</span><span class="sxs-lookup"><span data-stu-id="80a7a-199">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="80a7a-200">직접 라우팅 번호로 지정 된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 전화를 에이전트로 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-200">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="80a7a-201">통화 대기열 cmdlet</span><span class="sxs-lookup"><span data-stu-id="80a7a-201">Call queue cmdlets</span></span>

<span data-ttu-id="80a7a-202">또한 Windows PowerShell을 사용 하 여 통화 대기열을 만들고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-202">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="80a7a-203">다음은 통화 대기열을 관리 하는 데 사용 하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-203">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="80a7a-204">새로운 CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="80a7a-204">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="80a7a-205">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="80a7a-205">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="80a7a-206">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="80a7a-206">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="80a7a-207">제거-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="80a7a-207">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

## <a name="related-topics"></a><span data-ttu-id="80a7a-208">관련 항목</span><span class="sxs-lookup"><span data-stu-id="80a7a-208">Related topics</span></span>

[<span data-ttu-id="80a7a-209">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="80a7a-209">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="80a7a-210">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="80a7a-210">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="80a7a-211">오디오 회의 및 통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="80a7a-211">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="80a7a-212">새로운 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="80a7a-212">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="80a7a-213">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="80a7a-213">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
