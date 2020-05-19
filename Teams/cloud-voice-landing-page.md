---
title: Microsoft 팀의 클라우드 음성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: 클라우드 음성 기능에 대해 자세히 알아보고 필요한 배포 결정을 이해 하세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952eb7064844cf0e77e829cd2506c4303504074c
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281673"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="c5ba9-103">Microsoft 팀의 클라우드 음성</span><span class="sxs-lookup"><span data-stu-id="c5ba9-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="c5ba9-104">[시작](get-started-with-teams-quick-start.md)을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="c5ba9-105">조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="c5ba9-106">[모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="c5ba9-107">이제 사용자에 게 클라우드 음성 기능을 추가할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="c5ba9-108">클라우드 음성은 PBX (개인 브랜치 교환) 기능 및 PSTN (공개 통신 네트워크)에 연결 하기 위한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="c5ba9-109">이 문서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 클라우드 음성 설정을 변경 해야 하는지 여부를 결정 하는 데 도움이 되며, 각 변경 내용을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="c5ba9-110">두 그룹으로 설정 된 핵심 [변경 내용](#core-deployment-decisions)집합부터 시작 하 여 설정을 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="c5ba9-111">두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="c5ba9-112">모든 조직에서 핵심 의사 결정을 수행 하는 것이 좋으며 조직에 추가 요구 사항이 있는 경우 다음 자료를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="c5ba9-113">클라우드 음성에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5ba9-113">Learn more about cloud voice</span></span>

<span data-ttu-id="c5ba9-114">다음 문서는 팀에서 클라우드 음성 기능을 배포 하 고 사용 하는 방법에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="c5ba9-115">Office 365의 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="c5ba9-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="c5ba9-116">통화 요금제가 포함 되어 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="c5ba9-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="c5ba9-117">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="c5ba9-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="c5ba9-118">클라우드 음성 배포</span><span class="sxs-lookup"><span data-stu-id="c5ba9-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="c5ba9-119">Microsoft 전화 통신 솔루션</span><span class="sxs-lookup"><span data-stu-id="c5ba9-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="c5ba9-120">전화 시스템에 대 한 자세한 내용을 보려면 다음 세션을 시청 하세요. [Microsoft 팀의 전화 시스템 소개](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="c5ba9-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="c5ba9-121">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="c5ba9-121">Core deployment decisions</span></span>

<span data-ttu-id="c5ba9-122">대부분의 조직이 변경하려는 설정입니다 (Teams의 기본 설정이 조직에 적합하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="c5ba9-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="c5ba9-123">전화 시스템 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="c5ba9-123">Phone System (Office 365)</span></span>

<span data-ttu-id="c5ba9-124">전화 시스템은 Office 365 클라우드에서 통화 제어 및 PBX (개인 브랜치 교환) 기능을 사용 하도록 설정 하기 위한 Microsoft의 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="c5ba9-125">전화 시스템을 사용 하면 기존 개인 분기 교환 (PBX) 시스템을 Office 365에서 직접 전달 되는 기능 집합으로 대체 하 고 회사의 클라우드 생산성 환경에 긴밀 하 게 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="c5ba9-126">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-126">Ask yourself</span></span>|<span data-ttu-id="c5ba9-127">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c5ba9-128">어떤 사용자 위치 또는 사무실에서 전화 시스템을 구현 하나요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="c5ba9-129">전화 시스템에 대 한 자세한 내용은 [Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="c5ba9-130">PSTN (공개 교환 전화 네트워크)에 대 한 연결</span><span class="sxs-lookup"><span data-stu-id="c5ba9-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="c5ba9-131">사용자가 전세계에서 전화를 걸 수 있도록 휴대폰 시스템을 PSTN (공개 교환 전화 네트워크)에 연결 하려면 비즈니스 요구 사항에 따라 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="c5ba9-132">사용자에 게 다음을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-132">Ask yourself the following:</span></span>


|<span data-ttu-id="c5ba9-133">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-133">Ask yourself</span></span>|<span data-ttu-id="c5ba9-134">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="c5ba9-135">Microsoft 통화 요금제를 내 통신 회사로 사용 하 고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="c5ba9-136">자세한 내용은 통화 [요금제를 사용 하는 전화 시스템](calling-plan-landing-page.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="c5ba9-137">자체 전화 통신 회사를 사용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="c5ba9-138">자세한 내용은 [직접 라우팅이 포함 되어 있는 전화 시스템](direct-routing-landing-page.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="c5ba9-139">추가 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="c5ba9-139">Additional deployment decisions</span></span>

<span data-ttu-id="c5ba9-140">조직의 필요 및 구성에 따라 다음에 대 한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="c5ba9-141">음성 메일</span><span class="sxs-lookup"><span data-stu-id="c5ba9-141">Voicemail</span></span>
- <span data-ttu-id="c5ba9-142">통화 id</span><span class="sxs-lookup"><span data-stu-id="c5ba9-142">Calling identity</span></span>
- <span data-ttu-id="c5ba9-143">Microsoft의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="c5ba9-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="c5ba9-144">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="c5ba9-144">Dial plans</span></span>
- <span data-ttu-id="c5ba9-145">통화 큐</span><span class="sxs-lookup"><span data-stu-id="c5ba9-145">Call queues</span></span>
- <span data-ttu-id="c5ba9-146">자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="c5ba9-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="c5ba9-147">음성 메일</span><span class="sxs-lookup"><span data-stu-id="c5ba9-147">Voicemail</span></span>

<span data-ttu-id="c5ba9-148">Azure 보이스 메일 서비스를 통해 제공 되는 클라우드 보이스 메일은 Exchange 사서함에 대 한 보이스 메일 저축과 지원 하며 타사 전자 메일 시스템을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="c5ba9-149">클라우드 보이스 메일에는 조직의 모든 사용자가 기본적으로 사용 하도록 설정 된 음성 메일의 내용이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="c5ba9-150">비즈니스 요구에 따라 특정 사용자 또는 조직 전체에 대 한 보이스 메일을 사용 하지 않도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="c5ba9-151">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-151">Ask yourself</span></span>|<span data-ttu-id="c5ba9-152">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c5ba9-153">클라우드 보이스 메일을 사용 하 고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="c5ba9-154">보이스 메일 설정 절차는 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="c5ba9-155">일부 또는 전체 사용자에 대해 음성 메일을 사용 하도록 설정 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="c5ba9-156">보이스 메일 기록을 끄려면 [조직의 보이스 메일 정책 설정을](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="c5ba9-157">통화 id</span><span class="sxs-lookup"><span data-stu-id="c5ba9-157">Calling identity</span></span>

<span data-ttu-id="c5ba9-158">기본적으로 모든 아웃 바운드 통화는 지정 된 전화 번호를 통화 id (발신자 ID)로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="c5ba9-159">통화를 받는 사람은 발신자를 빠르게 확인 하 고 통화 수락 또는 거부 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="c5ba9-160">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-160">Ask yourself</span></span>|<span data-ttu-id="c5ba9-161">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c5ba9-162">발신자 ID를 마스킹 또는 사용 하지 않도록 설정 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="c5ba9-163">발신자 ID를 변경 하거나 차단 하려면 [사용자의 발신자 Id 설정을](set-the-caller-id-for-a-user.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="c5ba9-164">Microsoft의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="c5ba9-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="c5ba9-165">Microsoft에는 두 가지 유형의 전화 번호, 즉 조직의 사용자에 게 할당할 수 있는 *구독자* (사용자) 번호와 구독자 번호 보다 높은 동시 통화 용량을 갖는 유료 서비스 번호와 *서비스* 번호, 그리고 오디오 회의, 자동 전화 교환, 통화 대기열 등의 서비스에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="c5ba9-166">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-166">Ask yourself</span></span>|<span data-ttu-id="c5ba9-167">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="c5ba9-168">Microsoft에서 새 전화 번호를 필요로 하는 사용자 위치는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="c5ba9-169">전화 번호를 가져오는 방법에 대 한 자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 및 [사용자의 전화 번호 가져오기를](getting-phone-numbers-for-your-users.md)참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="c5ba9-170">어떤 종류의 전화 번호 (구독자 또는 서비스)가 필요 합니까?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="c5ba9-171">필요한 전화 번호 유형을 선택 하는 데 도움이 되도록 [통화 요금제에 사용 되는 다른 종류의 전화](different-kinds-of-phone-numbers-used-for-calling-plans.md)번호를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="c5ba9-172">기존 전화 번호를 팀에 게 이식 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-172">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="c5ba9-173">자세한 내용은 [Microsoft 팀으로 전화 번호 전송을](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-173">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="c5ba9-174">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="c5ba9-174">Dial plans</span></span>

<span data-ttu-id="c5ba9-175">Office 365의 전화 시스템 기능에 있는 다이얼 플랜은 전화 번호를 대체 형식 (일반적으로 E. \ 164 형식)으로 변환 하는 표준화 규칙 집합으로, 통화 승인 및 통화 라우팅을 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="c5ba9-176">다이얼 플랜에 대한 자세한 내용은 [다이얼 플랜이란?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="c5ba9-177">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-177">Ask yourself</span></span>|<span data-ttu-id="c5ba9-178">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c5ba9-179">조직에 사용자 지정 다이얼 플랜이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="c5ba9-180">사용자 지정 다이얼 플랜이 필요한 지 여부를 결정 하려면 [테 넌 트 다이얼 플랜 계획](what-are-dial-plans.md#planning-for-tenant-dial-plans) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="c5ba9-181">사용자 지정 다이얼 플랜을 필요로 하는 사용자는 누구이고 각 사용자에게 할당해야 하는 테넌트 다이얼 플랜은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="c5ba9-182">PowerShell의 사용자 지정 다이얼 플랜에 사용자를 추가 하려면 [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="c5ba9-183">통화 큐</span><span class="sxs-lookup"><span data-stu-id="c5ba9-183">Call queues</span></span>

<span data-ttu-id="c5ba9-184">클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화를 자동으로 대기 하는 기능, 전화를 걸고 있는 사용자가 대기 중인 음악을 수신 대기 하는 동안 사용 가능한 다음 통화 에이전트를 검색 하 여 통화를 처리 하는 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="c5ba9-185">조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="c5ba9-186">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-186">Ask yourself</span></span>|<span data-ttu-id="c5ba9-187">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c5ba9-188">내 조직에 통화 대기열이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-188">Does my organization need call queues?</span></span> | <span data-ttu-id="c5ba9-189">자세한 내용은 [클라우드 통화 대기열 만들기](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 및 [전화 시스템 설정을](setting-up-your-phone-system.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="c5ba9-190">자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="c5ba9-190">Auto attendants</span></span>

<span data-ttu-id="c5ba9-191">클라우드 자동 전화 교환을 사용 하 여 외부 및 내부 발신자가 조직의 회사 사용자 또는 부서로 전화를 걸고 배치 하거나 양도할 수 있는 조직의 메뉴 시스템을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="c5ba9-192">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="c5ba9-192">Ask yourself</span></span>|<span data-ttu-id="c5ba9-193">작업</span><span class="sxs-lookup"><span data-stu-id="c5ba9-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c5ba9-194">내 조직에 자동 전화 교환이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="c5ba9-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="c5ba9-195">자세한 내용은 [클라우드 자동 전화 교환 소개](what-are-phone-system-auto-attendants.md) 및 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="c5ba9-196">디바이스</span><span class="sxs-lookup"><span data-stu-id="c5ba9-196">Devices</span></span>

<span data-ttu-id="c5ba9-197">지원 되는 장치에 대 한 자세한 내용은 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="c5ba9-198">Microsoft 팀에서 장치 관리</span><span class="sxs-lookup"><span data-stu-id="c5ba9-198">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="c5ba9-199">IP 전화</span><span class="sxs-lookup"><span data-stu-id="c5ba9-199">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="c5ba9-200">USB 오디오 및 비디오 디바이스</span><span class="sxs-lookup"><span data-stu-id="c5ba9-200">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="c5ba9-201">장치에 대 한 지능형 통신</span><span class="sxs-lookup"><span data-stu-id="c5ba9-201">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


