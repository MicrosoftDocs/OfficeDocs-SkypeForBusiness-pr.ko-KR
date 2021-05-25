---
title: 전화 통화 큐 만들기 Microsoft Teams - 중소기업 자습서
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
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
description: 소규모 기업에 대한 통화 큐를 설정하는 방법을 Microsoft 365 Business Voice.
ms.openlocfilehash: 755c4914271c96cdd668bb2933872ebf1fa21b94
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629057"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="c0ee6-103">통화 큐 만들기 - 중소기업 자습서</span><span class="sxs-lookup"><span data-stu-id="c0ee6-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="c0ee6-104">통화 큐는 특정 문제나 질문에 대한 도움을 줄 수 있는 조직의 사용자에게 통화를 걸 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="c0ee6-105">호출은 큐의 사용자(*에이전트* 라고 함)에게 한 번에 하나씩 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="c0ee6-106">통화 큐는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-106">Call queues provide:</span></span>

- <span data-ttu-id="c0ee6-107">인사말 메시지</span><span class="sxs-lookup"><span data-stu-id="c0ee6-107">A greeting message.</span></span>

- <span data-ttu-id="c0ee6-108">큐에서 대기 중인 음악</span><span class="sxs-lookup"><span data-stu-id="c0ee6-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="c0ee6-109">에이전트에 대한 *FIFO(선입선출)* 순서 통화 라우팅.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="c0ee6-110">큐 오버플로 및 시간 제한에 대한 처리 옵션</span><span class="sxs-lookup"><span data-stu-id="c0ee6-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="c0ee6-111">비디오 데모</span><span class="sxs-lookup"><span data-stu-id="c0ee6-111">Video demonstration</span></span>

<span data-ttu-id="c0ee6-112">이 비디오에서는 호출 큐를 만드는 방법을 Teams.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="c0ee6-113">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c0ee6-113">Before you begin</span></span>

<span data-ttu-id="c0ee6-114">일부 전화 시스템 [- 가상](../teams-add-on-licensing/virtual-user.md) 사용자 라이선스가 없는 경우 가상 사용자 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="c0ee6-115">설정할 각 호출 큐 및 자동 참석자에 대해 하나를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="c0ee6-116">이러한 라이선스는 무료이기 때문에 향후 설정을 변경하기로 결정한 경우 몇 가지 추가를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="c0ee6-117">통화 큐의 에이전트가 전화 접속하여 고객 통화를 반환할 수 있습니다. 통화 에이전트의 발신자 ID를 주 전화 번호 또는 적절한 자동 참석자 수로 설정하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="c0ee6-118">자세한 내용은 [Microsoft Teams에서 발신자 ID 정책 관리](../caller-id-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="c0ee6-119">다음 단계에 따라 통화 큐를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="c0ee6-120">1단계 <br> 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="c0ee6-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="c0ee6-121">호출 큐를 만들 때 큐에 개별 사용자를 추가할 수 있습니다. 또는 기존 보안 그룹, Microsoft 365 그룹 또는 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="c0ee6-122">팀 채널을 [사용하는 것이 좋습니다.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="c0ee6-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="c0ee6-123">이렇게 하면 큐의 구성원이 서로 채팅하고, 아이디어를 공유하고, 문서 또는 기타 리소스를 만들어 고객에게 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="c0ee6-124">또한 팀은 발신자들이 몇 시간 후에 메시지를 남기거나 큐가 최대 용량에 도달하는 경우 음성 사서함을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="c0ee6-125">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="c0ee6-125">To create a team</span></span>

1. <span data-ttu-id="c0ee6-126">먼저 앱 **Teams** 왼쪽에 있는 앱을 클릭한  다음 참가를 클릭하거나 팀 목록 아래쪽에 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="c0ee6-127">그런 다음 **팀 만들기(첫** 번째 카드, 왼쪽 위 모서리)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="c0ee6-128">처음부터 **팀 빌드를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="c0ee6-129">다음으로 공용 팀 또는 개인 팀을 원하는지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="c0ee6-130">팀에  가입하여 사람들이 의도치 않은 큐에 참여하지 않도록 통화 큐에 개인을 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="c0ee6-131">팀 이름을 지정하고 선택적 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="c0ee6-132">완료되면 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="c0ee6-133">통화 큐에 하려는 사용자 이름을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="c0ee6-134">닫기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-134">Click **Close**.</span></span> <span data-ttu-id="c0ee6-135">팀에 추가한 사람들은 이제 팀 구성원이 됐고 팀이 팀 목록에 표시됩니다는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="c0ee6-136">다음으로 통화 큐에 사용할 채널을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="c0ee6-137">채널을 추가하는 경우</span><span class="sxs-lookup"><span data-stu-id="c0ee6-137">To add a channel</span></span>

1. <span data-ttu-id="c0ee6-138">이 Teams 방금 만든 팀을 찾고  추가 옵션(...)을 클릭한 다음 채널 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="c0ee6-139">채널의 이름 및 설명을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c0ee6-140">2단계 - 리소스 계정 ></span><span class="sxs-lookup"><span data-stu-id="c0ee6-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="c0ee6-141">2단계 <br> 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="c0ee6-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="c0ee6-142">만드는 각 호출 큐에는 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="c0ee6-143">이는 계정이 사용자 대신 자동 참석자 또는 통화 큐와 연결되어 있는 것을 제외하고 사용자 계정과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="c0ee6-144">이 단계에서는 계정을 만들고, 가상 사용자 *Microsoft 365 전화 시스템* 할당한 다음, 이 라이선스를 사용하여 호출 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="c0ee6-145">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="c0ee6-145">Create a resource account</span></span>

<span data-ttu-id="c0ee6-146">관리 센터에서 리소스 계정을 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="c0ee6-147">Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 리소스 계정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="c0ee6-148">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-148">Click **Add**.</span></span>

3. <span data-ttu-id="c0ee6-149">리소스 계정 **추가** 창에서 표시 **이름,** **사용자** 이름 및 를 입력하고 리소스 계정 유형에 **대한** 호출 **큐를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="c0ee6-150">에이전트는 큐에서 들어오는 호출을 수신할 때 표시 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add-cq.png)

4. <span data-ttu-id="c0ee6-152">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-152">Click **Save**.</span></span>

   <span data-ttu-id="c0ee6-153">새 계정이 계정 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-153">The new account will appear in the list of accounts.</span></span>

   ![리소스 계정 목록 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="c0ee6-155">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c0ee6-155">Assign a license</span></span>

<span data-ttu-id="c0ee6-156">리소스 계정에 Microsoft 365 전화 시스템 *가상* 사용자 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="c0ee6-157">관리 Microsoft 365 관리 센터의 **활성** 사용자 목록에서 라이선스를 할당할 리소스 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="c0ee6-158">라이선스 **및** 앱 탭의 라이선스에서 가상 **Microsoft 365 전화 시스템 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="c0ee6-159">변경 **내용 저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-159">Click **Save changes**.</span></span>

    ![관리 센터에서 라이선스 사용자 인터페이스 할당 Microsoft 365 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="c0ee6-161">통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="c0ee6-161">Create a call queue</span></span>

<span data-ttu-id="c0ee6-162">다음으로 새 호출 큐를 만들고 리소스 계정을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="c0ee6-163">Teams 관리 센터에서 **음성을** 확장하고 큐 **호출을** 클릭한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="c0ee6-164">통화 큐의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="c0ee6-165">**계정 추가** 를 클릭하고 이 통화 큐에 사용할 리소스 계정을 검색하고 **추가** 를 클릭하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="c0ee6-166">언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-166">Choose a language.</span></span> <span data-ttu-id="c0ee6-167">이 언어는 시스템에서 생성된 음성 프롬프트 및 음성 메시지(사용하도록 설정한 경우)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-167">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![리소스 계정 및 언어 설정 스크린샷](../media/call-queue-name-language.png)

4. <span data-ttu-id="c0ee6-169">발신자가 큐에 도착하면 발신자들에게 인사말을 재생할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-169">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="c0ee6-170">재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-170">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="c0ee6-171">Teams에서 사용자가 큐에 있는 동안 발신자에게 기본 음악이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-171">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="c0ee6-172">특정 오디오 파일을 재생하려면 **오디오 파일 재생** 을 선택하고 MP3 WAV 또는 WMA 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-172">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0ee6-173">업로드된 녹음/녹화의 크기는 5MB 이상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-173">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="c0ee6-174">Teams 통화 큐에서 제공하는 기본 음악은 조직에서 지불해야 하는 로열티가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-174">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="c0ee6-175">3단계 - 에이전트 호출 ></span><span class="sxs-lookup"><span data-stu-id="c0ee6-175">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="c0ee6-176">3단계 <br> 에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="c0ee6-176">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="c0ee6-177">에이전트를 호출 큐에 추가하기 위해 앞에서 만든 팀 및 채널에 에이전트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-177">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="c0ee6-178">팀 선택 **옵션을 선택하고** 채널 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-178">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="c0ee6-179">만든 팀의 이름을 입력하고, 선택한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-179">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="c0ee6-180">큐에 대해 만든 채널을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-180">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="c0ee6-181">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-181">Click **Apply**.</span></span>

    ![통화 큐에 대한 사용자 및 그룹 설정의 스크린샷](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="c0ee6-183">새 사용자가 팀에 추가될 때 첫 번째 통화가 도착하는 데 최대 8시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-183">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c0ee6-184">4단계 - 리소스 계정 ></span><span class="sxs-lookup"><span data-stu-id="c0ee6-184">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="c0ee6-185">4단계 <br> 라우팅 호출</span><span class="sxs-lookup"><span data-stu-id="c0ee6-185">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="c0ee6-186">사용할 호출 라우팅 메서드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-186">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="c0ee6-187">회의 **모드를 자동으로** **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-187">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="c0ee6-188">사용할 **라우팅** 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-188">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="c0ee6-189">그러면 에이전트가 큐에서 호출을 받는 순서가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-189">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="c0ee6-190">직렬  라우팅 또는 **라운드 로빈을 추천합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-190">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="c0ee6-191">다음 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-191">Choose from these options:</span></span>

    - <span data-ttu-id="c0ee6-192">**참석자 라우팅** 은 큐에 있는 모든 에이전트를 동시에 링합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-192">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="c0ee6-193">통화를 받은 첫 번째 통화 에이전트가 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-193">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="c0ee6-194">**직렬 라우팅은** 모든 호출 에이전트를 하나씩 링합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-194">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="c0ee6-195">에이전트가 통화를 취소하거나 통화를 받지 않으면 다음 에이전트가 호출을 울리고 선택되거나 시간이 초과될 때까지 모든 에이전트를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-195">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="c0ee6-196">**라운드 로빈** 은 각 호출 에이전트가 큐에서 동일한 수의 호출을 수신하도록 수신 호출 라우팅의 균형을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-196">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c0ee6-197">이는 모든 상담원 간에 동등한 기회를 보장하기 위해 인바운드 영업 환경에서 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-197">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="c0ee6-198">**가장 긴 유휴 상태** 는 각 통화를 가장 오랫동안 유휴 상태인 에이전트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-198">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="c0ee6-199">(현재 상태 상태가 10분 이상 멀어진 에이전트는 포함되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="c0ee6-199">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![회의 모드 및 라우팅 방법 설정 스크린샷](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="c0ee6-201">현재 **상태 기반 라우팅을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-201">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="c0ee6-202">이 경로는 현재 상태를 사용할 수 있는 에이전트에 **호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-202">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="c0ee6-203">에이전트가 통화를 옵트아웃할 수 있도록 허용할지 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-203">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="c0ee6-204">에이전트 **경고** 시간을 설정하여 큐에서 호출을 다음 에이전트로 리디렉션하기 전에 에이전트의 전화가 울리는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-204">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![라우팅, 옵트아웃 및 알림 시간 설정 스크린샷](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="c0ee6-206">5단계 - 오버플로 ></span><span class="sxs-lookup"><span data-stu-id="c0ee6-206">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="c0ee6-207">5단계 <br> 오버플로 호출</span><span class="sxs-lookup"><span data-stu-id="c0ee6-207">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="c0ee6-208">큐의 최대값을 초과하는 호출을 처리하는 방법을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-208">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="c0ee6-209">큐에서 **최대 호출을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-209">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="c0ee6-210">최대 호출 수에 도달하면 할 작업을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-210">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="c0ee6-211">통화 연결을 끊거나 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-211">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="c0ee6-212">호출을 다음 대상 중 하나로 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-212">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="c0ee6-213">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="c0ee6-213">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="c0ee6-214">**음성 앱** - 자동 참석자 또는 다른 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-214">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="c0ee6-215">(이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="c0ee6-215">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="c0ee6-216">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-216">**External phone number** - any phone number.</span></span> <span data-ttu-id="c0ee6-217">이 형식 사용: +[국가 코드][지역 코드][전화 번호]</span><span class="sxs-lookup"><span data-stu-id="c0ee6-217">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="c0ee6-218">**음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-218">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![통화 오버플로 설정 스크린샷](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="c0ee6-220">6단계 - 통화 시간 제한 ></span><span class="sxs-lookup"><span data-stu-id="c0ee6-220">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="c0ee6-221">6단계 <br> 통화 시간 제한</span><span class="sxs-lookup"><span data-stu-id="c0ee6-221">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="c0ee6-222">큐에서 호출이 너무 오래 대기 중일 때 어떤 일이 일어날지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-222">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="c0ee6-223">최대 **대기 시간 을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ee6-223">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="c0ee6-224">통화 시간 외의 경우 할 작업을 선택해야 합니다. 통화 연결을 끊거나 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-224">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="c0ee6-225">호출을 다음 대상 중 하나로 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-225">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="c0ee6-226">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="c0ee6-226">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="c0ee6-227">**음성 앱** - 자동 참석자 또는 다른 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-227">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="c0ee6-228">(이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="c0ee6-228">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="c0ee6-229">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-229">**External phone number** - any phone number.</span></span> <span data-ttu-id="c0ee6-230">이 형식 사용: +[국가 코드][지역 코드][전화 번호]</span><span class="sxs-lookup"><span data-stu-id="c0ee6-230">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="c0ee6-231">**음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-231">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![통화 오버플로 설정 스크린샷](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="c0ee6-233">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-233">Click **Save**.</span></span>

<span data-ttu-id="c0ee6-234">그러면 호출 큐의 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ee6-234">This completes the setup of your call queue.</span></span> <span data-ttu-id="c0ee6-235">다음으로 자동 참석자 [를 설정할 수 있습니다.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="c0ee6-235">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

