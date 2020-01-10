---
title: 통화 대기열 만들기
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
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
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Microsoft 팀을 사용 하 여 클라우드 통화 큐 용 전화 시스템을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 95cf9701705950d997e1d200fee117b5f8f9738b
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005196"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="98c7b-103">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="98c7b-103">Create a Cloud call queue</span></span>

<span data-ttu-id="98c7b-104">클라우드 통화 대기열은 다음을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="98c7b-105">인사말 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-105">A greeting message.</span></span>
- <span data-ttu-id="98c7b-106">다른 사용자가 대기 중에 음악을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="98c7b-107">메일 사용이 가능한 메일 그룹의 통화 에이전트와 보안 그룹에서 통화를 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="98c7b-108">큐 최대 크기, 시간 제한 및 통화 처리 옵션 등의 다른 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="98c7b-109">호출자가 조직에 대 한 메시지를 남기기 위해 보이스 메일을 공유 했습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="98c7b-110">[리소스 계정을](manage-resource-accounts.md)사용 하 여 전화 번호를 통화 대기열과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-110">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="98c7b-111">전화 큐는 직접 전화를 걸거나 자동 전화 교환에서 선택 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="98c7b-112">발신자는 대기 중에 음악을 듣게 되며, 통화 *는 선입 선출 (FIFO* ) 순서에 따라 통화 에이전트에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="98c7b-113">큐의 모든 호출은 다음 메서드 중 하나를 통해 에이전트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="98c7b-114">전화 통신 라우팅을 사용 하면 큐의 첫 번째 호출이 동시에 모든 에이전트를 울릴 때</span><span class="sxs-lookup"><span data-stu-id="98c7b-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="98c7b-115">직렬 라우팅을 사용 하면 큐의 첫 번째 호출이 모든 통화 에이전트를 하나씩 울립니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="98c7b-116">라운드 로빈으로, 들어오는 호출의 라우팅이 각 호출 에이전트가 대기열에서 같은 수의 통화를 제공 하도록 균형을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98c7b-117">**오프 라인**상태 이거나, 현재 상태가 **방해** 금지로 설정 되어 있거나, 통화 대기열에서 전화가 걸려 있지 않은 경우 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="98c7b-118">한 번에 하나의 수신 전화 알림 (큐 헤드의 통화에 대 한)만 통화 에이전트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="98c7b-119">통화 에이전트에서 통화를 수락 하면, 큐에서 다음에 수신 되는 통화가 통화 에이전트로 연결을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="98c7b-120">이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="98c7b-121">1 단계-시작 하기</span><span class="sxs-lookup"><span data-stu-id="98c7b-121">Step 1 — Get started</span></span>

<span data-ttu-id="98c7b-122">통화 대기열 사용을 시작 하려면 몇 가지 사항을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="98c7b-123">통화 대기열에는 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="98c7b-124">리소스 계정에 대 한 자세한 내용은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="98c7b-125">전화 번호를 자원 계정에 할당 하면 이제 비용 무료 전화 시스템 [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="98c7b-126">전화 시스템은 저렴 한 자동 전화 교환 및 통화 대기열 서비스에 사용할 수 있도록 조직 수준의 전화 번호를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="98c7b-127">통화 대기열에 대 한 직접 라우팅 서비스 번호는 Microsoft 팀 사용자 및 상담원만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="98c7b-128">온라인 상태에 있는 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="98c7b-129">[비즈니스용 Skype 라이선스 할당](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 또는 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-129">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="98c7b-130">엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="98c7b-131">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="98c7b-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="98c7b-132">Office 365 통화 요금제에 대 한 자세한 내용은 [office 365에 대 한](calling-plans-for-office-365.md) [전화 시스템 및 통화 요금제](calling-plan-landing-page.md) 및 통화 요금제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="98c7b-133">클라우드 통화 대기열에는 **Microsoft 팀 관리 센터** 에서 받은 유료 및 무료 서비스 전화번호만 할당할 수 있으며, 다른 서비스 공급자에 게 서 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="98c7b-134">무료 서비스 번호에는 통신 크레딧이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98c7b-135">사용자 (구독자) 전화 번호를 통화 대기열에 할당할 수 없음-서비스 수신자 또는 무료 무료 전화 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="98c7b-136">클라우드 통화 대기열과 연결 된 통화 에이전트는 다음 클라이언트가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="98c7b-137">비즈니스용 Skype 데스크톱 클라이언트 2016 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="98c7b-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="98c7b-138">Lync 데스크톱 클라이언트 2013 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="98c7b-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="98c7b-139">Microsoft 팀에서 지원 되는 모든 IP 전화 모델</span><span class="sxs-lookup"><span data-stu-id="98c7b-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="98c7b-140">[비즈니스용 Skype Online 전화 받기를](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="98c7b-141">Mac 비즈니스용 Skype 클라이언트 (버전 16.8.196 이상)</span><span class="sxs-lookup"><span data-stu-id="98c7b-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="98c7b-142">Android 비즈니스용 Skype 클라이언트 (버전 6.16.0.9 이상)</span><span class="sxs-lookup"><span data-stu-id="98c7b-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="98c7b-143">iPhone 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="98c7b-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="98c7b-144">iPad 용 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="98c7b-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="98c7b-145">Microsoft 팀 Windows 클라이언트 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="98c7b-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="98c7b-146">Microsoft 팀 Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="98c7b-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="98c7b-147">Microsoft 팀 iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="98c7b-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="98c7b-148">Microsoft 팀 Android 앱</span><span class="sxs-lookup"><span data-stu-id="98c7b-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="98c7b-149">직접 라우팅 번호로 지정 된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 휴대폰을 에이전트로 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="98c7b-150">2 단계-유료 또는 무료 서비스 전화 번호 가져오기 또는 전송</span><span class="sxs-lookup"><span data-stu-id="98c7b-150">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="98c7b-151">통화 대기열을 만들고 설정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이전 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="98c7b-152">무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터** > **음성** > **전화 번호** > 에 표시 되는 >**추가** 되며, **번호 형식이** 서비스로 나열 됩니다 **(무료)**.</span><span class="sxs-lookup"><span data-stu-id="98c7b-152">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers** > **ADD** >, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="98c7b-153">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md) 참조 하거나 기존 서비스 번호를 전송 하려면 [전화 번호를 Office 365에](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-153">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="98c7b-154">미국 이외의 지역에 거주 하는 경우에는 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-154">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="98c7b-155">미국 이외의 지역에서이를 수행 하는 방법을 확인 하려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-155">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="98c7b-156">여러 자동 전화 교환을 설정할 때 전화 번호를 기본 자동 전화 교환 리소스 계정에만 할당할 수 있으며,이는 호출자를 전화 큐 또는 중첩 된 자동 전화 교환에 바로 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-156">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="98c7b-157">이러한 경우에는 다이얼 패드 옵션을 할당 하지 않고 시스템에서 모든 자동 전화 교환 및 통화 대기열을 만든 다음 나중에 설정을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-157">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="98c7b-158">이는 아직 존재 하지 않는 통화 대기열 또는 자동 전화 교환에 대 한 연결 옵션을 만들 수 없기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-158">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="98c7b-159">3 단계-새 통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="98c7b-159">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="98c7b-160">모든 통화 대기열에는 연결 된 [리소스 계정이](manage-resource-accounts.md)있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-160">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="98c7b-161">먼저 리소스 계정을 만든 다음이를 통화 큐에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-161">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="98c7b-162">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="98c7b-162">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="98c7b-163">**Microsoft 팀 관리 센터**의 **음성** > **통화 대기열**에서 **+ 새로 추가**:를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-163">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="98c7b-164">통화 대기열 표시 이름 및 리소스 계정 설정</span><span class="sxs-lookup"><span data-stu-id="98c7b-164">Set the call queue display name and resource account</span></span>

![번호가 매겨진 설명선이 있는 새 통화 대기열 스크린샷](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="98c7b-166">![이전 스크린샷](media/sfbcallout1.png)
**이름의** 설명선을 참조 하는 숫자 1의 아이콘은 통화 대기열에 대 한 설명 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-166">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="98c7b-167">이 이름은 필수 이며 공백을 포함 하 여 최대 64 자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-167">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="98c7b-168">이 이름은 수신 전화에 대 한 알림에서 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-168">This name is displayed in the notification for the incoming call.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="98c7b-170">**계정 추가** 자원 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-170">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="98c7b-171">리소스 계정은 통화 대기열에 대 한 서비스 유료 또는 무료 전화 번호와 연결 될 수 있지만, 각 통화 대기열에는 연결 된 리소스 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-171">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="98c7b-172">나열 되지 않는 경우 앞에서 설명한 대로이 통화 대기열을 만들기 전에 서비스 번호를 얻고 리소스 계정에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-172">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="98c7b-173">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-173">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="98c7b-174">전화 큐에 연결 된 전화 번호를 사용 하려면 [팀의 자원 계정 관리](manage-resource-accounts.md) 에서 설명한 대로 리소스 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-174">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="98c7b-175">**도메인** 을 할당 해야 하는 경우에는 호출 대기열에 대 한 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-175">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="98c7b-176">대기 중에 재생 되는 인사말 및 음악 설정</span><span class="sxs-lookup"><span data-stu-id="98c7b-176">Set the greeting and music played while on hold</span></span>

![숫자 설명선이 있는 인사말 및 음악 옵션 스크린샷](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="98c7b-179">**인사말** 은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-179">**Greeting** is optional.</span></span> <span data-ttu-id="98c7b-180">이것은 통화 대기열 번호로 전화를 거는 사람들을 위해 플레이 하는 인사말입니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-180">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="98c7b-181">오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-181">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="98c7b-183">**대기 중인 음악** 통화 큐와 함께 제공 된 보류에 기본 음악을 사용 하거나 .wav, mp3 또는 .wma 형식의 오디오 파일을 업로드 하 여 사용자 지정 음악으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-183">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="98c7b-184">통화 응답 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="98c7b-184">Select the call answering options</span></span>

![통화 응답 옵션 스크린샷](media/5d249515-d532-4af2-90da-011404028b89.png) 

<span data-ttu-id="98c7b-186">개별 에이전트를 그룹에 추가 하지 않고 직접 추가 하려면 **사용자 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-186">To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="98c7b-187">개별 에이전트는 전화를 받을 순서 대로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-187">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="98c7b-188">20 개 이상의 개별 에이전트를 추가 하 여 그룹에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-188">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="98c7b-189">호출은 먼저 개별 에이전트로 라우팅 한 다음 그룹의 에이전트로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-189">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="98c7b-190">다음 메일 목록 또는 그룹 중 하나에 속한 최대 200 개의 통화 에이전트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-190">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="98c7b-191">Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="98c7b-191">Office 365 group</span></span>
- <span data-ttu-id="98c7b-192">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="98c7b-192">Security group</span></span>
- <span data-ttu-id="98c7b-193">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="98c7b-193">Distribution list</span></span>

<span data-ttu-id="98c7b-194">선택한 통화 에이전트는 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-194">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="98c7b-195">전화 시스템 라이선스 및 Enterprise Voice가 설정 된 온라인 사용자</span><span class="sxs-lookup"><span data-stu-id="98c7b-195">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="98c7b-196">통화 요금제를 사용 하는 온라인 사용자</span><span class="sxs-lookup"><span data-stu-id="98c7b-196">Online users with a Calling Plan</span></span>
- <span data-ttu-id="98c7b-197">온-프레미스 비즈니스용 Skype 서버 사용자</span><span class="sxs-lookup"><span data-stu-id="98c7b-197">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="98c7b-198">이는 온라인 상태인 조직의 사용자에 게 전화를 리디렉션하는 경우에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-198">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="98c7b-199">이러한 개인에 게는 **전화 시스템** 라이선스와 Enterprise Voice가 설정 되어 **있거나** 통화 요금제가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-199">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="98c7b-200">자세한 내용은 [비즈니스용 Skype 라이선스 할당](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Microsoft 팀 라이선스 할당](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)또는 [사용자에 게 적합 한 통화 계획](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-200">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="98c7b-201">엔터프라이즈 음성에 대 한 에이전트를 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-201">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="98c7b-202">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="98c7b-202">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="98c7b-203">Office 365 그룹에 추가 되는 **전화 시스템** 라이선스 또는 통화 요금제를 사용 하는 사용자 메일 사용이 가능한 메일 그룹 또는 보안 그룹.</span><span class="sxs-lookup"><span data-stu-id="98c7b-203">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="98c7b-204">배포 목록 또는 보안 그룹에 새로 추가 된 에이전트가 최대 3 시간까지 걸릴 수 있으며,이는 통화 대기열에서 전화를 받기 시작 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-204">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="98c7b-205">새로 만든 메일 그룹 또는 보안 그룹이 통화 큐와 함께 사용할 수 있게 되는 데 최대 48 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-205">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="98c7b-206">새로 생성 된 Office 365 그룹은 거의 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-206">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="98c7b-207">에이전트에서 Microsoft 팀 앱을 사용 하 여 통화 대기열 호출을 수행 하는 경우에는 팀 전용 모드에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-207">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![통화 에이전트 추가 창의 스크린샷](media/skype-for-business-add-agents-to-call-queue.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="98c7b-210">**라우팅 방법** 통화 대기열 배포 방법에 대해 **전화 교환**, **직렬**또는 **라운드 로빈** 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-210">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="98c7b-211">모든 새로운 및 기존 통화 대기열에는 기본적으로 수행자 라우팅이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-211">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="98c7b-212">수행자 라우팅이 사용 되는 경우 큐의 첫 번째 호출은 동시에 모든 통화 에이전트를 울립니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-212">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="98c7b-213">통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-213">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="98c7b-214">**수행자 라우팅은** 큐의 첫 번째 호출로 모든 통화 에이전트를 동시에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-214">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="98c7b-215">통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-215">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="98c7b-216">**직렬 라우팅** 들어오는 호출 에이전트 목록의 시작 부분에서 시작 하 여 전화를 한 번에 하나씩 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-216">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="98c7b-217">콜 에이전트 목록 내에서 에이전트를 주문할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-217">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="98c7b-218">에이전트가 전화를 걸거나 받지 못하는 경우, 통화는 목록의 다음 에이전트로 연결 되 고 큐에서 대기 시간을 선택할 때까지 모든 에이전트가 하나씩 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-218">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="98c7b-219">직렬 라우팅은 **오프 라인**상태인 에이전트를 건너뛰거나, 현재 상태를 **방해**금지로 설정 했거나,이 대기열에서 호출을 **옵트아웃** 한 경우를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-219">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="98c7b-220">**라운드 로빈** 각 호출 에이전트가 대기열에서 같은 개수의 호출을 받을 수 있도록 수신 전화의 라우팅을 분산 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-220">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="98c7b-221">이는 모든 통화 에이전트 간에 동일한 기회를 보장 하기 위해 인바운드 영업 환경에서 바람직 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-221">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="98c7b-222">에이전트 옵트아웃 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="98c7b-222">Select an agent opt-out option</span></span>

![번호 매기기 설명선이 있는 에이전트 옵트아웃 옵션 스크린샷](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="98c7b-225">**상담원에 게 전화를 거는 것을 옵트아웃 할 수 있음** 이 옵션을 사용 하 여 통화 대기열 에이전트가 특정 대기열에서 전화를 옵트아웃 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-225">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="98c7b-226">이 옵션을 사용 하도록 설정 하면이 큐의 모든 에이전트가 해당 통화 대기열의 통화를 시작 하거나 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-226">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="98c7b-227">언제 든 지 에이전트 옵트아웃 (opt out) 권한을 취소할 수 있으며,이 큐에 대 한 에이전트가 자동으로 다시 옵트인 되도록 (모든 에이전트의 기본 설정) 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-227">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="98c7b-228">옵트아웃 옵션에 액세스 하기 위해 상담원은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-228">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="98c7b-229">바탕 화면 비즈니스용 Skype 클라이언트에서 **옵션** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-229">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="98c7b-230">**착신 전환** 탭에서 **온라인 설정 편집** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-230">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="98c7b-231">사용자 설정 페이지에서 **통화 대기열**을 클릭 한 다음 옵트아웃을 원하는 모든 대기열의 확인란을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-231">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98c7b-232">비즈니스용 Skype Desktop이 아닌 앱 또는 끝점을 사용 하는 상담원은 사용자 설정 포털 [https://aka.ms/cqsettings](https://aka.ms/cqsettings)의 옵트아웃 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-232">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="98c7b-233">에이전트가 Microsoft 팀 데스크톱 클라이언트에 있는 경우에는 통화 설정을 사용 하 여 옵트아웃 (opt out) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-233">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

![옵트아웃 통화 설정 스크린샷](media/create-a-phone-system-call-queue-image1.png)

<span data-ttu-id="98c7b-235">![이전 스크린샷](media/sfbcallout2.png)
**에이전트 알림 설정** 의 설명선을 참조 하는 숫자 2의 아이콘</span><span class="sxs-lookup"><span data-stu-id="98c7b-235">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="98c7b-236">직렬 또는 라운드 로빈 라우팅 방법이 다음 에이전트로 이동 하기 전에 에이전트의 호출을 알리는 기간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-236">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="98c7b-237">기본 설정은 30 초 이지만 최대 3 분까지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-237">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="98c7b-238">통화 오버플로 및 시간 제한 처리 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="98c7b-238">Set the call overflow and timeout handling options</span></span>

![숫자 매기기 설명선이 있는 오버플로 처리 옵션 스크린샷](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="98c7b-241">**큐의 최대 통화** 이 모드를 사용 하 여 큐에서 동시에 대기할 수 있는 최대 통화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-241">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="98c7b-242">기본값은 50 이지만, 0에서 200 까지의 범위에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-242">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="98c7b-243">이 제한에 도달 하면 아래에 **최대 통화 수에 도달할 때** 설정 하는 방법에 따라 통화가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-243">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="98c7b-245">**최대 통화 수에 도달 하는 경우** 통화 대기열이 최대 크기에 도달 하면 ( **대기열 설정의 최대 통화** 수를 사용 하 여 설정), 새로운 수신 전화에 대 한 상황을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-245">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="98c7b-246">**연결 해제** 통화가 끊겼습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-246">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="98c7b-247">**리디렉션 대상** 이를 선택 하는 경우 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-247">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="98c7b-248">**회사의 사용자** **전화 시스템** 라이선스가 있는 온라인 사용자 이며 엔터프라이즈 음성 또는 통화 요금제를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-248">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="98c7b-249">전화를 음성 메일로 보낼 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-249">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="98c7b-250">이렇게 하려면 **회사에서 사용자** 를 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-250">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="98c7b-251">보이스 메일에 필요한 라이선스에 대해 알아보려면 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-251">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="98c7b-252">**음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-252">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![앞의 스크린샷은 설명선을 참조 하는 숫자 3의 아이콘](media/sfbcallout3.png)

<span data-ttu-id="98c7b-254">**통화 시간 제한: 최대 대기 시간** 또한 시간이 초과 되기 전에 큐에서 통화 대기 시간을 결정 하 고, 리디렉션 또는 연결 해제 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-254">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="98c7b-255">리디렉션 위치는 **통화 시간** 설정을 설정 하는 방법을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-255">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="98c7b-256">0에서 45 분 까지의 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-256">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="98c7b-257">Timeout 값을 초 단위로 15 초 간격으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-257">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="98c7b-258">이를 통해 호출 흐름을 보다 세밀 하 게 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-258">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="98c7b-259">예를 들어 30 초 내에 에이전트가 응답 하지 않는 모든 통화가 디렉터리 검색 자동 전화 교환으로 이동 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-259">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

<span data-ttu-id="98c7b-261">**통화 시간 초과 시** 통화가 **큐 설정에서 대기 하는 시간** 에 설정 된 제한에 도달 하면이 통화에 대해 수행할 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-261">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="98c7b-262">**연결 해제** 통화가 끊겼습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-262">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="98c7b-263">**착신 전환 대상:** 이 옵션을 선택 하면 다음 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-263">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="98c7b-264">**회사의 사용자** **전화 시스템** 라이선스가 있는 온라인 사용자 이며 엔터프라이즈 음성 또는 통화 요금제를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-264">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="98c7b-265">전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-265">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="98c7b-266">이렇게 하려면 **회사에서 사용자** 를 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-266">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="98c7b-267">보이스 메일에 필요한 라이선스에 대해 알아보려면 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-267">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="98c7b-268">**음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환과 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-268">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="98c7b-269">아웃 바운드 통화에 대 한 사용자의 발신자 ID 변경</span><span class="sxs-lookup"><span data-stu-id="98c7b-269">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="98c7b-270">**CsCallingLineIdentity** cmdlet을 사용 하 여 호출 대기열, 자동 전화 교환 또는 서비스 번호로 아웃 바운드 호출에 대 한 발신자 ID를 변경 하 여 사용자의 id를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-270">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="98c7b-271">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-271">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="98c7b-272">그런 다음 **CallingLineIdentity** cmdlet을 사용 하 여 사용자에 게 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-272">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="98c7b-273">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-273">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="98c7b-274">조직에서 [발신자 id를 사용](/microsoftteams/how-can-caller-id-be-used-in-your-organization)하는 방법 문서에서 조직의 발신자 id 설정을 설정 하는 방법에 대 한 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-274">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="98c7b-275">통화 대기열 cmdlet</span><span class="sxs-lookup"><span data-stu-id="98c7b-275">Call queue cmdlets</span></span>

<span data-ttu-id="98c7b-276">또한 Windows PowerShell을 사용 하 여 통화 대기열을 만들고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-276">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="98c7b-277">다음은 통화 대기열을 관리 하는 데 사용 하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-277">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="98c7b-278">새로운 CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="98c7b-278">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="98c7b-279">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="98c7b-279">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="98c7b-280">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="98c7b-280">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="98c7b-281">제거-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="98c7b-281">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="98c7b-282">Windows PowerShell에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="98c7b-282">More about Windows PowerShell</span></span>

- <span data-ttu-id="98c7b-283">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-283">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="98c7b-284">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 Microsoft 팀을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-284">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="98c7b-285">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-285">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="98c7b-286">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="98c7b-286">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="98c7b-287">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="98c7b-287">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="98c7b-288">Windows PowerShell에는 한 번에 많은 사용자의 설정을 변경 하는 경우와 같이 Microsoft 팀 관리 센터를 통한 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c7b-288">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="98c7b-289">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="98c7b-289">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="98c7b-290">Windows PowerShell을 사용 하 여 Office 365 관리</span><span class="sxs-lookup"><span data-stu-id="98c7b-290">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="98c7b-291">Windows PowerShell용 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="98c7b-291">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="98c7b-292">관련 항목</span><span class="sxs-lookup"><span data-stu-id="98c7b-292">Related topics</span></span>

[<span data-ttu-id="98c7b-293">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="98c7b-293">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="98c7b-294">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="98c7b-294">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="98c7b-295">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="98c7b-295">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="98c7b-296">새로운 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="98c7b-296">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
