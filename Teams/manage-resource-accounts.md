---
title: 팀에서 자원 계정 관리
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Microsoft 팀에서 자원 계정 관리에 대 한 자세한 정보
ms.openlocfilehash: dfb7a9b65003442266cc6cf25ea59b7270aa1c9c
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207170"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="d8eca-103">Microsoft 팀에서 자원 계정 관리</span><span class="sxs-lookup"><span data-stu-id="d8eca-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="d8eca-104">리소스 계정은 Azure AD의 *비활성 사용자 개체* 라고도 하며 일반적인 리소스를 나타내는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="d8eca-105">Exchange에서 회의실을 나타내는 데 사용 될 수 있으며, 예를 들어 전화 번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="d8eca-106">Microsoft 365 또는 구내에서 비즈니스용 Skype Server 2019를 사용 하 여 리소스 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="d8eca-107">Microsoft 팀 또는 비즈니스용 Skype Online에서 각 전화 시스템 통화 큐 또는 자동 전화 교환에는 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="d8eca-108">자원 계정이 지정 된 전화 번호에 필요한 지 여부는 다음 다이어그램에 표시 된 것 처럼 관련 통화 대기열 또는 자동 전화 교환의 용도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="d8eca-109">전화 번호를 리소스 계정에 할당 하기 전에이 문서의 맨 아래에 연결 된 통화 대기열 및 자동 전화 교환 문서를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![리소스 계정 및 사용자 라이선스의 예](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="d8eca-111">이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="d8eca-112">비즈니스용 Skype 서버 2019에 홈으로 표시 되는 리소스 계정의 경우 [리소스 계정 구성을](/SkypeForBusiness/hybrid/configure-onprem-ra)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="d8eca-113">개요</span><span class="sxs-lookup"><span data-stu-id="d8eca-113">Overview</span></span>

<span data-ttu-id="d8eca-114">조직에서 이미 하나 이상의 전화 시스템 라이선스를 사용 하 고 있는 경우 전화 시스템에 전화 번호를 지정 하려면 다음을 수행 합니다. 프로세스는 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue or auto attendant the process is:</span></span>

1. <span data-ttu-id="d8eca-115">서비스 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-115">Obtain a service number.</span></span>
2. <span data-ttu-id="d8eca-116">무료 전화 시스템- [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md) 또는 리소스 계정이 나 전화 시스템 라이선스와 함께 사용 하는 유료 전화 시스템 라이선스를 취득 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="d8eca-117">자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-117">Create the resource account.</span></span> <span data-ttu-id="d8eca-118">연결 된 리소스 계정이 있는 경우 자동 전화 교환 또는 통화 대기열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="d8eca-119">전화 시스템 또는 전화 시스템-가상 사용자 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="d8eca-120">방금 라이선스를 할당 한 리소스 계정에 서비스 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span> 
6. <span data-ttu-id="d8eca-121">전화 시스템 통화 대기열 또는 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="d8eca-122">통화 대기열 또는 자동 전화 교환과 함께 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-122">Link the resource account with a call queue or auto attendant.</span></span>

<span data-ttu-id="d8eca-123">자동 전화 교환 또는 통화 대기열이 최상위 수준 자동 전화 교환 아래에 중첩 되는 경우 연결 된 리소스 계정은 자동 전화 교환 및 통화 대기열의 구조에 여러 항목을 입력 하려는 경우에만 전화 번호를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="d8eca-124">온라인 상태인 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="d8eca-125">[Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="d8eca-126">엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d8eca-127">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d8eca-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="d8eca-128">자원 계정 관련 문제가 발생 하지 않도록 하려면 다음 단계를 순서 대로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="d8eca-129">생성 하는 전화 시스템 통화 대기열 또는 자동 전화 교환이 중첩 되 고 전화 번호가 필요 하지 않은 경우 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="d8eca-130">자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-130">Create the resource account</span></span> 
2. <span data-ttu-id="d8eca-131">전화 시스템 통화 대기열 또는 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="d8eca-132">전화 시스템에 리소스 계정 연결 통화 대기열 또는 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d8eca-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="d8eca-133">전화 번호를 사용 하 여 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="d8eca-134">최상위 자동 전화 교환 또는 통화 대기열이 있으면 전화 번호를 자동 전화 교환에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-134">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="d8eca-135">전화 번호를 사용 하는 리소스 계정을 만들기 위해 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-135">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="d8eca-136">무료 또는 유료 서비스 번호를 사용 하거나 포트를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-136">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="d8eca-137">다른 음성 서비스나 리소스 계정에 번호를 배정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-137">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="d8eca-138">리소스 계정에 전화 번호를 지정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-138">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="d8eca-139">무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터** > **음성** > **전화 번호로**표시 되며, **번호 유형이** 서비스로 나열 됩니다 ( **무료)**.</span><span class="sxs-lookup"><span data-stu-id="d8eca-139">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="d8eca-140">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md) 참조 하거나 기존 서비스 번호를 전송 하려면 [전화 번호를 Office 365에](transfer-phone-numbers-to-office-365.md)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-140">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="d8eca-141">리소스 계정에 전화 번호를 지정 하는 경우, 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-141">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="d8eca-142">이렇게 하면 조직 수준에서 전화 시스템 기능을 전화 번호에 제공 하 고 자동 전화 교환 및 통화 대기열 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-142">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="d8eca-143">전화 시스템 가상 사용자 라이선스 또는 일반 전화 시스템 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-143">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="d8eca-144">가상 사용자 라이선스를 얻으려면 Microsoft 365 관리 센터에서 **청구** > **구입 서비스** > **추가 기능 구독** 으로 이동 하 여 끝으로 스크롤합니다. "전화 시스템-가상 사용자" 라이선스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-144">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="d8eca-145">**지금 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-145">Select **Buy now**.</span></span> <span data-ttu-id="d8eca-146">비용이 0 인 경우에도 다음 단계를 따라 라이선스를 취득 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-146">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="d8eca-147">새 자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-147">Create a new resource account.</span></span> <span data-ttu-id="d8eca-148">[Microsoft 팀 관리 센터에서 자원 계정 만들기](#create-a-resource-account-in-microsoft-teams-admin-center) 또는 [Powershell에서 리소스 계정 만들기](#create-a-resource-account-in-powershell) 참조</span><span class="sxs-lookup"><span data-stu-id="d8eca-148">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="d8eca-149">전화 시스템- [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md) 또는 전화 시스템 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-149">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="d8eca-150">[Microsoft 팀 라이선스 할당](assign-teams-licenses.md) 및 [한 명의 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-150">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="d8eca-151">서비스 번호를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-151">Assign the service number to the resource account.</span></span> <span data-ttu-id="d8eca-152">[전화 번호 및 서비스 할당/할당 취소를](#assignunassign-phone-numbers-and-services)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-152">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="d8eca-153">다음 중 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-153">Set up one of the following:</span></span>
   - [<span data-ttu-id="d8eca-154">클라우드 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d8eca-154">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="d8eca-155">클라우드 통화 대기열</span><span class="sxs-lookup"><span data-stu-id="d8eca-155">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="d8eca-156">자동 전화 교환 또는 통화 대기열에 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-156">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="d8eca-157">[전화 번호 및 서비스 할당/할당 취소를](#assignunassign-phone-numbers-and-services) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-157">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="d8eca-158">전화 번호 없이 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-158">Create a resource account without a phone number</span></span>

<span data-ttu-id="d8eca-159">중첩 된 자동 전화 교환 또는 통화 대기열에는 리소스 계정이 필요 하지만 대부분의 경우 해당 리소스 계정은 전화 번호와 전화 번호를 지 원하는 데 필요한 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-159">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="d8eca-160">전화 번호가 필요 하지 않은 리소스 계정을 만들려면 다음 작업을 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-160">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="d8eca-161">새 자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-161">Create a new resource account.</span></span> <span data-ttu-id="d8eca-162">[Microsoft 팀 관리 센터에서 자원 계정 만들기](#create-a-resource-account-in-microsoft-teams-admin-center) 또는 [Powershell에서 리소스 계정 만들기](#create-a-resource-account-in-powershell) 참조</span><span class="sxs-lookup"><span data-stu-id="d8eca-162">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="d8eca-163">다음 중 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-163">Set up one of the following:</span></span>
   - [<span data-ttu-id="d8eca-164">클라우드 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d8eca-164">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="d8eca-165">클라우드 통화 대기열</span><span class="sxs-lookup"><span data-stu-id="d8eca-165">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="d8eca-166">통화 대기열 또는 자동 전화 교환에 리소스 계정을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-166">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="d8eca-167">[전화 번호 및 서비스 할당/할당 취소를](#assignunassign-phone-numbers-and-services) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-167">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="d8eca-168">Microsoft 팀 관리 센터에서 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-168">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="d8eca-169">전화 시스템 라이선스를 구매한 후 Microsoft 팀 관리 센터를 사용 하 여 **조직 전체 설정** > **리소스 계정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-169">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![자원 계정 페이지 스크린샷](media/r-a-master.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="d8eca-172">새 리소스 계정을 만들려면 **+ 새 계정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-172">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="d8eca-173">팝업 창에서 리소스 계정의 표시 이름과 사용자 이름 (도메인 이름이 자동으로 채워야 함)을 입력 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-173">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![새 자원 계정 옵션 스크린샷](media/res-acct.png)

<span data-ttu-id="d8eca-175">다음으로 [Office 365의 비즈니스용 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) 에서 설명한 대로 O365 관리 센터의 자원 계정에 라이선스를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-175">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="d8eca-176">자원 계정 이름 편집</span><span class="sxs-lookup"><span data-stu-id="d8eca-176">Edit resource account name</span></span>

<span data-ttu-id="d8eca-177">![이전 스크린샷](media/sfbcallout2.png) 의 설명선을 참조 하는 숫자 2의 아이콘은 **편집** 옵션을 사용 하 여 리소스 계정 표시 이름을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-177">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="d8eca-178">완료 되 면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-178">Click **Save** when you are done.</span></span>
<span data-ttu-id="d8eca-179">![자원 계정 편집 옵션 스크린샷](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="d8eca-179">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="d8eca-180">전화 번호 및 서비스 할당/할당 취소</span><span class="sxs-lookup"><span data-stu-id="d8eca-180">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="d8eca-181">![이전 스크린샷](media/sfbcallout3.png) 에서 설명선을 참조 하는 숫자 3의 아이콘입니다. 리소스 계정을 생성 하 고 라이선스를 할당 하면 **할당/할당** 취소를 클릭 하 여 리소스 계정에 서비스 번호를 할당 하거나 리소스를 할당할 수 있습니다. 이미 존재 하는 자동 전화 교환 또는 통화 대기열에 대 한 계정</span><span class="sxs-lookup"><span data-stu-id="d8eca-181">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="d8eca-182">직접 라우팅 번호 지정은 Cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-182">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="d8eca-183">통화 큐 또는 자동 전화 교환을 계속 만들어야 하는 경우에는 사용자가 만드는 동안 리소스 계정을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-183">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="d8eca-184">완료 되 면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-184">Click **Save** when you are done.</span></span>

<span data-ttu-id="d8eca-185">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당 하려면 PowerShell을 사용 해야 합니다. 다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-185">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8eca-186">리소스 계정에 유효한 라이선스가 없는 경우 리소스 계정에 전화 번호를 할당 하려고 하면 내부 검사에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-186">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="d8eca-187">번호를 할당 하거나 리소스 계정을 통화 대기열 또는 자동 전화 교환에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-187">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

![할당/할당 취소 옵션 스크린샷](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="d8eca-189">가상 사용자 라이선스를 사용 하도록 기존 리소스 계정 변경</span><span class="sxs-lookup"><span data-stu-id="d8eca-189">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="d8eca-190">기존 리소스 계정의 라이선스를 전화 시스템 라이선스에서 가상 사용자 라이선스로 전환 하려는 경우 무료 가상 사용자 라이선스를 취득 한 다음 Microsoft 365 관리 센터의 연결 된 단계에 따라 사용자를 다음으로 이동 합니다. [ 다른 구독](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="d8eca-190">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="d8eca-191">항상 전체 전화 시스템 라이선스를 제거 하 고 동일한 라이선스 활동에 가상 사용자 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-191">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="d8eca-192">이전 라이선스를 제거 하 고, 계정 변경 내용을 저장 하 고, 새 라이선스를 추가한 다음 계정 설정을 다시 저장 하면 리소스 계정이 더 이상 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-192">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="d8eca-193">이 문제가 발생 하는 경우 가상 사용자 라이선스에 대 한 새 리소스 계정을 만들고 끊어진 리소스 계정을 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-193">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="d8eca-194">Powershell에서 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-194">Create a resource account in Powershell</span></span>

<span data-ttu-id="d8eca-195">리소스 계정이 온라인 인지 아니면 구내에 있는지에 따라 관리자 권한을 사용 하 여 적절 한 Powershell 프롬프트에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-195">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="d8eca-196">다음 Powershell cmdlet 예제에서는 CsOnlineApplicationInstance가 온라인 인 리소스 계정을 만들기 위해 [New](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) 를 사용 하 여 리소스 계정을 온라인으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-196">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="d8eca-197">클라우드 통화 대기열 및 클라우드 자동 전화 교환에 사용할 수 있는 비즈니스용 Skype Server 2019에서 온-프레미스 리소스 계정의 경우 [클라우드 통화 큐 구성](/skypeforbusiness/hybrid/configure-call-queue.md) 또는 [클라우드 자동 전화 교환 구성을](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-197">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="d8eca-198">하이브리드 구현 (직접 라우팅에 있는 숫자)은 [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-198">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="d8eca-199">응용 프로그램 인스턴스를 만들 때 사용 해야 하는 응용 프로그램 ID는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-199">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="d8eca-200">**자동 전화 교환:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="d8eca-200">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="d8eca-201">**통화 대기열:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="d8eca-201">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="d8eca-202">온-프레미스 사용자가 통화 큐 또는 자동 전화 교환을 검색 가능 하 게 하려면 온라인 리소스 계정이 Active Directory와 동기화 되지 않으므로 리소스 계정을 온-프레미스로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-202">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="d8eca-203">자동 전화 교환에 사용할 리소스 계정을 온라인으로 만들려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-203">To create a resource account online for use with an auto attendant, use the following command.</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="d8eca-204">라이선스를 적용 하기 전에는 리소스 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-204">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="d8eca-205">O365 관리 센터의 계정에 라이선스를 적용 하는 방법에 대 한 자세한 내용은 [Office 365에서 비즈니스용 사용자에](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) 게 라이선스 할당 및 비즈니스용 [Skype 라이선스 할당](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-205">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="d8eca-206">) 자원 계정에 올바른 라이선스를 적용 한 후에는 다음과 같이 리소스 계정으로 전화 번호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-206">(Optional) Once the correct license is applied to the resource account you can set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="d8eca-207">일부 자원 계정에는 전화 번호가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-207">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="d8eca-208">자원 계정에 라이선스를 적용 하지 않은 경우에는 전화 번호 할당이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-208">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="d8eca-209">이 명령에 대 한 자세한 내용은 [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-209">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="d8eca-210">앞에서 설명한 대로 Microsoft 팀 관리 센터를 사용 하 여 온라인 전화 번호를 설정 하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-210">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="d8eca-211">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-211">To assign a direct routing or hybrid number to a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="d8eca-212">Microsoft 팀 관리 센터에서 자원 계정 설정 관리</span><span class="sxs-lookup"><span data-stu-id="d8eca-212">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="d8eca-213">Microsoft 팀 관리 센터에서 자원 계정 설정을 관리 하려면 **조직 전체 설정** > **리소스 계정**으로 이동 하 여 설정을 변경 하는 데 필요한 리소스 계정을 선택한 다음 **편집** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-213">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="d8eca-214">**리소스 계정 편집** 화면에서 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-214">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="d8eca-215">계정의 **표시 이름**</span><span class="sxs-lookup"><span data-stu-id="d8eca-215">**Display name** for the account</span></span>
- <span data-ttu-id="d8eca-216">계정을 사용 하는 통화 대기열 또는 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d8eca-216">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="d8eca-217">계정에 할당 된 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d8eca-217">Phone number assigned to the account</span></span>

<span data-ttu-id="d8eca-218">완료 되 면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-218">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="d8eca-219">자원 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="d8eca-219">Delete a resource account</span></span>

<span data-ttu-id="d8eca-220">서비스 번호가 보류 모드에서 중지 되지 않도록 하려면 먼저 리소스 계정에서 전화 번호를 분리 하 여 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-220">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="d8eca-221">다음 이상 기능을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-221">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="d8eca-222">이렇게 하면 사용자 탭의 O365 관리 포털에서 리소스 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-222">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d8eca-223">해결사</span><span class="sxs-lookup"><span data-stu-id="d8eca-223">Troubleshooting</span></span>

<span data-ttu-id="d8eca-224">팀 관리 센터에서 자원 계정에 할당 된 전화 번호가 표시 되지 않고 해당 번호를 할당할 수 없는 경우 다음 사항을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-224">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="d8eca-225">부서 특성에 비즈니스용 Skype 응용 프로그램 종점이 표시 되는 경우 아래에서 cmdlet을 실행 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8eca-225">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="d8eca-226">Cmldet을 실행 한 후 팀 관리 센터 웹 페이지를 새로 고치면 번호를 올바르게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eca-226">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="d8eca-227">관련 정보</span><span class="sxs-lookup"><span data-stu-id="d8eca-227">Related Information</span></span>

<span data-ttu-id="d8eca-228">비즈니스용 Skype 서버와 혼성으로 구현 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d8eca-228">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="d8eca-229">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="d8eca-229">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="d8eca-230">클라우드 통화 대기열 계획</span><span class="sxs-lookup"><span data-stu-id="d8eca-230">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="d8eca-231">프레미스 리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="d8eca-231">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="d8eca-232">팀 또는 비즈니스용 Skype Online에서의 구현:</span><span class="sxs-lookup"><span data-stu-id="d8eca-232">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="d8eca-233">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="d8eca-233">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="d8eca-234">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="d8eca-234">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="d8eca-235">Small business 예-자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="d8eca-235">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="d8eca-236">클라우드 통화 대기열 만들기</span><span class="sxs-lookup"><span data-stu-id="d8eca-236">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="d8eca-237">새로운 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8eca-237">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="d8eca-238">새로운 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d8eca-238">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="d8eca-239">전화 시스템-가상 사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="d8eca-239">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
