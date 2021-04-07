---
title: Microsoft Teams에서 호출 큐 만들기 - 중소기업 자습서
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
description: Microsoft 365 Business Voice를 사용하여 통화 큐를 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 40018ce331dfe8516e00c6781373d528a71e85c5
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607560"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="d3fc5-103">통화 큐 만들기 - 중소기업 자습서</span><span class="sxs-lookup"><span data-stu-id="d3fc5-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="d3fc5-104">호출 큐는 특정 문제 또는 질문에 도움을 줄 수 있는 조직 내 사용자에게 호출자 라우팅 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="d3fc5-105">호출은 큐의 사용자(*에이전트* 라고 함)에게 한 번에 하나씩 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="d3fc5-106">통화 큐는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-106">Call queues provide:</span></span>

- <span data-ttu-id="d3fc5-107">인사말 메시지</span><span class="sxs-lookup"><span data-stu-id="d3fc5-107">A greeting message.</span></span>

- <span data-ttu-id="d3fc5-108">큐에서 대기 중인 음악</span><span class="sxs-lookup"><span data-stu-id="d3fc5-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="d3fc5-109">에이전트에 대한 *FIFO(선입선출)* 순서 통화 라우팅.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="d3fc5-110">큐 오버플로 및 시간 제한에 대한 처리 옵션</span><span class="sxs-lookup"><span data-stu-id="d3fc5-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="d3fc5-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="d3fc5-111">Before you begin</span></span>

<span data-ttu-id="d3fc5-112">일부 [전화 시스템 - 아직](../teams-add-on-licensing/virtual-user.md) 없는 경우 가상 사용자 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="d3fc5-113">설정할 각 호출 큐 및 자동 참석자에 대해 하나를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="d3fc5-114">이러한 라이선스는 무료이기 때문에 향후 설정을 변경하기로 결정한 경우 몇 가지 추가를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="d3fc5-115">통화 큐의 에이전트가 전화 접속하여 고객 통화를 반환할 수 있습니다. 통화 에이전트의 발신자 ID를 주 전화 번호 또는 적절한 자동 참석자 수로 설정하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="d3fc5-116">자세한 내용은 [Microsoft Teams에서 발신자 ID 정책 관리](../caller-id-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="d3fc5-117">다음 단계에 따라 통화 큐를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="d3fc5-118">1단계 <br> 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="d3fc5-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="d3fc5-119">호출 큐를 만들 때 큐에 개별 사용자를 추가하거나 기존 보안 그룹, Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="d3fc5-120">팀 채널을 [사용하는 것이 좋습니다.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="d3fc5-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="d3fc5-121">이렇게 하면 큐의 구성원이 서로 채팅하고, 아이디어를 공유하고, 문서 또는 기타 리소스를 만들어 고객에게 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="d3fc5-122">또한 팀은 발신자들이 몇 시간 후에 메시지를 남기거나 큐가 최대 용량에 도달하는 경우 음성 사서함을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="d3fc5-123">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="d3fc5-123">To create a team</span></span>

1. <span data-ttu-id="d3fc5-124">먼저 앱의 왼쪽에서 **Teams를** 클릭한  다음 참가를 클릭하거나 팀 목록 맨 아래에 있는 팀 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="d3fc5-125">그런 다음 **팀 만들기(첫** 번째 카드, 왼쪽 위 모서리)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="d3fc5-126">처음부터 **팀 빌드를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="d3fc5-127">다음으로 공용 팀 또는 개인 팀을 원하는지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="d3fc5-128">팀에  가입하여 사람들이 의도치 않은 큐에 참여하지 않도록 통화 큐에 개인을 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="d3fc5-129">팀 이름을 지정하고 선택적 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="d3fc5-130">완료되면 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="d3fc5-131">통화 큐에 하려는 사용자 이름을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="d3fc5-132">닫기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-132">Click **Close**.</span></span> <span data-ttu-id="d3fc5-133">팀에 추가한 사람들은 이제 팀 구성원이 됐고 팀이 팀 목록에 표시됩니다는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="d3fc5-134">다음으로 통화 큐에 사용할 채널을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="d3fc5-135">채널을 추가하는 경우</span><span class="sxs-lookup"><span data-stu-id="d3fc5-135">To add a channel</span></span>

1. <span data-ttu-id="d3fc5-136">Teams에서 방금 만든 팀을  찾고 추가 옵션(...)을 클릭한 다음 채널 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="d3fc5-137">채널의 이름 및 설명을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3fc5-138">2단계 - 리소스 계정 ></span><span class="sxs-lookup"><span data-stu-id="d3fc5-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="d3fc5-139">2단계 <br> 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="d3fc5-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="d3fc5-140">만드는 각 호출 큐에는 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="d3fc5-141">이는 계정이 사용자 대신 자동 참석자 또는 통화 큐와 연결되어 있는 것을 제외하고 사용자 계정과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="d3fc5-142">이 단계에서는 계정을 만들고 *Microsoft 365 Phone System - Virtual User* 라이선스를 할당한 다음, 이 라이선스를 사용하여 통화 큐 만들기를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="d3fc5-143">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="d3fc5-143">Create a resource account</span></span>

<span data-ttu-id="d3fc5-144">Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="d3fc5-145">Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 **리소스 계정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="d3fc5-146">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-146">Click **Add**.</span></span>

3. <span data-ttu-id="d3fc5-147">리소스 계정 **추가** 창에서 표시 **이름,** **사용자** 이름 및 를 입력하고 리소스 계정 유형에 **대한** 호출 **큐를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="d3fc5-148">에이전트는 큐에서 들어오는 호출을 수신할 때 표시 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-148">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add-cq.png)

4. <span data-ttu-id="d3fc5-150">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-150">Click **Save**.</span></span>

<span data-ttu-id="d3fc5-151">새 계정이 계정 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-151">The new account will appear in the list of accounts.</span></span>

![리소스 계정 목록 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="d3fc5-153">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="d3fc5-153">Assign a license</span></span>

<span data-ttu-id="d3fc5-154">*Microsoft 365 Phone System - 가상 사용자* 라이선스를 리소스 계정에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-154">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="d3fc5-155">Microsoft 365 관리 센터의 **활성** 사용자 목록에서 라이선스를 할당할 리소스 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-155">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="d3fc5-156">라이선스 **및** 앱 탭의 라이선스 **아래에서** **Microsoft 365 Phone System - Virtual User 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-156">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="d3fc5-157">변경 **내용 저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-157">Click **Save changes**.</span></span>

    ![Microsoft 365 관리 센터에서 라이선스 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="d3fc5-159">통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="d3fc5-159">Create a call queue</span></span>

<span data-ttu-id="d3fc5-160">다음으로 새 호출 큐를 만들고 리소스 계정을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-160">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="d3fc5-161">Teams 관리 센터에서 **음성을** 확장하고 큐 호출을 **클릭한** 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-161">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="d3fc5-162">통화 큐의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-162">Type a name for the call queue.</span></span>

2. <span data-ttu-id="d3fc5-163">**계정 추가** 를 클릭하고 이 통화 큐에 사용할 리소스 계정을 검색하고 **추가** 를 클릭하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="d3fc5-164">언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-164">Choose a language.</span></span> <span data-ttu-id="d3fc5-165">이 언어는 시스템에서 생성된 음성 프롬프트 및 음성 메시지(사용하도록 설정한 경우)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![리소스 계정 및 언어 설정 스크린샷](../media/call-queue-name-language.png)

4. <span data-ttu-id="d3fc5-167">발신자가 큐에 도착하면 발신자들에게 인사말을 재생할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="d3fc5-168">재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="d3fc5-169">Teams에서 사용자가 큐에 있는 동안 발신자에게 기본 음악이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="d3fc5-170">특정 오디오 파일을 재생하려면 **오디오 파일 재생** 을 선택하고 MP3 WAV 또는 WMA 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="d3fc5-171">업로드된 녹음/녹화의 크기는 5MB 이상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-171">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="d3fc5-172">Teams 통화 큐에서 제공하는 기본 음악은 조직에서 지불해야 하는 로열티가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3fc5-173">3단계 - 에이전트 호출 ></span><span class="sxs-lookup"><span data-stu-id="d3fc5-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="d3fc5-174">3단계 <br> 에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="d3fc5-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="d3fc5-175">에이전트를 호출 큐에 추가하기 위해 앞에서 만든 팀 및 채널에 에이전트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="d3fc5-176">팀 선택 **옵션을 선택하고** 채널 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="d3fc5-177">만든 팀의 이름을 입력하고, 선택한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="d3fc5-178">큐에 대해 만든 채널을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="d3fc5-179">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-179">Click **Apply**.</span></span>

    ![통화 큐에 대한 사용자 및 그룹 설정의 스크린샷](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="d3fc5-181">새 사용자가 팀에 추가될 때 첫 번째 통화가 도착하는 데 최대 8시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3fc5-182">4단계 - 리소스 계정 ></span><span class="sxs-lookup"><span data-stu-id="d3fc5-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="d3fc5-183">4단계 <br> 라우팅 호출</span><span class="sxs-lookup"><span data-stu-id="d3fc5-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="d3fc5-184">사용할 호출 라우팅 메서드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="d3fc5-185">회의 **모드를 자동으로** **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="d3fc5-186">사용할 **라우팅** 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="d3fc5-187">그러면 에이전트가 큐에서 호출을 받는 순서가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="d3fc5-188">직렬  라우팅 또는 **라운드 로빈을 추천합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="d3fc5-189">다음 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-189">Choose from these options:</span></span>

    - <span data-ttu-id="d3fc5-190">**참석자 라우팅** 은 큐에 있는 모든 에이전트를 동시에 링합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="d3fc5-191">통화를 받은 첫 번째 통화 에이전트가 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="d3fc5-192">**직렬 라우팅은** 모든 호출 에이전트를 하나씩 링합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="d3fc5-193">에이전트가 통화를 취소하거나 통화를 받지 않으면 다음 에이전트가 호출을 울리고 선택되거나 시간이 초과될 때까지 모든 에이전트를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="d3fc5-194">**라운드 로빈** 은 각 호출 에이전트가 큐에서 동일한 수의 호출을 수신하도록 수신 호출 라우팅의 균형을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d3fc5-195">이는 모든 상담원 간에 동등한 기회를 보장하기 위해 인바운드 영업 환경에서 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="d3fc5-196">**가장 긴 유휴 상태** 는 각 통화를 가장 오랫동안 유휴 상태인 에이전트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="d3fc5-197">(현재 상태 상태가 10분 이상 멀어진 에이전트는 포함되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="d3fc5-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![회의 모드 및 라우팅 방법 설정 스크린샷](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="d3fc5-199">현재 **상태 기반 라우팅을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="d3fc5-200">이 경로는 현재 상태를 사용할 수 있는 에이전트에 **호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="d3fc5-201">에이전트가 통화를 옵트아웃할 수 있도록 허용할지 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="d3fc5-202">에이전트 **경고** 시간을 설정하여 큐에서 호출을 다음 에이전트로 리디렉션하기 전에 에이전트의 전화가 울리는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![라우팅, 옵트아웃 및 알림 시간 설정 스크린샷](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3fc5-204">5단계 - 오버플로 ></span><span class="sxs-lookup"><span data-stu-id="d3fc5-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="d3fc5-205">5단계 <br> 오버플로 호출</span><span class="sxs-lookup"><span data-stu-id="d3fc5-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="d3fc5-206">큐의 최대값을 초과하는 호출을 처리하는 방법을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="d3fc5-207">큐에서 **최대 호출을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="d3fc5-208">최대 호출 수에 도달하면 할 작업을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="d3fc5-209">통화 연결을 끊거나 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="d3fc5-210">호출을 다음 대상 중 하나로 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="d3fc5-211">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="d3fc5-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="d3fc5-212">**음성 앱** - 자동 참석자 또는 다른 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="d3fc5-213">(이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="d3fc5-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="d3fc5-214">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="d3fc5-215">이 형식 사용: +[국가 코드][지역 코드][전화 번호]</span><span class="sxs-lookup"><span data-stu-id="d3fc5-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d3fc5-216">**음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![통화 오버플로 설정 스크린샷](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3fc5-218">6단계 - 통화 시간 제한 ></span><span class="sxs-lookup"><span data-stu-id="d3fc5-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="d3fc5-219">6단계 <br> 통화 시간 제한</span><span class="sxs-lookup"><span data-stu-id="d3fc5-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="d3fc5-220">큐에서 호출이 너무 오래 대기 중일 때 어떤 일이 일어날지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="d3fc5-221">최대 **대기 시간 을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d3fc5-221">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="d3fc5-222">통화 시간 외의 경우 할 작업을 선택해야 합니다. 통화 연결을 끊거나 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="d3fc5-223">호출을 다음 대상 중 하나로 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="d3fc5-224">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="d3fc5-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="d3fc5-225">**음성 앱** - 자동 참석자 또는 다른 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="d3fc5-226">(이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="d3fc5-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="d3fc5-227">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="d3fc5-228">이 형식 사용: +[국가 코드][지역 코드][전화 번호]</span><span class="sxs-lookup"><span data-stu-id="d3fc5-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d3fc5-229">**음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![통화 오버플로 설정 스크린샷](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="d3fc5-231">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-231">Click **Save**.</span></span>

<span data-ttu-id="d3fc5-232">그러면 호출 큐의 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc5-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="d3fc5-233">다음으로 자동 참석자 [를 설정할 수 있습니다.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="d3fc5-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

