---
title: 특정 사용자의 SharePoint 액세스 차단하기
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 특정 사용자의 SharePoint 액세스를 차단하는 방법 알아보기
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203841"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="41122-103">특정 사용자의 SharePoint 액세스 차단하기</span><span class="sxs-lookup"><span data-stu-id="41122-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="41122-104">Microsoft 365의 SharePoint에 모든 조건부 액세스(CA) 정책을 적용하는 것이 Teams에서도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="41122-105">그러나 일부 조직의 경우, SharePoint 파일 액세스(업로드, 다운로드, 보기, 편집, 만들기)를 차단하면서도 직원들이 관리되지 않는 장치에서 Teams 데스크톱, 모바일 및 웹 클라이언트를 사용할 수 있도록 허용하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="41122-106">CA 정책 하에서 Sharepoint를 차단하면 Teams도 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="41122-107">이 문서에서는 어떻게 이 한계를 피하고, SharePoint에 저장된 파일 액세스를 완전히 차단하면서도 직원들이 Teams를 계속 사용할 수 있도록 허용할 수 있는지에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="41122-108">관리되지 않는 장치에서 액세스를 차단하거나 제한하는 기능은 Azure AD 조건부 액세스 정책을 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="41122-109">[Azure AD 라이선싱](https://azure.microsoft.com/pricing/details/active-directory/)에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="41122-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="41122-110">Azure AD의 조건부 액세스에 대한 개요는 [Azure Active Directory의 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41122-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="41122-111">권장하는 SharePoint Online 액세스 정책에 대한 자세한 내용은 [SharePoint 사이트 및 파일 보호를 위한 정책 권장 사항](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41122-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="41122-112">관리되지 않는 장치에서 액세스를 제한하는 경우, 관리되는 장치의 사용자는 [지원되는 OS 및 브라우저 조합](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition) 중 하나를 사용해야 합니다. 그렇지 않으면 액세스가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="41122-113">다음의 경우 액세스를 차단하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-113">You can block or limit access for:</span></span>

- <span data-ttu-id="41122-114">조직의 모든 사용자 또는 일부 사용자 또는 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="41122-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="41122-115">조직의 모든 사이트 또는 일부 사이트</span><span class="sxs-lookup"><span data-stu-id="41122-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="41122-116">액세스가 차단되면 사용자에게 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="41122-117">액세스를 차단하면 보안이 보장되고 기밀 데이터를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="41122-118">액세스가 차단되면 사용자에게 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="41122-119">SharePoint 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="41122-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="41122-120">**정책** > **액세스 정책** 을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="41122-121">**관리 되지 않은 장치** 구역에서 **액세스 차단** 을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![정책에 대한 관리 되지 않은 장치 섹션](media/no-sharepoint-access1.png)

4. <span data-ttu-id="41122-123">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 포털을 열고 **조건부 액세스 정책** 을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="41122-124">SharePoint에서 다음 예와 유사한 새 정책이 생성된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![브라우저 액세스를 위해 앱 적용 제한 사용이라는 새 정책](media/no-sharepoint-access2.png)

5. <span data-ttu-id="41122-126">정책을 업데이트하여 특정 사용자나 그룹만을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-126">Update the policy to target only specific users or a group.</span></span>

    ![사용자 선택 섹션이 강조 표시된 Sharepoint 관리 센터](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="41122-128">이 정책을 설정하면 SharePoint 관리 포털에 대한 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="41122-129">제외 정책을 구성하고 전역 및 SharePoint 관리자를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41122-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="41122-130">대상 클라우드 앱으로 SharePoint만 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![Sharepoint가 대상 앱으로 선택되었습니다.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="41122-132">데스크톱 클라이언트 또한 포함하도록 **조건** 을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![강조 표시된 데스크톱 및 모바일 앱](media/no-sharepoint-access4.png)

8. <span data-ttu-id="41122-134">**액세스 권한 부여** 가 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-134">Make sure that **Grant access** is enabled</span></span>

    ![액세스 권한 부여가 설정되었습니다.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="41122-136">**앱 적용 제한 사용** 이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="41122-137">정책 사용을 설정하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-137">Enable your policy and select **Save**.</span></span>

    ![앱 적용 제한 사용이 설정되었습니다.](media/no-sharepoint-access6.png)

<span data-ttu-id="41122-139">정책을 테스트하려면 Teams 데스크톱 앱 또는 비즈니스용 OneDrive 동기화 클라이언트와 같은 클라이언트에서 로그아웃한 다음 다시 로그인하여 정책이 적용되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41122-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="41122-140">액세스가 차단된 경우 Teams에서 항목이 존재하지 않을 수 있음을 알리는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![항목 없음 메시지](media/access-denied-sharepoint.png)

<span data-ttu-id="41122-142">Sharepoint에서 액세스 거부 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41122-142">In Sharepoint, you'll receive an access denied message.</span></span>

![액세스 거부 메시지](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="41122-144">관련 주제</span><span class="sxs-lookup"><span data-stu-id="41122-144">Related topics</span></span>

[<span data-ttu-id="41122-145">SharePoint에서 관리 되지 않은 장치에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="41122-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
