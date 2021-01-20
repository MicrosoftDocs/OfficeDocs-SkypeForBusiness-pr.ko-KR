---
title: Microsoft Teams에서 통화 큐 만들기 - Small Business 자습서
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
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
description: Microsoft 365 Business Voice를 사용하여 통화 큐를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909637"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="6ae8c-103">통화 큐 만들기 - Small Business 자습서</span><span class="sxs-lookup"><span data-stu-id="6ae8c-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="6ae8c-104">통화 큐는 특정 문제 또는 질문에 도움을 줄 수 있는 조직의 사용자에게 발신자 라우팅 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="6ae8c-105">호출은 큐에 있는 사람(에이전트라고도 하는)에게 한 번씩 *배포됩니다.*</span><span class="sxs-lookup"><span data-stu-id="6ae8c-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="6ae8c-106">호출 큐는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-106">Call queues provide:</span></span>

- <span data-ttu-id="6ae8c-107">인사말 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-107">A greeting message.</span></span>

- <span data-ttu-id="6ae8c-108">음악 대기 중인 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="6ae8c-109">호출 라우팅(FIFO(First *In, First Out)* 순서로 에이전트에 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="6ae8c-110">큐 오버플로 및 시간 제한에 대한 처리 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="6ae8c-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6ae8c-111">Before you begin</span></span>

<span data-ttu-id="6ae8c-112">아직 없는 경우 일부 전화 시스템 [-](../teams-add-on-licensing/virtual-user.md) 가상 사용자 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="6ae8c-113">설정할 각 통화 큐 및 자동 전화 회의에 대해 하나를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="6ae8c-114">이러한 라이선스는 무료이기 때문에 향후 설정을 변경하기로 결정한 경우 몇 가지 추가 사항을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="6ae8c-115">통화 큐의 에이전트가 고객 전화를 반환하기 위해 전화를 걸 수 있는 경우 통화 에이전트의 발신자 ID를 기본 전화 번호 또는 적절한 자동 전화 번호로 설정하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="6ae8c-116">자세한 [내용은 Microsoft Teams에서 발신자 ID](../caller-id-policies.md) 정책 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="6ae8c-117">다음 단계에 따라 호출 큐를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="6ae8c-118"><br>1단계 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae8c-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="6ae8c-119">통화 큐를 만들 때 개별 사용자를 큐에 추가하거나 기존 보안 그룹, Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="6ae8c-120">팀을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-120">We recommend using a team.</span></span> <span data-ttu-id="6ae8c-121">이렇게 하면 큐의 구성원이 서로 채팅하고, 아이디어를 공유하고, 문서 또는 기타 리소스를 만들어 고객이 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="6ae8c-122">또한 팀에서는 발신자에 대해 몇 시간 후 또는 큐가 최대 용량에 도달하면 메시지를 남길 수 있는 음성 사서함을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="6ae8c-123">팀을 만들자</span><span class="sxs-lookup"><span data-stu-id="6ae8c-123">To create a team</span></span>

1. <span data-ttu-id="6ae8c-124">먼저 앱의 왼쪽에 있는 **Teams를** 클릭한 다음 참가를 클릭하거나 팀 목록의 맨 아래에 팀을 만들어야 합니다. </span><span class="sxs-lookup"><span data-stu-id="6ae8c-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="6ae8c-125">그런 다음 **팀 만들기(첫** 번째 카드, 왼쪽 위 모서리)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="6ae8c-126">처음부터 **팀 빌드를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="6ae8c-127">다음으로, 공개 또는 비공개 팀을 원하는지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="6ae8c-128">팀에  합류하여 사람들이 의도치 않은 큐에 참여하지 않도록 통화 큐에 Private을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="6ae8c-129">팀 이름을 지정하고 선택적 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="6ae8c-130">완료되면 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="6ae8c-131">통화 큐에 원하는 사람 이름을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="6ae8c-132">닫기 **클릭**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-132">Click **Close**.</span></span> <span data-ttu-id="6ae8c-133">팀에 추가한 사람은 팀 구성원이 됐고 팀이 팀 목록에 표시될 것 같은 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6ae8c-134">2단계 - 리소스 계정 ></span><span class="sxs-lookup"><span data-stu-id="6ae8c-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="6ae8c-135">2단계 <br> 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="6ae8c-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="6ae8c-136">만드는 각 호출 큐에는 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="6ae8c-137">계정이 개인 대신 자동 전화 걸기 또는 통화 큐와 연결되어 있는 것을 제외하고는 사용자 계정과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="6ae8c-138">이 단계에서는 계정을 *만들고, Microsoft 365* 전화 시스템 - 가상 사용자 라이선스를 할당한 다음, 이를 사용하여 호출 큐 만들기를 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="6ae8c-139">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae8c-139">Create a resource account</span></span>

<span data-ttu-id="6ae8c-140">Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="6ae8c-141">Teams 관리 센터에서 **전체 설정을** 확장한 다음 리소스 **계정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="6ae8c-142">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-142">Click **Add**.</span></span>

3. <span data-ttu-id="6ae8c-143">리소스 계정 추가 **창에서** 표시 **이름,** 사용자 이름을  입력하고 리소스 계정 유형에 대한 호출 **큐를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add-cq.png)

4. <span data-ttu-id="6ae8c-145">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-145">Click **Save**.</span></span>

<span data-ttu-id="6ae8c-146">새 계정이 계정 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-146">The new account will appear in the list of accounts.</span></span>

![리소스 계정 목록의 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="6ae8c-148">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6ae8c-148">Assign a license</span></span>

<span data-ttu-id="6ae8c-149">리소스 계정에 *Microsoft 365 Phone System - 가상 사용자* 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="6ae8c-150">Microsoft 365 관리 센터에서 라이선스를 할당하려는 리소스 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="6ae8c-151">라이선스 **및** 앱 탭의 **라이선스** **아래에서 Microsoft 365 Phone System - Virtual User를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="6ae8c-152">변경 **내용 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-152">Click **Save changes**.</span></span>

    ![Microsoft 365 관리 센터의 라이선스 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="6ae8c-154">통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae8c-154">Create a call queue</span></span>

<span data-ttu-id="6ae8c-155">다음으로 새 호출 큐를 만들고 리소스 계정을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="6ae8c-156">Teams 관리 센터에서 **음성을** 확장하고 통화 큐를 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="6ae8c-157">호출 큐의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-157">Type a name for the call queue.</span></span> <span data-ttu-id="6ae8c-158">에이전트는 큐에서 들어오는 호출을 받으면 이 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="6ae8c-159">계정 **추가를** 클릭하고 이 호출 큐에 사용할 리소스 계정을 검색한 다음 추가를 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="6ae8c-160">언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-160">Choose a language.</span></span> <span data-ttu-id="6ae8c-161">이 언어는 시스템 생성 음성 프롬프트 및 음성메일 전사(사용하도록 설정한 경우)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![리소스 계정 및 언어 설정 스크린샷](../media/call-queue-name-language.png)

4. <span data-ttu-id="6ae8c-163">발신자들에게 큐에 도착할 때 인사말을 재생할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="6ae8c-164">재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="6ae8c-165">Teams는 큐에 대기 중인 발신자에 기본 음악을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="6ae8c-166">특정 오디오 파일을 재생하려면 오디오 파일 재생을 **선택하고** MP3, WAV 또는 WMA 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="6ae8c-167">업로드된 기록은 5MB를 넘지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="6ae8c-168">Teams 통화 큐에 제공되는 기본 음악은 조직에서 지불하는 로열티가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="6ae8c-169">3단계 - 에이전트 호출 ></span><span class="sxs-lookup"><span data-stu-id="6ae8c-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="6ae8c-170">3단계 <br> 에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="6ae8c-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="6ae8c-171">호출 큐에 에이전트를 추가하기 위해 앞에서 만든 팀을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="6ae8c-172">그룹 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="6ae8c-173">만든 팀의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="6ae8c-174">**추가를** 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-174">Click **Add**, and then click **Add**.</span></span>

    ![통화 큐에 대한 사용자 및 그룹 설정 스크린샷](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="6ae8c-176">그룹 또는 팀을 통해 최대 20개 에이전트를 개별적으로 최대 200개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="6ae8c-177">새 사용자가 팀에 추가된 경우 첫 번째 호출이 도착하는 데 최대 8시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6ae8c-178">4단계 - 리소스 계정 ></span><span class="sxs-lookup"><span data-stu-id="6ae8c-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="6ae8c-179">4단계 <br> 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="6ae8c-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="6ae8c-180">사용하려는 호출 라우팅 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="6ae8c-181">회의 **모드를 자동으로** **설정**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="6ae8c-182">사용하려는 **라우팅** 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="6ae8c-183">그러면 에이전트가 큐에서 호출을 받는 순서가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="6ae8c-184">직렬 **라우팅 또는** **라운드 로빈을 권장합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="6ae8c-185">다음 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-185">Choose from these options:</span></span>

    - <span data-ttu-id="6ae8c-186">**참석자 라우팅은** 큐에 있는 모든 에이전트를 동시에 링합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="6ae8c-187">호출을 픽업하는 첫 번째 호출 에이전트가 호출을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="6ae8c-188">**직렬 라우팅은** 모든 호출 에이전트를 하나씩 링합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="6ae8c-189">에이전트가 통화를 기각하거나 선택하지 않는 경우 호출은 다음 에이전트에 벨을 울리며, 에이전트가 선택되거나 시간 외 시간 외로 호출될 때까지 모든 에이전트를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="6ae8c-190">**라운드 로빈은** 들어오는 호출의 라우팅을 균형 조정하여 각 호출 에이전트가 큐에서 동일한 호출 수를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="6ae8c-191">인바운드 판매 환경에서는 모든 호출 에이전트가 동일한 기회를 보장하는 것이 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="6ae8c-192">**가장 긴 유휴** 시간은 각 호출을 유휴 시간이 가장 긴 에이전트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="6ae8c-193">(10분 넘게 현재 상태가 부재 중 상태인 에이전트는 포함되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="6ae8c-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![회의 모드 및 라우팅 방법 설정 스크린샷](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="6ae8c-195">현재 **상태 기반 라우팅을 켜야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="6ae8c-196">이렇게 하여 현재 상태를 사용할 수 있는 에이전트에 대한 호출을 **라우팅합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="6ae8c-197">에이전트가 통화를 옵트아웃할 수 있도록 허용할지 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="6ae8c-198">에이전트 경고 **시간을** 설정하여 큐가 다음 에이전트로 호출을 리디렉션하기 전에 에이전트의 전화가 울릴 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![라우팅, 옵트아웃 및 경고 시간 설정 스크린샷](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="6ae8c-200">5단계 - 오버플로 호출 ></span><span class="sxs-lookup"><span data-stu-id="6ae8c-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="6ae8c-201">5단계 <br> 오버플로 호출</span><span class="sxs-lookup"><span data-stu-id="6ae8c-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="6ae8c-202">큐의 최대값을 초과하는 호출을 처리하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="6ae8c-203">큐에서 **최대 호출을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="6ae8c-204">최대 호출 수에 도달할 때 할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="6ae8c-205">통화 연결을 끊거나 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="6ae8c-206">다음 대상 중 하나에 호출을 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="6ae8c-207">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람</span><span class="sxs-lookup"><span data-stu-id="6ae8c-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="6ae8c-208">**음성 앱** - 자동 전화 걸기 또는 다른 통화 큐.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="6ae8c-209">(이 대상을 선택할 때 자동 전화 연결 또는 통화 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="6ae8c-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="6ae8c-210">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="6ae8c-211">+[국가 코드][지역 번호][전화 번호] 형식 사용</span><span class="sxs-lookup"><span data-stu-id="6ae8c-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="6ae8c-212">**음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![호출 오버플로 설정 스크린샷](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="6ae8c-214">6단계 - 호출 시간 제한 ></span><span class="sxs-lookup"><span data-stu-id="6ae8c-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="6ae8c-215"><br>6단계 호출 시간 제한</span><span class="sxs-lookup"><span data-stu-id="6ae8c-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="6ae8c-216">호출이 큐에서 너무 오랫동안 대기 중인 경우 발생하려는 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="6ae8c-217">통화 시간 **제한 설정: 최대 대기 시간.**</span><span class="sxs-lookup"><span data-stu-id="6ae8c-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="6ae8c-218">통화가 시간보다 까다로우면 어떤 작업을 할지 선택해야 합니다. 통화 연결을 끊거나 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="6ae8c-219">다음 대상 중 하나에 호출을 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="6ae8c-220">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람</span><span class="sxs-lookup"><span data-stu-id="6ae8c-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="6ae8c-221">**음성 앱** - 자동 전화 걸기 또는 다른 통화 큐.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="6ae8c-222">(이 대상을 선택할 때 자동 전화 연결 또는 통화 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="6ae8c-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="6ae8c-223">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="6ae8c-224">+[국가 코드][지역 번호][전화 번호] 형식 사용</span><span class="sxs-lookup"><span data-stu-id="6ae8c-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="6ae8c-225">**음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![통화 시간 제한 설정 스크린샷](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="6ae8c-227">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-227">Click **Save**.</span></span>

<span data-ttu-id="6ae8c-228">그러면 호출 큐 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8c-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="6ae8c-229">다음으로 자동 [attendant를 설정할 수 있습니다.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="6ae8c-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

