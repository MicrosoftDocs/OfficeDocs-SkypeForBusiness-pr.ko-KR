---
title: 교육용 Microsoft Teams 리소스 관리
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Temas를 위한 라이선싱 연습입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83448f32ddfc96800a14b5a599ef9cb7af52bb9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119237"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="4bc35-103">교육에 대한 Microsoft 팀 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4bc35-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="4bc35-104">Microsoft Teams는 대화, 콘텐츠 및 앱을 한 위치에서 함께 가녀오는 디지털 허브입니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="4bc35-105">Office 365에서 개발되었기 때문에 학교에서 친숙한 Office 앱 및 서비스와의 통합을 통해 혜택을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="4bc35-106">교육 기관은 공동 작업 교실을 만들고 전문 학습 커뮤니티에 연결하고 교직원과 커뮤니케이션하고 모든 작업을 Microsoft Teams를 사용하여 교육용 Office 365 단일 환경에서 단일 환경에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="4bc35-107">시작하려면 IT 관리자가 Microsoft 365 관리 센터를 사용하여 [학교에 대한 Microsoft Teams를 사용할 수 있도록 설정해야 합니다](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="4bc35-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="4bc35-108">작업이 완료되면 사용자 계정에 라이선스를 할당하여 교직원, 직원 및 학생이 Microsoft Teams와 같은 Office 365 서비스에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="4bc35-109">사용자 계정을 사용자 계정에 개별적으로 할당 하거나 그룹 구성원을 통해 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="4bc35-110">이 문서에서는 Microsoft 365 관리 센터를 통해 개인 또는 소수의 사용자 계정에 Office 365 라이선스를 할당하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="4bc35-111">그룹 구성원을 통해 자동으로 라이선스를 할당 하려면 다음의 지원 문서 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc35-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="4bc35-112">Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bc35-112">Office 365 Powershell</span></span>](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="4bc35-113">Active Directory에서 그룹 기반 라이선싱</span><span class="sxs-lookup"><span data-stu-id="4bc35-113">Group-based Licensing in Active Directory</span></span>](/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="4bc35-114">**라이선스** 페이지 또는 **활성 사용자** 페이지에서 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="4bc35-115">제품 라이선스를 특정 사용자에게 할당할지 아니면 사용자 라이선스를 특정 제품에 할당할지 여부에 따라 사용하는 방법이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="4bc35-116">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="4bc35-117">라이선스 페이지에서 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4bc35-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="4bc35-118">전역 관리자, 청구 관리자, 라이선스 관리자 또는 사용자 관리 관리자 권한을 갖고 있어야 합니다. 자세한 내용은 [Office 365 관리자 역할 정보](/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc35-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="4bc35-119">**라이선스** 페이지를 사용하여 라이선스를 할당하는 경우 특정 제품에 대한 라이선스를 최대 20명의 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="4bc35-120">**라이선스** 페이지에서 구독이 있는 모든 제품의 목록, 각 제품에 대한 총 라이선스 수, 할당된 라이선스 수, 사용 가능한 개수 등이 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="4bc35-121">관리 센터에서 **청구** > [라이선스](https://go.microsoft.com/fwlink/p/?linkid=842264) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![청구 창 및 메뉴 옵션의 스크린샷.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="4bc35-123">라이선스를 할당하려는 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="4bc35-124">Microsoft 팀은 학생 SKU용 무료 Office 365 A1의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![라이선스를 할당하는 데 사용할 수 있는 제품이 있는 라이선스 페이지를 스크린샷합니다.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="4bc35-126">**라이선스 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-126">Select **Assign licenses**.</span></span>

   ![페이지의 사용자 섹션의 스크린샷 및 더하기 기호가 앞에 더하기 라이선스 할당 옵션입니다.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="4bc35-128">**사용자에 게 라이선스 할당** 창에서 이름을 입력하기 시작합니다. 이 경우 이름 목록이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="4bc35-129">검색 결과에서 찾으려는 이름을 선택하여 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="4bc35-130">한 번에 최대 20명의 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-130">You can add up to 20 users at a time.</span></span>

   ![사용자의 일부 이름을 입력하고, 일부 이름에 대한 검색 결과를 보여주는 사용자 페이지에 라이선스 할당을 스크린샷합니다.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="4bc35-132">**앱 및 서비스를 설정 또는 해제** 를 선택하여 Microsoft Teams와 같은 특정 항목에 대한 액세스 권한을 할당하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="4bc35-133">**Microsoft Teams** 및 **웹용 Office(교육)** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="4bc35-134">작업을 마치면 **할당** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="4bc35-135">사용자가 액세스할 수 있는 앱 및 서비스를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="4bc35-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="4bc35-136">사용자가 포함된 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="4bc35-137">오른쪽 창에서 액세스 권한을 부여 또는 제거할 앱과 서비스를 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="4bc35-138">작업을 마치면 **저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="4bc35-139">활성 사용자 페이지에서 개별 혹은 여러 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4bc35-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="4bc35-140">관리 센터에서 **사용자**  >  [활성 사용자](https://go.microsoft.com/fwlink/p/?linkid=834822) 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4bc35-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Microsoft O365 관리 센터에서 활성 사용자 메뉴 옵션의 스크린샷입니다.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="4bc35-142">라이선스를 할당하려는 사용자의 이름 옆의 원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![해당 이름 옆에 원이 채워져 일부 사용자가 선택된 활성 사용자 페이지 및 해당 페이지의 활성 사용자 목록의 스크린샷](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="4bc35-144">맨 위에 있는 **제품 라이선스 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-144">At the top select **Manage product licenses**.</span></span>

   ![제품 라이선스 탭 관리와 사용자 underneat가 사용 허가되지 않은 상태로 나열되는 스크린샷.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="4bc35-146">**제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당에 추가** > **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![기존 제품 라이선스 할당에 추가 라디오 단추가 선택된 제품 라이선스 관리 창의 스크린샷입니다.](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="4bc35-148">**기존 제품에 추가** 창에서 선택한 사용자에게 제공하려는 라이선스의 **설정** 위치로 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="4bc35-149">**Microsoft Teams** 및 **웹용 Office(교육)** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Microsoft Teams와 웹용 Office, 교육용, 기존 제품 탭에 추가 탭에 선택한 스크린샷입니다.](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="4bc35-151">기본적으로 이들 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="4bc35-152">사용자가 이용할 수 있는 서비스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="4bc35-153">사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글을 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="4bc35-154">창의 아래쪽에서 추가 > 닫기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc35-154">At the bottom of the pane, select Add > Close.</span></span>