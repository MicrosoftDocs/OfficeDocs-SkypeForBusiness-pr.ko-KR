---
title: 앱 사용자 지정 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
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
description: 앱에서 앱을 사용자 지정하는 Microsoft Teams.
ms.openlocfilehash: 6ef38c613151ece58591cf395add35276cb55c03
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796862"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="331a6-103">앱 사용자 지정 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="331a6-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="331a6-104">Microsoft Teams 환경을 개선하기 위해 앱 사용자 지정을 Teams 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="331a6-105">일부 앱 개발자는 앱 관리자에 의해 앱을 사용자 Teams 수 있습니다. 관리자는 관리 센터 관리 페이지를 사용하여 조직 요구에 따라 앱 속성을 사용자 지정하거나 Teams **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="331a6-106">사용자 지정할 수 있는 세부 정보는 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-106">The details you can customize are:</span></span>

- <span data-ttu-id="331a6-107">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="331a6-107">Short name</span></span>
- <span data-ttu-id="331a6-108">간략한 설명</span><span class="sxs-lookup"><span data-stu-id="331a6-108">Short description</span></span>
- <span data-ttu-id="331a6-109">전체 설명</span><span class="sxs-lookup"><span data-stu-id="331a6-109">Full description</span></span>
- <span data-ttu-id="331a6-110">개인 정보 취급 방침 URL</span><span class="sxs-lookup"><span data-stu-id="331a6-110">Privacy policy URL</span></span>
- <span data-ttu-id="331a6-111">웹 사이트 URL</span><span class="sxs-lookup"><span data-stu-id="331a6-111">Website URL</span></span>
- <span data-ttu-id="331a6-112">사용 약관 URL</span><span class="sxs-lookup"><span data-stu-id="331a6-112">Terms of use URL</span></span>
- <span data-ttu-id="331a6-113">색 아이콘</span><span class="sxs-lookup"><span data-stu-id="331a6-113">Color icon</span></span>
- <span data-ttu-id="331a6-114">개요 아이콘</span><span class="sxs-lookup"><span data-stu-id="331a6-114">Outline icon</span></span>
- <span data-ttu-id="331a6-115">강조 색</span><span class="sxs-lookup"><span data-stu-id="331a6-115">Accent color</span></span>

<span data-ttu-id="331a6-116">사용자 [지정할 Teams](/microsoftteams/platform/resources/schema/manifest-schema) 필드에 대한 자세한 내용은 매니페스트 매니페스트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-116">See the [Teams Manifest schema](/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="331a6-117">현재 GCCH(High) 정부 커뮤니티 클라우드(DoD) 또는 국방부(DoD)에서 앱을 사용자 지정하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="331a6-118">앱의 세부 정보 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="331a6-118">Customize the app's details</span></span>

<span data-ttu-id="331a6-119">앱 사용자 지정을 시작하고 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="331a6-120">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="331a6-121">앱 **Teams 확장하고** 앱 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="331a6-122">앱 **목록의** 사용자 지정 가능한 열을 확인하고 사용자 지정 가능한 앱별로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![정렬된 사용자 지정 열](media/customize-column.png)

   <span data-ttu-id="331a6-124">사용자 지정 기능에 액세스하는 세 가지 진입점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="331a6-125">사용자 지정하려는 앱 옆에 있는 를 선택한 다음 사용자 **지정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![사용자 지정 선택 옵션 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="331a6-127">앱 이름을 선택한 다음 **사용자 지정 가능 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-127">Select the app name and then **Customizable**.</span></span>

     ![사용자 지정 선택 옵션 2](media/app-details-customizable.png)

   - <span data-ttu-id="331a6-129">앱 이름을 선택한 다음 작업 **드롭다운에서** **사용자 지정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![사용자 지정 선택 옵션 3](media/customize-action-menu.png)

4. <span data-ttu-id="331a6-131">세부 정보 **섹션을** 확장하고 다음 필드를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="331a6-132">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="331a6-132">Short name</span></span>
    - <span data-ttu-id="331a6-133">간략한 설명</span><span class="sxs-lookup"><span data-stu-id="331a6-133">Short description</span></span>
    - <span data-ttu-id="331a6-134">전체 설명</span><span class="sxs-lookup"><span data-stu-id="331a6-134">Full description</span></span>
    - <span data-ttu-id="331a6-135">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="331a6-135">Website</span></span>
    - <span data-ttu-id="331a6-136">개인 정보 취급 방침 URL</span><span class="sxs-lookup"><span data-stu-id="331a6-136">Privacy policy URL</span></span>
    - <span data-ttu-id="331a6-137">사용 약관 URL</span><span class="sxs-lookup"><span data-stu-id="331a6-137">Terms of use URL</span></span>

   ![사용자 지정 설정](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="331a6-139">앱 개발자가 사용자 지정 가능으로 할당한 필드만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="331a6-140">아이콘 **섹션을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="331a6-141">a.</span><span class="sxs-lookup"><span data-stu-id="331a6-141">a.</span></span> <span data-ttu-id="331a6-142">업로드 아이콘을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-142">Upload an icon.</span></span> <span data-ttu-id="331a6-143">PNG 형식으로 하나의 전체 색 아이콘(192x192) 픽셀을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="331a6-144">b.</span><span class="sxs-lookup"><span data-stu-id="331a6-144">b.</span></span> <span data-ttu-id="331a6-145">아이콘 개요 색을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-145">Choose an icon outline color.</span></span> <span data-ttu-id="331a6-146">투명한 윤곽선(32x32) 픽셀을 PNG 형식으로 사용</span><span class="sxs-lookup"><span data-stu-id="331a6-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="331a6-147">c.</span><span class="sxs-lookup"><span data-stu-id="331a6-147">c.</span></span> <span data-ttu-id="331a6-148">아이콘과 일치하는 앱 악센트 색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-148">Select an app accent color that matches the icon.</span></span>

    ![아이콘 패널 색 옵션 사용자 지정](media/customize-app-colors.png)

6. <span data-ttu-id="331a6-150">앱이 사용자 지정되고 나면 적용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="331a6-151">게시를 **선택하여** 사용자 지정된 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="331a6-152">이제 사용자 지정된 앱이 앱 관리 페이지에 **나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="331a6-153">앱 기능을 사용자 지정해도 앱의 복사본을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="331a6-154">이제 최종 Teams 사용자 지정 앱을 보기 위해 Teams 클라이언트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![클라이언트에서 사용자 Teams 앱](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="331a6-156">앱 사용자 지정을 위한 특별한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="331a6-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="331a6-157">다음 노트에는 앱 사용자 지정에 대한 중요한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="331a6-158">앱 및 앱과 관련된 설명을 사용자 지정할 때 해당 설명서 또는 사용 약관에 앱 게시자가 제공한 사용자 지정 지침을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="331a6-159">또한 사용할 수 있는 타사 이미지와 관련하여 다른 사용자의 권리를 존중할 책임도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="331a6-160">관리자 제공 사용자 지정 데이터는 가장 가까운 지역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="331a6-161">귀하는 사용 약관 또는 개인 정보 취급 방침에 대한 링크가 유효한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="331a6-162">앱 게시자가 더 이상 필드를 사용자 지정할 수 없는 경우 앱 세부 정보 페이지에 더 이상 사용자 지정할 수 없는 필드에 대해 관리자에게 알리는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="331a6-163">이 필드에 대한 변경 내용은 모두 원래 값으로 되버렸다.</span><span class="sxs-lookup"><span data-stu-id="331a6-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="331a6-164">프로덕션 환경에서 이러한 변경을 수행하기 Teams 테스트 테넌트에서 앱 사용자 지정 변경을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-164">We recommend testing app customization changes in a Teams test tenant before making these changes in your production environment.</span></span>
> - <span data-ttu-id="331a6-165">브랜디드를 변경하려면 사용자가 변경 내용을 볼 수 있도록 최대 24시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-165">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="331a6-166">앱 세부 정보 검토</span><span class="sxs-lookup"><span data-stu-id="331a6-166">Review app details</span></span>

<span data-ttu-id="331a6-167">정보를 검토하기 위해 앱 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-167">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="331a6-168">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-168">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="331a6-169">**Teams 앱** 을 확장하고 **앱 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-169">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="331a6-170">앱 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-170">Select the app name.</span></span>

4. <span data-ttu-id="331a6-171">퍼블리셔의 원래 앱 이름 짧은 이름을 포함하여 앱 **세부 정보를 볼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-171">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![아이콘 패널 앱 이름 사용자 지정](media/original-app-version.png)

   <span data-ttu-id="331a6-173">게시자 **필드의** 짧은 이름은 앱의 짧은 이름을 변경한 경우만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-173">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="331a6-174">앱 세부 정보를 기본값으로 다시 설정</span><span class="sxs-lookup"><span data-stu-id="331a6-174">Reset app details to default</span></span>

<span data-ttu-id="331a6-175">앱 세부 정보를 원래 설정으로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-175">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="331a6-176">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-176">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="331a6-177">앱 **Teams 확장하고** 앱 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="331a6-177">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="331a6-178">앱 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-178">Select the app name.</span></span>

4. <span data-ttu-id="331a6-179">작업 **드롭다운에서 기본값으로** **재설정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-179">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![기본 강조 표시된으로 다시 설정 선택](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="331a6-181">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="331a6-181">Frequently asked questions</span></span>

<span data-ttu-id="331a6-182">**사용자 지정 앱을 보는 데 얼마나 오래 걸릴까요?**</span><span class="sxs-lookup"><span data-stu-id="331a6-182">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="331a6-183">관리자가 관리자 센터의 변경 내용을 즉시 볼 수 Teams 최종 사용자가 변경 내용을 보는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-183">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="331a6-184">**앱 공급자가 고객을 위해 앱을 사용자 지정할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="331a6-184">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="331a6-185">아니요, 테넌트 관리자는 관리 센터를 사용하여 테넌트에 대한 앱을 사용자 지정해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-185">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="331a6-186">**테넌트에서 현재 사용자 지정 앱을 바꾸기 위해 사용자 지정된 앱이 자동으로 배포될까요?**</span><span class="sxs-lookup"><span data-stu-id="331a6-186">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="331a6-187">아니요, 테넌트 관리자는 사용자 지정 앱을 수동으로 제거하고 사용자 지정된 버전의 앱을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-187">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="331a6-188">앱을 사용자 지정하고 사용자 지정 앱으로 게시한 경우 앱 사용자 지정 기능을 사용하여 사용자 지정한 새 앱이 현재 사용자 지정 앱을 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-188">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="331a6-189">**앱 사용 보고서에 사용자 지정된 짧은 이름과 같은 사용자 지정된 값도 표시하나요?**</span><span class="sxs-lookup"><span data-stu-id="331a6-189">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="331a6-190">아니요, 앱 사용 보고서는 퍼블리셔에서 보낸 앱의 원래 이름을 계속 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-190">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="331a6-191">**앱 사용자 지정 기능을 사용하여 어떤 앱을 사용자 지정할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="331a6-191">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="331a6-192">앱 게시자가 사용자 지정할 수 있도록 허용된 앱만 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-192">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="331a6-193">앱 게시자는 고객이 앱을 사용자 지정할 수 있도록 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-193">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="331a6-194">**그래프 사용 권한 동의 화면에 사용자 지정 속성이 표시될까요?**</span><span class="sxs-lookup"><span data-stu-id="331a6-194">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="331a6-195">아니요, 권한 동의 화면은 퍼블리셔가 보낸 원래 값을 계속 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="331a6-195">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="331a6-196">관련 문서</span><span class="sxs-lookup"><span data-stu-id="331a6-196">Related article</span></span>

- [<span data-ttu-id="331a6-197">앱 관리</span><span class="sxs-lookup"><span data-stu-id="331a6-197">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="331a6-198">앱 스토어 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="331a6-198">Customize your app store</span></span>](customize-your-app-store.md)
- [<span data-ttu-id="331a6-199">앱 다시브랜드</span><span class="sxs-lookup"><span data-stu-id="331a6-199">Rebrand your apps</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
