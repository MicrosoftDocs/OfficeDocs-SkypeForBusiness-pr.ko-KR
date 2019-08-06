---
title: 클라우드 자동 전화 교환 계획
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환 사용 개요
ms.openlocfilehash: 635d9c6548ba807153876d63ad228f69646e93c8
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207036"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="dd77a-103">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="dd77a-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="dd77a-104">Exchange 통합 메시징에 사용 되는 자동 전화 교환 (Exchange Server 2013 또는 Exchange Server 2016)을 Exchange Server 2019 또는 Exchange Online에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="dd77a-105">비즈니스용 Skype 서버 2019이 이러한 Exchange 버전 중 하 나와 통합 된 경우에는 전화 시스템과 관련 된 온라인 클라우드 음성 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="dd77a-106">Exchange server 2013 및 2016의 exchange UM 서비스를 클라우드로 이동 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="dd77a-107">이것은 자동 전화 교환 같은 통합 메시징 기능을 사용 하려는 경우 비즈니스용 Skype 서버 2019을 하이브리드 구현 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="dd77a-108">자세한 내용은 [비즈니스용 Skype 서버 및 Office 365에서 하이브리드 연결 구성을](configure-hybrid-connectivity.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-108">See [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="dd77a-109">자동 전화 교환은 고객 전화를 받고, 인사말을 재생 하 고, 메뉴 옵션을 제공 하 고, 음성 또는 다이얼 패드를 사용 하는 호출자와 상호 작용 하 여 전화를 올바른 목적지로 라우팅하는 클라우드 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-109">An Auto attendant is a cloud service that accept customer calls and play greetings, provide them with menu options, and interact with callers using speech or the dialpad to route their calls to the right destination.</span></span> <span data-ttu-id="dd77a-110">Microsoft 팀 관리 센터의 자동 전화 교환에 직접 연결 되는 비즈니스용 Skype Server 2019 시스템에서 각 자동 전화 교환에는 **리소스 계정** ([리소스 계정 구성](configure-onprem-ra.md)참조)이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-110">Each auto attendant is assigned a **resource account** (see[Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="dd77a-111">자동 전화 교환에 대 한 자세한 내용과 자동 전화 교환에 대 한 옵션 및 기능에 대 한 자세한 내용은 [클라우드 자동 전화 교환을](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="dd77a-112">여러 개의 Microsoft 서비스 번호 또는 하이브리드 번호를 자동 전화 교환에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-112">You can assign multiple Microsoft service numbers or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="dd77a-113">클라우드 자동 전화 교환으로 들어오는 호출은 다음과 같이 여러 경로 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![자동 전화 교환 다이어그램](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="dd77a-115">비즈니스용 Skype 서버 2019을 통해</span><span class="sxs-lookup"><span data-stu-id="dd77a-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="dd77a-116">[세션 경계 컨트롤러](/MicrosoftTeams/direct-routing-border-controllers.md) 및 [직접 라우팅](/MicrosoftTeams/direct-routing-plan.md) 통해</span><span class="sxs-lookup"><span data-stu-id="dd77a-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="dd77a-117">Office 365에서 온라인으로 홈을 통해 전화를 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-117">Via a number homed online in Office 365.</span></span>

<span data-ttu-id="dd77a-118">또한 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-118">Also see:</span></span>

- [<span data-ttu-id="dd77a-119">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="dd77a-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="dd77a-120">자동으로 수신 전화 응답 및 라우팅</span><span class="sxs-lookup"><span data-stu-id="dd77a-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="dd77a-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd77a-121">Requirements</span></span>

<span data-ttu-id="dd77a-122">다음 요구 사항은 지원 되는 토폴로지에서 비즈니스용 Skype 서버 2019이 이미 배포 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="dd77a-123">요구 사항은 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="dd77a-124">이미 Exchange UM online 또는 온-프레미스를 사용 하 고 있고 비즈니스용 Skype 2019으로 업그레이드 한 경우 자동 전화 교환의 구조를 캡처하여 클라우드 자동 전화 교환을 사용 하 여 클라우드에서 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-124">If you are already using Exchange UM online or on-premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="dd77a-125">자세한 내용은 [EXCHANGE UM 자동 전화 교환 또는 통화 대기열을 전화 시스템으로 이동](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="dd77a-126">클라우드 자동 전화 교환에 대 한 새로운 구성을 보려면 [리소스 계정 구성](configure-onprem-ra.md)에 설명 된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="dd77a-127">위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 자동 전화 교환 서비스에 연결 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="dd77a-128">하이브리드 연결.</span><span class="sxs-lookup"><span data-stu-id="dd77a-128">Hybrid connectivity.</span></span> <span data-ttu-id="dd77a-129">비즈니스용 Skype 서버를 이미 배포 하 고 온-프레미스 사용자에 대해 클라우드 자동 전화 교환을 사용 하려면 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="dd77a-130">이를 도메인 분할 구성이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="dd77a-131">자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="dd77a-132">자동 전화 교환에 전화 번호를 할당 하는 경우에는 [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="dd77a-133">각 자동 전화 교환에 대해 온라인 [리소스 계정](/MicrosoftTeams/manage-resource-accounts.md) 또는 온-프레미스 [리소스 계정을](configure-onprem-ra.md)만들고 전화 번호와 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-133">Create an online [resource account](/MicrosoftTeams/manage-resource-accounts.md) or on-premises [resource account](configure-onprem-ra.md)for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="dd77a-134">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="dd77a-134">Migration and interoperability</span></span>

<span data-ttu-id="dd77a-135">비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019을 배포 하려는 경우, 자동 전화 교환을 계속 지원 하도록 마이그레이션을 신중 하 게 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="dd77a-136">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-136">Keep the following in mind:</span></span>

- <span data-ttu-id="dd77a-137">Exchange Server 2019에서 더 이상 Exchange UM 기능을 제공 하지 않음</span><span class="sxs-lookup"><span data-stu-id="dd77a-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="dd77a-138">Exchange 통합 메시징이 만료 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-138">Exchange Unified Messaging is in retirement mode</span></span>
- <span data-ttu-id="dd77a-139">비즈니스용 Skype 서버 2019이 더 이상 Exchange Online UM과 통합 되지 않음</span><span class="sxs-lookup"><span data-stu-id="dd77a-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="dd77a-140">클라우드 자동 전화 교환는 비즈니스용 Skype 서버 2019, 2015 및 2013으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="dd77a-141">Microsoft는 다음 마이그레이션 경로를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="dd77a-142">비즈니스용 Skype 서버 2019으로 업그레이드 하는 경우 exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019을 사용 하는 경우에는 클라우드 자동 전화 교환으로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="dd77a-143">Exchange Server 2019으로 업그레이드 하는 경우 비즈니스용 Skype Server voice messaging 용 Exchange Server UM의 이전 버전을 사용 하는 경우 사서함 업그레이드 전에 비즈니스용 Skype Server 2019으로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="dd77a-144">그렇지 않으면 음성 메시지 기능이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="dd77a-145">마이그레이션 계획에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="dd77a-146">이전에 구현 된 Exchange UM 자동 전화 교환 시스템 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dd77a-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="dd77a-147">현재는 Exchange 2013 또는 2016에서 만든 UM 자동 전화 교환 시스템의 클라우드로 자동화 된 마이그레이션을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="dd77a-148">자동 전화 교환 시스템을 수동으로 다시 만들려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="dd77a-149">Exchange 관리 powershell 명령을 사용 하 여 중첩 된 자동 전화 교환 및 통화 대기열을 포함 하 여 이전 자동 교환 시스템의 구조를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-149">Use Exchange admin powershell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="dd77a-150">각 UM 자동 전화 교환 노드와 연결 된 텍스트 음성 변환 스크립트 또는 기록 된 메시지의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="dd77a-151">테스트 전화 번호 및 개체에 대 한 라이선스 할당을 포함 하 여 각 자동 전화 교환 노드에 대 한 온-프레미스 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="dd77a-152">이제 전화 시스템 같은 온라인 서비스에서 사용 하는 온-프레미스 전화 번호 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="dd77a-153">비즈니스용 Skype Online 및 전화 시스템을 사용 하 여 새 클라우드 자동 전화 교환 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-153">Implement a new Cloud auto attendant service with Skype for Business Online and Phone System.</span></span> <span data-ttu-id="dd77a-154">자세한 내용은 구현 세부 정보에 대 한 [리소스 계정 구성을](configure-onprem-ra.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="dd77a-155">이 작업을 수행할 때 각 UM 자동 전화 교환 노드와 연결 된 텍스트 음성 변환 스크립트 또는 기록 된 메시지를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="dd77a-156">클라우드 자동 전화 교환의 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="dd77a-157">이전 Exchange UM 자동 전화 교환에 할당 된 전화 번호를 새로 만든 주 클라우드 자동 전화 교환에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="dd77a-158">이러한 단계에 대 한 자세한 내용은 [EXCHANGE UM 자동 전화 교환 또는 통화 대기열을 전화 시스템으로 이동을](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd77a-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

## <a name="additional-planning-resources"></a><span data-ttu-id="dd77a-159">추가 계획 리소스</span><span class="sxs-lookup"><span data-stu-id="dd77a-159">Additional planning resources</span></span>

<span data-ttu-id="dd77a-160">사용자 요구에 대 한 정보를 수집 하는 프로세스, 자동 전화 교환 및 사용자의 구조 계획, 메뉴 프롬프트를 작성 하는 등의 간단한 비즈니스와 같은 자습서에서 [자동 전화 교환을 설정](/microsoftteams/tutorial-org-aa) 하면 팀 관리 센터에서 계획을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-160">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Teams admin center.</span></span> <span data-ttu-id="dd77a-161">자습서를 검토 하 고 연습을 사용 하 여 계획을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-161">Review the tutorial and use the exercises there to create your plan.</span></span>

<span data-ttu-id="dd77a-162">사용자의 요구에 맞는 솔리드 구조와 고객을 효율적으로 안내 하는 스크립트를 사용 하는 경우 [리소스 계정 구성을](configure-onprem-ra.md)진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-162">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="dd77a-163">[KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)에서 설명한 대로 서버 2015에서 만든 Exchange UM 자동 전화 교환을 서버 2019를 실행 하는 서버로 이동 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-163">As mentioned in [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="dd77a-164">시간이 coexistance 모드로 실행 되는 비즈니스용 Skype Server 2015 풀에 보관 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd77a-164">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd77a-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd77a-165">See Also</span></span>

[<span data-ttu-id="dd77a-166">비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="dd77a-166">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="dd77a-167">자원 계정 구성</span><span class="sxs-lookup"><span data-stu-id="dd77a-167">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="dd77a-168">전화 사용자 인터페이스를 사용 하 여 사용자 지정 음성 안내 기록 사용</span><span class="sxs-lookup"><span data-stu-id="dd77a-168">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="dd77a-169">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="dd77a-169">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="dd77a-170">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="dd77a-170">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="dd77a-171">Exchange UM: [자동으로 수신 전화 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="dd77a-171">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="dd77a-172">비즈니스용 Skype 서버와 Office 365 하이브리드 연결 계획</span><span class="sxs-lookup"><span data-stu-id="dd77a-172">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="dd77a-173">비즈니스용 Skype 서버와 Office 365 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="dd77a-173">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="dd77a-174">KB4480742: 연락처 개체를 비즈니스용 Skype Server 2019로 이동한 후 구독자 액세스 또는 자동 전화 교환에 대 한 빠른 사용량이 나 "500 Server Internal" 오류가 발생 함</span><span class="sxs-lookup"><span data-stu-id="dd77a-174">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
