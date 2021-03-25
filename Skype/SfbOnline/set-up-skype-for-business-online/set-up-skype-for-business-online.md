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
description: '조직에서 비즈니스용 Skype를 설치할 도메인, 사용자, IM 및 현재 상태 설정에 대해 알아보고 있습니다. 또한 오디오 회의, 전화 시스템 및 통화 계획 및 Skype 모임 브로드캐스트를 설정하는 방법을 참조하세요. '
ms.openlocfilehash: 0c357c1dbe5b91c06b385562bf31d5f1307bd240
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109964"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="33be8-104">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-104">Set up Skype for Business Online</span></span>

<span data-ttu-id="33be8-105">비즈니스용 Skype를 설정하려면 전역 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-105">You must have global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="33be8-106">웹의 일부에 대한 액세스를 제한하는 방화벽 또는 프록시 서버가 있는 경우 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하여 비즈니스용 Skype를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="33be8-107">Skype 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-107">Setting up Skype</span></span>

<span data-ttu-id="33be8-108">Microsoft 365 또는 Office 365 구독을 사용하여 Skype를 설정하는 데 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-108">Looks like you need help setting up Skype with your Microsoft 365 or Office 365 subscription.</span></span> <span data-ttu-id="33be8-109">이 문서의 단계를 따라 설정을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="33be8-110">1. 비즈니스용 Skype 계획</span><span class="sxs-lookup"><span data-stu-id="33be8-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="33be8-111">**[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** 또는 Business **Essentials가** 있는 경우 비즈니스용 Skype를 사용하여 구독에 있는 비즈니스의 다른 사용자와 온라인 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-111">If you have **[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="33be8-112">예를 들어 비즈니스에 10명이 있는 경우 아래 2-6단계를 수행한 후 비즈니스용 Skype를 사용하여 [IM용](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) 비즈니스용 Skype 및 온라인 모임을 시작하고 비즈니스용 [Skype를](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) 사용하여 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="33be8-113">Outlook에서 비즈니스용 Skype 모임을 [온라인](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) 모임에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="33be8-114">비즈니스용 Skype를 사용하여 비즈니스 외부  사용자로부터  전화를 걸고 수신하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="33be8-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="33be8-115">**옵션 1. 무료 [Skype 앱을 사용하세요.](https://www.skype.com/)**</span><span class="sxs-lookup"><span data-stu-id="33be8-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="33be8-116">소규모 비즈니스(예: 1-2명)가 있는 경우 Skype 앱을 사용하는 것이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="33be8-117">국내 및 국제 통화에 사용하는 비용은 저렴합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="33be8-118">프레젠테이션을 위해 전화 회의를 개최하고, 화상 통화를 할 수 있으며, 데스크톱을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="33be8-119">[요금 및 결제 옵션을 체크 아웃합니다.](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)</span><span class="sxs-lookup"><span data-stu-id="33be8-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="33be8-120">**옵션 2. 계획을 업그레이드하고 Office 365용** 전화 시스템 및 통화 계획을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="33be8-121">이 비용의 정도를 확인한 다음 스위치를 전환하는 가장 쉬운 방법은 비즈니스 제품에 대한 지원에 [문의하고](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 관리자 도움말을 통해 모든 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="33be8-122">자세한 내용은 [비즈니스용 Office 365 설정 계획을 참조합니다.](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)</span><span class="sxs-lookup"><span data-stu-id="33be8-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="33be8-123">2. Office 365에 로그인</span><span class="sxs-lookup"><span data-stu-id="33be8-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="33be8-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-124"><a name="bkmk_signin"> </a></span></span>

<span data-ttu-id="33be8-125">비즈니스용 Skype Online은 Office 365 서비스 제품군의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="33be8-126">비즈니스용 Skype Online을 설정하려면 Office 365에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="33be8-127">이 작업을 하는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-127">Here's how you do that:</span></span>

1. <span data-ttu-id="33be8-128">Microsoft 365 또는 Office 365 사용자 ID를  <em>찾습니다(예:</em>  rob@fourthcoffee.com).</span><span class="sxs-lookup"><span data-stu-id="33be8-128">Locate your Microsoft 365 or Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ).</span></span> <span data-ttu-id="33be8-129">비즈니스용 Skype 온라인을 구매할 때 만든 Microsoft 365 또는 Office 365 사용자 ID가 Microsoft Online Services 팀에서 전자 메일을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-129">You received an email from the Microsoft Online Services Team that contains the Microsoft 365 or Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="33be8-130">메일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-130">The mail looks something like this:</span></span>

    ![비즈니스용 Skype Online에 등록한 후 받은 환영 전자 메일의 예입니다.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="33be8-133">관리 센터에 [로그인하고](https://admin.microsoft.com) Microsoft 365 또는 Office 365 사용자 ID 및 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-133">Sign in to the [admin center](https://admin.microsoft.com) and enter your Microsoft 365 or Office 365 user ID and password.</span></span> 

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="33be8-134">3. 도메인 및 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-134">3. Set up your domain and users</span></span>
<span data-ttu-id="33be8-135"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-135"><a name="bkmk_users"> </a></span></span>

<span data-ttu-id="33be8-136">이제 Office 365에 로그인한 후 비즈니스용 Skype Online을 사용할 도메인 및 조직의 사용자로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-136">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="33be8-137">[Office 365에](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)도메인 및 사용자를 추가: Office 365 설치 마법사를 사용하여 Office 365에서 사용자 지정 *도메인(예:* fourthcoffee.com)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-137">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="33be8-138">**기본적으로 Office 365 설정 마법사에는 비즈니스용 Skype Online 설정 및 비즈니스용 Skype 사용자 ID 만들기가 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="33be8-138">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="33be8-139">이미 마법사를 사용하여 Office 365에 대한 도메인을 설정한 경우 이 단계를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-139">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="33be8-140">[도메인 및 DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)연결 확인 : 도메인 문제 해결사 - 도메인 및 DNS 설정이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-140">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="33be8-141">이 작업을 수행하면 나중에 DNS 설정을 향후 문제의 원인으로 제거할 수 있게 됐기 때문에 나중에 설정 문제를 알아내기 위해 많은 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-141">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="33be8-142">[Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)및 IP 주소 범위: 대부분의 소규모 기업은 이 단계를 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-142">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="33be8-143">**그러나 웹의** 일부에 대한 액세스를 제한하는 방화벽 또는 프록시 서버가 있는 경우 비즈니스용 Skype Online 엔드포인트에 대한 액세스를 허용하는 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-143">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="33be8-144">방화벽 및 프록시 서버를 구성한 경험이 있는 사용자가 가장 잘 수행한 고급 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-144">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="33be8-145">전에 이 일을 수행하지 않은 경우 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하여 비즈니스용 Skype를 설정하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-145">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="33be8-146">4. 조직에서 IM 및 현재 상태 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-146">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="33be8-147"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-147"><a name="bkmk_IM"> </a></span></span>

<span data-ttu-id="33be8-148">메신저(메신저) 및 현재[상태(비즈니스용 Skype에서](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)현재 상태 정보에 대한 제어 액세스 제어)는 비즈니스용 Skype에 포함된 기본 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-148">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="33be8-149">기본적으로 비즈니스의 사람들은 서로 Skype 및 IM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-149">By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="33be8-150">**비즈니스용 Skype 사용자가 다음과 통신할 수 있는 다른 사용자를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="33be8-150">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="33be8-151">[사용자가 비즈니스용 외부 Skype 사용자에 문의할 수 있도록 허용](allow-users-to-contact-external-skype-for-business-users.md) 사용자와 *다른*  비즈니스 모두 시스템을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-151">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="33be8-152">**중요:** 비즈니스에 두 개의 도메인(예: rob@contosowest.com ina@contosoeast.com)이 있는 경우 이 단계를 통해 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-152">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="33be8-153">[비즈니스용 Skype 사용자가 비즈니스 외부에 Skype 연락처를](let-skype-for-business-users-add-skype-contacts.md) 추가하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-153">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="33be8-154">**공동 작업자가 온라인인지** 여부를 보는 사용자 선택: 현재 상태 기능은 온라인 상태인 사람 및 사용 가능한 가용성(예: 사용 가능, 사용 중, 비우기 또는 발표)을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-154">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![개인 메시지가 있는 사람의 온라인 상태의 예입니다.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="33be8-156">비즈니스의 모든 사용자에 대한 기본 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-156">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="33be8-157">조직의 모든 사용자에 대한 사람의 온라인 현재 상태 자동으로 표시</span><span class="sxs-lookup"><span data-stu-id="33be8-157">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="33be8-158">연락처에만 사람의 온라인 현재 상태 표시</span><span class="sxs-lookup"><span data-stu-id="33be8-158">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="33be8-159">지침은 비즈니스용 [Skype Online에서 현재 상태 구성을 참조하세요.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="33be8-159">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="33be8-160">5. 비즈니스용 Skype 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="33be8-160">5. Download and install Skype for Business</span></span>
<span data-ttu-id="33be8-161"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-161"><a name="bkmk_download"> </a></span></span>

<span data-ttu-id="33be8-162">PC, Mac 또는 모바일 장치에서 비즈니스용 Skype를 사용하려면 사용자 및 비즈니스의 다른 사람이 먼저 디바이스에 비즈니스용 Skype 다운로드를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-162">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="33be8-163">[비즈니스용 Skype 설치:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Microsoft 365 관리 센터에서 앱을 다운로드하고 PC 또는 Mac에 설치하는 방법에 대한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-163">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Microsoft 365 admin center, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="33be8-164">[Office 365에서 비즈니스용 Skype](deploy-the-skype-for-business-client-in-office-365.md)클라이언트 배포: 대기업에서 앱을 배포하기 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-164">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="33be8-165">[비즈니스용 Skype 설치:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Android 디바이스, iOS 디바이스 및 Windows 휴대폰에서 비즈니스용 Skype에 다운로드, 설치 및 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="33be8-166">[휴대폰 알림](turn-on-or-off-mobile-phone-notifications.md)켜기 또는 해제 : 비즈니스용 Skype가 모바일 디바이스에 설치되어 있는 경우 사용자 및 비즈니스의 다른 사용자가 수신 및 누락된 인스턴트 메시지에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-166">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="33be8-167">6. 모든 것이 작동하고 있는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-167">6. Test to make sure everything is working</span></span>
<span data-ttu-id="33be8-168"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-168"><a name="bkmk_test"> </a></span></span>

<span data-ttu-id="33be8-169">먼저 사용자와 비즈니스의 다른 사용자들이 [Video: 비즈니스용 Skype](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)로그인 및 아웃할 수 있는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-169">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="33be8-170">서로를 IM할 수 있는지 확인하고, 서로의 현재 존재를 확인하고, 빠른 모임을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-170">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="33be8-171">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="33be8-171">Problems?</span></span> <span data-ttu-id="33be8-172">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-172">Do the following:</span></span>

- <span data-ttu-id="33be8-173">[비즈니스용 Skype에 로그인하는 데 도움이 필요하세요?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) 일반적인 로그인 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-173">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="33be8-174">[비즈니스 제품에 대해 고객 지원 센터 문의 - 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="33be8-174">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="33be8-175">도움이 됐습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-175">We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="33be8-176">사용 가능한 다른 기능을 설정하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="33be8-176">Do you want to set up other available features?</span></span>
<span data-ttu-id="33be8-177"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-177"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="33be8-178">더 많은 기능을 설정하기 전에 라이선스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-178">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="33be8-179">비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="33be8-179">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="33be8-180">오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-180">Set up Audio Conferencing</span></span>

<span data-ttu-id="33be8-181">조직의 사람들이 전화를 사용하여 모임에 전화해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-181">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="33be8-182">비즈니스용 Skype에는 이 상황에 대한 오디오 회의 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-182">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="33be8-183">모바일 디바이스 또는 PC에서 비즈니스용 Skype 앱을 사용하는 대신 휴대폰을 사용하여 비즈니스용 Skype 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-183">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="33be8-184">Office 365에서 전화 시스템 및 통화 계획 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-184">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="33be8-185">Office 365의 전화 시스템 기능은 비즈니스용 전화 시스템을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-185">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="33be8-186">조직의 다른 비즈니스용 Skype 사용자에 대한 통화는 무료이며, 직원들은 서로 및 외부 발신자로부터 음성 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-186">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="33be8-187">다음은 Phone System을 통해 얻을 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-187">Here's what you get with Phone System.</span></span>

<span data-ttu-id="33be8-188">전화 요금제 서비스를 추가하면 직원이 비즈니스용 Skype에서 기본 전화 번호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-188">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="33be8-189">비즈니스 외부에서 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-189">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="33be8-190">VoIP 휴대폰, PC 및 모바일 장치에서 음성 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-190">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="33be8-191">또한 긴급한 경우 911을 호출하여 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-191">And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="33be8-192">단계별 설정 지침은 통화 계획 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33be8-192">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="33be8-193">Skype 모임 브로드캐스트 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-193">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="33be8-194">Skype 모임 브로드캐스트는 최대 10,000명이 참석하는 모임을 생성, 호스트 및 브로드캐스트할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-194">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="33be8-195">**작동 방식에 대한 자세한 내용은 Skype 모임 브로드캐스트란?을 [참조하세요.](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span><span class="sxs-lookup"><span data-stu-id="33be8-195">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="33be8-196">Skype 모임 브로드캐스트를 설정하는 단계에 대한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-196">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="33be8-197">[비즈니스용 Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)라이선스 할당 또는 제거: 브로드캐스트 모임을 호스트할  모든 사용자에게 비즈니스용 **Skype Online** 또는 **Enterprise Plan** 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="33be8-197">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="33be8-198">[Skype 모임 브로드캐스트 사용:](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)기본적으로 이 기능은 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-198">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="33be8-199">설정한 후 사용자는 조직의 다른 사용자와 브로드캐스트 모임을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-199">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="33be8-200">[Skype 모임](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)브로드캐스트에 대한 네트워크 설정 : 조직 외부의 참석자들과 웨비나 및 기타 브로드캐스트를 호스트하려면 네트워크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-200">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="33be8-201">[Skype 모임](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) 브로드캐스트 예약 및 Skype 모임 브로드캐스트 [참가:](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)Skype 모임 브로드캐스트를 예약한 다음 다른 사용자가 모임에 참가하려고 하여 브로드캐스트 모임이 작동해야  *https://portal.broadcast.skype.com*  합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-201">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="33be8-202">네트워크 연결 요구 사항에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="33be8-202">Learn about network connectivity requirements</span></span>
<span data-ttu-id="33be8-203"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-203"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="33be8-204">비즈니스용 Skype에서 오디오, 비디오 및 애플리케이션 공유의 품질은 종단 및 종단 네트워크 연결의 품질에 크게 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-204">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="33be8-205">최적의 환경을 위해 회사 네트워크와 비즈니스용 Skype Online 간에 고품질의 연결이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33be8-205">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="33be8-206">네트워크 및 튜닝 정보는 비즈니스용 Skype Online 성능 [조정을 참조하세요.](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)</span><span class="sxs-lookup"><span data-stu-id="33be8-206">For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="33be8-207">모든 설정이 완료된가요?</span><span class="sxs-lookup"><span data-stu-id="33be8-207">All done setting up?</span></span> <span data-ttu-id="33be8-208">비즈니스용 Skype 사용 시작</span><span class="sxs-lookup"><span data-stu-id="33be8-208">Getting started using Skype for Business</span></span>
<span data-ttu-id="33be8-209"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-209"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="33be8-210">[비즈니스용 Skype 교육](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): 빠르게 시작하는 데 도움이 되는 교육 항목 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33be8-210">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="33be8-211">비즈니스용 Skype 전화 회의 시작</span><span class="sxs-lookup"><span data-stu-id="33be8-211">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[<span data-ttu-id="33be8-212">비즈니스용 Skype에서 비디오 디바이스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="33be8-212">Set Video Device options in Skype for Business</span></span>](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[<span data-ttu-id="33be8-213">비즈니스용 Skype를 사용하여 화상 통화 만들기 및 수신</span><span class="sxs-lookup"><span data-stu-id="33be8-213">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="33be8-214">관련 항목</span><span class="sxs-lookup"><span data-stu-id="33be8-214">Related topics</span></span>
<span data-ttu-id="33be8-215"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="33be8-215"><a name="bkmk_more"> </a></span></span>

[<span data-ttu-id="33be8-216">비즈니스용 Skype 서버와 비즈니스용 Skype Online 간의 하이브리드 연결 계획</span><span class="sxs-lookup"><span data-stu-id="33be8-216">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)