---
title: 비즈니스용 Skype 서버 2019에서 자원 계정 구성
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에 대 한 리소스 계정을 설정 합니다.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185547"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="5cb14-103">자원 계정 구성</span><span class="sxs-lookup"><span data-stu-id="5cb14-103">Configure resource accounts</span></span>

<span data-ttu-id="5cb14-104">비즈니스용 Skype Server 2019 하이브리드 구현은 통합 메시징을 위해 전화 시스템에서 제공 하는 클라우드 서비스만 사용 하 고 Exchange Online과 통합 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="5cb14-105">비즈니스용 Skype 서버 2019에서 이제 클라우드 통화 대기열과 자동 전화를 사용할 수 있습니다 [Office 365에서 전화 시스템을](/MicrosoftTeams/here-s-what-you-get-with-phone-system)사용 하 여 다음을 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="5cb14-106">비즈니스용 Skype Server 2019에서 이러한 전화 시스템 서비스를 사용 하려면 응용 프로그램 끝점 역할을 하는 리소스 계정을 만들고 전화 번호를 할당할 수 있도록 한 다음 온라인 팀 관리 센터를 사용 하 여 통화 큐 또는 자동 전화 교환을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="5cb14-107">이 리소스 계정은이 문서에서 설명 하는 대로 온라인 ( [Microsoft 팀의 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts) ) 또는 온-프레미스로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="5cb14-108">일반적으로 여러 개의 전화 시스템 서비스 노드가 있으며, 각각 리소스 계정으로 매핑되고 온라인 또는 비즈니스용 Skype 서버 2019에 연결 되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="5cb14-109">기존 Exchange UM 자동 전화 교환 및 통화 대기열 시스템을 사용 하는 경우 Exchange Server 2019 또는 Exchange online으로 전환 하기 전에 아래 설명 된 대로 세부 정보를 수동으로 기록해 야 하 고 팀 관리 센터를 사용 하 여 완전히 새로운 시스템을 구현 해야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="5cb14-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="5cb14-110">개요</span><span class="sxs-lookup"><span data-stu-id="5cb14-110">Overview</span></span>

<span data-ttu-id="5cb14-111">전화 시스템 서비스에 서비스 번호가 필요한 경우 다음 순서에 따라 다양 한 종속성을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="5cb14-112">서비스 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="5cb14-112">Obtain a service number</span></span>
2. <span data-ttu-id="5cb14-113">전화 시스템 라이선스 구입</span><span class="sxs-lookup"><span data-stu-id="5cb14-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="5cb14-114">자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-114">Create the resource account.</span></span> <span data-ttu-id="5cb14-115">연결 된 리소스 계정이 있는 경우 자동 전화 교환 또는 통화 대기열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="5cb14-116">온라인 및 온-프레미스 간 active directory 동기화 대기</span><span class="sxs-lookup"><span data-stu-id="5cb14-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="5cb14-117">전화 시스템 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="5cb14-118">서비스 번호를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="5cb14-119">전화 시스템 서비스 만들기 (통화 대기열 또는 자동 전화 교환)</span><span class="sxs-lookup"><span data-stu-id="5cb14-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="5cb14-120">리소스 계정을 서비스와 연결: (새-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="5cb14-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="5cb14-121">자동 전화 교환 또는 통화 대기열이 최상위 수준 자동 전화 교환 아래에 중첩 되는 경우 연결 된 리소스 계정은 자동 전화 교환 및 통화 대기열의 구조에 여러 항목을 입력 하려는 경우에만 전화 번호를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="5cb14-122">온라인 상태인 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="5cb14-123">[Microsoft 팀 라이선스 할당](/MicrosoftTeams/assign-teams-licenses)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="5cb14-124">엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="5cb14-125">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="5cb14-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="5cb14-126">생성 하는 전화 시스템 서비스가 중첩 되 고 전화 번호가 필요 하지 않은 경우 프로세스는 다음과 같이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="5cb14-127">자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-127">Create the resource account</span></span>  
2. <span data-ttu-id="5cb14-128">온라인 및 온-프레미스 간 active directory 동기화 대기</span><span class="sxs-lookup"><span data-stu-id="5cb14-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="5cb14-129">전화 시스템 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-129">Create a Phone System service</span></span>
4. <span data-ttu-id="5cb14-130">전화 시스템 서비스에 리소스 계정 연결</span><span class="sxs-lookup"><span data-stu-id="5cb14-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="5cb14-131">전화 번호를 사용 하 여 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="5cb14-132">전화 번호를 사용 하는 리소스 계정을 만들려면 다음 작업을 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="5cb14-133">무료 또는 유료 서비스 번호를 사용 하거나 포트를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="5cb14-134">다른 음성 서비스나 리소스 계정에 번호를 배정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="5cb14-135">리소스 계정에 전화 번호를 지정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="5cb14-136">무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터** > **음성** > **전화 번호로**표시 되며 나열 된 **번호 유형이** 서비스로 나열 됩니다 ( **무료)**.</span><span class="sxs-lookup"><span data-stu-id="5cb14-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="5cb14-137">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](/MicrosoftTeams/getting-service-phone-numbers) 참조 하거나 기존 서비스 번호를 전송 하려면 [전화 번호를 Office 365에](/MicrosoftTeams/transfer-phone-numbers-to-office-365)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="5cb14-138">미국 이외의 지역에 거주 하는 경우에는 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="5cb14-139">미국 이외의 지역에서이를 수행 하는 방법을 확인 하려면 [조직의 전화 번호 관리](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="5cb14-140">전화 시스템 라이선스를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-140">Buy a Phone System license.</span></span> <span data-ttu-id="5cb14-141">보기</span><span class="sxs-lookup"><span data-stu-id="5cb14-141">See:</span></span>  
   - [<span data-ttu-id="5cb14-142">Office 365 Enterprise E1 및 E3</span><span class="sxs-lookup"><span data-stu-id="5cb14-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="5cb14-143">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="5cb14-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="5cb14-144">Office 365 Enterprise E5 비즈니스 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="5cb14-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="5cb14-145">각 전화 시스템 서비스에 대 한 `New-CsHybridApplicationEndpoint` cmdlet을 실행 하 여 온-프레미스 리소스 계정을 만들고 각각 이름, sip 주소 등을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="5cb14-146">이 명령에 대 한 자세한 내용은 [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="5cb14-147">) 리소스 계정을 만든 후에는 광고가 온라인 및 온-프레미스 간에 동기화 될 때까지 기다리거나, 동기화를 실행 하 고 전화 시스템 서비스의 온라인 구성을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="5cb14-148">강제로 동기화 하려면 AAD Connect를 실행 하는 컴퓨터에서 다음 명령을 실행 합니다 (명령을 실행 하기 위해 이미 로드 `import-module adsync` 해야 하는 경우에는 완료 하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="5cb14-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="5cb14-149">이 명령에 대 한 자세한 내용은 [시작-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="5cb14-150">전화 시스템 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="5cb14-151">[Microsoft 팀 라이선스 할당](/MicrosoftTeams/assign-teams-licenses) 및 [한 명의 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="5cb14-152">리소스 계정에 전화 번호를 지정 하는 경우, 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="5cb14-153">이렇게 하면 조직 수준에서 전화 시스템 기능을 전화 번호에 제공 하 고 자동 전화 교환 및 통화 대기열 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="5cb14-154">서비스 번호를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="5cb14-155">`Set-CsHybridApplicationEndpoint` 명령을 사용 하 여 리소스 계정에 전화 번호 (-lineuri 옵션 포함)를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="5cb14-156">이 명령에 대 한 자세한 내용은 [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="5cb14-157">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="5cb14-158">최상위 자동 전화 교환 또는 통화 대기열에 할당 되는 경우, 리소스 계정에는 지정 된 전화번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="5cb14-159">사용자 (구독자) 전화 번호를 리소스 계정에 할당할 수 없는 경우에는 서비스 수신자 또는 무료 전화 번호만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="5cb14-160">전화 시스템 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-160">Create the Phone system service.</span></span> <span data-ttu-id="5cb14-161">다음 중 하나를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-161">See one of the following:</span></span>

   - [<span data-ttu-id="5cb14-162">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="5cb14-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="5cb14-163">클라우드 통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="5cb14-164">이전에 선택한 전화 시스템 서비스에 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="5cb14-165">소규모 비즈니스 구현의 예는 Small business에서 사용할 수 있습니다. [예-자동 전화 교환](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) 및 [small business 설정 예-통화 대기열 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)</span><span class="sxs-lookup"><span data-stu-id="5cb14-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="5cb14-166">전화 번호 없이 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="5cb14-167">이 섹션에서는 온-프레미스에 속한 리소스 계정 만들기에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="5cb14-168">온라인 인 리소스 계정을 만들려면 [Microsoft 팀의 자원 계정 관리](/MicrosoftTeams/manage-resource-accounts)에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="5cb14-169">이러한 단계는 새 휴대폰 시스템 서비스 시스템을 만들거나 Exchange UM에서 원래 만든 구조를 다시 만드는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="5cb14-170">비즈니스용 Skype 프런트 엔드 서버에 로그인 하 고 다음 PowerShell cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="5cb14-171">각 전화 시스템 서비스에 대 한 `New-CsHybridApplicationEndpoint` cmdlet을 실행 하 여 온-프레미스 리소스 계정을 만들고 각각 이름, sip 주소 등을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="5cb14-172">이 명령에 대 한 자세한 내용은 [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="5cb14-173">) 리소스 계정을 만든 후에는 광고가 온라인 및 온-프레미스 간에 동기화 될 때까지 기다리거나, 동기화를 실행 하 고 전화 시스템 서비스의 온라인 구성을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="5cb14-174">강제로 동기화 하려면 AAD Connect를 실행 하는 컴퓨터에서 다음 명령을 실행 합니다 (명령을 실행 하기 위해 이미 로드 `import-module adsync` 해야 하는 경우에는 완료 하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="5cb14-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="5cb14-175">이 명령에 대 한 자세한 내용은 [시작-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="5cb14-176">전화 시스템 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-176">Create the Phone system service.</span></span> <span data-ttu-id="5cb14-177">다음 중 하나를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-177">See one of the following:</span></span>
   - [<span data-ttu-id="5cb14-178">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="5cb14-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="5cb14-179">클라우드 통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="5cb14-180">이전에 선택한 리소스 계정과 전화 시스템 서비스를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="5cb14-181">소규모 비즈니스 구현의 예는 Small business에서 사용할 수 있습니다. [예-자동 전화 교환](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) 및 [small business 설정 예-통화 대기열 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)</span><span class="sxs-lookup"><span data-stu-id="5cb14-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="5cb14-182">구현 테스트</span><span class="sxs-lookup"><span data-stu-id="5cb14-182">Test the implementation</span></span>

<span data-ttu-id="5cb14-183">구현을 테스트 하는 가장 좋은 방법은 전화 시스템 서비스에 대해 구성 된 번호를 호출 하 고 에이전트 또는 메뉴 중 하나에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="5cb14-184">관리 센터 작업 창의 **테스트 단추** 를 사용 하 여 테스트 호출을 빠르게 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="5cb14-185">휴대폰 시스템 서비스를 변경 하려는 경우이를 선택 하 고 작업 창에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="5cb14-186">Exchange UM 자동 전화 교환 또는 통화 대기열을 전화 시스템으로 이동</span><span class="sxs-lookup"><span data-stu-id="5cb14-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="5cb14-187">Exchange UM에서 전화 시스템으로 마이그레이션한 후에는 통화 대기열 및 자동 전화 교환 구조를 다시 만들어야 하며, 한 쪽에서 다른으로 직접 마이그레이션하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="5cb14-188">통화 대기열 및 자동 전화 교환 집합을 다시 구현 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="5cb14-189">관리자 권한으로 로그인 하는 동안 Exchange 2013 또는 2016 시스템에서 다음 명령을 실행 하 여 모든 Exchange UM 자동 전화 교환 및 통화 큐의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="5cb14-190">나열 된 각 Exchange UM 통화 큐 또는 자동 전화 교환에 대해 구조에서 해당 위치를 확인 하 고, 연결 된 소리 또는 텍스트 음성 변환 파일의 복사본을 가져옵니다 (출력의 guid는 파일이 저장 된 폴더의 이름).</span><span class="sxs-lookup"><span data-stu-id="5cb14-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="5cb14-191">다음 명령을 실행 하 여 이러한 세부 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="5cb14-192">이 명령에 대 한 자세한 내용은 [Get UMAutoAttendant 전화 교환을](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb14-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="5cb14-193">캡처 해야 할 수 있는 옵션의 전체 목록은 [Umautoattendant 전화 교환 구성원](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 이지만 가장 중요 한 몇 가지 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="5cb14-194">업무 시간</span><span class="sxs-lookup"><span data-stu-id="5cb14-194">Business hours</span></span>
    - <span data-ttu-id="5cb14-195">근무 외 시간</span><span class="sxs-lookup"><span data-stu-id="5cb14-195">Non-business hours</span></span>
    - <span data-ttu-id="5cb14-196">언어</span><span class="sxs-lookup"><span data-stu-id="5cb14-196">Language</span></span>
    - <span data-ttu-id="5cb14-197">휴일 일정</span><span class="sxs-lookup"><span data-stu-id="5cb14-197">Holiday schedule</span></span>

3. <span data-ttu-id="5cb14-198">앞에서 설명한 대로 새 온-프레미스 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="5cb14-199">테스트 목적으로 최상위 자동 전화 교환 임시 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="5cb14-200">앞에서 설명한 대로 끝점을 사용 하는 전화 시스템 서비스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="5cb14-201">Small business 이라는 자습서의 연습을 사용 하는 것이 유용할 수 있습니다. 기존 Exchange UM 시스템의 계층 구조에 대 한 논리적 지도를 만들기 위해 [자동 전화 교환 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) 하기를 예로 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="5cb14-202">전화 시스템 서비스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="5cb14-203">Exchange UM 통화 대기열 또는 자동 전화 교환에 연결 된 전화 번호를 해당 전화 시스템 서비스에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="5cb14-204">이 시점에서 이미 UM 보이스 메일을 마이그레이션한 경우에는 Exchange Server 2019으로 마이그레이션해야 하는 위치에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb14-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cb14-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cb14-205">See Also</span></span>

[<span data-ttu-id="5cb14-206">클라우드 통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="5cb14-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="5cb14-207">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="5cb14-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="5cb14-208">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="5cb14-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="5cb14-209">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="5cb14-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="5cb14-210">클라우드 통화 대기열 계획</span><span class="sxs-lookup"><span data-stu-id="5cb14-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="5cb14-211">온-프레미스 사용자를 위한 클라우드 보이스 메일 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="5cb14-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="5cb14-212">새로운 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="5cb14-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="5cb14-213">새로운 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="5cb14-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="5cb14-214">[Microsoft 팀](/MicrosoftTeams/manage-resource-accounts) - \(에서 자원 계정을 관리 하 여 온라인으로 자원 계정 만들기 홈\)</span><span class="sxs-lookup"><span data-stu-id="5cb14-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
