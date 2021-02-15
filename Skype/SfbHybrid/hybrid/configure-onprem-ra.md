---
title: 비즈니스용 Skype 서버 2019에서 리소스 계정 구성
ms.author: crowe
author: CarolynRowe
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
description: 비즈니스용 Skype 서버 2019에 대한 리소스 계정을 설정합니다.
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919014"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="06b49-103">리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="06b49-103">Configure resource accounts</span></span>

<span data-ttu-id="06b49-104">비즈니스용 Skype 서버 2019 하이브리드 구현에서는 전화 시스템에서 제공하는 클라우드 서비스만 통합 메시징에 사용하며 Exchange Online과 통합되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="06b49-105">비즈니스용 Skype 서버 2019에서는 [이제 Microsoft 365 또는 Office 365의](/MicrosoftTeams/here-s-what-you-get-with-phone-system)전화 시스템으로 얻을 수 있는 클라우드 통화 큐 및 자동 전화 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="06b49-106">비즈니스용 Skype 서버 2019에서 전화 시스템 자동 전화 걸기 또는 통화 큐를 사용하려면 응용 프로그램 끝점 역할을 하는 리소스 계정을 만들고 전화 번호를 할당할 수 있는 리소스 계정을 만든 다음 온라인 Teams 관리 센터를 사용하여 통화 큐 또는 자동 전화 걸기 기능을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="06b49-107">이 리소스 계정은 온라인에 있을 수 있습니다(온라인에 있는 리소스 계정을 만들 수 [있는 Microsoft Teams의](/MicrosoftTeams/manage-resource-accounts) 리소스 계정 관리 참조) 또는 이 문서에 설명된 바와 같이 프레미스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="06b49-108">일반적으로 여러 개의 전화 시스템 자동 전화 연결 또는 통화 큐 노드가 있습니다. 각 노드는 온라인 또는 비즈니스용 Skype 서버 2019에 있을 수 있는 리소스 계정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="06b49-109">기존 Exchange UM 자동 전화 교환 및 통화 큐 시스템이 있는 경우 Exchange Server 2019 또는 Exchange Online으로 전환하기 전에 아래 설명된 세부 정보를 수동으로 기록한 다음 Teams 관리 센터를 사용하여 완전히 새로운 시스템을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="06b49-110">개요</span><span class="sxs-lookup"><span data-stu-id="06b49-110">Overview</span></span>

<span data-ttu-id="06b49-111">전화 시스템 자동 전화 연결 또는 통화 큐에 서비스 번호가 필요한 경우 다음과 같은 순서로 다양한 종속성을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="06b49-112">서비스 번호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-112">Obtain a service number.</span></span>
2. <span data-ttu-id="06b49-113">무료 전화 시스템 - 가상 [사용자 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 또는 리소스 계정과 함께 사용할 유료 전화 시스템 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="06b49-114">리소스 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-114">Create the resource account.</span></span> <span data-ttu-id="06b49-115">연결된 리소스 계정이 있는 경우 자동 전화 통신 또는 통화 큐가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="06b49-116">온라인과 프레미스 간의 Active Directory 동기화를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="06b49-117">전화 시스템 라이선스를 리소스 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="06b49-118">서비스 번호를 리소스 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="06b49-119">전화 시스템 통화 큐 또는 자동 전화 걸기 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="06b49-120">리소스 계정을 자동 전화 통신 또는 통화 큐에 연결합니다. (New-CsApplicationInstanceAssociation).</span><span class="sxs-lookup"><span data-stu-id="06b49-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="06b49-121">자동 전화 걸기 또는 통화 큐가 최상위 자동 전화 통신 아래에 중첩된 경우 자동 전화 걸기 및 통화 큐의 구조에 여러 지점을 입력하려는 경우 연결된 리소스 계정에는 전화 번호만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="06b49-122">온라인에 있는 조직의 사용자로 통화를 리디렉션하려면 전화  시스템 라이선스가 있어야 합니다. 이 사용자가 전화 시스템 라이선스를 Enterprise Voice 또는 Microsoft 365 또는 Office 365 통화 플랜을 사용할 수 있도록 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="06b49-123">[Microsoft Teams 라이선스 할당을 참조합니다.](/MicrosoftTeams/assign-teams-licenses)</span><span class="sxs-lookup"><span data-stu-id="06b49-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="06b49-124">사용자에 대해 사용하도록 Enterprise Voice 수 있도록 설정하려면 다음을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06b49-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="06b49-125">예를 들어 다음을 실행합니다.  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="06b49-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="06b49-126">만들 전화 시스템 자동 전화 연결 또는 통화 큐가 중첩되어 전화 번호가 필요하지 않은 경우 프로세스는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="06b49-127">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-127">Create the resource account</span></span>  
2. <span data-ttu-id="06b49-128">온라인과온-프레미스 간의 Active Directory 동기화 대기</span><span class="sxs-lookup"><span data-stu-id="06b49-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="06b49-129">전화 시스템 자동 전화 연결 또는 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="06b49-130">리소스 계정을 전화 시스템 자동 전화 연결 또는 통화 큐와 연결</span><span class="sxs-lookup"><span data-stu-id="06b49-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="06b49-131">전화 번호가 있는 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="06b49-132">전화 번호를 사용하는 리소스 계정을 만들 경우 다음 순서로 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="06b49-133">무료 또는 무료 서비스 번호를 포트하거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="06b49-134">이 번호는 다른 음성 서비스 또는 리소스 계정에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="06b49-135">리소스 계정에 전화 번호를 할당하기 전에 기존 무료 또는 무료 서비스 번호를 얻거나 이식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="06b49-136">무료 또는 무료 서비스 전화 번호를 다운로드하면 **Microsoft Teams** 관리 센터 음성 전화 번호에 표시하며 나열된 번호 유형이 서비스 - 무료로  >    >   **나열됩니다.** </span><span class="sxs-lookup"><span data-stu-id="06b49-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="06b49-137">서비스 번호를 확인하거나 [](/MicrosoftTeams/getting-service-phone-numbers) 기존 서비스 번호를 전송하려는 경우 Teams로 전화 번호 전송을 [참조합니다.](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)</span><span class="sxs-lookup"><span data-stu-id="06b49-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="06b49-138">미국 이외 국가인 경우 Microsoft Teams 관리 센터를 사용하여 서비스 번호를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="06b49-139">대신 [조직의](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 전화 번호 관리로 이동하여 미국 외부에서 전화 번호를 관리하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="06b49-140">전화 시스템 라이선스를 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-140">Buy a Phone System license.</span></span> <span data-ttu-id="06b49-141">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-141">See:</span></span>  
   - [<span data-ttu-id="06b49-142">전화 시스템–가상 사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="06b49-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="06b49-143">Office 365 Enterprise E1 and E3</span><span class="sxs-lookup"><span data-stu-id="06b49-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="06b49-144">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="06b49-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="06b49-145">Office 365 Enterprise E5 Business 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="06b49-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="06b49-146">각 전화 시스템 자동 전화 연결 또는 통화 큐에 대해 cmdlet을 실행하여 프레미스 리소스 계정을 만들고 각 계정에 이름, sip 주소 등이 `New-CsHybridApplicationEndpoint` 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="06b49-147">이 명령에 대한 자세한 내용은 [New-CsHybridApplicationEndpoint를](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="06b49-148">(선택 사항) 리소스 계정을 만든 후 AD가 온라인과 프레미스 간에 동기화될 때까지 기다리거나 동기화를 강제 적용하고 전화 시스템 자동 전화 연결 또는 통화 큐의 온라인 구성을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="06b49-149">동기화를 강제로 수행하려면 AAD Connect를 실행하는 컴퓨터에서 다음 명령을 실행합니다(아직 실행하지 않은 경우 명령을 실행하려면 로드해야 `import-module adsync` 합니다).</span><span class="sxs-lookup"><span data-stu-id="06b49-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="06b49-150">이 명령에 대한 자세한 내용은 [Start-ADSyncSyncCycle을](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>
    
    <span data-ttu-id="06b49-151">이때 계정이 동기화된 것일 수 있지만 프로비전이 완료되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-151">Note-at this point, the account may have synced, but provisioning may not be complete.</span></span>  <span data-ttu-id="06b49-152">[Get-CsOnlineApplicationEndpoint의 출력을 검사합니다.](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)</span><span class="sxs-lookup"><span data-stu-id="06b49-152">Check the output of [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).</span></span>  <span data-ttu-id="06b49-153">동기화된 끝점이 아직 프로비전을 완료하지 않은 경우 여기에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-153">If the synced endpoint has not completed provisioning yet, then it will not appear here.</span></span>  <span data-ttu-id="06b49-154">Teams 설치 상태의 M365 포털에서 프로비전 요청의 [상태를 확인할 수 있습니다.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)</span><span class="sxs-lookup"><span data-stu-id="06b49-154">You can check the status of the provisioning requests in the M365 portal under [Teams Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).</span></span>  <span data-ttu-id="06b49-155">이 프로비전 단계는 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-155">This provisioning phase can take up to 24 hours.</span></span>

5. <span data-ttu-id="06b49-156">전화 시스템 - 가상 사용자 또는 전화 시스템 라이선스를 리소스 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-156">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="06b49-157">Microsoft [Teams 추가 기능](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 라이선스 할당 및 사용자에게 라이선스 [할당을 참조합니다.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="06b49-157">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

   <span data-ttu-id="06b49-158">리소스 계정에 전화 번호를 할당하는 경우 이제 무료 전화 시스템인 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-158">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="06b49-159">이렇게 하면 조직 수준의 전화 번호에 전화 시스템 기능이 제공될 수 있으며 자동 전화 걸기 및 통화 큐 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-159">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="06b49-160">서비스 번호를 리소스 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-160">Assign the service number to the resource account.</span></span> <span data-ttu-id="06b49-161">이 명령을 사용하여 -LineURI 옵션과 함께 전화 번호를 리소스 계정에 `Set-CsHybridApplicationEndpoint` 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-161">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="06b49-162">이 명령에 대한 자세한 내용은 [Set-CsHybridApplicationEndpoint를](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-162">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="06b49-163">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당하려면 다음 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-163">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="06b49-164">리소스 계정에는 할당된 전화 번호가 필요한 경우 최상위 자동 전화 번호 또는 통화 큐에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-164">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="06b49-165">사용자(구독자) 전화 번호를 리소스 계정에 할당할 수 없습니다. 서비스 전화 번호 또는 무료 전화 번호만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-165">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="06b49-166">직접 라우팅 또는 하이브리드 번호를 리소스 계정에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-166">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="06b49-167">자세한 내용은 [직접](/MicrosoftTeams/direct-routing-plan) 라우팅 계획 및 클라우드 자동 연결 [계획(Plan Cloud auto attendants)을 참조합니다.](plan-cloud-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="06b49-167">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="06b49-168">자동 전화 연결 및 통화 큐에 대한 리소스 계정에 할당된 직접 라우팅 서비스 번호는 Microsoft Teams 사용자 및 에이전트에 한해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-168">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="06b49-169">전화 시스템 자동 전화 연결 또는 통화 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-169">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="06b49-170">다음 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-170">See one of the following:</span></span>

   - [<span data-ttu-id="06b49-171">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="06b49-171">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="06b49-172">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-172">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="06b49-173">리소스 계정을 이전에 선택한 전화 시스템 자동 전화 통신 또는 통화 큐와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-173">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="06b49-174">전화 번호 없이 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-174">Create a resource account without a phone number</span></span>

<span data-ttu-id="06b49-175">이 섹션에서는 프레미스에 있는 리소스 계정 만들기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-175">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="06b49-176">온라인에 있는 리소스 계정 만들기는 Microsoft Teams의 리소스 계정 관리에서 [설명됩니다.](/MicrosoftTeams/manage-resource-accounts)</span><span class="sxs-lookup"><span data-stu-id="06b49-176">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="06b49-177">이러한 단계는 새 전화 시스템 자동 전화 교환 또는 통화 큐 구조를 만들거나 Exchange UM에서 원래 만든 구조를 다시 작성하는 경우 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-177">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="06b49-178">비즈니스용 Skype 프런트 엔드 서버에 로그인하고 다음 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-178">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="06b49-179">각 전화 시스템 자동 전화 연결 또는 통화 큐에 대해 cmdlet을 실행하여 프레미스 리소스 계정을 만들고 각 계정에 이름, sip 주소 등이 `New-CsHybridApplicationEndpoint` 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-179">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="06b49-180">이 명령에 대한 자세한 내용은 [New-CsHybridApplicationEndpoint를](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-180">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="06b49-181">(선택 사항) 리소스 계정을 만든 후 AD가 온라인과 프레미스 간에 동기화될 때까지 기다리거나 동기화를 강제 적용하고 전화 시스템 자동 전화 연결 또는 통화 큐의 온라인 구성을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-181">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="06b49-182">동기화를 강제로 수행하려면 AAD Connect를 실행하는 컴퓨터에서 다음 명령을 실행합니다(아직 실행하지 않은 경우 명령을 실행하려면 로드해야 `import-module adsync` 합니다).</span><span class="sxs-lookup"><span data-stu-id="06b49-182">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="06b49-183">이 명령에 대한 자세한 내용은 [Start-ADSyncSyncCycle을](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-183">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="06b49-184">전화 시스템 자동 전화 연결 또는 통화 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-184">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="06b49-185">다음 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-185">See one of the following:</span></span>
   - [<span data-ttu-id="06b49-186">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="06b49-186">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="06b49-187">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-187">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="06b49-188">이전에 선택한 리소스 계정과 전화 시스템 자동 전화 통신 또는 통화 큐를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-188">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="06b49-189">구현 테스트</span><span class="sxs-lookup"><span data-stu-id="06b49-189">Test the implementation</span></span>

<span data-ttu-id="06b49-190">구현을 테스트하는 가장 좋은 방법은 전화 시스템 자동 전화 연결 또는 통화 큐에 대해 구성된 번호를 호출하고 에이전트 또는 메뉴 중 하나에 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-190">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="06b49-191">관리 센터 작업 창에서 테스트 단추를 사용하여 테스트 호출을 신속하게 **걸** 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-191">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="06b49-192">전화 시스템 자동 전화 연결 또는 통화 큐를 변경하려면 이 옵션을 선택하고 작업 창에서 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06b49-192">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="06b49-193">리소스 계정이 통화 큐 또는 자동 전화 회의에 할당되는 데 어려움이 있는 [](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) 경우 [Microsoft Teams에](/MicrosoftTeams/Known-issues#phone-system) 대한 알려진 문제와 Microsoft Teams 블로그의 하이브리드 응용 프로그램 인스턴스를 수정하는 방법 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b49-193">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="06b49-194">Exchange UM 자동 전화 교환 또는 통화 큐를 전화 시스템으로 이동</span><span class="sxs-lookup"><span data-stu-id="06b49-194">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="06b49-195">Exchange UM에서 전화 시스템으로 마이그레이션하려면 통화 큐 및 자동 전화 교환 구조를 다시 설정해야 합니다. 이 경우 통화 큐와 자동 전화 교환 구조를 직접 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-195">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="06b49-196">통화 큐 및 자동 전화 걸기 집합을 다시 구현하는 경우:</span><span class="sxs-lookup"><span data-stu-id="06b49-196">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="06b49-197">관리자로 로그인한 동안 Exchange 2013 또는 2016 시스템에서 다음 명령을 실행하여 모든 Exchange UM 자동 전화 교환 및 통화 큐 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-197">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="06b49-198">나열된 각 Exchange UM 통화 큐 또는 자동 전화 교환에 대해 구조, 설정 및 관련 소리 또는 텍스트 음성 음성 파일의 복사본을 확인합니다(출력의 GUID는 파일이 저장된 폴더의 이름임).</span><span class="sxs-lookup"><span data-stu-id="06b49-198">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="06b49-199">다음 명령을 실행하여 이러한 세부 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-199">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="06b49-200">이 명령에 대한 자세한 내용은 [Get-UMAutoAttendant를](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-200">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="06b49-201">캡처해야 할 수 있는 옵션의 전체 목록은 [UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 구성원이지만 가장 중요한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-201">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="06b49-202">업무 시간</span><span class="sxs-lookup"><span data-stu-id="06b49-202">Business hours</span></span>
    - <span data-ttu-id="06b49-203">업무 시간 이행 시간</span><span class="sxs-lookup"><span data-stu-id="06b49-203">Non-business hours</span></span>
    - <span data-ttu-id="06b49-204">언어</span><span class="sxs-lookup"><span data-stu-id="06b49-204">Language</span></span>
    - <span data-ttu-id="06b49-205">휴일 일정</span><span class="sxs-lookup"><span data-stu-id="06b49-205">Holiday schedule</span></span>

3. <span data-ttu-id="06b49-206">앞서 설명한 새 On-premises 끝점을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="06b49-206">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="06b49-207">테스트 목적으로 최상위 자동 전화 번호를 임시로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-207">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="06b49-208">앞서 설명한 바와 같이 끝점을 사용하는 전화 시스템 자동 전화 연결 또는 통화 큐를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-208">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

5. <span data-ttu-id="06b49-209">전화 시스템 자동 전화 연결 또는 통화 큐를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-209">Test the Phone System auto attendant or call queue.</span></span>

6. <span data-ttu-id="06b49-210">Exchange UM 통화 큐 또는 자동 전화 교환에 연결된 전화 번호를 해당 전화 시스템 자동 전화 교환 또는 통화 큐에 다시 배정합니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-210">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="06b49-211">이제 이미 UM 음성메일을 마이그레이션한 경우 2019년 10월로 마이그레이션할 Exchange Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b49-211">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="06b49-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06b49-212">See Also</span></span>

[<span data-ttu-id="06b49-213">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="06b49-213">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="06b49-214">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="06b49-214">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="06b49-215">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="06b49-215">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="06b49-216">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="06b49-216">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="06b49-217">클라우드 통화 큐 계획</span><span class="sxs-lookup"><span data-stu-id="06b49-217">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="06b49-218">On-premises 사용자를 위한 클라우드 음성메일 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="06b49-218">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="06b49-219">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="06b49-219">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="06b49-220">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="06b49-220">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="06b49-221">[Microsoft Teams에서 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts)  -  \( 온라인에 있는 리소스 계정을 만들 수 있습니다.\)</span><span class="sxs-lookup"><span data-stu-id="06b49-221">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
