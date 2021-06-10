---
title: 리소스 계정 관리 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 이 문서에서는 이 문서에서 리소스 계정을 만들고 편집하고 관리하는 방법을 Microsoft Teams.
ms.openlocfilehash: 21824c360e26e568ae47a9729960fca01a100ae8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094248"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="24d8b-103">Microsoft Teams에서 리소스 계정 관리</span><span class="sxs-lookup"><span data-stu-id="24d8b-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="24d8b-104">리소스 계정은 Azure AD에서 사용할 수 없는 사용자 개체로, 일반적으로 리소스를 나타내는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="24d8b-105">예를 들어 리소스 계정을 사용하여 회의실을 Exchange 전화 번호와 일정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="24d8b-106">리소스 계정은 2019년 2019를 사용하여 Microsoft 365 또는 비즈니스용 Skype 서버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="24d8b-107">Microsoft Teams 각 자동 참석자 또는 호출 큐에 대한 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="24d8b-108">리소스 계정에 서비스 전화 번호가 할당될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="24d8b-109">자동 참석자 및 통화 큐에 전화 번호를 할당하여 외부의 Teams 전화 큐에 도달할 수 있도록 하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="24d8b-110">이 문서에서는 리소스 계정을 만들고 자동 참석자 및 호출 큐와 함께 사용할 수 있도록 준비하는 방법을 다 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="24d8b-111">이 문서에서 절차를 시작하기 전에 다음을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="24d8b-112">가상 사용자 라이선스 획득</span><span class="sxs-lookup"><span data-stu-id="24d8b-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="24d8b-113">서비스 번호 획득</span><span class="sxs-lookup"><span data-stu-id="24d8b-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="24d8b-114">가상 사용자 라이선스 획득</span><span class="sxs-lookup"><span data-stu-id="24d8b-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="24d8b-115">각 리소스 계정에는 자동 참석자 작업 및 큐 호출을 위해 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="24d8b-116">가상 사용자 라이선스 - Microsoft 365 전화 시스템 *사용할 수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="24d8b-117">이러한 라이선스를 얻은 경우 [Virtual User 라이선스 를 참조합니다.](teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="24d8b-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="24d8b-118">이 문서의 나중에 리소스 계정에 라이선스를 할당하는 방법에 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="24d8b-119">가상 사용자 라이선스를 얻게 Microsoft 365 관리 센터에서 청구 구매 서비스 추가 기능 구독으로 이동하고 끝까지 스크롤합니다. 전화 시스템  >    >   - Virtual *User 라이선스가* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="24d8b-120">지금 **구입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-120">Select **Buy now**.</span></span> <span data-ttu-id="24d8b-121">비용은 0이지만 라이선스를 획득하려면 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="24d8b-122">서비스 번호 획득</span><span class="sxs-lookup"><span data-stu-id="24d8b-122">Obtain service numbers</span></span>

<span data-ttu-id="24d8b-123">서비스 번호는 자동 참석자 및 통화 큐에 선택적이지만 발신자가 자동 참석자에 도달하고 큐 구성을 호출하려면 하나 이상의 서비스 번호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="24d8b-124">서비스 번호로 직접 연결하려는 자동 참석자 또는 호출 큐의 경우 연결된 서비스 번호가 있는 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="24d8b-125">리소스 계정은 무료 서비스 번호 또는 무료 서비스 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="24d8b-126">다른 통신사에서 새 번호 또는 포트 기존 번호를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="24d8b-127">새 서비스 번호를 얻은 경우 서비스 전화 번호 를 [참조합니다.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="24d8b-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="24d8b-128">다른 통신사에서 번호를 포트하는 경우 전화 [번호 전송을 Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="24d8b-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="24d8b-129">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="24d8b-129">Create a resource account</span></span>

<span data-ttu-id="24d8b-130">관리 센터에서 리소스 계정을 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-130">You can create a resource account in the Teams admin center.</span></span>

![리소스 계정 사용자 인터페이스 추가 스크린샷](media/resource-account-add.png)

1. <span data-ttu-id="24d8b-132">Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 리소스 계정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="24d8b-133">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-133">Click **Add**.</span></span>

3. <span data-ttu-id="24d8b-134">리소스 계정 **추가 창에서** 표시 **이름,** **사용자** 이름 및 리소스 계정 유형 **을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="24d8b-135">리소스 계정 유형은 이 리소스 계정을 사용하는 방법에 따라 **자동** 참석자 또는 통화 큐일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="24d8b-136">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-136">Click **Save**.</span></span>

![리소스 계정 목록 스크린샷](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="24d8b-138">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="24d8b-138">Assign a license</span></span>

<span data-ttu-id="24d8b-139">각 리소스 계정에 대해 가상 사용자 *Microsoft 365 전화 시스템 라이선스* 또는 전화 시스템 *할당해야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![관리 센터에서 라이선스 사용자 인터페이스 할당 Microsoft 365 스크린샷](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="24d8b-141">관리 Microsoft 365 관리 센터에서 라이선스를 할당할 리소스 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="24d8b-142">라이선스 **및** 앱 탭의 라이선스에서 가상 **Microsoft 365 전화 시스템 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="24d8b-143">변경 **내용 저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="24d8b-144">서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="24d8b-144">Assign a service number</span></span>

<span data-ttu-id="24d8b-145">서비스 번호가 필요한 자동 참석자 또는 호출 큐에서 리소스 계정을 사용하려면 리소스 계정에 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![서비스 번호 사용자 인터페이스 할당 스크린샷](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="24d8b-147">관리 Teams 관리 센터의 **리소스** 계정 페이지에서 서비스 번호를 할당할 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="24d8b-148">숫자 **전화** 드롭다운에서 사용할 숫자 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="24d8b-149">할당된 전화 번호 **상자에서** 사용할 번호를 검색하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="24d8b-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="24d8b-150">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-150">Click **Save**.</span></span>


<span data-ttu-id="24d8b-151">리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당하려면 PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="24d8b-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="24d8b-152">Next steps</span></span>

<span data-ttu-id="24d8b-153">리소스 계정 설정을 완료하고 필요한 경우 서비스 번호를 할당하면 자동 참석자 또는 통화 큐에서 리소스 계정을 사용할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="24d8b-154">다음 참조를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-154">See the following references:</span></span>

 - [<span data-ttu-id="24d8b-155">클라우드 자동 참석자</span><span class="sxs-lookup"><span data-stu-id="24d8b-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="24d8b-156">클라우드 호출 큐</span><span class="sxs-lookup"><span data-stu-id="24d8b-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="24d8b-157">편집 옵션을 사용하여 리소스 계정 **표시 이름** 및 **리소스 계정** 유형을 **편집할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="24d8b-158">완료되면  저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="24d8b-159">Virtual User 라이선스를 사용하도록 기존 리소스 계정 변경</span><span class="sxs-lookup"><span data-stu-id="24d8b-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="24d8b-160">기존 리소스 계정의 **라이선스를** 가상 사용자 전화 시스템 라이선스로 전환하려면 무료 가상 사용자 라이선스를 획득한 다음 관리 센터의 Microsoft 365 단계를 따라 다른 구독으로 사용자를 이동해야 [합니다.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="24d8b-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="24d8b-161">항상 전체 라이선스를 전화 시스템 동일한 라이선스 작업에서 Virtual User 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="24d8b-162">이전 라이선스를 제거하고, 계정 변경 내용을 저장하고, 새 라이선스를 추가한 다음 계정 설정을 다시 저장하면 리소스 계정이 더 이상 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="24d8b-163">이 경우 Virtual User 라이선스에 대한 새 리소스 계정을 만들고 손상된 리소스 계정을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="24d8b-164">Skype Business Server 2019용</span><span class="sxs-lookup"><span data-stu-id="24d8b-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="24d8b-165">클라우드 호출 큐 및 클라우드 자동 Skype 사용할 수 있는 비즈니스용 서버 2019에 있는 [](/SkypeforBusiness/hybrid/plan-call-queue) 리소스 계정의 경우 클라우드 호출 큐 계획 또는 클라우드 자동 참석자 계획 을 [참조합니다.](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)</span><span class="sxs-lookup"><span data-stu-id="24d8b-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="24d8b-166">하이브리드 구현(직접 라우팅에 있는 숫자)은 2019년 2019년 프레미스 서버의 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet을 사용하여 비즈니스용 Skype 서버 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="24d8b-167">애플리케이션 인스턴스를 만드는 동안 사용해야 하는 애플리케이션 신분은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="24d8b-168">**자동 전화 교환:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="24d8b-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="24d8b-169">**통화 큐:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="24d8b-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="24d8b-170">비즈니스용 Server 2019 사용자에 의해 호출 큐 또는 자동 참석자가 검색할 수 있도록 Skype 경우 온라인 리소스 계정이 Active Directory에 동기화되지 Skype For Business Server 2019에서 리소스 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="24d8b-171">sipfederationtls에 대한 DNS SRV 레코드가 2019 비즈니스용 Skype 서버 확인되면 SfB Management 셸을 사용하여 Skype For Business Server 2019에서 리소스 계정을 만들어 Azure AD에 동기화해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="24d8b-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="24d8b-172">다음을 통해 하이브리드되는 구현의 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="24d8b-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="24d8b-173">클라우드 자동 전화 교환 계획</span><span class="sxs-lookup"><span data-stu-id="24d8b-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="24d8b-174">클라우드 통화 큐 계획</span><span class="sxs-lookup"><span data-stu-id="24d8b-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="24d8b-175">프레미스 리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="24d8b-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="24d8b-176">리소스 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="24d8b-176">Delete a resource account</span></span>

<span data-ttu-id="24d8b-177">서비스 번호가 보류 중인 모드에 찌르지 않도록 해당 번호를 삭제하기 전에 리소스 계정에서 전화 번호를 해리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="24d8b-178">이 작업을 진행한 후 사용자 탭의 Microsoft 365 관리 센터에서 리소스 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d8b-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="24d8b-179">리소스 계정에서 직접 라우팅 전화 번호를 분해하려면 다음 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="24d8b-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```