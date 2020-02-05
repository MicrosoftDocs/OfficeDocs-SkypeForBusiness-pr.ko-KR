---
title: 비즈니스용 Skype 서버 2019에서 리소스 계정 구성
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에 대 한 리소스 계정을 설정 합니다.
ms.openlocfilehash: e16f75063cfbe794ff0257cb9cccdf44065a5448
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726778"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="7c083-103">리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="7c083-103">Configure resource accounts</span></span>

<span data-ttu-id="7c083-104">비즈니스용 Skype 서버 2019 하이브리드 구현에서는 통합 메시징을 위해 전화 시스템에서 제공 하는 클라우드 서비스만 사용 하 고 Exchange Online과 통합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="7c083-105">비즈니스용 Skype 서버 2019에서 이제 [Office 365의 전화 시스템](/MicrosoftTeams/here-s-what-you-get-with-phone-system)에서 제공 하는 것과 같이 클라우드 통화 큐와 자동 전화 교환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="7c083-106">비즈니스용 Skype 서버 2019에서 전화 시스템 자동 전화 교환 또는 통화 큐를 사용 하려면 응용 프로그램 끝점으로 작동 하 고 전화 번호를 할당할 수 있는 리소스 계정을 만들고 온라인 팀 관리 센터를 사용 하 여 통화 큐를 구성 해야 합니다. 자동 전화 교환입니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="7c083-107">이 리소스 계정은 온라인으로 사용할 수 있습니다 (이 문서에서 설명 하는 것 처럼, [Microsoft 팀의 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts) 를 참조 하세요.) 또는 온-프레미스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="7c083-108">일반적으로 여러 전화 시스템 자동 전화 교환 또는 전화 큐 노드가 있으며, 각각은 온라인 또는 비즈니스용 Skype 서버 2019에 있는 리소스 계정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="7c083-109">기존 Exchange UM 자동 전화 교환과 전화 큐 시스템이 있는 경우 Exchange Server 2019 또는 Exchange online으로 전환 하기 전에 아래 설명에 따라 세부 정보를 수동으로 기록 하 고 팀 관리 센터를 사용 하 여 완전히 새로운 시스템을 구현 해야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="7c083-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="7c083-110">개요</span><span class="sxs-lookup"><span data-stu-id="7c083-110">Overview</span></span>

<span data-ttu-id="7c083-111">전화 시스템 자동 전화 교환 또는 통화 큐에 서비스 번호가 필요한 경우에는 다음과 같은 순서로 다양 한 종속성을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="7c083-112">서비스 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="7c083-112">Obtain a service number</span></span>
2. <span data-ttu-id="7c083-113">리소스 계정과 함께 사용할 수 있는 무료 전화 시스템- [가상 사용자 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 또는 유료 전화 시스템 라이선스를 취득 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="7c083-114">자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-114">Create the resource account.</span></span> <span data-ttu-id="7c083-115">연결 된 리소스 계정이 있는 자동 전화 교환 또는 전화 큐가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="7c083-116">온라인 및 온-프레미스 간에 active directory 동기화가 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="7c083-117">리소스 계정에 전화 시스템 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="7c083-118">리소스 계정에 서비스 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="7c083-119">전화 시스템 통화 큐 또는 자동 전화 교환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="7c083-120">리소스 계정을 자동 전화 교환 또는 통화 큐에 연결 합니다 (새-CsApplicationInstanceAssociation).</span><span class="sxs-lookup"><span data-stu-id="7c083-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="7c083-121">자동 전화 교환 또는 통화 큐가 최상위 자동 전화 교환 아래에 중첩 되어 있는 경우 연결 된 리소스 계정은 자동 전화 교환 및 전화 큐의 구조로 여러 항목을 입력 하려는 경우에만 전화 번호를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="7c083-122">온라인에 있는 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="7c083-123">[Microsoft 팀 라이선스 할당](/MicrosoftTeams/assign-teams-licenses)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="7c083-124">Windows PowerShell을 사용 하 여 Enterprise Voice에서 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="7c083-125">예를 들면 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="7c083-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="7c083-126">만들려는 전화 시스템 자동 전화 교환 또는 통화 큐가 중첩 되 고 전화 번호가 필요 하지 않은 경우 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="7c083-127">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-127">Create the resource account</span></span>  
2. <span data-ttu-id="7c083-128">온라인 및 온-프레미스 간에 active directory 동기화 대기</span><span class="sxs-lookup"><span data-stu-id="7c083-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="7c083-129">전화 시스템 자동 전화 교환 또는 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="7c083-130">리소스 계정을 전화 시스템 자동 전화 교환 또는 통화 큐에 연결</span><span class="sxs-lookup"><span data-stu-id="7c083-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="7c083-131">전화 번호를 사용 하 여 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="7c083-132">전화 번호를 사용 하는 리소스 계정을 만들려면 다음 작업을 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="7c083-133">무료 또는 유료 서비스 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="7c083-134">다른 음성 서비스나 자원 계정에는 번호를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="7c083-135">리소스 계정에 전화 번호를 할당 하기 전에 기존 유료 또는 무료 서비스 번호를 가져오거나 이식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="7c083-136">무료 또는 무료 서비스 전화 번호를 가져온 후에는 **Microsoft 팀 관리 센터** > **의 음성** > **전화 번호**에 표시 되며 나열 된 **번호 유형이** **서비스 무료 사용 가능**으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="7c083-137">서비스 번호를 가져오려면 [서비스 전화 번호 가져오기를](/MicrosoftTeams/getting-service-phone-numbers) 참조 하거나 기존 서비스 번호를 전송 하려는 경우 [전화 번호를 팀에](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="7c083-138">미국 이외의 사용자는 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="7c083-139">미국 외부에서 작업을 수행 하는 방법을 확인 하기 위해 대신 [조직의 전화 번호 관리](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="7c083-140">전화 시스템 라이선스를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-140">Buy a Phone System license.</span></span> <span data-ttu-id="7c083-141">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-141">See:</span></span>  
   - [<span data-ttu-id="7c083-142">전화 시스템-가상 사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="7c083-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="7c083-143">Office 365 Enterprise E1 및 E3</span><span class="sxs-lookup"><span data-stu-id="7c083-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="7c083-144">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="7c083-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="7c083-145">Office 365 Enterprise E5 비즈니스 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="7c083-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="7c083-146">각 전화 시스템 자동 전화 교환 또는 통화 큐에 `New-CsHybridApplicationEndpoint` 대해 cmdlet을 실행 하 여 온-프레미스 리소스 계정을 만들고 각 계정에 이름, sip 주소 등을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="7c083-147">이 명령에 대 한 자세한 내용은 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c083-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="7c083-148">반드시 리소스 계정을 만든 후에는 AD가 온라인 및 온-프레미스 간에 동기화 될 때까지 기다리거나, 동기화를 강제 수행 하 고 전화 시스템 자동 전화 교환 또는 통화 큐의 온라인 구성을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="7c083-149">동기화를 강제 수행 하려면 AAD 연결을 실행 하는 컴퓨터에서 다음 명령을 실행 합니다 (이 명령을 실행 하기 위해 로드 `import-module adsync` 해야 할 필요가 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="7c083-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="7c083-150">이 명령에 대 한 자세한 내용은 [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c083-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="7c083-151">전화 시스템-가상 사용자 또는 전화 시스템 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-151">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="7c083-152">[Microsoft 팀 라이선스 할당](/MicrosoftTeams/assign-teams-licenses) 및 [한 명의 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-152">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

   <span data-ttu-id="7c083-153">리소스 계정에 전화 번호를 할당 하는 경우 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-153">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="7c083-154">이렇게 하면 조직 수준의 전화 번호에 전화 시스템 기능이 제공 되며, 자동 전화 교환 및 전화 큐 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-154">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="7c083-155">서비스 번호를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-155">Assign the service number to the resource account.</span></span> <span data-ttu-id="7c083-156">`Set-CsHybridApplicationEndpoint` 명령을 사용 하 여 리소스 계정에-lineuri 옵션을 사용 하 여 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-156">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="7c083-157">이 명령에 대 한 자세한 내용은 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c083-157">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="7c083-158">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-158">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="7c083-159">최상위 자동 전화 교환 또는 통화 큐에 할당 될 경우 자원 계정에 할당 된 전화 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-159">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="7c083-160">사용자 (구독자) 전화 번호를 리소스 계정에 할당할 수 없는 경우 서비스 수신자 또는 무료 전화 번호로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-160">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

  <span data-ttu-id="7c083-161">리소스 계정에 직접 라우팅 하이브리드 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-161">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="7c083-162">자세한 내용은 [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-162">See [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) for details.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7c083-163">자동 전화 교환 및 통화 큐에 대 한 리소스 계정에 할당 되는 직접 라우팅 서비스 번호는 Microsoft 팀 사용자 및 에이전트에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-163">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="7c083-164">전화 시스템 자동 전화 교환 또는 통화 대기열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-164">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="7c083-165">다음 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-165">See one of the following:</span></span>

   - [<span data-ttu-id="7c083-166">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="7c083-166">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="7c083-167">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-167">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="7c083-168">이전에 선택한 전화 시스템 자동 전화 교환 또는 통화 큐에 자원 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-168">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="7c083-169">소규모 비즈니스 구현의 예는 다음을 예로 들 수 있습니다. [예-자동 전화 교환 설정](/microsoftteams/tutorial-org-aa) 및 [소규모 비즈니스 예-전화 큐 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)</span><span class="sxs-lookup"><span data-stu-id="7c083-169">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="7c083-170">전화 번호를 사용 하지 않고 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-170">Create a resource account without a phone number</span></span>

<span data-ttu-id="7c083-171">이 섹션에서는 온-프레미스에 있는 리소스 계정을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-171">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="7c083-172">홈에 있는 리소스 계정을 만들려면 [Microsoft 팀의 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts)에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-172">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="7c083-173">이러한 단계는 새로운 전화 시스템 자동 전화 교환 또는 전화 큐 구조를 만들거나 Exchange UM에서 원래 만든 구조를 다시 만드는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-173">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="7c083-174">비즈니스용 Skype 프런트 엔드 서버에 로그인 하 고 다음 PowerShell cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-174">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="7c083-175">각 전화 시스템 자동 전화 교환 또는 통화 큐에 `New-CsHybridApplicationEndpoint` 대해 cmdlet을 실행 하 여 온-프레미스 리소스 계정을 만들고 각 계정에 이름, sip 주소 등을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-175">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="7c083-176">이 명령에 대 한 자세한 내용은 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c083-176">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="7c083-177">반드시 리소스 계정을 만든 후에는 AD가 온라인 및 온-프레미스 간에 동기화 될 때까지 기다리거나, 동기화를 강제 수행 하 고 전화 시스템 자동 전화 교환 또는 통화 큐의 온라인 구성을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-177">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="7c083-178">동기화를 강제 수행 하려면 AAD 연결을 실행 하는 컴퓨터에서 다음 명령을 실행 합니다 (이 명령을 실행 하기 위해 로드 `import-module adsync` 해야 할 필요가 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="7c083-178">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="7c083-179">이 명령에 대 한 자세한 내용은 [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c083-179">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="7c083-180">전화 시스템 자동 전화 교환 또는 통화 대기열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-180">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="7c083-181">다음 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-181">See one of the following:</span></span>
   - [<span data-ttu-id="7c083-182">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="7c083-182">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="7c083-183">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-183">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="7c083-184">이전에 선택한 전화 시스템 자동 전화 교환 또는 통화 큐와 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-184">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="7c083-185">소규모 비즈니스 구현의 예는 다음을 예로 들 수 있습니다. [예-자동 전화 교환 설정](/microsoftteams/tutorial-org-aa) 및 [소규모 비즈니스 예-전화 큐 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)</span><span class="sxs-lookup"><span data-stu-id="7c083-185">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="7c083-186">구현 테스트</span><span class="sxs-lookup"><span data-stu-id="7c083-186">Test the implementation</span></span>

<span data-ttu-id="7c083-187">구현을 테스트 하는 가장 좋은 방법은 전화 시스템 자동 전화 교환 또는 통화 큐에 대해 구성 된 번호로 전화를 걸어 에이전트 또는 메뉴 중 하나에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-187">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="7c083-188">관리 센터 작업 창의 **테스트 단추** 를 사용 하 여 테스트 호출을 빠르게 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-188">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="7c083-189">전화 시스템 자동 전화 교환 또는 통화 큐를 변경 하려면 해당 서비스를 선택한 다음 작업 창에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-189">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="7c083-190">리소스 계정에 통화 큐 또는 자동 전화 교환에 할당 하는 데 문제가 있는 경우 microsoft 팀 [에 알려진 문제](/MicrosoftTeams/Known-issues#phone-system) 를 확인 하 고, [내 하이브리드 응용 프로그램 인스턴스를 수정 하는 방법](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c083-190">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="7c083-191">Exchange UM 자동 전화 교환 또는 통화 큐를 전화 시스템으로 이동</span><span class="sxs-lookup"><span data-stu-id="7c083-191">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="7c083-192">Exchange UM에서 전화 시스템으로 마이그레이션하는 경우에는 통화 큐 및 자동 전화 교환 구조를 다시 만들어야 하며, 한 쪽에서 다른 사람에 게 직접 마이그레이션하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-192">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="7c083-193">전화 큐 및 자동 전화 교환 집합을 다시 구현 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-193">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="7c083-194">관리자 권한으로 로그인 한 상태에서 Exchange 2013 또는 2016 시스템에서 다음 명령을 실행 하 여 모든 Exchange UM 자동 전화 교환 및 전화 큐의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-194">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="7c083-195">나열 된 각 Exchange UM 통화 큐 또는 자동 전화 교환에 대해 구조, 설정 및 관련 소리 또는 텍스트 음성 변환 파일 복사본의 위치를 기록해 둡니다 (출력의 guid는 파일이 저장 되는 폴더의 이름).</span><span class="sxs-lookup"><span data-stu-id="7c083-195">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="7c083-196">다음 명령을 실행 하 여 이러한 세부 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-196">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="7c083-197">이 명령에 대 한 자세한 내용은 [Get UMAutoAttendant 전화 교환을](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-197">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="7c083-198">캡처 해야 할 수 있는 옵션의 전체 목록은 [Umautoattendant 전화 교환 구성원](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 이지만, 가장 중요 한 몇 가지 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-198">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="7c083-199">업무 시간</span><span class="sxs-lookup"><span data-stu-id="7c083-199">Business hours</span></span>
    - <span data-ttu-id="7c083-200">업무 시간 외</span><span class="sxs-lookup"><span data-stu-id="7c083-200">Non-business hours</span></span>
    - <span data-ttu-id="7c083-201">언어</span><span class="sxs-lookup"><span data-stu-id="7c083-201">Language</span></span>
    - <span data-ttu-id="7c083-202">휴일 일정</span><span class="sxs-lookup"><span data-stu-id="7c083-202">Holiday schedule</span></span>

3. <span data-ttu-id="7c083-203">앞에서 설명한 것 처럼 새로운 온-프레미스 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-203">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="7c083-204">테스트 목적으로 최상위 자동 전화 교환에 임시 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-204">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="7c083-205">이전에 설명한 것 처럼 끝점을 사용 하는 전화 시스템 자동 전화 교환 또는 통화 큐를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-205">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="7c083-206">[Small business 예제-up a auto attendant을 설정](/microsoftteams/tutorial-org-aa) 하 여 이전 Exchange UM 시스템에 계층 구조의 논리 맵을 만들려면 아래의 연습을 사용 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-206">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="7c083-207">전화 시스템 자동 전화 교환 또는 통화 큐를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-207">Test the Phone System auto attendant or call queue.</span></span>
6. <span data-ttu-id="7c083-208">Exchange UM 통화 대기열 또는 자동 전화 교환에 연결 된 전화 번호를 해당 전화 시스템 자동 전화 교환 또는 통화 큐에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-208">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="7c083-209">이 시점에서 UM 음성 메일을 이미 마이그레이션한 경우 Exchange Server 2019로 마이그레이션할 위치에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-209">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c083-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c083-210">See Also</span></span>

[<span data-ttu-id="7c083-211">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="7c083-211">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="7c083-212">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="7c083-212">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="7c083-213">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="7c083-213">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="7c083-214">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="7c083-214">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="7c083-215">클라우드 통화 큐 계획</span><span class="sxs-lookup"><span data-stu-id="7c083-215">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="7c083-216">온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="7c083-216">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="7c083-217">CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="7c083-217">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="7c083-218">CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="7c083-218">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="7c083-219">[Microsoft 팀](/MicrosoftTeams/manage-resource-accounts) - \(의 자원 계정을 관리 하 여 온라인으로 리소스 계정 만들기 홈\)</span><span class="sxs-lookup"><span data-stu-id="7c083-219">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
