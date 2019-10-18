---
title: Microsoft 팀에서 장치 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 조직에서 팀과 함께 사용 되는 장치를 관리 하는 방법을 알아봅니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1473acc92113cc8788ae5cc27eecc11ad909124
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571794"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="d854b-103">Microsoft 팀에서 장치 관리</span><span class="sxs-lookup"><span data-stu-id="d854b-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="d854b-104">관리자는 Microsoft 팀 관리 센터에서 조직의 팀과 함께 사용 되는 모든 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="d854b-105">조직의 장치 인벤토리를 보고 관리 하 고 장치에 대 한 업데이트, 다시 시작, 모니터링 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="d854b-106">장치 또는 장치 그룹에 구성 프로필을 만들고 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="d854b-107">어떤 장치를 관리할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d854b-107">What devices can you manage?</span></span>
<span data-ttu-id="d854b-108">장치가 팀에 대해 인증 되 고 팀에 등록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="d854b-109">장치는 사용자가 처음으로 장치에서 팀에 로그인 할 때 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="d854b-110">관리할 수 있는 인증 디바이스 목록은 [전화 회의 전화](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) 및 [일반 전화기](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d854b-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="d854b-111">Microsoft Intune이 있는 경우 장치가 Intune에 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="d854b-112">장치가 등록 되 면 디바이스 호환성이 확인 되 고 조건부 액세스 정책이 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="d854b-113">팀에서 장치 관리</span><span class="sxs-lookup"><span data-stu-id="d854b-113">Manage devices in Teams</span></span>

<span data-ttu-id="d854b-114">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="d854b-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d854b-115">왼쪽 탐색 창 **에서 장치** > **관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="d854b-116">**모든 장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="d854b-117">여기에서 조직의 팀에 등록 된 모든 장치를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="d854b-118">각 디바이스에 대해 표시 되는 정보에는 장치 이름, 제조업체, 모델, 사용자, 상태, 동작, 마지막 표시 및 기록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="d854b-119">보기를 사용자 지정 하 여 요구 사항에 맞는 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="d854b-120">다음은 조직의 팀 장치를 관리 하는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="d854b-121">이 작업을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="d854b-121">To do this...</span></span>  |<span data-ttu-id="d854b-122">실행할 작업</span><span class="sxs-lookup"><span data-stu-id="d854b-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="d854b-123">장치 정보 변경</span><span class="sxs-lookup"><span data-stu-id="d854b-123">Change device information</span></span>   | <span data-ttu-id="d854b-124">장치 > **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-124">Select a device > **Edit**.</span></span> <span data-ttu-id="d854b-125">장치 이름, 사용자 정보, 자산 태그, 메모 추가 등의 세부 정보를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="d854b-126">소프트웨어 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="d854b-126">Manage software updates</span></span>   |<span data-ttu-id="d854b-127">장치 > **업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-127">Select a device > **Update**.</span></span> <span data-ttu-id="d854b-128">장치에서 사용할 수 있는 소프트웨어 및 펌웨어 업데이트 목록을 보고 설치할 업데이트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="d854b-129">장치 다시 시작</span><span class="sxs-lookup"><span data-stu-id="d854b-129">Restart a device</span></span>   |<span data-ttu-id="d854b-130">장치 > **다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="d854b-131">장치 기록 보기</span><span class="sxs-lookup"><span data-stu-id="d854b-131">View device history</span></span>  | <span data-ttu-id="d854b-132">장치 > **기록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-132">Select a device > **History**.</span></span> <span data-ttu-id="d854b-133">장치에 대 한 업데이트 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="d854b-134">진단 보기</span><span class="sxs-lookup"><span data-stu-id="d854b-134">View diagnostics</span></span>  | <span data-ttu-id="d854b-135">장치 > **진단을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="d854b-136">팀에서 구성 프로필 사용</span><span class="sxs-lookup"><span data-stu-id="d854b-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="d854b-137">구성 프로필을 사용 하 여 조직의 팀 디바이스에 대 한 설정 및 기능을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="d854b-138">구성 프로필을 만들거나 업로드 하 여 사용 하거나 사용 하지 않도록 설정할 설정 및 기능을 포함 한 다음 장치 또는 장치 그룹에 프로필을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="d854b-139">구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="d854b-139">Create a configuration profile</span></span>

::: zone target="docs"

![Microsoft 팀 로고를 표시 하는 아이콘](media/teams-logo-30x30.png) <span data-ttu-id="d854b-141">비즈니스용 Skype 관리 센터 & Microsoft 팀 사용</span><span class="sxs-lookup"><span data-stu-id="d854b-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="d854b-142">왼쪽 탐색 창 **에서 장치** > **관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="d854b-143">**구성 프로필**을 선택한 다음 **새 구성 프로필**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="d854b-144">프로필의 이름을 입력 하 고 원하는 경우 간단한 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="d854b-145">프로필에 대해 원하는 설정을 지정한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="d854b-146">구성 프로필 할당</span><span class="sxs-lookup"><span data-stu-id="d854b-146">Assign a configuration profile</span></span>

::: zone target="docs"

![Microsoft 팀 로고를 표시 하는 아이콘](media/teams-logo-30x30.png) <span data-ttu-id="d854b-148">비즈니스용 Skype 관리 센터 & Microsoft 팀 사용</span><span class="sxs-lookup"><span data-stu-id="d854b-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="d854b-149">왼쪽 탐색 창 **에서 장치** > **관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="d854b-150">**구성 프로필**을 선택한 다음 할당 하려는 프로필의 **할당 대상** 에서 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="d854b-151">**장치를 구성 프로필에 할당** 창에서 할당 하려는 장치를 검색 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="d854b-152">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d854b-152">Click **Save**.</span></span>
