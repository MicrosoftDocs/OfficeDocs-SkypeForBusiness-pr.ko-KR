---
title: Microsoft 팀에서 장치 관리
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
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 조직에서 팀과 함께 사용 되는 장치를 관리 하는 방법을 알아봅니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587297"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="0f271-103">Microsoft 팀에서 장치 관리</span><span class="sxs-lookup"><span data-stu-id="0f271-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="0f271-104">관리자는 Microsoft 팀 관리 센터에서 조직의 팀과 함께 사용 되는 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="0f271-105">조직의 장치 인벤토리를 보고 관리 하 고 장치에 대 한 업데이트, 다시 시작, 모니터링 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="0f271-106">장치 또는 장치 그룹에 구성 프로필을 만들고 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="0f271-107">어떤 장치를 관리할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="0f271-107">What devices can you manage?</span></span>
<span data-ttu-id="0f271-108">팀에 대해 인증 되 고 등록 된 모든 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="0f271-109">장치는 사용자가 처음으로 장치에서 팀에 로그인 할 때 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="0f271-110">관리할 수 있는 인증 된 디바이스의 목록은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f271-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="0f271-111">전화 회의</span><span class="sxs-lookup"><span data-stu-id="0f271-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="0f271-112">일반 전화기</span><span class="sxs-lookup"><span data-stu-id="0f271-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="0f271-113">공동 작업 표시줄</span><span class="sxs-lookup"><span data-stu-id="0f271-113">Collaboration bars</span></span>

<span data-ttu-id="0f271-114">장치는 [Microsoft 팀 관리 센터](https://admin.teams.microsoft.com) 에서 왼쪽 탐색 모음에 있는 **장치** 아래에 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="0f271-115">Microsoft Intune이 있는 경우 장치가 Intune에 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="0f271-116">장치가 등록 되 면 디바이스 호환성이 확인 되 고 조건부 액세스 정책이 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="0f271-117">팀에서 전화 및 공동 작업 모음 관리</span><span class="sxs-lookup"><span data-stu-id="0f271-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="0f271-118">휴대폰 및 공동 작업 모음은 Microsoft 팀 관리 센터에서 동일 하 게 관리 되지만, **장치**아래에 있는 왼쪽 탐색의 각 섹션은 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="0f271-119">이렇게 하면 각 장치 유형을 개별적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="0f271-120">여기에서 조직의 팀에 등록 된 휴대폰 및 공동 작업 표시줄을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="0f271-121">각 디바이스에 대해 표시 되는 정보에는 장치 이름, 제조업체, 모델, 사용자, 상태, 동작, 마지막 표시 및 기록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="0f271-122">보기를 사용자 지정 하 여 요구 사항에 맞는 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="0f271-123">다음은 조직의 팀 장치를 관리 하는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="0f271-124">이 작업을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="0f271-124">To do this...</span></span>  |<span data-ttu-id="0f271-125">실행할 작업</span><span class="sxs-lookup"><span data-stu-id="0f271-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="0f271-126">장치 정보 변경</span><span class="sxs-lookup"><span data-stu-id="0f271-126">Change device information</span></span>   | <span data-ttu-id="0f271-127">장치 > **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-127">Select a device > **Edit**.</span></span> <span data-ttu-id="0f271-128">장치 이름, 자산 태그 등의 세부 정보를 편집 하 고 노트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="0f271-129">소프트웨어 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="0f271-129">Manage software updates</span></span>   |<span data-ttu-id="0f271-130">장치 > **업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-130">Select a device > **Update**.</span></span> <span data-ttu-id="0f271-131">장치에서 사용할 수 있는 소프트웨어 및 펌웨어 업데이트 목록을 보고 설치할 업데이트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="0f271-132">장치 다시 시작</span><span class="sxs-lookup"><span data-stu-id="0f271-132">Restart a device</span></span>   |<span data-ttu-id="0f271-133">장치 > **다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="0f271-134">장치 기록 보기</span><span class="sxs-lookup"><span data-stu-id="0f271-134">View device history</span></span>  | <span data-ttu-id="0f271-135">장치 > **기록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-135">Select a device > **History**.</span></span> <span data-ttu-id="0f271-136">장치에 대 한 업데이트 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="0f271-137">진단 보기</span><span class="sxs-lookup"><span data-stu-id="0f271-137">View diagnostics</span></span>  | <span data-ttu-id="0f271-138">장치 > **진단을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="0f271-139">팀에서 구성 프로필 사용</span><span class="sxs-lookup"><span data-stu-id="0f271-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="0f271-140">구성 프로필을 사용 하 여 조직의 팀 디바이스에 대 한 설정 및 기능을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="0f271-141">구성 프로필을 만들거나 업로드 하 여 사용 하거나 사용 하지 않도록 설정할 설정 및 기능을 포함 한 다음 장치 또는 장치 그룹에 프로필을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="0f271-142">구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="0f271-142">Create a configuration profile</span></span>

1. <span data-ttu-id="0f271-143">왼쪽 탐색 창에서 **장치** > **구성 프로필로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="0f271-144">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-144">Click **Add**.</span></span>
3. <span data-ttu-id="0f271-145">프로필의 이름을 입력 하 고 원하는 경우 간단한 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="0f271-146">프로필에 대해 원하는 설정을 지정한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="0f271-147">구성 프로필 할당</span><span class="sxs-lookup"><span data-stu-id="0f271-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="0f271-148">왼쪽 탐색 창에서 **장치** > **구성 프로필로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="0f271-149">할당 하려는 **구성 프로필** 을 선택한 다음 **장치에 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="0f271-150">**장치를 구성 프로필에 할당** 창에서 할당 하려는 장치를 검색 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="0f271-151">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f271-151">Click **Save**.</span></span>
