---
title: 디바이스 태그 Microsoft Teams 관리 및 필터링
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
description: 디바이스에서 태그를 관리하고 필터링하는 Microsoft Teams 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a4f8ac718a965834678098a8960347278d13aa3
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874998"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="31d55-103">디바이스 Microsoft Teams 관리</span><span class="sxs-lookup"><span data-stu-id="31d55-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="31d55-104">조직의 디바이스 태그를 Microsoft Teams 조직에서 배포한 디바이스를 그룹화, 구성 및 보다 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="31d55-105">Microsoft Teams 관리 센터를 사용하면 하나 이상의 태그를 디바이스에 추가하고 필터를 사용하여 지정한 태그와 일치하는 디바이스를 보고 해당 태그가 있는 디바이스에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions on the devices that have that tag.</span></span>

<span data-ttu-id="31d55-106">디바이스 태그를 두 개 이상의 디바이스 유형에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="31d55-107">그러나 관리 센터에서 디바이스 창을 열면 해당 유형의 디바이스만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="31d55-108">예를 들어 휴대폰 및 디바이스 모두에 "회사" 태그를 할당할 Teams 룸 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="31d55-109">디바이스 휴대폰에서 "회사" 태그를 검색하는 경우  >  휴대폰만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="31d55-110">마찬가지로 디바이스에서 "회사" 태그를 검색하는   >  **Teams 룸** 디바이스만 Teams 룸 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="31d55-111">디바이스 태그를 관리하려면 전역 관리자, 서비스 Teams 또는 디바이스 Teams 관리해야 합니다. 관리자 역할에 대한 자세한 내용은 [관리자](../using-admin-roles.md)Microsoft Teams 관리자 역할 사용 을 Teams.</span><span class="sxs-lookup"><span data-stu-id="31d55-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31d55-112">디바이스 태그는 디바이스에 로그인된 리소스 계정에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="31d55-113">한 디바이스에서 리소스 계정을 로그인한 다음 이를 사용하여 다른 디바이스에 로그인하면 디바이스 태그가 새 디바이스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-113">If you sign a resource account out of one device and then use it to sign in to another device, the device tags are applied to the new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="31d55-114">디바이스 태그 만들기, 제거 또는 이름 변경</span><span class="sxs-lookup"><span data-stu-id="31d55-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="31d55-115">디바이스 태그 관리 패널을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="31d55-116">모든 디바이스 태그를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31d55-116">See all your device tags.</span></span>
- <span data-ttu-id="31d55-117">여러 디바이스 태그를 쉽게 만든 다음 나중에 디바이스에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="31d55-118">태그는 최대 25자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="31d55-119">더 이상 필요하지 않습니다 디바이스 태그를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="31d55-120">디바이스 태그를 제거하려면 먼저 추가된 모든 디바이스에서 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="31d55-121">디바이스 태그의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-121">Rename device tags.</span></span> <span data-ttu-id="31d55-122">디바이스 태그의 이름을 바꾸면 해당 변경이 추가된 모든 디바이스에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="31d55-123">태그는 최대 25자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="31d55-124">를 방문하여 Microsoft Teams 관리 센터에 https://admin.teams.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="31d55-125">디바이스로 **이동한** 다음 휴대폰과 같은 디바이스 **창을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="31d55-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="31d55-126">페이지의 **오른쪽** 위 모서리에서 작업을 선택하고 모든 **디바이스 태그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="31d55-127">디바이스 태그를 만들하려면 **+** 추가 , 디바이스 태그에 대한 값을 제공하고 저장 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="31d55-128">디바이스 태그를 제거하려면 제거하려는  디바이스 태그 옆에 있는 타원...을 선택하고 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="31d55-129">디바이스에 추가된 디바이스 태그를 제거하려고 하는 경우 모든 장치에서 제거할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="31d55-130">이렇게 하고 디바이스 태그를 계속 제거하려면 디바이스 태그 제거 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="31d55-131">디바이스 태그의 이름을 변경하려면 이름을 변경하려는 디바이스 태그 옆에 있는 타원...을 선택하고 **편집을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="31d55-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="31d55-132">디바이스 태그에 대한 새 값을 제공하고 저장 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="31d55-133">단일 디바이스에서 태그 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="31d55-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="31d55-134">디바이스에 태그를 추가할 때 기존 태그를 선택하거나 새 태그를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="31d55-135">태그는 최대 25자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="31d55-136">를 방문하여 Microsoft Teams 관리 센터에 https://admin.teams.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="31d55-137">디바이스로 **이동한** 다음, 태그를 추가하거나 제거할 디바이스가 포함된 디바이스 창을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="31d55-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="31d55-138">태그를 추가하거나 제거할 디바이스 옆에 확인 표시를 지정하고 태그 관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="31d55-139">태그를 추가하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="31d55-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="31d55-140">추가할 태그 이름을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="31d55-141">태그가 이미 있는 경우 반환되는 태그 목록에서 태그를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="31d55-142">태그가 없는 경우 **""를 새 태그로 추가 \<tag name> 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="31d55-143">태그는 최대 25자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="31d55-144">태그를 제거하려면 제거할 태그 옆에 **있는 X를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="31d55-145">태그를 추가하거나 제거하려는 경우 위의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="31d55-146">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="31d55-147">여러 디바이스에서 태그 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="31d55-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="31d55-148">디바이스에 태그를 추가할 때 기존 태그를 선택하거나 새 태그를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="31d55-149">태그는 최대 25자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="31d55-150">여러 장치에서 태그를 제거하려면 디바이스와 Teams 태그를 선택하고 사용자에서 태그를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="31d55-151">를 방문하여 Microsoft Teams 관리 센터에 https://admin.teams.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="31d55-152">디바이스로 **이동한** 다음 태그를 추가하거나 제거할 디바이스가 포함된 디바이스 창을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="31d55-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="31d55-153">태그를 추가하거나 제거할 디바이스 옆에 확인 표시를 지정하고 태그 관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="31d55-154">태그를 추가하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="31d55-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="31d55-155">사용자의 모든 디바이스에 대한 태그 관리에서 추가할 태그 이름을 Teams **시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="31d55-156">태그가 이미 있는 경우 반환되는 태그 목록에서 태그를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="31d55-157">태그가 없는 경우 **""를 새 태그로 추가 \<tag name> 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="31d55-158">태그를 제거하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="31d55-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="31d55-159">사용자 **선택을 Teams 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="31d55-160">**\<x> 태그를** 제거하려는 Teams 사용자의 이름으로 태그를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="31d55-161">제거할 **태그** 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="31d55-162">태그를 추가하거나 제거하려는 경우 위의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="31d55-163">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="31d55-164">필터를 사용하여 특정 태그가 있는 디바이스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="31d55-165">디바이스에 디바이스 태그를 추가한 경우 디바이스 목록을 필터링하여 지정된 태그가 추가된 디바이스만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="31d55-166">특정 방의 모든 디바이스, 특정 유형의 모든 디바이스 또는 태그를 추가할 때 사용한 기타 조건을 모두 확인하려는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="31d55-167">또한 웨이브에서 업데이트를 적용하거나 디바이스 태그를 사용하여 식별된 디바이스 그룹에 따라 다른 구성 정책을 설정하는 등 반환된 디바이스에서 대량 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="31d55-168">를 방문하여 Microsoft Teams 관리 센터에 https://admin.teams.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="31d55-169">디바이스로 **이동한** 다음 필터링할 디바이스가 포함된 디바이스 창을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="31d55-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="31d55-170">필터 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="31d55-171">단일 태그만 지정하려는 경우 또는 지정한 모든 태그가 있는 디바이스를 찾으면 이러한 모든 조건 **일치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="31d55-172">하나 이상의 디바이스 태그와 일치하는 디바이스를 찾으하려면 이러한 조건 중 하나와 **일치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="31d55-173">태그 **필드를** 선택한 다음 값 입력 필드에 디바이스 태그 이름을 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="31d55-174">더 많은 디바이스 태그를 추가하려면  추가 추가를 선택하고 추가하려는 각 태그에 대해 6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="31d55-175">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="31d55-175">Select **Apply**.</span></span>

<span data-ttu-id="31d55-176">디바이스 목록에서 디바이스를 필터링한 후 정상적으로 해당 디바이스에 대한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="31d55-177">예를 들어 구성을 선택한 다음, 구성을 할당하고, 설정 편집(디바이스에 있는 경우) Teams 룸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d55-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="31d55-178">완료되면 태그 필터 항목 옆에 있는 **X를** 선택하거나 목록의 오른쪽에 있는  모두 지우기를 선택하여 필터를 제거할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="31d55-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
