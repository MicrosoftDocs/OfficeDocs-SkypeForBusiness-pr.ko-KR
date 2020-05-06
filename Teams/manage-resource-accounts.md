---
title: 팀에서 자원 계정 관리
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft 팀에서 자원 계정을 만들고, 편집 하 고, 관리 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: a8023ddf27b28fc64cd76b38127f43d4509a702d
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041765"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="f3e0a-103">Microsoft Teams에서 리소스 계정 관리</span><span class="sxs-lookup"><span data-stu-id="f3e0a-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="f3e0a-104">리소스 계정은 Azure AD의 *비활성 사용자 개체* 라고도 하며 일반적인 리소스를 나타내는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="f3e0a-105">Exchange에서 회의실을 나타내는 데 사용 될 수 있으며, 예를 들어 전화 번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="f3e0a-106">Microsoft 365 또는 구내에서 비즈니스용 Skype Server 2019를 사용 하 여 리소스 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="f3e0a-107">Microsoft 팀 또는 비즈니스용 Skype Online에서는 연결 된 리소스 계정이 하나 이상 있어야 하는 각 전화 시스템 통화 큐 또는 자동 전화 교환이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="f3e0a-108">자원 계정이 지정 된 전화 번호에 필요한 지 여부는 다음 다이어그램에 표시 된 것 처럼 관련 통화 대기열 또는 자동 전화 교환의 용도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="f3e0a-109">전화 번호를 리소스 계정에 할당 하기 전에이 문서의 맨 아래에 연결 된 통화 대기열 및 자동 전화 교환 문서를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![리소스 계정 및 사용자 라이선스의 예](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="f3e0a-111">이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="f3e0a-112">비즈니스용 Skype 서버 2019에 홈으로 표시 되는 리소스 계정의 경우 [리소스 계정 구성을](/SkypeForBusiness/hybrid/configure-onprem-ra)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="f3e0a-113">전화 시스템 통화 대기열에 전화 번호 지정</span><span class="sxs-lookup"><span data-stu-id="f3e0a-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="f3e0a-114">조직에서 이미 하나 이상의 전화 시스템 라이선스를 사용 하 고 있는 경우 전화 시스템 통화 대기열에 전화 번호를 지정 하는 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="f3e0a-115">서비스 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-115">Obtain a service number.</span></span>
2. <span data-ttu-id="f3e0a-116">무료 전화 시스템- [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md) 또는 리소스 계정이 나 전화 시스템 라이선스와 함께 사용 하는 유료 전화 시스템 라이선스를 취득 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="f3e0a-117">자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-117">Create the resource account.</span></span> <span data-ttu-id="f3e0a-118">연결 된 리소스 계정이 있는 경우 자동 전화 교환 또는 통화 대기열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="f3e0a-119">전화 시스템 또는 전화 시스템-가상 사용자 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="f3e0a-120">방금 라이선스를 할당 한 리소스 계정에 서비스 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="f3e0a-121">전화 시스템 통화 대기열 또는 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="f3e0a-122">통화 대기열 또는 자동 전화 교환과 함께 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="f3e0a-123">자동 전화 교환 또는 통화 대기열이 최상위 수준 자동 전화 교환 아래에 중첩 되는 경우 연결 된 리소스 계정은 자동 전화 교환 및 통화 대기열의 구조에 여러 항목을 입력 하려는 경우에만 전화 번호를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="f3e0a-124">온라인 상태인 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="f3e0a-125">[Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="f3e0a-126">엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f3e0a-127">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f3e0a-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="f3e0a-128">자원 계정 관련 문제가 발생 하지 않도록 하려면 다음 단계를 순서 대로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="f3e0a-129">생성 하는 전화 시스템 통화 대기열 또는 자동 전화 교환이 중첩 되 고 전화 번호가 필요 하지 않은 경우 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="f3e0a-130">자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-130">Create the resource account</span></span>
2. <span data-ttu-id="f3e0a-131">전화 시스템 통화 대기열 또는 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="f3e0a-132">전화 시스템에 리소스 계정 연결 통화 대기열 또는 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="f3e0a-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="f3e0a-133">전화 번호를 사용 하 여 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="f3e0a-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="f3e0a-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3e0a-135">전화 번호는 자동 전화 교환 또는 통화 대기열에 직접 할당 되지 않고 자동 전화 교환 또는 통화 대기열에 연결 된 리소스 계정으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="f3e0a-136">최상위 자동 전화 교환 또는 통화 대기열이 있으면 전화 번호를 자동 전화 교환에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="f3e0a-137">전화 번호를 사용 하는 리소스 계정을 만들기 위해 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="f3e0a-138">무료 또는 유료 서비스 번호를 사용 하거나 포트를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="f3e0a-139">다른 음성 서비스나 리소스 계정에 번호를 배정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="f3e0a-140">리소스 계정에 전화 번호를 지정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f3e0a-141">무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터** > **음성** > **전화 번호로**표시 되며, **번호 유형이** 서비스로 나열 됩니다 ( **무료)**.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f3e0a-142">서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md) 참조 하거나 기존 서비스 번호를 전송 하려는 경우 [전화 번호를 팀에 게 양도](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="f3e0a-143">리소스 계정에 전화 번호를 지정 하는 경우, 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="f3e0a-144">이렇게 하면 조직 수준에서 전화 시스템 기능을 전화 번호에 제공 하 고 자동 전화 교환 및 통화 대기열 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="f3e0a-145">전화 시스템 가상 사용자 라이선스 또는 일반 전화 시스템 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="f3e0a-146">가상 사용자 라이선스를 얻으려면 Microsoft 365 관리 센터에서 **청구** > **구입 서비스** > **추가 기능 구독** 으로 이동 하 여 끝으로 스크롤합니다. "전화 시스템-가상 사용자" 라이선스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="f3e0a-147">**지금 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-147">Select **Buy now**.</span></span> <span data-ttu-id="f3e0a-148">비용이 0 인 경우에도 다음 단계를 따라 라이선스를 취득 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="f3e0a-149">새 자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-149">Create a new resource account.</span></span> <span data-ttu-id="f3e0a-150">[Microsoft 팀 관리 센터에서 자원 계정 만들기](#create-a-resource-account-in-microsoft-teams-admin-center) 또는 [Powershell에서 리소스 계정 만들기](#create-a-resource-account-in-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="f3e0a-151">전화 시스템- [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md) 또는 전화 시스템 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="f3e0a-152">[한 명의 사용자에 게](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user) [Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md) 및 라이선스 할당을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="f3e0a-153">서비스 번호를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="f3e0a-154">[전화 번호 및 서비스 할당/할당 취소를](#assignunassign-phone-numbers-and-services)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="f3e0a-155">다음 중 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="f3e0a-156">클라우드 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="f3e0a-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="f3e0a-157">클라우드 통화 대기열</span><span class="sxs-lookup"><span data-stu-id="f3e0a-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="f3e0a-158">자동 전화 교환 또는 통화 대기열에 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="f3e0a-159">[전화 번호 및 서비스 할당/할당 취소를](#assignunassign-phone-numbers-and-services) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="f3e0a-160">자동 전화 교환을 만드는 동안 리소스 계정을 만들면 라이선스가 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="f3e0a-161">전화 번호 없이 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="f3e0a-162">중첩 된 자동 전화 교환 또는 통화 대기열에는 리소스 계정이 필요 하지만 대부분의 경우 해당 리소스 계정은 전화 번호와 전화 번호를 지 원하는 데 필요한 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="f3e0a-163">전화 번호가 필요 하지 않은 리소스 계정을 만들려면 다음 작업을 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="f3e0a-164">새 자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-164">Create a new resource account.</span></span> <span data-ttu-id="f3e0a-165">[Microsoft 팀 관리 센터에서 자원 계정 만들기](#create-a-resource-account-in-microsoft-teams-admin-center) 또는 [Powershell에서 리소스 계정 만들기](#create-a-resource-account-in-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
2. <span data-ttu-id="f3e0a-166">다음 중 하나를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="f3e0a-167">클라우드 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="f3e0a-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="f3e0a-168">클라우드 통화 대기열</span><span class="sxs-lookup"><span data-stu-id="f3e0a-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="f3e0a-169">통화 대기열 또는 자동 전화 교환에 리소스 계정을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="f3e0a-170">[전화 번호 및 서비스 할당/할당 취소를](#assignunassign-phone-numbers-and-services)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="f3e0a-171">Microsoft 팀 관리 센터에서 자원 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-171">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="f3e0a-172">전화 시스템 라이선스를 구매한 후 Microsoft 팀 관리 센터를 사용 하 여 **조직 전체 설정** > **리소스 계정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-172">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![자원 계정 페이지 스크린샷](media/r-a-master.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/teamscallout1.png)

<span data-ttu-id="f3e0a-175">새 리소스 계정을 만들려면 **+ 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-175">To create a new resource account click **+ Add**.</span></span> <span data-ttu-id="f3e0a-176">팝업 창에서 **표시 이름**, **사용자 이름** (도메인 이름)을 자동으로 채워야 함) 및 리소스 계정의 **리소스 계정 종류** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-176">In the pop-up, fill out the **Display name**, **Username** (the domain name should populate automatically), and **Resource account type**  for the resource account.</span></span> <span data-ttu-id="f3e0a-177">리소스 계정 종류는 리소스 계정에 연결 하려는 앱에 따라 **자동 전화 교환** 또는 **통화 대기열** 이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-177">Resource account type can be either **Auto attendant** or **Call queue** depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="f3e0a-178">준비가 되 면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-178">When you are ready,  click **Save**.</span></span>

![새 자원 계정 옵션 스크린샷](media/res-acct.png)

<span data-ttu-id="f3e0a-180">다음으로 [Office 365의 비즈니스용 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)에서 설명한 대로 O365 관리 센터의 리소스 계정에 라이선스를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-180">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="f3e0a-181">자원 계정 편집</span><span class="sxs-lookup"><span data-stu-id="f3e0a-181">Edit resource account</span></span> 

<span data-ttu-id="f3e0a-182">![](media/teamscallout2.png) 이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘 **편집** 옵션을 사용 하 여 리소스 계정 **표시 이름** 및 **리소스 계정** 유형을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="f3e0a-183">완료 되 면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-183">Click **Save** when you are done.</span></span>

![자원 계정 편집 옵션 스크린샷](media/r-a-edit.png)

<span data-ttu-id="f3e0a-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="f3e0a-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="f3e0a-186">전화 번호 및 서비스 할당/할당 취소</span><span class="sxs-lookup"><span data-stu-id="f3e0a-186">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="f3e0a-187">![이전 스크린샷](media/teamscallout3.png) 의 설명선을 참조 하는 번호 3의 아이콘입니다. 리소스 계정을 생성 하 고 라이선스를 할당 한 후에는 **할당/할당** 취소를 클릭 하 여 리소스 계정에 서비스 번호를 할당 하거나, 전화 번호 유형을 설정 하거나, 이미 존재 하는 특정 자동 전화 교환 또는 통화 대기열에 리소스 계정을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="f3e0a-188">직접 라우팅 번호 지정은 Cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="f3e0a-189">리소스 계정에 연결할 통화 대기열 또는 자동 전화 교환을 아직 만들지 않은 경우에는 해당 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account,leave that field blank.</span></span> <span data-ttu-id="f3e0a-190">생성 하는 동안 리소스 계정을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="f3e0a-191">완료 되 면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="f3e0a-192">**전화 번호 형식** 에 대 한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="f3e0a-193">없음</span><span class="sxs-lookup"><span data-stu-id="f3e0a-193">None</span></span>
- <span data-ttu-id="f3e0a-194">온라인</span><span class="sxs-lookup"><span data-stu-id="f3e0a-194">Online</span></span>
- <span data-ttu-id="f3e0a-195">무료</span><span class="sxs-lookup"><span data-stu-id="f3e0a-195">Toll-free</span></span>
- <span data-ttu-id="f3e0a-196">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="f3e0a-196">On-premises</span></span>

![할당/할당 취소 옵션 스크린샷](media/r-a-assign.png)

<span data-ttu-id="f3e0a-198">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당 하려면 PowerShell을 사용 해야 합니다. 다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3e0a-199">리소스 계정에 유효한 라이선스가 없는 경우 리소스 계정에 전화 번호를 할당 하려고 하면 내부 검사에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="f3e0a-200">번호를 할당 하거나 리소스 계정을 통화 대기열 또는 자동 전화 교환에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3e0a-201">전화 번호는 자동 전화 교환 또는 통화 대기열에 직접 할당 되지 않고 자동 전화 교환 또는 통화 대기열에 연결 된 리소스 계정으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="f3e0a-202">가상 사용자 라이선스를 사용 하도록 기존 리소스 계정 변경</span><span class="sxs-lookup"><span data-stu-id="f3e0a-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="f3e0a-203">기존 리소스 계정의 라이선스를 전화 시스템 라이선스에서 가상 사용자 라이선스로 전환 하려는 경우 무료 가상 사용자 라이선스를 취득 한 다음 Microsoft 365 관리 센터의 연결 된 단계에 따라 [사용자를 다른 구독으로 이동](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-203">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="f3e0a-204">항상 전체 전화 시스템 라이선스를 제거 하 고 동일한 라이선스 활동에 가상 사용자 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="f3e0a-205">이전 라이선스를 제거 하 고, 계정 변경 내용을 저장 하 고, 새 라이선스를 추가한 다음 계정 설정을 다시 저장 하면 리소스 계정이 더 이상 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="f3e0a-206">이 문제가 발생 하는 경우 가상 사용자 라이선스에 대 한 새 리소스 계정을 만들고 끊어진 리소스 계정을 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="f3e0a-207">Powershell에서 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="f3e0a-208">리소스 계정이 온라인 상태 인지 또는 비즈니스용 Skype Server 2019에 따라 관리자 권한을 사용 하 여 적절 한 Powershell 프롬프트에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="f3e0a-209">다음 Powershell cmdlet 예제에서는 [새 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)를 사용 하 여 온라인으로 리소스 계정을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="f3e0a-210">클라우드 통화 대기열 및 클라우드 자동 전화 교환에 사용할 수 있는 비즈니스용 Skype Server 2019에 있는 리소스 계정의 경우 [클라우드 통화 대기열 계획](/SkypeforBusiness/hybrid/plan-call-queue) 또는 [클라우드 자동 전화 교환 계획](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="f3e0a-211">하이브리드 구현 (직접 라우팅에 있는 숫자)은 온-프레미스 비즈니스용 Skype Server 2019 서버에서 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="f3e0a-212">응용 프로그램 인스턴스를 만들 때 사용 해야 하는 응용 프로그램 ID는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="f3e0a-213">**자동 전화 교환:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="f3e0a-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="f3e0a-214">**통화 대기열:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="f3e0a-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="f3e0a-215">Skype For Business Server 2019 사용자가 통화 대기열 또는 자동 전화 교환을 검색 가능 하 게 하려면 온라인 리소스 계정이 Active Directory로 동기화 되지 않으므로 비즈니스용 Skype Server 2019에서 리소스 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="f3e0a-216">Sipfederationtls 용 DNS SRV 레코드가 비즈니스용 Skype Server 2019에서 해결 되 면 SfB Management shell을 사용 하 여 비즈니스용 Skype Server 2019에서 리소스 계정을 만들고 온라인 Azure AD와 동기화 **해야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="f3e0a-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="f3e0a-217">자동 전화 교환에 사용할 리소스 계정을 온라인으로 만들려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="f3e0a-218">라이선스를 적용 하기 전에는 리소스 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="f3e0a-219">O365 관리 센터의 계정에 라이선스를 적용 하는 방법에 대 한 자세한 내용은 [Office 365에서 비즈니스용 사용자에](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) 게 라이선스 할당 및 비즈니스용 [Skype 라이선스 할당](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-219">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="f3e0a-220">) 자원 계정에 올바른 라이선스가 적용 되 면 아래와 같이 리소스 계정에 전화 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-220">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="f3e0a-221">일부 자원 계정에는 전화 번호가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="f3e0a-222">자원 계정에 라이선스를 적용 하지 않은 경우에는 전화 번호 할당이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-222">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="f3e0a-223">이 명령에 대 한 자세한 내용은 [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f3e0a-224">앞에서 설명한 대로 Microsoft 팀 관리 센터를 사용 하 여 온라인 전화 번호를 설정 하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="f3e0a-225">Microsoft 팀 또는 비즈니스용 Skype Server 2019에 있는 리소스 계정에 직접 라우팅 전화 번호를 할당 하려면 비즈니스용 Skype Online Powershell에 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="f3e0a-226">Microsoft 팀 관리 센터에서 자원 계정 설정 관리</span><span class="sxs-lookup"><span data-stu-id="f3e0a-226">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="f3e0a-227">Microsoft 팀 관리 센터에서 자원 계정 설정을 관리 하려면 **조직 전체 설정** > **리소스 계정**으로 이동 하 여 설정을 변경 하는 데 필요한 리소스 계정을 선택한 다음 **편집** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-227">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="f3e0a-228">**리소스 계정 편집** 화면에서 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-228">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="f3e0a-229">계정의 **표시 이름**</span><span class="sxs-lookup"><span data-stu-id="f3e0a-229">**Display name** for the account</span></span>
- <span data-ttu-id="f3e0a-230">계정을 사용 하는 통화 대기열 또는 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="f3e0a-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="f3e0a-231">계정에 할당 된 전화 번호</span><span class="sxs-lookup"><span data-stu-id="f3e0a-231">Phone number assigned to the account</span></span>

<span data-ttu-id="f3e0a-232">완료 되 면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-232">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="f3e0a-233">자원 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="f3e0a-233">Delete a resource account</span></span>

<span data-ttu-id="f3e0a-234">서비스 번호가 보류 모드에서 중지 되지 않도록 하려면 먼저 리소스 계정에서 전화 번호를 분리 하 여 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="f3e0a-235">다음 이상 기능을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-235">You can do that using the following commandlet:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="f3e0a-236">이렇게 하면 사용자 탭의 O365 관리 포털에서 리소스 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-236">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="f3e0a-237">리소스 계정에서 직접 라우팅 전화 번호의 연관을 해제 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="f3e0a-238">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f3e0a-238">Troubleshooting</span></span>

<span data-ttu-id="f3e0a-239">팀 관리 센터에서 자원 계정에 할당 된 전화 번호가 표시 되지 않고 해당 번호를 할당할 수 없는 경우 다음 사항을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-239">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="f3e0a-240">부서 특성에 비즈니스용 Skype 응용 프로그램 종점이 표시 되는 경우 아래에서 cmdlet을 실행 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-240">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="f3e0a-241">Cmldet을 실행 한 후 팀 관리 센터 웹 페이지를 새로 고치면 번호를 올바르게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0a-241">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="f3e0a-242">관련 정보</span><span class="sxs-lookup"><span data-stu-id="f3e0a-242">Related Information</span></span>

<span data-ttu-id="f3e0a-243">비즈니스용 Skype 서버와 혼성으로 구현 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="f3e0a-243">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="f3e0a-244">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="f3e0a-244">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="f3e0a-245">클라우드 통화 큐 계획</span><span class="sxs-lookup"><span data-stu-id="f3e0a-245">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="f3e0a-246">프레미스 리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="f3e0a-246">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="f3e0a-247">팀 또는 비즈니스용 Skype Online에서의 구현:</span><span class="sxs-lookup"><span data-stu-id="f3e0a-247">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="f3e0a-248">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="f3e0a-248">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="f3e0a-249">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="f3e0a-249">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="f3e0a-250">소규모 기업 예제 - 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="f3e0a-250">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="f3e0a-251">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="f3e0a-251">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="f3e0a-252">새로운 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f3e0a-252">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f3e0a-253">새로운 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f3e0a-253">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="f3e0a-254">전화 시스템-가상 사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="f3e0a-254">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
