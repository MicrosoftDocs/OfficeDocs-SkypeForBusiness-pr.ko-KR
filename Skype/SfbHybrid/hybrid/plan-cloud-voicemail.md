---
title: 온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 계획 | PBX 비즈니스용 Skype 서버 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 이 문서에서는 Microsoft Cloud 음성 메일 서비스를 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대해 설명 합니다. 클라우드 음성 메일을 구성 하는 방법에 대 한 자세한 내용은 클라우드 음성 메일 구성을 참조 하세요.
ms.openlocfilehash: 30a4983c79f4a7cddd274c272b5a094c17653bbb
ms.sourcegitcommit: 7c08d88dcaa85e34e93131bb9a5a64597c6d8155
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210634"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="1632e-104">온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="1632e-104">Plan Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="1632e-105">개요</span><span class="sxs-lookup"><span data-stu-id="1632e-105">Overview</span></span>

<span data-ttu-id="1632e-106">이 문서에서는 온-프레미스 사용자를 위해 Microsoft 클라우드 음성 메일 서비스를 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service for your on-premises users.</span></span> <span data-ttu-id="1632e-107">클라우드 음성 메일을 구성 하는 방법에 대 한 자세한 내용은 [클라우드 음성 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1632e-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="1632e-108">클라우드 음성 메일은 exchange UM (통합 메시징)을 사용 하 여 exchange Server 2019 또는 Exchange Online에 사서함이 있는 비즈니스용 Skype 2019 음성 사용자에 게 음성 메시징 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="1632e-109">클라우드 음성 메일은 온-프레미스 및 온라인 사용자 모두에 게 다음과 같은 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="1632e-110">향상 된 음성 기록의 음성 메일 응답 및 입금 기능</span><span class="sxs-lookup"><span data-stu-id="1632e-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="1632e-111">비즈니스용 Skype 온라인 또는 Outlook 클라이언트를 사용 하 여 사용자의 Exchange 사서함에 있는 음성 메일에 액세스</span><span class="sxs-lookup"><span data-stu-id="1632e-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span>

- <span data-ttu-id="1632e-112">Office 365 웹 기반 포털을 사용 하 여 음성 메일 옵션을 관리 하는 기능</span><span class="sxs-lookup"><span data-stu-id="1632e-112">The ability to use the Office 365 web-based portal to manage voicemail options</span></span>

- <span data-ttu-id="1632e-113">온-프레미스 또는 클라우드에서 Exchange 사서함 지원</span><span class="sxs-lookup"><span data-stu-id="1632e-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="1632e-114">Exchange Online 통합 메시징의 기존 사용자 인사말 활용</span><span class="sxs-lookup"><span data-stu-id="1632e-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

<span data-ttu-id="1632e-115">기능 비교에 대 한 자세한 내용은 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션을 계획](plan-um-migration.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1632e-115">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="1632e-116">비즈니스용 Skype 서버 2019에서는 사서함이 이전 버전의 Exchange Server (2013, 2016)에 있는 사용자에 대해 Exchange UM을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-116">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="1632e-117">Exchange Server 및 비즈니스용 Skype 서버 버전을 기반으로 사용 되는 음성 메일 솔루션을 이해 하는 것은 비즈니스용 Skype 서버 2019 또는 Exchange Server 2019로의 마이그레이션을 계획 하는 데 있어 중요 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-117">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="1632e-118">마이그레이션 및 상호 운용성에 대 한 자세한 내용은 [Plan For 비즈니스용 Skype 서버 및 Exchange Server migration](plan-um-migration.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1632e-118">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="1632e-119">클라우드 음성 메일을 사용 하는 경우에는 다음과 같은 이유로 관리 작업이 크게 간단해 집니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-119">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="1632e-120">Exchange UM 역할을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-120">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="1632e-121">클라우드 음성 메일의 설치 작업은 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-121">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="1632e-122">음성 메일 기능에 대 한 업데이트는 클라우드에서 직접 배달 되므로 사용자는 CUs (누적 업데이트)에 대 한 종속성이 낮아 최신 기능 및 업데이트에 항상 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-122">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="1632e-123">온-프레미스 및 온라인 Exchange 사서함 둘 다에 대해 동일한 컨트롤 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-123">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="1632e-124">이러한 컨트롤에 대 한 자세한 내용은 [전화 시스템 음성 메일 설정을](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1632e-124">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).</span></span>

<span data-ttu-id="1632e-125">다음 다이어그램에서는 하이브리드 배포의 클라우드 음성 메일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-125">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>

![SfB Cloud 음성 메일](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="1632e-127">응답 하지 않은 호출은 다음과 같이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-127">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="1632e-128">비즈니스용 Skype 2019 온-프레미스에 있는 사용자의 경우 온-프레미스 비즈니스용 Skype 서버에서 온라인 클라우드 음성 메일 서비스로 응답 하지 않은 전화가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-128">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span>
2. <span data-ttu-id="1632e-129">이 서비스는 기록을 포함 하 여 음성 메일을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-129">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="1632e-130">그런 다음이 서비스는 사서함이 온-프레미스 또는 온라인 인지에 관계 없이 사용자의 Exchange 사서함에 있는 음성 메일을 저축금과 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-130">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="1632e-131">사용자는 비즈니스용 Skype 또는 Outlook 클라이언트에서 음성 메일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-131">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="1632e-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1632e-132">Requirements</span></span>

<span data-ttu-id="1632e-133">다음 요구 사항에 따라 지원 되는 토폴로지에서 비즈니스용 Skype 서버를 이미 배포 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-133">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="1632e-134">요구 사항은 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-134">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="1632e-135">이미 Exchange UM online을 사용 하 고 있고 비즈니스용 Skype 2019로 업그레이드 하는 경우 호스트 된 음성 메일 정책을 수정 하 고 호스팅 공급자가 올바르게 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-135">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="1632e-136">자세한 내용은 [클라우드 음성 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1632e-136">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="1632e-137">Exchange UM을 온-프레미스에서 사용 중이거나 Exchange UM online 및 온-프레미스를 사용 하는 사용자가 섞여 있는 경우에는 호스팅된 음성 메일 정책 및 호스팅 공급자를 모두 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-137">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="1632e-138">자세한 내용은 [클라우드 음성 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1632e-138">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="1632e-139">클라우드 음성 메일의 새 구성을 위해 [클라우드 음성 메일 서비스 구성](configure-cloud-voicemail.md)에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-139">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="1632e-140">위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 음성 메일 서비스에 연결 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-140">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="1632e-141">하이브리드 연결</span><span class="sxs-lookup"><span data-stu-id="1632e-141">Hybrid connectivity.</span></span> <span data-ttu-id="1632e-142">비즈니스용 Skype 서버가 이미 배포 되어 있고 온-프레미스 사용자가 클라우드 음성 메일을 사용 하도록 설정 하려는 경우 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-142">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="1632e-143">이를 분할 도메인 구성 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-143">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="1632e-144">자세한 내용은 비즈니스용 [Skype 서버 및 office 365의 하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [비즈니스용 Skype 서버 및 office 365 간의 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1632e-144">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="1632e-145">비즈니스용 Skype 서버에서 Enterprise Voice 및 호스팅된 음성 메일을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-145">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="1632e-146">외부 EWS (Exchange 웹 서비스) URL 및 자동 검색을 설정 해야 하거나 일부 클라우드 음성 메일 기능이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-146">An External Exchange Web Services (EWS) URL and Autodiscover must be set up or some Cloud Voicemail features will be limited.</span></span>

- <span data-ttu-id="1632e-147">온-프레미스 전용 배포&#x2014;, 즉 Exchange 및 비즈니스용 Skype 온-프레미스 서버를&#x2014;하지만 클라우드 음성 메일을 활용 하려는 경우에는 전화 시스템 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-147">If you have an on-premises only deployment&#x2014;that is, only Exchange and Skype for Business on-premises servers&#x2014;but you want to take advantage of Cloud Voicemail, you will need a Phone System license.</span></span>

## <a name="migration-and-interoperability"></a><span data-ttu-id="1632e-148">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="1632e-148">Migration and interoperability</span></span>

<span data-ttu-id="1632e-149">비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019을 배포 하려는 경우에는 음성 메시징에 대 한 지속적인 서비스를 위해 마이그레이션을 신중 하 게 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-149">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="1632e-150">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-150">Keep the following in mind:</span></span>

- <span data-ttu-id="1632e-151">Exchange 서버 2019에서 더 이상 Exchange UM 기능을 제공 하지 않음</span><span class="sxs-lookup"><span data-stu-id="1632e-151">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="1632e-152">비즈니스용 Skype 서버 2019이 더 이상 Exchange Online UM에 통합 되지 않음</span><span class="sxs-lookup"><span data-stu-id="1632e-152">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="1632e-153">버전 상호 운용성 및 클라우드 음성 메일에 대해 지원 되는 토폴로지는 다음 표에 나와 있으며,이는 사용자가 사용할 수 있는 비즈니스용 Skype 서버 버전과 Exchange 사서함을 제공 하는 가능한 버전을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-153">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table, which compares the Skype for Business Server versions the user might be homed on with the possible version providing their Exchange Mailbox.</span></span> <span data-ttu-id="1632e-154">Exchange Online 또는 Exchange Server 2019에서 비즈니스용 Skype 2019을 사용 하려는 경우에는 클라우드 음성 메일을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-154">You need to use Cloud Voicemail if you want to use Skype for Business 2019 with Exchange Online or Exchange Server 2019.</span></span>

| | <span data-ttu-id="1632e-155">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="1632e-155">Exchange Server 2013</span></span> | <span data-ttu-id="1632e-156">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="1632e-156">Exchange Server 2016</span></span> | <span data-ttu-id="1632e-157">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="1632e-157">Exchange Server 2019</span></span> | <span data-ttu-id="1632e-158">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1632e-158">Exchange Online</span></span>   |
|:---    |:--- |:--- |:--- |:---  |
| <span data-ttu-id="1632e-159">비즈니스용 Skype 서버 2019</span><span class="sxs-lookup"><span data-stu-id="1632e-159">Skype for Business Server 2019</span></span> | <span data-ttu-id="1632e-160">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="1632e-160">Exchange Server UM</span></span> | <span data-ttu-id="1632e-161">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="1632e-161">Exchange Server UM</span></span> | <span data-ttu-id="1632e-162">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="1632e-162">Cloud Voicemail</span></span> | <span data-ttu-id="1632e-163">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="1632e-163">Cloud Voicemail</span></span> |
| <span data-ttu-id="1632e-164">비즈니스용 Skype 서버 2015</span><span class="sxs-lookup"><span data-stu-id="1632e-164">Skype for Business Server 2015</span></span> | <span data-ttu-id="1632e-165">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="1632e-165">Exchange Server UM</span></span> | <span data-ttu-id="1632e-166">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="1632e-166">Exchange Server UM</span></span> | <span data-ttu-id="1632e-167">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="1632e-167">Cloud Voicemail</span></span> | <span data-ttu-id="1632e-168">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="1632e-168">Cloud Voicemail</span></span> |
| <span data-ttu-id="1632e-169">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1632e-169">Lync Server 2013</span></span> <br>  | <span data-ttu-id="1632e-170">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="1632e-170">Exchange Server UM</span></span> | <span data-ttu-id="1632e-171">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="1632e-171">Exchange Server UM</span></span> | <span data-ttu-id="1632e-172">미지원</span><span class="sxs-lookup"><span data-stu-id="1632e-172">Not Supported</span></span> | <span data-ttu-id="1632e-173">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="1632e-173">Cloud Voicemail</span></span> |

<span data-ttu-id="1632e-174">Microsoft는 다음과 같은 마이그레이션 경로를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-174">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="1632e-175">비즈니스용 Skype 서버 2019로 업그레이드 하는 경우 exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019을 사용 하는 경우 클라우드 음성 메일로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-175">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>
- <span data-ttu-id="1632e-176">Exchange Server 2019로 업그레이드 하는 경우 비즈니스용 Skype 서버 음성 메시징의 이전 버전의 Exchange Server UM을 사용 하는 경우에는 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-176">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="1632e-177">그렇지 않으면 음성 메시징 기능을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-177">Otherwise, voice messaging capabilities will be lost.</span></span>
- <span data-ttu-id="1632e-178">비즈니스용 skype 서버 2019로 업그레이드 하 고 Exchange Online UM과의 음성 메일에 비즈니스용 Skype 서버 2015을 구성 하는 경우 사용자의 음성 메일이 Exchange Online UM에서 클라우드 음성 2019 메일로 자동으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="1632e-178">If you are upgrading to Skype for Business Server 2019, and have Skype for Business Server 2015 configured for voicemail with Exchange Online UM, users' voicemail will automatically migrate from Exchange Online UM to Cloud Voicemail when their account is moved to Skype for Business Server 2019.</span></span> 

<span data-ttu-id="1632e-179">마이그레이션 계획에 대 한 자세한 내용은 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션을 계획](plan-um-migration.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1632e-179">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
