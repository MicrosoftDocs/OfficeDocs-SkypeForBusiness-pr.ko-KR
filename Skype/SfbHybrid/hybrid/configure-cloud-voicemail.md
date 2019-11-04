---
title: 온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 구성
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버에 있는 사용자에 대해 클라우드 기반 음성 메일을 구현 하기 위한 지침입니다.
ms.openlocfilehash: 7423f16e7985a063ae5a974ea6c36684bfb75e7c
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37616079"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="f6f41-103">온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="f6f41-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="f6f41-104">개요</span><span class="sxs-lookup"><span data-stu-id="f6f41-104">Overview</span></span> 
<span data-ttu-id="f6f41-105">이 문서에서는 비즈니스용 Skype 온-프레미스 사용자에 대해 Microsoft 클라우드 음성 메일 서비스를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="f6f41-106">이 문서에서는 이미 지원 되는 토폴로지에서 비즈니스용 Skype 서버를 배포 했으며 하이브리드 연결을 설정 하기 위한 필수 구성 요소를 충족 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="f6f41-107">클라우드 음성 메일을 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대 한 자세한 내용은 [클라우드 음성 메일 서비스 계획](plan-cloud-voicemail.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6f41-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="f6f41-108">클라우드 음성 메일을 구성 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="f6f41-109">[Plan Cloud 음성 메일 서비스](plan-cloud-voicemail.md)에 설명 된 대로 필수 구성 요소를 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="f6f41-110">[하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [하이브리드 연결 구성](configure-hybrid-connectivity.md)에 설명 된 대로 하이브리드 연결을 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="f6f41-111">이 문서에 설명 된 대로 [,에 지 서버에서 호스팅 공급자로 클라우드 음성 메일을 구성](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="f6f41-112">이 문서에 설명 [된 대로 호스팅된 음성 메일 정책을 구성](#configure-a-hosted-voicemail-policy) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="f6f41-113">이 문서에 설명 [된 대로 호스팅된 음성 메일 정책을 할당](#assign-a-hosted-voicemail-policy) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="f6f41-114">이 문서에 설명 된 대로 [클라우드 음성 사서함에 대해 사용자를 사용 하도록 설정](#enable-a-user-for-cloud-voicemail) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="f6f41-115">에 지 서버에서 호스팅 공급자로 클라우드 음성 메일 구성</span><span class="sxs-lookup"><span data-stu-id="f6f41-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="f6f41-116">다음 매개 변수를 사용 하 여 새-CsHostingProvider cmdlet을 통해 프런트 엔드 서버의 호스팅 공급자로 클라우드 음성 메일을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="f6f41-117">**Identity** 는 만들려는 호스팅 공급자에 대 한 고유 문자열 값 식별자를 지정 합니다. 예를 들어 클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="f6f41-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="f6f41-118">**Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="f6f41-119">이 매개 변수는 True로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="f6f41-120">**EnabledSharedAddressSpace**는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="f6f41-121">이 매개 변수는 True로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="f6f41-122">**HostsOCSUsers** 은 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스트 하는 데 사용 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="f6f41-123">이 매개 변수는 False로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="f6f41-124">**Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 예: proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f6f41-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="f6f41-125">이 정보는 호스팅 공급자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6f41-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="f6f41-126">이 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-126">This value cannot be modified.</span></span> <span data-ttu-id="f6f41-127">호스팅 공급자가 프록시 서버를 변경 하는 경우 해당 공급자에 대 한 항목을 삭제 한 다음 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="f6f41-128">**Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지에 포함 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="f6f41-129">이 매개 변수는 False로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-129">This parameter must be set to False.</span></span>

<span data-ttu-id="f6f41-130">예를 들어 비즈니스용 Skype 관리 셸에서 다음 cmdlet은 호스팅 공급자로 클라우드 음성 메일을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="f6f41-131">호스팅된 음성 메일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f6f41-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="f6f41-132">조직의 음성 메일이 클라우드 음성 메일 서비스로 라우팅되도록 하려면 조직에 대해 호스팅된 음성 메일 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="f6f41-133">대부분의 경우 호스팅된 음성 메일 정책은 하나만 필요 하며, 모든 요구 사항을 충족 하도록 글로벌 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="f6f41-134">조직에서 호스팅된 음성 메일 정책이 여러 개 필요한 경우 set-cshostedvoicemailpolicy cmdlet을 사용 하 여 정책을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="f6f41-135">전역 정책을 수정 하려면 조직 및 TenantID를 업데이트 한 후 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="f6f41-136">**대상** 호스트 된 클라우드 음성 메일 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="f6f41-137">이 값은 **exap.um.outlook.com**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="f6f41-138">**조직** 은 테 넌 트에 할당 된 기본 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="f6f41-139">테 넌 트 관리자 로그인을 통해 office.com에이 정보를 검색할 수 있으며, 관리 센터 앱을 클릭 하 고, 왼쪽의 **설정** 으로 이동한 후 **도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="f6f41-140">예: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="f6f41-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="f6f41-141">조직 이름은 Office 365의 기본 도메인 이름 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="f6f41-142">**테 넌 트** 는 Office 365에서 테 넌 트를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-142">**Tenant** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="f6f41-143">자세한 내용은 [Office 365 테 넌 트 ID 찾기를](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6f41-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="f6f41-144">호스팅된 음성 메일 정책이 제대로 만들어졌는지 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="f6f41-145">호스팅된 음성 메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f6f41-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="f6f41-146">기본적으로는 글로벌 호스팅된 음성 메일 정책이 모든 사용자에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="f6f41-147">다른 정책을 사용 하는 경우에는 사용자가 호스팅된 음성 메일을 사용 하도록 설정 하기 전에 먼저 [set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet을 사용 하 여 원하는 호스팅된 음성 메일 정책을 사용자에 게 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="f6f41-148">예를 들어 다음 명령은 비전역로 호스팅된 음성 메일 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="f6f41-149">사용자가 클라우드 음성 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="f6f41-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="f6f41-150">사용자의 음성 메일 통화를 클라우드 음성 메일로 라우팅되도록 설정 하려면 HostedVoiceMail 매개 변수와 함께 [csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="f6f41-151">예를 들어 다음 명령은 클라우드 음성 메일에 대해 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="f6f41-152">이 cmdlet은 전역, 사이트 또는 사용자 수준에서 클라우드 음성 메일 정책이이 사용자에 게 적용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="f6f41-153">정책이 적용 되지 않으면 cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="f6f41-154">다음은 클라우드 음성 메일에 대 한 사용자 계정을 사용 하지 않도록 설정 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="f6f41-155">이 cmdlet은 전역, 사이트 또는 사용자 수준에서 호스팅된 음성 메일 정책 (이 사용자에 게 적용 됨)이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="f6f41-156">정책이 적용 되 면 cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="f6f41-157">Microsoft 클라우드 음성 메일 서비스를 사용 하려면 사용자가 enterprise voice를 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f41-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
