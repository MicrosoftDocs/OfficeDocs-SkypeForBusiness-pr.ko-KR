---
title: 비즈니스용 Skype 온라인 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: '비즈니스용 Skype를 설치 하도록 조직의 도메인, 사용자, IM, 현재 상태를 설정 하는 방법을 알아봅니다. 오디오 회의, 전화 시스템 및 통화 요금제 및 Skype 모임 브로드캐스트를 설정 하는 방법도 알아봅니다. '
ms.openlocfilehash: c61e2b7dd4a9c4bb4e04a90ffa403e930e4d142b
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777183"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="7397a-104">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-104">Set up Skype for Business Online</span></span>

<span data-ttu-id="7397a-105">비즈니스용 Skype를 설정 하려면 전역 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-105">You must have global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="7397a-106">웹의 일부분에 대 한 액세스를 제한 하는 방화벽 또는 프록시 서버가 있는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여 비즈니스용 Skype를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="7397a-107">Skype 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-107">Setting up Skype</span></span>

<span data-ttu-id="7397a-108">Microsoft 365 또는 Office 365 구독을 사용 하 여 Skype를 설정 하는 데 도움이 필요한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-108">Looks like you need help setting up Skype with your Microsoft 365 or Office 365 subscription.</span></span> <span data-ttu-id="7397a-109">이 문서에 나와 있는 단계를 따라 설치를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="7397a-110">1. 비즈니스용 Skype 계획</span><span class="sxs-lookup"><span data-stu-id="7397a-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="7397a-111">**[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** 또는 **Business Essentials**가 있는 경우 비즈니스용 Skype를 사용 하 여 구독 중인 비즈니스의 다른 사용자에 게 온라인으로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-111">If you have **[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="7397a-112">예를 들어 비즈니스에 10 명의 사용자가 있는 경우 [IM 및 온라인 모임에 비즈니스용 skype를 사용 하](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) 고, 아래에서 2-6 단계를 수행한 후 비즈니스용 skype를 사용 하 여 비즈니스용 Skype [로 모임을](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="7397a-113">Outlook에서 온라인 모임으로도 [비즈니스용 Skype 모임을 설정할](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="7397a-114">비즈니스용 Skype를 사용 하 여 회사 *외부* 의 사용자에 게 **전화를 걸고** 수신 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="7397a-115">**옵션 1. 무료 [Skype 앱](https://www.skype.com/)을 사용**하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="7397a-116">소규모 기업 (예: 1-2 사람)이 있는 경우 Skype 앱을 사용 하는 것이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="7397a-117">국내 및 국제 전화에 사용 하는 것은 저렴 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="7397a-118">계속 해 서 컨퍼런스 통화를 개최 하 고 영상 통화를 하 고 데스크톱을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="7397a-119">[요금 및 결제 옵션을 확인](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="7397a-120">**옵션 2. 요금제를 업그레이드 하 고 Office 365에 대 한 전화 시스템 및 통화 요금제를 구입**합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="7397a-121">이 비용을 확인 하 고 전환 하는 가장 쉬운 방법은 [비즈니스 제품에 대 한 지원 팀에 문의](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 하 여 관리자의 도움을 요청 하 고 모든 작업을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="7397a-122">자세히 알아보려면 [비즈니스용 Office 365의 설정 계획](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="7397a-123">2. Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="7397a-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-124"><a name="bkmk_signin"> </a></span></span>

<span data-ttu-id="7397a-125">비즈니스용 Skype Online은 Office 365 서비스 제품군의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="7397a-126">비즈니스용 Skype Online을 설정 하려면 Office 365에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="7397a-127">이 작업을 수행 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-127">Here's how you do that:</span></span>

1. <span data-ttu-id="7397a-128">Microsoft 365 또는 Office 365 사용자 ID (예: <em>rob@fourthcoffee.com</em> )를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-128">Locate your Microsoft 365 or Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ).</span></span> <span data-ttu-id="7397a-129">비즈니스용 Skype Online을 구입 했을 때 만든 Microsoft 365 또는 Office 365 사용자 ID가 포함 된 Microsoft Online Services 팀에서 전자 메일을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-129">You received an email from the Microsoft Online Services Team that contains the Microsoft 365 or Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="7397a-130">메일의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-130">The mail looks something like this:</span></span>

    ![비즈니스용 Skype Online에 등록 한 후 받은 환영 전자 메일의 예입니다.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="7397a-133">[관리 센터](https://admin.microsoft.com) 에 로그인 하 고 Microsoft 365 또는 Office 365 사용자 ID와 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-133">Sign in to the [admin center](https://admin.microsoft.com) and enter your Microsoft 365 or Office 365 user ID and password.</span></span> 

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="7397a-134">3. 도메인 및 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-134">3. Set up your domain and users</span></span>
<span data-ttu-id="7397a-135"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-135"><a name="bkmk_users"> </a></span></span>

<span data-ttu-id="7397a-136">Office 365에 로그인 한 후에는 비즈니스용 Skype Online을 사용 하도록 도메인 및 조직 구성원을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-136">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="7397a-137">Office [365에 도메인 및 사용자 추가](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): office 365 설정 마법사를 사용 하 여 office 365을 사용 하 여 사용자 지정 도메인 (예: *fourthcoffee.com*)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-137">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="7397a-138">**기본적으로 Office 365 설치 마법사에는 비즈니스용 Skype Online 설정 및 비즈니스용 Skype 사용자 Id 만들기가 포함 되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7397a-138">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="7397a-139">이미 마법사를 사용 하 여 Office 365에 대 한 도메인을 설정한 경우에는이 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-139">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="7397a-140">도메인 및 dns [연결](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): 도구-도메인 문제 해결사를 사용 하 여 도메인 및 dns 설정이 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-140">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="7397a-141">이 작업을 수행 하면 나중에 DNS 설정을 향후 문제의 원본으로 제거할 수 있기 때문에 모든 설치 문제를 파악 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-141">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="7397a-142">[Office 365 url 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): 대부분의 small 기업은이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-142">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="7397a-143">**그러나 웹의 일부에 대 한 액세스를 제한 하는 방화벽 또는 프록시 서버가 있는 경우**비즈니스용 Skype Online 끝점에 대 한 액세스를 허용 하는 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-143">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="7397a-144">이는 방화벽과 프록시 서버를 구성 하는 데 경험이 많은 사용자가 수행 하는 고급 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-144">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="7397a-145">이전에이 작업을 수행 하지 않은 경우에는 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여 비즈니스용 Skype를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-145">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="7397a-146">4. 조직에서 메신저 대화 및 현재 상태 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-146">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="7397a-147"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-147"><a name="bkmk_IM"> </a></span></span>

<span data-ttu-id="7397a-148">인스턴트 메시지 (IM) 및 현재 상태 (비즈니스용[skype의 현재 상태 정보에 대 한 액세스 제어](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c))는 비즈니스용 skype에 포함 된 기본 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-148">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="7397a-149">기본적으로 비즈니스 사용자는 서로 Skype와 인스턴트 메시지를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-149">By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="7397a-150">**비즈니스용 Skype 사용자가 통신할 수 있는 사람을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7397a-150">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="7397a-151">[사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](allow-users-to-contact-external-skype-for-business-users.md) 귀하 *와* 다른 기업 모두에서 시스템을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-151">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="7397a-152">**중요**: 비즈니스에 rob@contosowest.com 및 ina@contosoeast.com와 같은 두 개의 도메인이 있는 경우이 단계를 수행 해야 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-152">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="7397a-153">[비즈니스용 skype 사용자가 회사 외부의 skype 연락처를 추가 하도록 허용](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="7397a-153">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="7397a-154">**동료가 온라인 상태 인지를 볼 수 있는 사람을 선택 합니다.** 현재 상태 기능에는 온라인 상태와 사용 가능한 시간 (예: 약속 있음/없음, 자리 비움, 프레젠테이션)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-154">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![개인 메시지를 사용 하 여 사용자의 온라인 상태에 대 한 예입니다.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="7397a-156">비즈니스의 모든 사용자에 대 한 기본 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-156">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="7397a-157">사용자의 온라인 상태를 조직의 모든 사용자에 게 자동으로 표시</span><span class="sxs-lookup"><span data-stu-id="7397a-157">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="7397a-158">사용자의 온라인 상태를 자신의 연락처에만 표시</span><span class="sxs-lookup"><span data-stu-id="7397a-158">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="7397a-159">지침은 [비즈니스용 Skype Online에서 현재 상태 구성을](configure-presence-in-skype-for-business-online.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-159">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="7397a-160">5. 비즈니스용 Skype 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="7397a-160">5. Download and install Skype for Business</span></span>
<span data-ttu-id="7397a-161"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-161"><a name="bkmk_download"> </a></span></span>

<span data-ttu-id="7397a-162">PC, Mac 또는 모바일 장치에서 비즈니스용 Skype를 사용 하려면 사용자와 비즈니스의 다른 사람들이 먼저 장치에 비즈니스용 Skype 다운로드를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-162">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="7397a-163">[비즈니스용 Skype 설치](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Microsoft 365 관리 센터에서 앱을 다운로드 하 고 PC 또는 Mac에 설치 하는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-163">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Microsoft 365 admin center, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="7397a-164">[Office 365에서 비즈니스용 Skype 클라이언트 배포](deploy-the-skype-for-business-client-in-office-365.md)대규모 엔터프라이즈에서 앱을 배포 하는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-164">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="7397a-165">비즈니스용 [Skype 설치](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Android 장치, iOS 장치, Windows phone에서 비즈니스용 skype를 다운로드 하 고 설치 하 고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="7397a-166">[휴대폰 전화 알림 설정 또는 해제](turn-on-or-off-mobile-phone-notifications.md): 모바일 장치에 비즈니스용 Skype가 설치 되어 있는 경우 사용자와 회사의 다른 사용자가 수신 및 부재 중 메신저 대화에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-166">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="7397a-167">6. 모든 작업이 제대로 수행 되는지 테스트</span><span class="sxs-lookup"><span data-stu-id="7397a-167">6. Test to make sure everything is working</span></span>
<span data-ttu-id="7397a-168"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-168"><a name="bkmk_test"> </a></span></span>

<span data-ttu-id="7397a-169">먼저 사용자와 비즈니스의 다른 사용자가 비디오를 사용할 수 있는지 여부를 테스트 하세요. [비즈니스용 Skype에 로그인 및 로그 아웃](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)</span><span class="sxs-lookup"><span data-stu-id="7397a-169">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="7397a-170">서로 메신저 대화를 보내고 상대방의 현재 상태를 보고 빠른 모임에 참가할 수 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-170">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="7397a-171">문제?</span><span class="sxs-lookup"><span data-stu-id="7397a-171">Problems?</span></span> <span data-ttu-id="7397a-172">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-172">Do the following:</span></span>

- <span data-ttu-id="7397a-173">[비즈니스용 Skype에 로그인 하는 데 도움이 필요 하세요?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) 일반적인 로그인 문제</span><span class="sxs-lookup"><span data-stu-id="7397a-173">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="7397a-174">[비즈니스 제품에 대해 고객 지원 센터 문의 - 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="7397a-174">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="7397a-175">저희에 게 도움을 주세요!</span><span class="sxs-lookup"><span data-stu-id="7397a-175">We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="7397a-176">다른 사용 가능한 기능을 설정 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="7397a-176">Do you want to set up other available features?</span></span>
<span data-ttu-id="7397a-177"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-177"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="7397a-178">추가 기능을 설정 하기 전에 라이선스가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-178">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="7397a-179">비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="7397a-179">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="7397a-180">오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-180">Set up Audio Conferencing</span></span>

<span data-ttu-id="7397a-181">조직의 사용자가 모임에 전화를 걸 때 휴대폰을 사용 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-181">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="7397a-182">비즈니스용 Skype에는 이러한 상황에 대 한 오디오 회의 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-182">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="7397a-183">모바일 장치 또는 PC에서 비즈니스용 Skype 앱을 사용 하는 대신 휴대폰을 사용 하 여 비즈니스용 Skype 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-183">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="7397a-184">Office 365에서 전화 시스템 및 통화 계획 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-184">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="7397a-185">Office 365의 전화 시스템 기능은 비즈니스에 대 한 전화 시스템을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-185">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="7397a-186">조직의 다른 비즈니스용 Skype 사용자에 게 전화를 거는 무료 이며, 직원 들은 서로 또는 외부 발신자 로부터 보이스 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-186">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="7397a-187">전화 시스템을 사용 하 여 얻을 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-187">Here's what you get with Phone System.</span></span>

<span data-ttu-id="7397a-188">통화 요금제 서비스를 추가 하면 직원 들이 비즈니스용 Skype에서 기본 전화 번호를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-188">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="7397a-189">회사 외부에서 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-189">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="7397a-190">VoIP 전화, Pc 및 모바일 장치에서 음성 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-190">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="7397a-191">비상시의 경우에는 911를 호출 하 여 도움을 받으세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-191">And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="7397a-192">단계별 설정 지침은 통화 계획 설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-192">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="7397a-193">Skype 모임 브로드캐스트 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-193">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="7397a-194">Skype 모임 브로드캐스트는 최대 1만 참석자와의 모임을 생성, 호스팅 및 브로드캐스트할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-194">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="7397a-195">**작동 방식에 대해 자세히 알아보려면 [Skype 모임 브로드캐스트 란?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 를 참조 하세요.**</span><span class="sxs-lookup"><span data-stu-id="7397a-195">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="7397a-196">Skype 모임 브로드캐스트를 설정 하는 단계에 대 한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-196">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="7397a-197">비즈니스용 [Office 365에 대 한 라이선스 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): 브로드캐스트 모임을 **호스트할** 모든 사용자에 게 비즈니스용 **Skype Online** 또는 **Enterprise 계획** 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-197">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="7397a-198">[Skype 모임 브로드캐스트 사용](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md):이 기능은 기본적으로 활성화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-198">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="7397a-199">이 기능을 설정 하 고 나면 사용자는 조직의 다른 사용자와 브로드캐스트 모임을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-199">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="7397a-200">[Skype 모임 브로드캐스트를 위한 네트워크 설정](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): 조직 외부의 참석자와 웹 세미나 진행 및 기타 브로드캐스트를 호스팅하려면 네트워크를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-200">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="7397a-201">[Skype 모임 브로드캐스트 예약](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) 및 [Skype 모임 브로드캐스트 참가](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): 다른 사용자가 모임에 참가 하 려 할 때 *https://portal.broadcast.skype.com* skype 모임 브로드캐스트 일정을 예약 하 여 모임 브로드캐스트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-201">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="7397a-202">네트워크 연결 요구 사항에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="7397a-202">Learn about network connectivity requirements</span></span>
<span data-ttu-id="7397a-203"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-203"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="7397a-204">비즈니스용 Skype에서 오디오, 비디오, 응용 프로그램 공유 품질은 종단간 네트워크 연결의 품질에 따라 크게 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-204">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="7397a-205">최상의 환경을 위해서는 회사 네트워크와 비즈니스용 Skype Online 간에 고품질의 연결을 설정 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7397a-205">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="7397a-206">네트워크 및 조정 정보는 [비즈니스용 Skype Online 성능을 조정](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-206">For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="7397a-207">설정이 모두 완료 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="7397a-207">All done setting up?</span></span> <span data-ttu-id="7397a-208">비즈니스용 Skype 사용 시작 하기</span><span class="sxs-lookup"><span data-stu-id="7397a-208">Getting started using Skype for Business</span></span>
<span data-ttu-id="7397a-209"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-209"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="7397a-210">[비즈니스용 Skype 교육](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): 빠르게 시작 하는 데 도움이 되는 교육 항목 목록을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="7397a-210">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="7397a-211">비즈니스용 Skype 전화 회의 시작</span><span class="sxs-lookup"><span data-stu-id="7397a-211">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[<span data-ttu-id="7397a-212">비즈니스용 Skype에서 비디오 장치 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="7397a-212">Set Video Device options in Skype for Business</span></span>](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[<span data-ttu-id="7397a-213">비즈니스용 Skype를 사용 하 여 영상 통화 만들기 및 받기</span><span class="sxs-lookup"><span data-stu-id="7397a-213">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="7397a-214">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7397a-214">Related topics</span></span>
<span data-ttu-id="7397a-215"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="7397a-215"><a name="bkmk_more"> </a></span></span>

[<span data-ttu-id="7397a-216">비즈니스용 Skype 서버와 비즈니스용 Skype Online 간 하이브리드 연결 계획</span><span class="sxs-lookup"><span data-stu-id="7397a-216">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/p/?linkid=400791)



