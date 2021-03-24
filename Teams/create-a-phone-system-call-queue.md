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
description: 인사말 메시지를 제공하고, 음악 중지, 통화 리디렉션 및 기타 기능을 제공하는 Microsoft Teams에서 통화 큐에 통화 시스템을 설정하는 방법을 알아보세요.
ms.openlocfilehash: 9bb33e5590df1af6b70dffecba64eb313838b228
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092716"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="8408e-103">통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="8408e-103">Create a call queue</span></span>

<span data-ttu-id="8408e-104">통화 큐는 특정 문제나 질문에 대한 도움을 줄 수 있는 조직의 사용자에게 통화를 걸 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="8408e-105">호출은 큐의 사용자(*에이전트* 라고 함)에게 한 번에 하나씩 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="8408e-106">통화 큐는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-106">Call queues provide:</span></span>

- <span data-ttu-id="8408e-107">인사말 메시지</span><span class="sxs-lookup"><span data-stu-id="8408e-107">A greeting message.</span></span>

- <span data-ttu-id="8408e-108">큐에서 대기 중인 음악</span><span class="sxs-lookup"><span data-stu-id="8408e-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="8408e-109">에이전트에 대한 *FIFO(선입선출)* 순서 통화 라우팅.</span><span class="sxs-lookup"><span data-stu-id="8408e-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="8408e-110">큐 오버플로 및 시간 제한에 대한 처리 옵션</span><span class="sxs-lookup"><span data-stu-id="8408e-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="8408e-111">이 문서의 절차를 수행하기 전에 [Teams 자동 수행 및 통화 대기에 대한 계획](plan-auto-attendant-call-queue.md)을 읽고 [시작 단계](plan-auto-attendant-call-queue.md#getting-started)를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="8408e-112">통화 큐를 설정하려면 Teams 관리 센터에서 **음성** 확장하고 **통화 큐** 클릭한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="8408e-113">리소스 계정 및 언어</span><span class="sxs-lookup"><span data-stu-id="8408e-113">Resource account and language</span></span>

![리소스 계정 및 언어 설정 스크린샷](media/call-queue-name-language.png)

1. <span data-ttu-id="8408e-115">통화 큐의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="8408e-116">**계정 추가** 를 클릭하고 이 통화 큐에 사용할 리소스 계정을 검색하고 **추가** 를 클릭하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="8408e-117">(에이전트가 들어오는 호출을 받을 때 리소스 계정 이름이 표시됩니다.)</span><span class="sxs-lookup"><span data-stu-id="8408e-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="8408e-118">지원되는 [언어를 선택 합니다.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="8408e-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="8408e-119">이 언어는 시스템에서 생성된 음성 프롬프트 및 음성 메시지(사용하도록 설정한 경우)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="8408e-120">대기 중인 인사말 및 음악</span><span class="sxs-lookup"><span data-stu-id="8408e-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="8408e-121">발신자가 큐에 도착하면 발신자들에게 인사말을 재생할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="8408e-122">재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="8408e-123">Teams에서 사용자가 큐에 있는 동안 발신자에게 기본 음악이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="8408e-124">특정 오디오 파일을 재생하려면 **오디오 파일 재생** 을 선택하고 MP3 WAV 또는 WMA 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="8408e-125">업로드된 녹음/녹화의 크기는 5MB 이상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="8408e-126">Teams 통화 큐에서 제공하는 기본 음악은 조직에서 지불해야 하는 로열티가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="8408e-127">통화 에이전트</span><span class="sxs-lookup"><span data-stu-id="8408e-127">Call agents</span></span>

<span data-ttu-id="8408e-128">통화 큐에 에이전트를 추가하려면 [사전 요구 사항](plan-auto-attendant-call-queue.md#prerequisites)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8408e-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![통화 큐에 대한 사용자 및 그룹 설정의 스크린샷](media/call-queue-users-groups.png)

<span data-ttu-id="8408e-130">그룹을 통해 최대 20대의 에이전트를 개별적으로, 최대 200명까지 에이전트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="8408e-131">큐에 사용자를 추가하려면 **사용자 추가** 를 클릭하고 사용자를 검색한 다음 **추가** 를 클릭하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="8408e-132">큐에 그룹을 추가하려면 **그룹 추가** 를 클릭하고 그룹을 검색한 다음 **추가** 를 클릭하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="8408e-133">메일 그룹, 보안 그룹, Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="8408e-134">그룹에 추가된 새 사용자는 첫 번째 통화가 도착하는 데 최대 8시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="8408e-135">통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="8408e-135">Call routing</span></span>

![회의 모드 및 라우팅 방법 설정 스크린샷](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="8408e-137">**회의 모드** 를 사용하면 에이전트가 호출을 수락한 후 호출자가 에이전트에 연결되는 데 걸리는 시간이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="8408e-138">회의 모드가 작동하려면 통화 큐의 에이전트가 다음 클라이언트 중 하나를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="8408e-139">최신 버전의 Microsoft Teams 데스크톱 클라이언트, Android 앱 또는 iOS 앱</span><span class="sxs-lookup"><span data-stu-id="8408e-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="8408e-140">Microsoft Teams 통화 버전 1449/1.0.94.2020051601 이상</span><span class="sxs-lookup"><span data-stu-id="8408e-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="8408e-141">에이전트의 Teams 계정은 Teams 전용 모드로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="8408e-142">요구 사항을 충족하지 않는 에이전트는 통화 라우팅 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="8408e-143">에이전트가 모두 호환되는 클라이언트를 사용하고 있는 경우 통화 큐에 통화 회의 모드를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="8408e-144">**라우팅 방법** 은 에이전트가 큐에서 통화를 받는 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="8408e-145">다음 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-145">Choose from these options:</span></span>

- <span data-ttu-id="8408e-146">**참석자 라우팅** 은 큐에 있는 모든 에이전트를 동시에 링합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="8408e-147">통화를 받은 첫 번째 통화 에이전트가 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="8408e-148">**직렬 라우팅** 은 모든 **콜 에이전트** 를 콜 에이전트 목록에 지정된 순서대로 하나씩 울립니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="8408e-149">에이전트가 통화를 취소하거나 통화를 받지 않으면 다음 에이전트가 호출을 울리고 선택되거나 시간이 초과될 때까지 모든 에이전트를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="8408e-150">**라운드 로빈** 은 각 호출 에이전트가 큐에서 동일한 수의 호출을 수신하도록 수신 호출 라우팅의 균형을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="8408e-151">이는 모든 상담원 간에 동등한 기회를 보장하기 위해 인바운드 영업 환경에서 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="8408e-152">**가장 긴 유휴 상태** 는 각 통화를 가장 오랫동안 유휴 상태인 에이전트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="8408e-153">에이전트는 현재 상태 사용 가능 상태 또는 현재 상태가 10분 미만인 경우 유휴 상태로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="8408e-154">부재중 상태가 10분 이상 부재중인 에이전트는 유휴 상태로 간주되지 않으며 부재중 상태를 사용 가능으로 변경할 때까지 호출을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![라우팅, 옵트아웃 및 알림 시간 설정 스크린샷](media/call-queue-presence-agents-time.png)


<span data-ttu-id="8408e-156">**현재 상태 기반 라우팅** 은 통화 에이전트의 가용성 상태를 사용하여 선택한 라우팅 방법에 대한 통화 라우팅 목록에 에이전트를 포함할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="8408e-157">가용성 상태가 **사용 가능** 으로 설정된 통화 에이전트는 통화 라우팅 목록에 포함되며 호출을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="8408e-158">가용성 상태가 다른 상태로 설정된 에이전트는 통화 라우팅 목록에서 제외되며, 가용성 상태가 다시 **사용 가능** 으로 변경될 때까지 호출을 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="8408e-159">라우팅 방법을 사용하여 현재 상태 기반 통화 라우팅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="8408e-160">에이전트가 통화를 옵트아웃하면 해당 에이전트가 수신 가능 여부가 설정된 상태와 관계없이 통화 라우팅 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="8408e-161">현재 상태 기반 라우팅이 사용하도록 설정된 경우 비즈니스용 Skype 클라이언트를 사용하는 에이전트가 통화 라우팅 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="8408e-162">비즈니스용 Skype를 사용하는 에이전트가 있는 경우 현재 상태 기반 통화 라우팅을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="8408e-163">**에이전트 알림 시간** 은 큐가 다음 에이전트로 통화를 리디렉션하기 전에 에이전트의 통화가 울리는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="8408e-164">다음 설정은 권장되는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-164">The following settings are recommended:</span></span>

- <span data-ttu-id="8408e-165">**회의 모드** 는 **자동** 으로</span><span class="sxs-lookup"><span data-stu-id="8408e-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="8408e-166">**라우팅 방법** 은 **라운드 로빈** 또는 **최대 유휴 상태** 로</span><span class="sxs-lookup"><span data-stu-id="8408e-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="8408e-167">**현재 상태 기반 라우팅** 은 **켬** 으로</span><span class="sxs-lookup"><span data-stu-id="8408e-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="8408e-168">**에이전트 경고 시간** 은 **20초로**</span><span class="sxs-lookup"><span data-stu-id="8408e-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="8408e-169">현재 상태 기반 라우팅이 사용하도록 설정되어 있지 않은 경우 큐에 여러 통화가 있는 경우 시스템에서 현재 상태와 상관없이 이러한 통화를 에이전트에게 동시에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="8408e-170">이렇게 하면 에이전트에게 여러 통화 알림이 전송됩니다. 특히 일부 에이전트가 최초 통화에 응답하지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="8408e-171">통화 오버플로 처리</span><span class="sxs-lookup"><span data-stu-id="8408e-171">Call overflow handling</span></span>

![통화 오버플로 설정 스크린샷](media/call-queue-overflow-handling.png)

<span data-ttu-id="8408e-173">**큐 최대 호출 수** 는 지정된 시간에 큐에 대기할 수 있는 최대 통화 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="8408e-174">기본값은 50이지만 0에서 200까지의 범위일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="8408e-175">이 제한에 도달하면 **최대 통화 수에 도달할 때** 설정에 지정된 대로 통화가 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="8408e-176">통화 연결을 끊거나 통화 라우팅 대상로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="8408e-177">예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="8408e-178">외부 전송의 경우 [필수 구성 요소](plan-auto-attendant-call-queue.md#prerequisites)와 번호 서식에 대한 [외부 전화 번호 전송 - 기술 세부 정보](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8408e-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="8408e-179">최대 통화 수가 0으로 설정된 경우 인사말 메시지는 재생되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="8408e-180">통화 시간 제한 처리</span><span class="sxs-lookup"><span data-stu-id="8408e-180">Call timeout handling</span></span>

![통화 오버플로 설정 스크린샷](media/call-queue-timeout-handling.png)

<span data-ttu-id="8408e-182">**통화 시간 초과: 최대 대기 시간** 은 통화가 리디렉션되거나 연결이 끊어지기 전에 큐에 대기할 수 있는 최대 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="8408e-183">0초에서 45분까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="8408e-184">통화 연결을 끊거나 통화 라우팅 대상로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="8408e-185">예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="8408e-186">외부 전송의 경우 [필수 구성 요소](plan-auto-attendant-call-queue.md#prerequisites)와 번호 서식에 대한 [외부 전화 번호 전송 - 기술 세부 정보](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8408e-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="8408e-187">통화 시간 제한 옵션을 선택한 경우 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="8408e-188">아웃바운드 통화의 발신자 ID</span><span class="sxs-lookup"><span data-stu-id="8408e-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="8408e-189">통화 큐에 있는 에이전트가 통화를 걸어 고객 통화를 반환할 수 있으므로, 통화 큐에 있는 구성원의 발신자 ID를 적절한 자동차 에이전트의 서비스 번호로 설정하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="8408e-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="8408e-190">자세한 내용은 [Microsoft Teams에서 발신자 ID 정책 관리](caller-id-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8408e-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="8408e-191">지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8408e-191">Supported clients</span></span>

<span data-ttu-id="8408e-192">다음 클라이언트는 통화 큐의 통화 에이전트에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="8408e-193">비즈니스용 Skype 데스크톱 클라이언트 2016(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="8408e-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8408e-194">Lync 데스크톱 클라이언트 2013(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="8408e-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8408e-195">모든 IP 통화 모델은 Microsoft Teams에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="8408e-196">[비즈니스용 Skype Online 휴대폰 받기](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8408e-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="8408e-197">Mac용 비즈니스용 Skype(버전 16.8.196 이상)</span><span class="sxs-lookup"><span data-stu-id="8408e-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="8408e-198">Android 비즈니스용 Skype® 클라이언트(버전 6.16.0.9 이상)</span><span class="sxs-lookup"><span data-stu-id="8408e-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="8408e-199">iPhone용 비즈니스용 Skype® 클라이언트(버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="8408e-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="8408e-200">iPad용 비즈니스용 Skype® 클라이언트(버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="8408e-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="8408e-201">Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="8408e-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8408e-202">Microsoft Teams Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8408e-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="8408e-203">Microsoft Teams iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="8408e-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="8408e-204">Microsoft Teams Android 앱</span><span class="sxs-lookup"><span data-stu-id="8408e-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="8408e-205">직접 라우팅 번호가 할당된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 통화가 에이전트로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="8408e-206">통화 큐 cmdlets</span><span class="sxs-lookup"><span data-stu-id="8408e-206">Call queue cmdlets</span></span>

<span data-ttu-id="8408e-207">Windows PowerShell을 사용하여 통화 큐를 만들고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="8408e-208">다음은 통화 큐를 관리하는 데 사용하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="8408e-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8408e-209">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="8408e-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8408e-210">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="8408e-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8408e-211">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="8408e-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8408e-212">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="8408e-213">관련 주제</span><span class="sxs-lookup"><span data-stu-id="8408e-213">Related topics</span></span>

[<span data-ttu-id="8408e-214">다음은 통화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8408e-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="8408e-215">서비스 통화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="8408e-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="8408e-216">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="8408e-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="8408e-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="8408e-217">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="8408e-218">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="8408e-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)