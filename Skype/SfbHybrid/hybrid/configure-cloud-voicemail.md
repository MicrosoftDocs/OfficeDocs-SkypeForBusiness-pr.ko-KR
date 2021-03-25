---
title: 클라우드 음성메일 서비스 구성
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버에 있는 사용자에 대해 클라우드 기반 음성메일을 구현하기 위한 지침입니다.
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118987"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="9d220-103">클라우드 음성메일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="9d220-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="9d220-104">개요</span><span class="sxs-lookup"><span data-stu-id="9d220-104">Overview</span></span> 
<span data-ttu-id="9d220-105">이 문서에서는 비즈니스용 Skype의 사내 사용자에 대해 Microsoft Cloud Voicemail 서비스를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="9d220-106">이 문서에서는 지원되는 토폴로지에서 비즈니스용 Skype 서버가 이미 배포되어 있으며 하이브리드 연결 설정에 대한 선행 방법을 충족했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="9d220-107">클라우드 음성메일 구현을 위한 이점, 계획 고려 사항 및 요구 사항에 대한 자세한 내용은 [Plan Cloud Voicemail service을 참조하십시오.](plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="9d220-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="9d220-108">클라우드 음성메일 구성에는 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="9d220-109">[Plan Cloud Voicemail service](plan-cloud-voicemail.md)에 설명된 선행 조문을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="9d220-110">하이브리드 연결 계획 및 하이브리드 연결 [](plan-hybrid-connectivity.md) 구성에 설명된 바와 같이 하이브리드 [연결을 설정해야 합니다.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="9d220-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="9d220-111">이 문서에 설명된 바와 같이 프런트 엔드 서버에서 호스팅 공급자로 Cloud [Voicemail을](#configure-cloud-voicemail-as-the-hosting-provider) 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="9d220-112">[이 문서에 설명된](#configure-a-hosted-voicemail-policy) 바와 같이 호스팅된 음성메일 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="9d220-113">[이 문서에 설명된](#assign-a-hosted-voicemail-policy) 바와 같이 호스팅된 음성메일 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="9d220-114">[이 문서에 설명된](#enable-a-user-for-cloud-voicemail) 바와 같이 사용자가 클라우드 음성메일을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="9d220-115">호스팅 공급자로 Cloud Voicemail 구성</span><span class="sxs-lookup"><span data-stu-id="9d220-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="9d220-116">다음 매개 변수와 함께 New-CsHostingProvider 사용하여 Cloud Voicemail을 프런트 엔드 서버에서 호스팅 공급자로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="9d220-117">**Identity는** 만들 호스팅 공급자의 고유 문자열 값 식별자를 지정합니다. 예를 들어 Cloud Voicemail과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="9d220-118">**Enabled** 는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="9d220-119">이 매개 변수는 True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="9d220-120">**EnabledSharedAddressSpace** 는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="9d220-121">이 매개 변수는 True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="9d220-122">**HostsOCSUsers는** 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스팅하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="9d220-123">이 매개 변수는 False로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="9d220-124">**ProxyFQDN은** 호스팅 공급자가 사용하는 프록시 서버의 FQDN(FQDN)을 지정합니다. 예를 들어 proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9d220-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="9d220-125">이 정보는 호스팅 공급자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d220-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="9d220-126">이 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-126">This value cannot be modified.</span></span> <span data-ttu-id="9d220-127">호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="9d220-128">**IsLocal은** 호스팅 공급자가 사용하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지 내에 포함되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="9d220-129">이 매개 변수는 False로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-129">This parameter must be set to False.</span></span>

<span data-ttu-id="9d220-130">예를 들어 비즈니스용 Skype 관리 셸에서 다음 cmdlet은 Cloud Voicemail을 호스팅 공급자로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="9d220-131">호스팅된 음성메일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9d220-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="9d220-132">조직의 음성메일이 클라우드 음성메일 서비스로 라우팅되도록 조직에 대해 호스팅된 음성메일 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="9d220-133">대부분의 경우 호스팅된 음성메일 정책은 하나만 필요하며 모든 요구 사항을 충족하도록 글로벌 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="9d220-134">조직에 호스팅된 음성메일 정책이 여러 개 필요한 경우 new-cshostedvoicemailpolicy cmdlet을 사용하여 정책을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="9d220-135">글로벌 정책을 수정하려면 조직 및 TenantID를 업데이트한 후 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="9d220-136">**Destination은** 호스팅된 클라우드 음성메일 서비스의 FQDN(FQDN)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="9d220-137">이 값은 를 로 **exap.um.outlook.com.**</span><span class="sxs-lookup"><span data-stu-id="9d220-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="9d220-138">**조직은** 테넌트에 할당된 기본 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="9d220-139">테넌트 관리자가 로그인하여 관리 센터 앱을 office.com 왼쪽의 설치로 이동한 다음  도메인 을 클릭하여 이 정보를 검색할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9d220-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="9d220-140">예: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="9d220-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="9d220-141">조직 이름은 Microsoft 365 또는 Office 365의 기본 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="9d220-142">호스팅된 음성메일 정책이 만들어지기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="9d220-143">호스팅된 음성메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9d220-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="9d220-144">기본적으로 전역 호스팅된 음성메일 정책은 모든 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="9d220-145">다른 정책을 사용하는 경우 호스팅된 음성메일에 대해 사용자를 사용하도록 설정하기 전에 [먼저 Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet을 사용하여 사용자에게 원하는 호스팅된 음성메일 정책을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="9d220-146">예를 들어 다음 명령은 전역이 아닌 호스팅된 음성메일 정책을 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="9d220-147">사용자가 클라우드 음성메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="9d220-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="9d220-148">사용자의 음성메일 통화가 클라우드 음성메일로 라우팅될 수 있도록 설정하려면 [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet을 HostedVoiceMail 매개 변수와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="9d220-149">예를 들어 다음 명령은 클라우드 음성메일에 대해 사용자 계정을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="9d220-150">이 cmdlet은 전역, 사이트 또는 사용자 수준에서 Cloud Voicemail 정책이 이 사용자에게 적용되는지 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="9d220-151">정책을 적용하지 않을 경우 cmdlet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="9d220-152">다음 예에서는 Cloud Voicemail에 대한 사용자 계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="9d220-153">이 cmdlet은 전역, 사이트 또는 사용자 수준에서 호스팅된 음성메일 정책이 이 사용자에게 적용되는 것이 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="9d220-154">정책이 적용될 경우 cmdlet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="9d220-155">Microsoft Cloud Voicemail 서비스를 사용하려면 사용자가 엔터프라이즈 음성을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d220-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>