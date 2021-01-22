---
title: Microsoft Teams에서 통화 큐 만들기
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
- m365initiative-voice
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
description: 인사말 메시지를 제공하고, 음악, 통화 리디렉션 및 기타 기능을 제공하는 Microsoft Teams를 사용하여 통화 큐에 전화 시스템을 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919034"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="378a6-103">통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="378a6-103">Create a call queue</span></span>

<span data-ttu-id="378a6-104">통화 큐는 특정 문제 또는 질문에 도움을 줄 수 있는 조직의 사용자에게 발신자 라우팅 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="378a6-105">호출은 큐에 있는 사람(에이전트라고도 하는)에게 한 번씩 *배포됩니다.*</span><span class="sxs-lookup"><span data-stu-id="378a6-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="378a6-106">호출 큐는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-106">Call queues provide:</span></span>

- <span data-ttu-id="378a6-107">인사말 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-107">A greeting message.</span></span>

- <span data-ttu-id="378a6-108">음악 대기 중인 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="378a6-109">호출 라우팅(FIFO(First *In, First Out)* 순서로 에이전트에 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="378a6-110">큐 오버플로 및 시간 제한에 대한 처리 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="378a6-111">이 문서의 절차를 수행하기 전에 [Teams](plan-auto-attendant-call-queue.md) 자동 전화 회의 [](plan-auto-attendant-call-queue.md#getting-started) 및 통화 큐에 대한 계획을 읽고 시작 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="378a6-112">통화 큐를 설정하려면 Teams 관리 센터에서 음성을 확장하고 **통화** 큐를 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="378a6-113">리소스 계정 및 언어</span><span class="sxs-lookup"><span data-stu-id="378a6-113">Resource account and language</span></span>

![리소스 계정 및 언어 설정 스크린샷](media/call-queue-name-language.png)

1. <span data-ttu-id="378a6-115">호출 큐의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-115">Type a name for the call queue.</span></span> <span data-ttu-id="378a6-116">에이전트는 큐에서 들어오는 호출을 받으면 이 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="378a6-117">계정 **추가를** 클릭하고 이 호출 큐에 사용할 리소스 계정을 검색한 다음 추가를 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="378a6-118">언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-118">Choose a language.</span></span> <span data-ttu-id="378a6-119">이 언어는 시스템 생성 음성 프롬프트 및 음성메일 전사(사용하도록 설정한 경우)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="378a6-120">대기 중인 큐에서 인사말 및 음악</span><span class="sxs-lookup"><span data-stu-id="378a6-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="378a6-121">발신자들에게 큐에 도착할 때 인사말을 재생할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="378a6-122">재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="378a6-123">Teams는 발신자에 큐에 대기 중인 동안 발신자에 기본 음악을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="378a6-124">특정 오디오 파일을 재생하려면 오디오 파일 재생을 **선택하고** MP3, WAV 또는 WMA 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="378a6-125">업로드된 기록은 5MB를 넘지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="378a6-126">Teams 통화 큐에 제공되는 기본 음악은 조직에서 지불하는 로열티가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="378a6-127">에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="378a6-127">Call agents</span></span>

<span data-ttu-id="378a6-128">호출 [큐에](plan-auto-attendant-call-queue.md#prerequisites) 에이전트를 추가할 수 있는 경우 전제적 준비를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![통화 큐에 대한 사용자 및 그룹 설정 스크린샷](media/call-queue-users-groups.png)

<span data-ttu-id="378a6-130">그룹을 통해 최대 20개 에이전트를 개별적으로 최대 200개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="378a6-131">사용자를 큐에 추가하려면 **사용자** 추가를 클릭하고 사용자를 검색하고 추가를 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="378a6-132">큐에 그룹을 추가하려면 그룹 추가를 클릭하고 **그룹을** 검색한 다음 추가를 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="378a6-133">메일 그룹, 보안 그룹 및 Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="378a6-134">그룹에 추가된 새 사용자는 첫 번째 호출이 도착하는 데 최대 8시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="378a6-135">통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="378a6-135">Call routing</span></span>

![회의 모드 및 라우팅 방법 설정 스크린샷](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="378a6-137">**전화 회의 모드는** 에이전트가 통화를 수락한 후 발신자에 연결되는 데 걸리는 시간을 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="378a6-138">전화 회의 모드가 작동하려면 통화 큐의 에이전트가 다음 클라이언트 중 하나를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="378a6-139">최신 버전의 Microsoft Teams 데스크톱 클라이언트, Android 앱 또는 iOS 앱</span><span class="sxs-lookup"><span data-stu-id="378a6-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="378a6-140">Microsoft Teams 휴대폰 버전 1449/1.0.94.2020051601 이상</span><span class="sxs-lookup"><span data-stu-id="378a6-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="378a6-141">에이전트의 Teams 계정을 Teams 전용 모드로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="378a6-142">요구 사항을 충족하지 않는 에이전트는 통화 라우팅 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="378a6-143">에이전트가 호환되는 클라이언트를 모두 사용하는 경우 통화 큐에 전화 회의 모드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="378a6-144">사용 중이면 회의 모드에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="378a6-145">현재 상태 기반 라우팅을 사용하도록 설정하지 않은 경우 비 호출 큐 호출의 에이전트는 호출 큐 호출과 함께 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="378a6-146">**라우팅 메서드는** 에이전트가 큐에서 호출을 수신하는 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="378a6-147">다음 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-147">Choose from these options:</span></span>

- <span data-ttu-id="378a6-148">**참석자 라우팅은** 큐에 있는 모든 에이전트를 동시에 링합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="378a6-149">호출을 픽업하는 첫 번째 호출 에이전트가 호출을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="378a6-150">**직렬 라우팅은** 호출 에이전트 목록에 지정된 순서대로 모든 호출 에이전트를 하나씩 **링합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="378a6-151">에이전트가 통화를 기각하거나 선택하지 않는 경우 호출은 다음 에이전트에 벨을 울리며, 에이전트가 선택되거나 시간 외 시간 외로 호출될 때까지 모든 에이전트를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="378a6-152">**라운드 로빈은** 들어오는 호출의 라우팅을 균형 조정하여 각 호출 에이전트가 큐에서 동일한 호출 수를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="378a6-153">인바운드 판매 환경에서는 모든 호출 에이전트가 동일한 기회를 보장하는 것이 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="378a6-154">**가장 긴 유휴** 시간은 각 호출을 유휴 시간이 가장 긴 에이전트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="378a6-155">에이전트는 현재 상태를 사용할 수 있는 경우 또는 현재 상태가 10분 미만 동안 비어 있는 경우 유휴 상태로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="378a6-156">현재 상태가 10분 넘게 부재 중 상태인 에이전트는 유휴 상태로 간주되지 않습니다. 현재 상태를 사용 가능으로 변경할 때까지 통화를 받을 자격이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![라우팅, 옵트아웃 및 경고 시간 설정 스크린샷](media/call-queue-presence-agents-time.png)


<span data-ttu-id="378a6-158">**현재 상태 기반 라우팅은** 호출 에이전트의 가용성 상태를 사용하여 선택한 라우팅 방법에 대한 호출 라우팅 목록에 에이전트를 포함해야 하는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="378a6-159">가용성 상태가 사용 가능으로  설정된 호출 에이전트는 통화 라우팅 목록에 포함되어 있으며 통화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="378a6-160">가용성 상태가 다른 상태로 설정된 에이전트는 통화 라우팅 목록에서 제외되어 가용성 상태가 사용 가능으로 다시 변경될 때까지 통화를 받지 **못합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="378a6-161">라우팅 방법 중 원하는 방법으로 현재 상태 기반 호출 라우팅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="378a6-162">에이전트가 통화 수신을 옵트아웃하면 해당 가용성 상태가 설정되어 있는지와 관계없이 통화 라우팅 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="378a6-163">비즈니스용 Skype 클라이언트를 사용하는 에이전트는 현재 상태 기반 라우팅을 사용하도록 설정한 경우 통화 라우팅 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="378a6-164">비즈니스용 Skype를 사용하는 에이전트가 있는 경우 현재 상태 기반 통화 라우팅을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="378a6-165">**에이전트 경고 시간은** 큐가 다음 에이전트로 호출을 리디렉션하기 전에 에이전트의 전화가 울리는 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="378a6-166">볼륨이 큰 큐의 경우 다음 설정이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="378a6-167">**회의 모드에서** **자동으로**</span><span class="sxs-lookup"><span data-stu-id="378a6-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="378a6-168">**Attendant 라우팅에** 라우팅 **방법**</span><span class="sxs-lookup"><span data-stu-id="378a6-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="378a6-169">**에 대한** 현재 상태 기반 **라우팅**</span><span class="sxs-lookup"><span data-stu-id="378a6-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="378a6-170">**에이전트 경고 시간:** **20초**</span><span class="sxs-lookup"><span data-stu-id="378a6-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="378a6-171">호출 오버플로 처리</span><span class="sxs-lookup"><span data-stu-id="378a6-171">Call overflow handling</span></span>

![호출 오버플로 설정 스크린샷](media/call-queue-overflow-handling.png)

<span data-ttu-id="378a6-173">**큐의 최대 호출은** 주어진 시간 동안 큐에서 대기할 수 있는 최대 호출 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="378a6-174">기본값은 50이지만 0~200 범위일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="378a6-175">이 제한에 도달하면 최대 호출 수에 도달한 경우 설정에 따라 호출이 **처리됩니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="378a6-176">통화 연결을 끊거나 통화 라우팅 대상 중 하나에 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="378a6-177">예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="378a6-178">외부 전송의 경우 번호 [](plan-auto-attendant-call-queue.md#prerequisites) 서식에 대한 기술 [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 세부 정보인 전제 사항 및 외부 전화 번호 전송을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="378a6-179">최대 호출 수를 0으로 설정하면 인사말 메시지가 재생되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="378a6-180">호출 시간 제한 처리</span><span class="sxs-lookup"><span data-stu-id="378a6-180">Call timeout handling</span></span>

![통화 시간 제한 설정 스크린샷](media/call-queue-timeout-handling.png)

<span data-ttu-id="378a6-182">**호출 시간 제한: 최대** 대기 시간은 리디렉션되거나 연결이 끊기기 전에 큐에 통화가 대기할 수 있는 최대 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="378a6-183">0초에서 45분까지 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="378a6-184">통화 연결을 끊거나 통화 라우팅 대상 중 하나에 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="378a6-185">예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="378a6-186">외부 전송의 경우 번호 [](plan-auto-attendant-call-queue.md#prerequisites) 서식에 대한 기술 [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 세부 정보인 전제 사항 및 외부 전화 번호 전송을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="378a6-187">통화 시간 제한 옵션을 선택한 경우 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="378a6-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="378a6-188">아웃바운드 호출에 대한 호출자 ID</span><span class="sxs-lookup"><span data-stu-id="378a6-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="378a6-189">호출 큐의 에이전트가 고객 호출을 반환하기 위해 전화를 걸 수 있는 경우 통화 큐의 구성원에 대한 발신자 ID를 적절한 자동 전화 연결의 서비스 번호로 설정하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="378a6-190">자세한 [내용은 Microsoft Teams에서 발신자 ID](caller-id-policies.md) 정책 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="378a6-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="378a6-191">지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="378a6-191">Supported clients</span></span>

<span data-ttu-id="378a6-192">다음 클라이언트는 호출 큐의 호출 에이전트에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="378a6-193">비즈니스용 Skype 데스크톱 클라이언트 2016(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="378a6-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="378a6-194">Lync 데스크톱 클라이언트 2013(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="378a6-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="378a6-195">Microsoft Teams에서 지원되는 모든 IP 전화 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="378a6-196">비즈니스용 [Skype Online용 전화기 보기를 참조하세요.](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="378a6-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="378a6-197">Mac 비즈니스용 Skype 클라이언트(버전 16.8.196 이상)</span><span class="sxs-lookup"><span data-stu-id="378a6-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="378a6-198">Android 비즈니스용 Skype 클라이언트(버전 6.16.0.9 이상)</span><span class="sxs-lookup"><span data-stu-id="378a6-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="378a6-199">iPhone 비즈니스용 Skype 클라이언트(버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="378a6-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="378a6-200">iPad 비즈니스용 Skype 클라이언트(버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="378a6-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="378a6-201">Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="378a6-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="378a6-202">Microsoft Teams Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="378a6-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="378a6-203">Microsoft Teams iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="378a6-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="378a6-204">Microsoft Teams Android 앱</span><span class="sxs-lookup"><span data-stu-id="378a6-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="378a6-205">직접 라우팅 번호가 할당된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 전화기에서 에이전트로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="378a6-206">큐 cmdlet 호출</span><span class="sxs-lookup"><span data-stu-id="378a6-206">Call queue cmdlets</span></span>

<span data-ttu-id="378a6-207">또한 이 기능을 사용하여 Windows PowerShell 큐를 만들고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="378a6-208">다음은 호출 큐를 관리하는 데 사용하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="378a6-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="378a6-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="378a6-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="378a6-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="378a6-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="378a6-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="378a6-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="378a6-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="378a6-213">관련 항목</span><span class="sxs-lookup"><span data-stu-id="378a6-213">Related topics</span></span>

[<span data-ttu-id="378a6-214">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="378a6-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="378a6-215">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="378a6-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="378a6-216">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="378a6-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="378a6-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="378a6-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="378a6-218">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="378a6-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
