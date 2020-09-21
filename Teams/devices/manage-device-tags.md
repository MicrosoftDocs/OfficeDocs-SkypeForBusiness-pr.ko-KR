---
title: Microsoft 팀 디바이스 태그 관리 및 필터링
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
description: Microsoft 팀 디바이스에서 태그를 관리 하 고 필터링 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d29bc28de39c8d145914d3bddab4ed949ad0a338
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962899"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="274d6-103">Microsoft 팀 디바이스 태그 관리</span><span class="sxs-lookup"><span data-stu-id="274d6-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="274d6-104">Microsoft 팀의 디바이스 태그를 사용 하면 조직에 배포 된 장치를 그룹화 하 고 구성 하 고 더 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="274d6-105">Microsoft 팀 관리 센터를 사용 하 여 장치에 하나 이상의 태그를 추가 하 고, 필터를 사용 하 여 지정한 태그와 일치 하는 장치를 표시 한 다음 해당 태그가 있는 장치를 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions the devices that have that tag.</span></span>

<span data-ttu-id="274d6-106">장치 태그를 두 개 이상의 장치 유형에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="274d6-107">그러나 관리 센터에서 장치 창을 열면 해당 형식의 장치만 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="274d6-108">예를 들어 휴대폰 및 팀 대화방 장치에 "기업" 태그를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="274d6-109">**장치**전화에서 "회사" 태그를 검색 하는 경우에는  >  **Phones**전화기만 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="274d6-110">마찬가지로 **디바이스**팀 대화방에서 "회사" 태그를 검색 하는 경우  >  **Teams Rooms**팀 대화방 장치만 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="274d6-111">디바이스 태그를 관리 하려면 전역 관리자, 팀 서비스 관리자 또는 팀 장치 관리자 여야 합니다. 관리자 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](../using-admin-roles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="274d6-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="274d6-112">장치 태그는 장치에 로그인 한 리소스 계정에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="274d6-113">한 장치에서 리소스 계정을 서명한 다음이를 사용 하 여 다른 장치에 로그인 하는 경우 디바이스 태그가 새 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-113">If you sign a resource account out of one device and then use it to sign into another devices, the device tags are applied to new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="274d6-114">디바이스 태그 만들기, 제거 또는 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="274d6-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="274d6-115">장치 태그 관리 패널을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="274d6-116">모든 장치 태그를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-116">See all your device tags.</span></span>
- <span data-ttu-id="274d6-117">여러 장치 태그를 쉽게 만든 다음 나중에 장치에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="274d6-118">태그는 최대 25 자까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="274d6-119">더 이상 필요 하지 않은 장치 태그를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="274d6-120">디바이스 태그를 제거 하려면 먼저 추가 된 모든 장치에서 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="274d6-121">디바이스 태그의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-121">Rename device tags.</span></span> <span data-ttu-id="274d6-122">디바이스 태그의 이름을 바꾸면 해당 변경 내용이 추가 된 모든 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="274d6-123">태그는 최대 25 자까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="274d6-124">방문 하 여 Microsoft 팀 관리 센터에 로그인 https://admin.teams.microsoft.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="274d6-125">**장치로** 이동한 다음 장치 창 (예: **전화기**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="274d6-126">페이지의 오른쪽 위 모서리에서 **작업** 을 선택 하 고 **모든 장치 태그**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="274d6-127">장치 태그를 만들려면 **+ 추가**를 선택 하 고 디바이스 태그에 대 한 값을 입력 한 다음 **저장** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="274d6-128">장치 태그를 제거 하려면 제거 하려는 장치 태그 옆에 **있는 줄임표 (...)** 를 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="274d6-129">디바이스에 추가 된 디바이스 태그를 제거 하려고 하면 모든 장치에서 제거할 것인지 묻는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="274d6-130">이 작업을 수행 하 고 디바이스 태그를 계속 제거 하려면 **Untag 장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="274d6-131">디바이스 태그의 이름을 바꾸려면 이름을 바꿀 장치 태그 옆에 있는 줄임표 **...** 를 선택 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="274d6-132">디바이스 태그에 새 값을 입력 하 고 **저장** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="274d6-133">단일 장치에서 태그 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="274d6-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="274d6-134">장치에 태그를 추가 하는 경우 기존 태그를 선택 하거나 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="274d6-135">태그는 최대 25 자까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="274d6-136">방문 하 여 Microsoft 팀 관리 센터에 로그인 https://admin.teams.microsoft.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="274d6-137">**장치로** 이동한 다음 추가 하거나 태그를 제거할 장치가 포함 된 장치 창을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="274d6-138">추가 하거나 제거 하려는 장치 옆에 확인 표시를 놓고 **태그 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="274d6-139">태그를 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="274d6-140">추가 하려는 태그 이름을 입력 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="274d6-141">태그가 이미 있는 경우 반환 되는 태그 목록에서 해당 태그를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="274d6-142">태그가 없는 경우 \*\* \<tag name> 새 태그로 "" 추가\*\*를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="274d6-143">태그는 최대 25 자까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="274d6-144">태그를 제거 하려면 제거 하려는 태그 옆에 있는 **X** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="274d6-145">더 많은 태그를 추가 하거나 제거 하려면 위 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="274d6-146">**적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="274d6-147">여러 장치에서 태그 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="274d6-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="274d6-148">장치에 태그를 추가 하는 경우 기존 태그를 선택 하거나 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="274d6-149">태그는 최대 25 자까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="274d6-150">여러 장치에서 태그를 제거 하려면 장치와 연결 된 팀 사용자를 선택 하 고 사용자의 태그를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="274d6-151">방문 하 여 Microsoft 팀 관리 센터에 로그인 https://admin.teams.microsoft.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="274d6-152">**장치로** 이동한 다음 태그를 추가 하거나 제거 하려는 장치가 포함 된 장치 창을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="274d6-153">추가 하거나 제거할 장치 옆에 확인 표시를 놓고 **태그 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="274d6-154">태그를 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="274d6-155">**팀 사용자의 모든 장치에 대 한 관리 태그**에 추가 하려는 태그 이름을 입력 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="274d6-156">태그가 이미 있는 경우 반환 되는 태그 목록에서 해당 태그를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="274d6-157">태그가 없는 경우 \*\* \<tag name> 새 태그로 "" 추가\*\*를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="274d6-158">태그를 제거 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="274d6-159">**팀 사용자 선택을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="274d6-160">태그를 제거 하려는 팀 사용자의 이름 아래에 있는 \*\* \<x> 태그\*\* 를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="274d6-161">제거 하려는 태그 옆에 있는 **X** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="274d6-162">더 많은 태그를 추가 하거나 제거 하려면 위 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="274d6-163">**적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="274d6-164">필터를 사용 하 여 특정 태그를 가진 디바이스 반환</span><span class="sxs-lookup"><span data-stu-id="274d6-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="274d6-165">장치에 디바이스 태그를 추가한 경우이를 사용 하 여 디바이스 목록을 필터링 하 여 지정 된 태그가 추가 된 장치만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="274d6-166">이는 특정 룸의 모든 장치, 특정 유형의 모든 장치 또는 태그를 추가할 때 사용한 다른 기준을 보기만 할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="274d6-167">또한 장치 태그를 사용 하 여 식별 된 장치 그룹에 따라, 전파에 업데이트를 적용 하는 등 반환 된 장치에서 대량 작업을 수행 하거나 다른 구성 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="274d6-168">방문 하 여 Microsoft 팀 관리 센터에 로그인 https://admin.teams.microsoft.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="274d6-169">**장치로** 이동한 다음 필터링 할 장치가 포함 된 장치 창을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="274d6-170">**필터** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="274d6-171">단일 태그만 지정 하거나 지정한 태그를 모두 포함 하는 장치를 찾으려는 경우에는 **다음 조건 모두 일치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="274d6-172">하나 이상의 디바이스 태그와 일치 하는 디바이스를 찾으려면 **다음 조건 중 하나**에 해당 하는 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="274d6-173">**태그** 필드를 선택한 다음 **값 입력** 필드에 장치 태그 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="274d6-174">디바이스 태그를 더 추가 하려는 경우 추가 하려는 각 태그에 **대해 추가를 선택 하** 고 6 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="274d6-175">**적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-175">Select **Apply**.</span></span>

<span data-ttu-id="274d6-176">장치 목록에서 장치를 필터링 한 후 평소와 마찬가지로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="274d6-177">예를 들어 해당 항목을 선택 하 고 구성을 할당 하 고 해당 설정 (팀 대화방 장치인 경우)을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="274d6-178">작업을 마치면 **태그** 필터 항목 옆에 있는 **X** 를 선택 하거나 목록의 오른쪽에 있는 **모두 지우기를** 선택 하 여 필터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="274d6-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
