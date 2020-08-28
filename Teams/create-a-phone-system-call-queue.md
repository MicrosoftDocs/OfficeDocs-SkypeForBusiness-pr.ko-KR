---
title: 통화 대기열 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 인사말 메시지, 음악 보관, 착신 전환, 기타 기능을 제공 하는 Microsoft 팀을 사용 하 여 클라우드 통화 큐 용 전화 시스템을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: be43c2dc378b985b63c47b9322b336eeadfeecb6
ms.sourcegitcommit: 515f6cf7c16c0ab6ea7acbbd59084ac89b57dfb8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47295283"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="8a337-103">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="8a337-103">Create a Cloud call queue</span></span>

<span data-ttu-id="8a337-104">클라우드 통화 대기열은 다음을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="8a337-105">인사말 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-105">A greeting message.</span></span>

- <span data-ttu-id="8a337-106">다른 사용자가 대기 중에 음악을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-106">Music while people are waiting on hold.</span></span>

- <span data-ttu-id="8a337-107">메일 사용이 가능한 메일 그룹의 통화 에이전트와 보안 그룹에서 통화를 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>

- <span data-ttu-id="8a337-108">큐 최대 크기, 시간 제한 및 통화 처리 옵션 등의 다른 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

- <span data-ttu-id="8a337-109">호출자가 조직에 대 한 메시지를 남기기 위해 보이스 메일을 공유 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="8a337-110">전화 번호를 통화 대기열에 직접 연결 하지 않고, 대신 전화 번호가 [리소스 계정과](manage-resource-accounts.md)연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="8a337-111">전화 큐는 직접 전화를 걸거나 자동 전화 교환에서 선택 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="8a337-112">발신자는 대기 중에 음악을 듣게 되며, 통화 *는 선입 선출 (FIFO* ) 순서에 따라 통화 에이전트에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="8a337-113">큐의 모든 호출은 다음 메서드 중 하나를 통해 에이전트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="8a337-114">전화 통신 라우팅을 사용 하면 큐의 첫 번째 호출이 동시에 모든 에이전트를 울릴 때</span><span class="sxs-lookup"><span data-stu-id="8a337-114">With attendant routing, the first call in the queue rings all agents at the same time.</span></span>

- <span data-ttu-id="8a337-115">직렬 라우팅을 사용 하면 큐의 첫 번째 호출이 모든 통화 에이전트를 하나씩 울립니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>

- <span data-ttu-id="8a337-116">가장 긴 유휴 라우팅의 경우 가장 오래 된 시간 동안 유휴 상태에 있는 통화 에이전트는 다음 통화를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-116">With longest idle routing, the call agent whose has been idle the longest time receives the next available call.</span></span> <span data-ttu-id="8a337-117">유휴 시간은 통화 에이전트의 현재 상태가 **사용 가능** 또는 **자리 비움** (10 분 미만)으로 설정 되는 시간으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-117">The idle time is defined as the length of time a call agent's presence state is set to **Available** or **Away** (if less than 10 minutes), at the time of the call.</span></span> <span data-ttu-id="8a337-118">통화 에이전트의 현재 상태가 10 분 이상 **자리 비움** 상태 이면 유휴 타이머가 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-118">If a call agent's presence is **Away** for more than 10 minutes, the idle timer resets.</span></span>

- <span data-ttu-id="8a337-119">라운드 로빈으로, 들어오는 호출의 라우팅이 각 호출 에이전트가 대기열에서 같은 수의 통화를 제공 하도록 균형을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-119">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

<span data-ttu-id="8a337-120">위의 방법 중 하나를 사용 하 여 에이전트 옵트인/옵트아웃, 현재 상태 기반 라우팅, 통화 대기 시간, 통화 시간 제한 옵션 등의 통화 처리 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-120">You can set call handling options, such as agent opt-in/opt-out, presence-based routing, call wait time, and call time-out options with any of the above methods.</span></span>

<span data-ttu-id="8a337-121">한 번에 하나의 수신 전화 알림 (큐 헤드의 통화에 대 한)만 통화 에이전트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-121">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span> <span data-ttu-id="8a337-122">통화 에이전트에서 통화를 수락 하면, 큐에서 다음에 수신 되는 통화가 통화 에이전트로 연결을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-122">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="8a337-123">이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-123">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="8a337-124">1 단계-시작 하기</span><span class="sxs-lookup"><span data-stu-id="8a337-124">Step 1 — Get started</span></span>

<span data-ttu-id="8a337-125">통화 대기열 사용을 시작 하려면 몇 가지 사항을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-125">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="8a337-126">통화 대기열에는 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-126">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="8a337-127">리소스 계정에 대 한 자세한 내용은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-127">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>

- <span data-ttu-id="8a337-128">전화 번호를 자원 계정에 할당 하면 이제 비용 무료 전화 시스템 [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-128">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="8a337-129">전화 시스템은 저렴 한 자동 전화 교환 및 통화 대기열 서비스에 사용할 수 있도록 조직 수준의 전화 번호를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-129">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8a337-130">통화 대기열에 대 한 직접 라우팅 서비스 번호는 Microsoft 팀 사용자 및 상담원만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-130">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8a337-131">온라인 상태에 있는 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하 고 Enterprise Voice를 사용 하도록 설정 하거나 Microsoft 365 또는 Office 365 통화 요금제가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-131">To redirect calls to people in your organization who are online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="8a337-132">[Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-132">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="8a337-133">엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-133">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8a337-134">예를 들어 ' Set-CsUser-id "Amos 대리석"-EnterpriseVoiceEnabled $true를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-134">For example, run: \`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true.</span></span>

- <span data-ttu-id="8a337-135">통화 요금제에 대 한 자세한 내용은 [Microsoft 365 또는 Office 365에 대 한](calling-plans-for-office-365.md) [전화 시스템 및 통화 요금제](calling-plan-landing-page.md) 및 통화 요금제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-135">To learn more about Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="8a337-136">클라우드 통화 대기열에는 **Microsoft 팀 관리 센터** 에서 받은 유료 및 무료 서비스 전화번호만 할당할 수 있으며, 다른 서비스 공급자에 게 서 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-136">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="8a337-137">무료 서비스 번호에는 통신 크레딧이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-137">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a337-138">사용자 (구독자) 전화 번호를 통화 대기열에 할당할 수 없음-서비스 수신자 또는 무료 무료 전화 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-138">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="8a337-139">클라우드 통화 대기열과 연결 된 통화 에이전트는 다음 클라이언트가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-139">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="8a337-140">비즈니스용 Skype 데스크톱 클라이언트 2016 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="8a337-140">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8a337-141">Lync 데스크톱 클라이언트 2013 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="8a337-141">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8a337-142">Microsoft 팀에서 지원 되는 모든 IP 전화 모델</span><span class="sxs-lookup"><span data-stu-id="8a337-142">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="8a337-143">[비즈니스용 Skype Online 전화 받기를](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-143">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="8a337-144">Mac 비즈니스용 Skype 클라이언트 (버전 16.8.196 이상)</span><span class="sxs-lookup"><span data-stu-id="8a337-144">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="8a337-145">Android 비즈니스용 Skype 클라이언트 (버전 6.16.0.9 이상)</span><span class="sxs-lookup"><span data-stu-id="8a337-145">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="8a337-146">iPhone 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="8a337-146">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="8a337-147">iPad 용 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)</span><span class="sxs-lookup"><span data-stu-id="8a337-147">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="8a337-148">Microsoft 팀 Windows 클라이언트 (32 비트 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="8a337-148">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8a337-149">Microsoft 팀 Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8a337-149">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="8a337-150">Microsoft 팀 iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="8a337-150">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="8a337-151">Microsoft 팀 Android 앱</span><span class="sxs-lookup"><span data-stu-id="8a337-151">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a337-152">직접 라우팅 번호로 지정 된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 전화를 에이전트로 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-152">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="8a337-153">2 단계-유료 또는 무료 서비스 전화 번호 받기 또는 전송</span><span class="sxs-lookup"><span data-stu-id="8a337-153">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="8a337-154">통화 대기열을 만들고 설정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이전 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-154">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="8a337-155">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md) 참조 하거나 기존 서비스 번호를 전송 하려는 경우 [전화 번호를 팀에 게 양도](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-155">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="8a337-156">무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터**의  >  **음성**  >  **전화 번호로**표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-156">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="8a337-157">무료 전화 번호에는 다양 한 서비스 **유형** (무료 **)** 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-157">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="8a337-158">미국 이외의 지역에 거주 하는 경우에는 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-158">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="8a337-159">미국 이외의 지역에서이를 수행 하는 방법을 확인 하려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-159">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="8a337-160">여러 자동 전화 교환을 설정 하는 경우 일반적으로 주 자동 전화 교환의 리소스 계정에 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-160">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="8a337-161">네스트된 자동 전화 교환 또는 통화 대기열에 연결 된 리소스 계정은 전화 번호가 필요 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-161">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="8a337-162">이 자동 전화 교환은 전화 번호가 없는 경우에도 사용자의 통화 큐 또는 중첩 자동 전화 교환에 발신자를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-162">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="8a337-163">이러한 경우에는 다이얼 패드 옵션을 할당 하지 않고 시스템에서 모든 자동 전화 교환 및 통화 대기열을 만든 다음 나중에 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-163">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="8a337-164">메뉴 옵션으로 설정 하려면 통화 대기열 또는 자동 수행자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-164">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="8a337-165">3 단계-통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="8a337-165">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="8a337-166">모든 통화 대기열에는 연결 된 [리소스 계정이](manage-resource-accounts.md)있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-166">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="8a337-167">먼저 리소스 계정을 만든 다음이를 통화 큐에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-167">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="8a337-168">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8a337-168">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="8a337-169">**Microsoft 팀 관리 센터**의 **음성**  >  **통화 대기열**에서 **+ 새로 추가**:를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-169">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="8a337-170">표시 이름 및 리소스 계정 설정</span><span class="sxs-lookup"><span data-stu-id="8a337-170">Set the display name and resource account</span></span>

![번호가 매겨진 설명선이 있는 새 통화 대기열 스크린샷](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="8a337-172">![이전 스크린샷 이름의 설명선을 참조 하는 숫자 1의 아이콘은 ](media/teamscallout1.png)
 **Name** 통화 대기열에 대 한 설명 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-172">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="8a337-173">이 이름은 필수 이며 공백을 포함 하 여 최대 64 자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-173">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="8a337-174">이 이름은 수신 전화에 대 한 알림에서 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-174">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="8a337-175">![숫자 2의 아이콘으로, 이전 스크린샷의 설명선을 참조 하 고, ](media/teamscallout2.png)
 **계정 추가** 리소스 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-175">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="8a337-176">모든 통화 대기열에는 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-176">All call queues are required to have a resource account.</span></span> <span data-ttu-id="8a337-177">자원 계정에는 서비스 수신자 또는 무료 전화 번호가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-177">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="8a337-178">나열 되지 않는 경우 앞에서 설명한 대로 통화 대기열을 만들기 전에 서비스 번호를 가져오고이를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-178">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="8a337-179">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-179">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="8a337-180">전화 번호를 할당 하는 방법에 대 한 구체적인 방법은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-180">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="8a337-181">**도메인** 을 할당 해야 하는 경우에는 호출 대기열에 대 한 리소스 계정에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-181">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="8a337-182">대기 중에 재생 되는 인사말 및 음악 설정</span><span class="sxs-lookup"><span data-stu-id="8a337-182">Set the greeting and music played while on hold</span></span>

![숫자 설명선이 있는 인사말 및 음악 옵션 스크린샷](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="8a337-184">![숫자 1의 아이콘으로, 이전 스크린샷의 설명선을 참조 합니다 ](media/teamscallout1.png)
 . 통화 대기열 번호를 호출 하는 사용자를 위해 재생**되는** 선택적 인사말입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-184">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="8a337-185">오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-185">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="8a337-186">![번호 2의 아이콘으로, 보류 중인 이전 스크린샷 음악의 설명선을 참조 ](media/teamscallout2.png)
 **Music on hold** 합니다. 통화 대기열과 함께 제공 된 보류에 대 한 기본 음악을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-186">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="8a337-187">.Wav, mp3 또는 .wma 형식의 오디오 파일을 업로드 하 여 사용자 지정 음악으로 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-187">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="8a337-188">통화 응답 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="8a337-188">Select the call answering options</span></span>

![통화 응답 옵션 스크린샷](media/teams-cq-call-answering-options.png)

<span data-ttu-id="8a337-190">![숫자 1의 아이콘, 이전 스크린샷 ](media/teamscallout1.png)
 **호출 에이전트 및 그룹** 에서 설명선을 참조 하 여 그룹에 추가 하지 않고 개별 에이전트를 직접 추가 하려면 **사용자 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-190">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="8a337-191">개별 에이전트는 전화를 받을 순서 대로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-191">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="8a337-192">20 개 이상의 개별 에이전트를 추가 하 여 그룹에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-192">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="8a337-193">호출은 먼저 개별 에이전트로 라우팅 한 다음 그룹의 에이전트로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-193">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="8a337-194">다음 메일 목록 또는 그룹 중 하나에 속한 최대 200 개의 통화 에이전트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-194">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="8a337-195">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="8a337-195">Microsoft 365 group</span></span>
- <span data-ttu-id="8a337-196">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8a337-196">Security group</span></span>
- <span data-ttu-id="8a337-197">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="8a337-197">Distribution list</span></span>

<span data-ttu-id="8a337-198">선택한 통화 에이전트는 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-198">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="8a337-199">전화 시스템 라이선스 및 Enterprise Voice가 설정 된 온라인 사용자</span><span class="sxs-lookup"><span data-stu-id="8a337-199">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="8a337-200">통화 요금제를 사용 하는 온라인 사용자</span><span class="sxs-lookup"><span data-stu-id="8a337-200">Online users with a Calling Plan</span></span>
- <span data-ttu-id="8a337-201">온-프레미스 비즈니스용 Skype 서버 사용자</span><span class="sxs-lookup"><span data-stu-id="8a337-201">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="8a337-202">이는 온라인 상태인 조직의 사용자에 게 전화를 리디렉션하는 경우에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-202">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="8a337-203">이러한 개인에 게는 전화 시스템 라이선스와 Enterprise Voice가 설정 되어 *있거나* 통화 요금제가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-203">These individuals must have a Phone System license and Enterprise Voice enabled *or* have a Calling Plan.</span></span> <span data-ttu-id="8a337-204">자세한 내용은 [비즈니스용 Skype 라이선스 할당](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Microsoft 팀 라이선스 할당](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)또는 [사용자에 게 적합 한 통화 계획](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-204">For more information, see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

   <span data-ttu-id="8a337-205">엔터프라이즈 음성에 대 한 에이전트를 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-205">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8a337-206">예를 들어 다음을 실행 합니다. `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8a337-206">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="8a337-207">전화 시스템 라이선스 또는 Microsoft 365 그룹, 메일 사용이 가능한 배포 목록 또는 보안 그룹에 추가 되는 통화 요금제를 사용 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="8a337-207">Users with a Phone System license or a Calling Plan that are added to a Microsoft 365 Group, a mail-enabled distribution list, or a security group.</span></span> <span data-ttu-id="8a337-208">배포 목록 또는 보안 그룹의 에이전트를 통화 대기열 에이전트로 추가 하는 경우 첫 번째 통화가 도착 하는 데 최대 3 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-208">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="8a337-209">새로 만든 메일 그룹 또는 보안 그룹이 통화 큐와 함께 사용할 수 있게 되는 데 최대 48 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-209">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="8a337-210">새로 만든 Microsoft 365 그룹은 거의 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-210">Newly created Microsoft 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="8a337-211">상담원은 통화 대기열 통화를 위해 Microsoft 팀 앱을 사용 하 고 있는 경우에는 TeamsOnly 모드에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-211">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="8a337-212">![숫자 2의 아이콘으로, 이전 스크린샷 ](media/teamscallout2.png)
 **회의 모드** 회의 모드의 설명선을 참조 하면 에이전트에서 호출을 수락한 후 호출자가 에이전트에 연결 하는 데 걸리는 시간이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-212">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Conference mode** Conference mode significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="8a337-213">통화 대기열이 두 개 이상인 경우에는 일부 또는 전체 통화 대기열에서 컨퍼런스 모드를 사용 하도록 설정할 수 있습니다. 한 통화 대기열에서 컨퍼런스 모드를 사용 하거나 사용 하지 않도록 설정 해도 다른 통화 대기열에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-213">If you have more than one call queue, you can enable conference mode on some or all of your call queues; enabling or disabling conference mode on one call queue doesn't impact any other call queues.</span></span>

<span data-ttu-id="8a337-214">회의 모드는 기본적으로 사용 하지 않도록 설정 되어 있지만 다음 요구 사항이 충족 되는 경우 언제 든 지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-214">Conference mode is disabled by default but can be enabled at any time if the following requirements are met:</span></span>

- <span data-ttu-id="8a337-215">통화 대기열에 추가 된 상담원은 다음 클라이언트 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-215">Agents added to the call queue need to use one of the following clients:</span></span>

  - <span data-ttu-id="8a337-216">최신 버전의 Microsoft 팀 데스크톱 클라이언트, Android 앱 또는 iOS 앱</span><span class="sxs-lookup"><span data-stu-id="8a337-216">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="8a337-217">Microsoft 팀 전화 버전 1449/1.0.94.2020051601 이상</span><span class="sxs-lookup"><span data-stu-id="8a337-217">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
- <span data-ttu-id="8a337-218">에이전트 팀 계정은 팀 전용 모드로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-218">Agents' Teams accounts need to be set to Teams-only mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a337-219">위의 에이전트 요구 사항이 충족 되지 않고 통화 대기열에 대해 회의 모드를 사용 하도록 설정 되어 있는 경우 요구 사항을 충족 하지 않는 상담원은 통화 라우팅 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-219">If the agent requirements above aren't met and conference mode is enabled on a call queue, agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="8a337-220">통화 라우팅 목록에 없는 상담원은 통화를 수신 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-220">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="8a337-221">위의 에이전트 요구 사항에 맞지 않는 에이전트가 있는 경우에는 통화 대기열에서 컨퍼런스 모드를 사용 하도록 설정 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-221">If you have agents who don't meet the agent requirements above, don't enable conference mode on the call queue.</span></span>

<span data-ttu-id="8a337-222">전화 대기열에서 컨퍼런스 모드를 사용 하도록 설정한 후에는 다음 방법 중 하나를 통해 수신 되는 경우 더 빠른 연결 시간으로 통화가 혜택을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-222">After conference mode is enabled on a call queue, calls will benefit from the faster connection time if they're received via one of the following methods:</span></span>

- <span data-ttu-id="8a337-223">다른 Microsoft 팀 데스크톱 클라이언트의 VoIP 통화</span><span class="sxs-lookup"><span data-stu-id="8a337-223">VoIP calls from another Microsoft Teams desktop client</span></span>
- <span data-ttu-id="8a337-224">통화 요금제 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="8a337-224">Calling Plan PSTN calls</span></span>
- <span data-ttu-id="8a337-225">PSTN 통화 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a337-225">Direct Routing PSTN calls</span></span>

<span data-ttu-id="8a337-226">대부분의 통화는 위에 나열 된 방법 중 하나를 통해 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-226">The majority of calls are received via one of the methods listed above.</span></span> <span data-ttu-id="8a337-227">다른 방법 (예: 비즈니스용 Skype 클라이언트의 VoIP 통화)을 통해 전화를 받으면 통화가 통화 대기열에 추가 되지만, 더 빠른 연결 시간으로는 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-227">If a call is received via another method (such as a VoIP call from a Skype for Business client), the call will still be added to the call queue, however, it won't benefit from the faster connection time.</span></span>

> [!NOTE]
> <span data-ttu-id="8a337-228">다른 용무 중 통화 모드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-228">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="8a337-229">현재 상태 기반 라우팅이 활성화 되어 있지 않은 경우 통화 대기열 호출이 계속 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-229">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>


<span data-ttu-id="8a337-230">![숫자 3의 아이콘, 이전 스크린샷 ](media/teamscallout3.png)
 **라우팅 메서드의** 설명선 참조 **전화 교환**, **직렬**, **가장 긴 유휴**또는 **라운드 로빈** 중 하나를 배포 방법으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-230">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Routing method** You can choose either **Attendant**, **Serial**, **Longest idle**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="8a337-231">모든 새로운 및 기존 통화 대기열에는 기본적으로 수행자 라우팅이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-231">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="8a337-232">수행자 라우팅이 사용 되는 경우 큐의 첫 번째 호출은 동시에 모든 통화 에이전트를 울립니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-232">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="8a337-233">통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-233">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="8a337-234">**수행자 라우팅은** 큐의 첫 번째 호출로 모든 통화 에이전트를 동시에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-234">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="8a337-235">통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-235">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="8a337-236">**직렬 라우팅** 수신 전화는 통화 에이전트 목록의 시작 부분에서 모든 통화 에이전트를 하나씩 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-236">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="8a337-237">콜 에이전트 목록 내에서 에이전트를 주문할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-237">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="8a337-238">에이전트가 전화를 걸거나 받지 못하는 경우 통화는 다음 에이전트로 연결 되며, 모든 에이전트가 선택 되거나 시간 초과 될 때까지 시도 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-238">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
- <span data-ttu-id="8a337-239">**가장 긴 유휴** 시간 유휴 상태에 있는 통화 에이전트에 사용할 수 있는 다음 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-239">**Longest idle** routes the next available call to the call agent whose has been idle the longest time.</span></span> <span data-ttu-id="8a337-240">유휴 시간은 통화 에이전트의 현재 상태가 **사용 가능** 또는 **자리 비움** (10 분 미만)으로 설정 되는 시간으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-240">The idle time is defined as the length of time a call agent's presence state is set to **Available** or **Away** (if less than 10 minutes), at the time of the call.</span></span> <span data-ttu-id="8a337-241">통화 에이전트의 현재 상태가 10 분 **이상으로 설정** 되어 있으면 유휴 타이머가 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-241">If a call agent's presence is set to **Away** for more than 10 minutes, the idle timer resets.</span></span> <span data-ttu-id="8a337-242">사용자의 현재 상태는 분 단위로 쿼리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-242">Presence states of users are queried every minute.</span></span>

    <span data-ttu-id="8a337-243">이 설정을 사용 하면 **현재 상태 기반 회람** 도 강제로 사용할 수 있다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-243">It's important to know that enabling this setting forces **Presence-based routing** to also be enabled.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8a337-244">가장 긴 유휴 설정을 사용 하는 경우 비즈니스용 Skype 클라이언트를 사용 하는 상담원은 통화를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-244">Agents who use the Skype for Business client won't receive calls when the longest idle setting is enabled.</span></span> <span data-ttu-id="8a337-245">Skype 또는 Business를 사용 하는 에이전트가 있는 경우이 설정을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-245">If you have agents who use Skype or Business, don't enable this setting.</span></span>
- <span data-ttu-id="8a337-246">**라운드 로빈** 각 호출 에이전트가 대기열에서 같은 개수의 호출을 받을 수 있도록 수신 전화의 라우팅을 분산 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-246">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="8a337-247">이는 모든 통화 에이전트 간에 동일한 기회를 보장 하기 위해 인바운드 영업 환경에서 바람직 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-247">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

<span data-ttu-id="8a337-248">![숫자 4의 아이콘, 이전 스크린샷 ](media/teamscallout4.png)
 **현재 상태 기반 라우팅** 현재 상태 기반 라우팅에는 호출 에이전트의 사용 가능 여부를 사용 하 여 선택한 라우팅 메서드의 호출 라우팅 목록에 에이전트가 포함 되어야 하는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-248">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**Presence-based routing** Presence-based routing uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="8a337-249">가용성 상태가 **사용 가능** 으로 설정 된 통화 에이전트는 통화 라우팅 목록에 포함 되며 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-249">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="8a337-250">가용성 상태가 다른 상태로 설정 된 에이전트는 통화 라우팅 목록에서 제외 되며, 해당 사용 가능 상태가 다시 **사용 가능**으로 변경 될 때까지 통화를 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-250">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span>  

<span data-ttu-id="8a337-251">라우팅 메서드를 사용 하 여 현재 상태 기반 통화 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-251">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="8a337-252">에이전트가 전화를 opts 경우 사용 가능한 상태에 관계 없이 통화 라우팅 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-252">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8a337-253">비즈니스용 Skype 클라이언트를 사용 하는 상담원은 사용 가능 상태에 관계 없이 상태 기반 라우팅이 사용 되는 경우 통화 라우팅 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-253">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled, regardless of their availability status.</span></span> <span data-ttu-id="8a337-254">통화 라우팅 목록에 없는 상담원은 통화를 수신 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-254">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="8a337-255">비즈니스용 Skype를 사용 하는 에이전트가 있는 경우 현재 상태 기반 통화 회람을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-255">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a337-256">고용량 통화를 위해 대기 하는 경우 권장 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-256">For high volume calls queues the recommended settings are:</span></span>
>
> <span data-ttu-id="8a337-257">컨퍼런스 모드: 자동</span><span class="sxs-lookup"><span data-stu-id="8a337-257">Conference mode: Auto</span></span><br>
> <span data-ttu-id="8a337-258">라우팅 방법: 전화 교환 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a337-258">Routing method: Attendant routing</span></span><br>
> <span data-ttu-id="8a337-259">현재 상태 기반 라우팅: 설정</span><span class="sxs-lookup"><span data-stu-id="8a337-259">Presence-based routing: On</span></span><br>
> <span data-ttu-id="8a337-260">에이전트 알림 시간: 20 초</span><span class="sxs-lookup"><span data-stu-id="8a337-260">Agent alert time: 20 seconds</span></span>


### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="8a337-261">에이전트 옵트아웃 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="8a337-261">Select an agent opt-out option</span></span>

![번호 매기기 설명선이 있는 에이전트 옵트아웃 옵션 스크린샷](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="8a337-263">![숫자 1의 아이콘, 이전 스크린샷 에이전트의 설명선을 참조 하 여 전화를 받지 못하는 경우, ](media/teamscallout1.png)
 **Agent can opt out of getting calls** 이 옵션을 사용 하 여 통화 대기열 에이전트에서 특정 큐의 통화를 옵트아웃 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-263">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="8a337-264">이 옵션을 사용 하도록 설정 하면이 큐의 모든 에이전트가 해당 통화 대기열의 통화를 시작 하거나 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-264">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="8a337-265">언제 든 지 에이전트 옵트아웃 (opt out) 권한을 취소할 수 있으며,이 큐에 대 한 에이전트가 자동으로 다시 옵트인 되도록 (모든 에이전트의 기본 설정) 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-265">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="8a337-266">옵트아웃 옵션에 액세스 하려면 상담원은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-266">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="8a337-267">바탕 화면 비즈니스용 Skype 클라이언트에서 **옵션** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-267">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="8a337-268">**착신 전환** 탭에서 **온라인 설정 편집** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-268">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="8a337-269">사용자 설정 페이지에서 **통화 대기열**을 클릭 한 다음 큐에서 옵트아웃 (opt out) 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-269">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a337-270">비즈니스용 Skype Desktop이 아닌 앱 또는 끝점을 사용 하는 상담원은 사용자 설정 포털의 옵트아웃 옵션에 액세스할 수 있습니다 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) .</span><span class="sxs-lookup"><span data-stu-id="8a337-270">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="8a337-271">에이전트가 Microsoft 팀 데스크톱 클라이언트에 있는 경우에는 통화 설정을 사용 하 여 옵트아웃 (opt out) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-271">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="8a337-272">![숫자 2의 아이콘으로, 이전 스크린샷 ](media/teamscallout2.png)
 **에이전트 알림 설정** 의 설명선을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-272">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="8a337-273">직렬 또는 라운드 로빈 라우팅 방법이 다음 에이전트로 이동 하기 전에 에이전트의 호출을 알리는 기간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-273">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="8a337-274">기본 설정은 30 초 이지만 최대 3 분까지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-274">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="8a337-275">통화 오버플로 및 시간 제한 처리 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="8a337-275">Set the call overflow and timeout handling options</span></span>

![숫자 매기기 설명선이 있는 오버플로 처리 옵션 스크린샷](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="8a337-277">![숫자 1의 아이콘으로, 이전 스크린샷의 설명선을 참조 합니다 ](media/teamscallout1.png)
 .**대기열의 최대 통화** 는 큐에서 동시에 대기할 수 있는 최대 통화를 설정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-277">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="8a337-278">기본값은 50 이지만, 0에서 200 까지의 범위에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-278">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="8a337-279">이 제한에 도달 하면 아래에 **최대 통화 수에 도달할 때** 설정 하는 방법에 따라 통화가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-279">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="8a337-280">![숫자 2의 아이콘으로, ](media/teamscallout2.png)
 호출 대기열이 최대 크기에 도달 하면**최대 호출 수에 도달 하면** 이전 스크린샷의 설명선을 참조 합니다 ( **큐 설정의 최대 통화** 수를 사용 하 여 설정). 새 수신 전화에 대 한 진행 상황을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-280">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="8a337-281">**연결 해제** 통화가 끊겼습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-281">**Disconnect** The call is disconnected.</span></span>

- <span data-ttu-id="8a337-282">**리디렉션 대상** 이를 선택 하는 경우 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-282">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="8a337-283">**조직의 사용자** 전화 시스템 라이선스가 있는 온라인 사용자 이며 엔터프라이즈 음성에 대해 사용 하도록 설정 되었거나 통화 요금제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-283">**Person in organization** An online user with a Phone System license and is enabled for Enterprise Voice or has a Calling Plan.</span></span>

  - <span data-ttu-id="8a337-284">**음성 앱** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-284">**Voice app** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

  - <span data-ttu-id="8a337-285">**외부 전화 번호** 지정 된 외부 전화 번호로 발신자를 전송 하려면이를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-285">**External phone number** Choose this to transfer the caller to an external phone number that you specify.</span></span> <span data-ttu-id="8a337-286">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-286">Note the following:</span></span>

    - <span data-ttu-id="8a337-287">PSTN을 전송 하는 응용 프로그램에 연결 된 리소스 계정은 전화 번호를가지고 있고 가상 전화 시스템 라이선스를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-287">The resource account associated with the application making the PSTN transfer out must have a phone number and be assigned a Virtual Phone System license.</span></span> <span data-ttu-id="8a337-288">전화 시스템 라이선스가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-288">Phone System licenses aren't supported.</span></span> <span data-ttu-id="8a337-289">또한 리소스 계정에는 다음 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-289">Additionally, the resource account must have one of the following:</span></span>
        - <span data-ttu-id="8a337-290">통화 요금제 번호가 있는 자원 계정의 경우, [통화 요금제](calling-plans-for-office-365.md) 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-290">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
        - <span data-ttu-id="8a337-291">직접 라우팅 번호가 있는 리소스 계정의 경우 [온라인 음성 라우팅 정책을](manage-voice-routing-policies.md)할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-291">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
    - <span data-ttu-id="8a337-292">표시 되는 아웃 바운드 전화 번호는 다음과 같이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-292">The outbound phone number that's displayed is determined as follows:</span></span>
        - <span data-ttu-id="8a337-293">통화 요금제 번호의 경우 최초 발신자의 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-293">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
        - <span data-ttu-id="8a337-294">직접 라우팅 번호의 경우 전송 되는 숫자는 다음과 같이 SBC에 대 한 P-어설션된-Identity (PAI) 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-294">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
            - <span data-ttu-id="8a337-295">사용 안 함으로 설정 하면 최초 발신자의 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-295">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="8a337-296">이 설정이 기본값 이며 권장 되는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-296">This is the default and recommended setting.</span></span>
            - <span data-ttu-id="8a337-297">사용으로 설정 하면 리소스 계정 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-297">If set to Enabled, the resource account phone number is displayed.</span></span>
    - <span data-ttu-id="8a337-298">통화 요금제 trunks와 다이렉트 라우팅 trunks 간에 전송이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-298">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>
    
  - <span data-ttu-id="8a337-299">보이스 **메일** 조직의 사용자가이 통화 대기열에서 받은 음성 메일에 액세스 해야 하는 Microsoft 365 그룹을 선택 하 고 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-299">**Voicemail** Select the Microsoft 365 group that contains the users in your organization that need to access voicemail received by this call queue, and then select one of the following:</span></span>
      - <span data-ttu-id="8a337-300">**오디오 파일 재생** 이 옵션을 선택 하는 경우에는 **파일 업로드** 를 선택 하 여 녹음 된 인사말 메시지를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-300">**Play an audio file** If you choose this option, select **Upload file** to upload a recorded greeting message.</span></span> <span data-ttu-id="8a337-301">기록의 크기는 5mb를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-301">The recording can be no larger than 5 MB.</span></span> 
      - <span data-ttu-id="8a337-302">**인사말 메시지 입력** 이 옵션을 선택 하는 경우 시스템에서 읽을 텍스트를 입력 합니다 (최대 1000 자).</span><span class="sxs-lookup"><span data-stu-id="8a337-302">**Type in a greeting message** If you choose this option, enter text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="8a337-303">예를 들어 이번에는 전화를 걸 수 없음을 "미안 하 게 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-303">For example, you can type "Sorry that we can't take your call at this time.</span></span> <span data-ttu-id="8a337-304">귀하의 이름, 전화번호, 그리고 통화를 하기 위한 이유는 비프음 후에 남겨 주십시오. "</span><span class="sxs-lookup"><span data-stu-id="8a337-304">Please leave your name, phone number, and reason for your call after the beep."</span></span>

      <span data-ttu-id="8a337-305">보이스 메일 메시지의 음성-텍스트 기록을 사용 하려는 경우에는 기록을 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="8a337-305">Turn on transcription if you want to enable voice-to-text transcription of voicemail messages.</span></span>

      <span data-ttu-id="8a337-306">보이스 메일 메시지는 사용자가 지정한 Microsoft 365 그룹으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-306">Voicemail messages are sent to the Microsoft 365 group you specify.</span></span> <span data-ttu-id="8a337-307">음성 메일 메시지에 액세스 하려면 해당 그룹의 구성원이 Outlook의 그룹으로 이동 하 여 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-307">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

* * *

<span data-ttu-id="8a337-308">![숫자 3의 아이콘, 이전 스크린샷의 설명선 참조 ](media/teamscallout3.png)
 **시간 초과: 최대 대기 시간** 또한 호출이 시간 초과 되기 전에 대기 또는 연결 해제 해야 하는 시간을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-308">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="8a337-309">리디렉션 위치는 **통화 시간** 설정을 설정 하는 방법을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-309">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="8a337-310">0에서 45 분 까지의 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-310">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="8a337-311">Timeout 값을 초 단위로 15 초 간격으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-311">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="8a337-312">이를 통해 호출 흐름을 보다 세밀 하 게 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-312">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="8a337-313">예를 들어 30 초 내에 에이전트가 응답 하지 않는 모든 통화가 디렉터리 검색 자동 전화 교환으로 이동 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-313">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="8a337-314">![숫자 4의 아이콘, 호출이 ](media/teamscallout4.png)
 **큐 설정에 대기할 수** 있는 시간에 대해 설정한 제한 시간에 도달 했을 때**전화를 건** 후의 이전 스크린샷에 대 한 설명선을 참조 하는 경우, 통화에 발생 하는 상황을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-314">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="8a337-315">**연결 해제** 통화가 끊겼습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-315">**Disconnect** The call is disconnected.</span></span>

- <span data-ttu-id="8a337-316">**착신 전환 대상:** 이 옵션을 선택 하면 다음 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-316">**Redirect this call to** When you choose this, you have these options:</span></span>

  - <span data-ttu-id="8a337-317">**조직의 사용자** 전화 시스템 라이선스가 있고 엔터프라이즈 음성 또는 통화 요금제를 사용 하는 온라인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-317">**Person in organization** An online user with a Phone System license and enabled for Enterprise Voice or have Calling Plans.</span></span>

  - <span data-ttu-id="8a337-318">**음성 앱** 이미 만든 통화 대기열 또는 자동 전화 교환 중 하 나와 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-318">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

  - <span data-ttu-id="8a337-319">**외부 전화 번호** 지정 된 외부 전화 번호로 발신자를 전송 하려면이를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-319">**External phone number** Choose this to transfer the caller to an external phone number that you specify.</span></span> <span data-ttu-id="8a337-320">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-320">Note the following:</span></span>

    - <span data-ttu-id="8a337-321">PSTN을 전송 하는 응용 프로그램에 연결 된 리소스 계정은 전화 번호를가지고 있고 가상 전화 시스템 라이선스를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-321">The resource account associated with the application making the PSTN transfer out must have a phone number and be assigned a Virtual Phone System license.</span></span> <span data-ttu-id="8a337-322">전화 시스템 라이선스가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-322">Phone System licenses aren't supported.</span></span> <span data-ttu-id="8a337-323">또한 리소스 계정에는 다음 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-323">Additionally, the resource account must have one of the following:</span></span>
        - <span data-ttu-id="8a337-324">통화 요금제 번호가 있는 자원 계정의 경우, [통화 요금제](calling-plans-for-office-365.md) 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-324">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
        - <span data-ttu-id="8a337-325">직접 라우팅 번호가 있는 리소스 계정의 경우 [온라인 음성 라우팅 정책을](manage-voice-routing-policies.md)할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-325">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
    - <span data-ttu-id="8a337-326">표시 되는 아웃 바운드 전화 번호는 다음과 같이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-326">The outbound phone number that's displayed is determined as follows:</span></span>
        - <span data-ttu-id="8a337-327">통화 요금제 번호의 경우 최초 발신자의 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-327">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
        - <span data-ttu-id="8a337-328">직접 라우팅 번호의 경우 전송 되는 숫자는 다음과 같이 SBC에 대 한 P-어설션된-Identity (PAI) 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-328">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
            - <span data-ttu-id="8a337-329">사용 안 함으로 설정 하면 최초 발신자의 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-329">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="8a337-330">이 설정이 기본값 이며 권장 되는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-330">This is the default and recommended setting.</span></span>
            - <span data-ttu-id="8a337-331">사용으로 설정 하면 리소스 계정 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-331">If set to Enabled, the resource account phone number is displayed.</span></span>
    - <span data-ttu-id="8a337-332">통화 요금제 trunks와 다이렉트 라우팅 trunks 간에 전송이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-332">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>
    - <span data-ttu-id="8a337-333">보이스 **메일** 조직의 사용자가이 통화 대기열에서 받은 음성 메일에 액세스 해야 하는 Microsoft 365 그룹을 선택 하 고 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-333">**Voicemail** Select the Microsoft 365 group that contains the users in your organization that need to access voicemail received by this call queue, and then select one of the following:</span></span>
      - <span data-ttu-id="8a337-334">**오디오 파일 재생** 이 옵션을 선택 하는 경우에는 **파일 업로드** 를 선택 하 여 녹음 된 인사말 메시지를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-334">**Play an audio file** If you choose this option, select **Upload file** to upload a recorded greeting message.</span></span> <span data-ttu-id="8a337-335">기록의 크기는 5mb를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-335">The recording can be no larger than 5 MB.</span></span>
      
      - <span data-ttu-id="8a337-336">**인사말 메시지 입력** 이 옵션을 선택 하는 경우 시스템에서 읽을 텍스트를 입력 합니다 (최대 1000 자).</span><span class="sxs-lookup"><span data-stu-id="8a337-336">**Type in a greeting message** If you choose this option, enter text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="8a337-337">예를 들어 이번에는 전화를 걸 수 없음을 "미안 하 게 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-337">For example, you can type "Sorry that we can't take your call at this time.</span></span> <span data-ttu-id="8a337-338">귀하의 이름, 전화번호, 그리고 통화를 하기 위한 이유는 비프음 후에 남겨 주십시오. "</span><span class="sxs-lookup"><span data-stu-id="8a337-338">Please leave your name, phone number, and reason for your call after the beep."</span></span>

      <span data-ttu-id="8a337-339">보이스 메일 메시지의 음성-텍스트 기록을 사용 하려는 경우에는 기록을 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="8a337-339">Turn on transcription if you want to enable voice-to-text transcription of voicemail messages.</span></span>

      <span data-ttu-id="8a337-340">보이스 메일 메시지는 사용자가 지정한 Microsoft 365 그룹으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-340">Voicemail messages are sent to the Microsoft 365 group you specify.</span></span> <span data-ttu-id="8a337-341">음성 메일 메시지에 액세스 하려면 해당 그룹의 구성원이 Outlook의 그룹으로 이동 하 여 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-341">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="8a337-342">발신 전화의 발신자 ID 변경</span><span class="sxs-lookup"><span data-stu-id="8a337-342">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="8a337-343">호출 에이전트의 id를 보호 하려면 다음 예제와 같이 **새 CsCallingLineIdentity** cmdlet을 사용 하 여 통화 큐, 자동 전화 교환 또는 서비스 번호로의 발신 호출에 대 한 발신자 ID를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-343">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

```powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="8a337-344">그런 다음 다음 예제와 같이 **CallingLineIdentity** cmdlet을 사용 하 여 사용자에 게 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-344">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

```powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="8a337-345">자세한 내용은 [조직에서 발신자 ID를 사용 하는 방법](/microsoftteams/how-can-caller-id-be-used-in-your-organization)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-345">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="8a337-346">통화 대기열 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8a337-346">Call queue cmdlets</span></span>

<span data-ttu-id="8a337-347">또한 Windows PowerShell을 사용 하 여 통화 대기열을 만들고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-347">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="8a337-348">다음은 통화 대기열을 관리 하는 데 사용 하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-348">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="8a337-349">새로운 CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8a337-349">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="8a337-350">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8a337-350">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="8a337-351">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8a337-351">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="8a337-352">제거-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8a337-352">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="8a337-353">Windows PowerShell에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="8a337-353">More about Windows PowerShell</span></span>

- <span data-ttu-id="8a337-354">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-354">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8a337-355">Windows PowerShell을 사용 하 여 단일 관리 지점으로 Microsoft 365 또는 Office 365 및 Microsoft 팀을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-355">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="8a337-356">여러 작업이 수행 되는 경우 일상 업무를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-356">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8a337-357">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-357">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="8a337-358">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="8a337-358">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="8a337-359">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="8a337-359">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="8a337-360">Windows PowerShell에는 여러 사용자가 한 번에 변경할 경우 Microsoft 팀 관리 센터에서 속도, 단순성, 생산성에 많은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-360">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="8a337-361">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8a337-361">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="8a337-362">Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365 관리</span><span class="sxs-lookup"><span data-stu-id="8a337-362">Manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="8a337-363">Windows PowerShell용 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="8a337-363">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="8a337-364">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8a337-364">Related topics</span></span>

[<span data-ttu-id="8a337-365">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8a337-365">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="8a337-366">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="8a337-366">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="8a337-367">오디오 회의 및 통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="8a337-367">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="8a337-368">새로운 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="8a337-368">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
