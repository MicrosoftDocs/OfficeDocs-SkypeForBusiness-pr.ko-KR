---
title: 특정 사용자를 위해 SharePoint에 대 한 액세스 차단
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
description: 특정 사용자를 위해 SharePoint에 대 한 액세스를 차단 하는 방법에 대 한 자세한 정보
ms.openlocfilehash: 959de8c06e26d2d12c3a3698375b11d373392447
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956039"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="6a898-103">특정 사용자를 위해 SharePoint에 대 한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6a898-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="6a898-104">SharePoint Online (SPO)에 대 한 모든 조건부 액세스 (CA) 정책은 팀에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-104">Applying any Conditional Access (CA) policy on SharePoint Online (SPO) is also applied to Teams.</span></span> <span data-ttu-id="6a898-105">그러나 일부 조직에서는 SharePoint 파일에 대 한 액세스를 차단 하 여 (업로드, 다운로드, 보기, 편집, 만들기) 아직 직원이 관리 되지 않는 장치에서 팀 데스크톱, 모바일, 웹 클라이언트를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="6a898-106">CA 정책 규칙에 따라 SPO를 차단 하면 팀도 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-106">Under the CA policy rules, blocking SPO would lead to blocking Teams as well.</span></span> <span data-ttu-id="6a898-107">이 문서에서는이 제한을 해결 하 고 직원이 SPO에 저장 된 파일에 대 한 액세스를 완전히 차단 하면서 팀을 계속 사용할 수 있도록 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SPO.</span></span>

> [!Note]
> <span data-ttu-id="6a898-108">관리 되지 않는 장치에서 액세스를 차단 하거나 제한 하는 것은 Azure AD 조건부 액세스 정책에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="6a898-109">[AZURE AD 라이선스](https://azure.microsoft.com/pricing/details/active-directory/)에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="6a898-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="6a898-110">Azure AD의 조건부 액세스에 대 한 개요는 [Azure Active Directory에서 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a898-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="6a898-111">추천 SharePoint 액세스 정책에 대 한 자세한 내용은 [sharepoint 사이트 및 파일 보호에 대 한 정책 권장 사항을](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a898-111">For info about recommended SharePoint access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="6a898-112">관리 되지 않는 장치에 대 한 액세스를 제한 하는 경우 관리 디바이스의 사용자가 [지원 되는 OS 및 브라우저 조합](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)중 하나를 사용 해야 하며 그렇지 않은 경우에도 액세스가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="6a898-113">다음에 대 한 액세스를 차단 하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-113">You can block or limit access for:</span></span>

- <span data-ttu-id="6a898-114">조직의 사용자 또는 일부 사용자 또는 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="6a898-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="6a898-115">조직의 모든 사이트 또는 일부 사이트만</span><span class="sxs-lookup"><span data-stu-id="6a898-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="6a898-116">액세스가 차단 되 면 사용자에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="6a898-117">액세스를 차단 하면 보안을 제공 하 고 보안 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="6a898-118">액세스가 차단 되 면 사용자에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="6a898-119">SharePoint [관리 센터](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="6a898-120">**정책**  >  **액세스 정책을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="6a898-121">**관리 되지 않는 장치** 섹션에서 **액세스 차단** 을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![정책에 대 한 관리 되지 않는 장치 섹션](media/no-sharepoint-access1.png)

4. <span data-ttu-id="6a898-123">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 포털을 열고 **조건부 액세스 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="6a898-124">이 예제와 유사한 새 정책이 SharePoint에서 생성 된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![브라우저 액세스에 대 한 앱 적용 제한 사용 이라는 새로운 정책](media/no-sharepoint-access2.png)

5. <span data-ttu-id="6a898-126">정책을 업데이트 하 여 특정 사용자 또는 그룹만 대상으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-126">Update the policy to target only specific users or a group.</span></span>

    ![사용자 선택 섹션이 강조 표시 된 Sharepoint 관리 센터입니다.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="6a898-128">이 정책을 설정 하면 SharePoint 관리자 포털에 대 한 액세스를 잘라낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="6a898-129">제외 정책을 구성 하 고 전역 및 SharePoint 관리자를 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="6a898-130">SharePoint Online만 대상 클라우드 앱으로 선택 되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="6a898-130">Verify that only SharePoint Online is selected as targeted Cloud App</span></span>

    ![대상 앱으로 Sharepoint online이 선택 되어 있습니다.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="6a898-132">데스크톱 클라이언트도 포함 하도록 **조건을** 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![데스크톱 및 모바일 앱이 강조 표시 됨](media/no-sharepoint-access4.png)

8. <span data-ttu-id="6a898-134">**액세스 허용** 이 설정 되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="6a898-134">Make sure that **Grant access** is enabled</span></span>

    ![액세스 허용이 활성화 되어 있습니다.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="6a898-136">**앱 적용 제한 사용** 이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="6a898-137">정책을 사용 하도록 설정 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-137">Enable your policy and select **Save**.</span></span>

    ![앱 적용 제한을 사용할 수 있습니다.](media/no-sharepoint-access6.png)

<span data-ttu-id="6a898-139">정책을 테스트 하려면 팀 데스크톱 앱 또는 OneDrive 동기화 클라이언트 등의 클라이언트에서 로그 아웃 하 고 다시 로그인 하 여 정책 작동을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="6a898-140">액세스가 차단 된 경우에는 항목이 존재 하지 않을 수 있다는 메시지가 팀에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![항목을 찾을 수 없음 메시지가 있습니다.](media/access-denied-sharepoint.png)

<span data-ttu-id="6a898-142">Sharepoint에서는 액세스 거부 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a898-142">In Sharepoint, you'll receive an access denied message.</span></span> 

![액세스 거부 메시지입니다.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="6a898-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6a898-144">Related topics</span></span>

[<span data-ttu-id="6a898-145">SharePoint의 관리 되지 않는 장치에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="6a898-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
