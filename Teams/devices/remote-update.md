---
title: Microsoft 팀 장치를 원격으로 업데이트
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 팀 관리 센터를 사용 하 여 원격으로 Microsoft 팀 전화 및 공동 작업 모음 업데이트
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962889"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="f1d46-103">Microsoft 팀 장치를 원격으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="f1d46-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="f1d46-104">Microsoft 팀 관리 센터를 사용 하 여 전화 및 공동 작업 표시줄과 같은 팀 장치를 원격으로 업데이트할 수 있으며 디바이스 펌웨어 자동 업데이트 동작을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="f1d46-105">팀 관리 센터를 사용 하 여 장치에서 다음을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="f1d46-106">팀 앱 및 팀 관리 에이전트</span><span class="sxs-lookup"><span data-stu-id="f1d46-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="f1d46-107">회사 포털 앱</span><span class="sxs-lookup"><span data-stu-id="f1d46-107">Company portal app</span></span>
- <span data-ttu-id="f1d46-108">OEM 에이전트 앱</span><span class="sxs-lookup"><span data-stu-id="f1d46-108">OEM agent app</span></span>
- <span data-ttu-id="f1d46-109">장치 펌웨어</span><span class="sxs-lookup"><span data-stu-id="f1d46-109">Device firmware</span></span>

<span data-ttu-id="f1d46-110">장치 펌웨어 업데이트는 이후 날짜 및 시간에 자동으로 적용 되거나 예약 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="f1d46-111">다른 사용 가능한 장치 업데이트는 자동으로 적용 되지 않지만 수동으로 적용 하거나 나중에 날짜와 시간에 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="f1d46-112">장치 펌웨어 업데이트를 예약할 수 있는 동안, 예약 된 날짜와 시간이 구성 된 최대 30 또는 90 일 지연 이후 이면 펌웨어 업데이트가 최대 지연에 도달할 때 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="f1d46-113">예약 된 날짜와 시간은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="f1d46-114">또한 Microsoft 팀 디바이스를 원격으로 업데이트 하는 기능은 미국 정부 클라우드 테 넌 트 (GCC-높음)에서 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="f1d46-115">장치를 관리 하려면 전역 관리자, 팀 서비스 관리자 또는 팀 장치 관리자 여야 합니다. 관리자 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](../using-admin-roles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1d46-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="f1d46-116">자동 장치 펌웨어 업데이트 동작 선택</span><span class="sxs-lookup"><span data-stu-id="f1d46-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="f1d46-117">장치 펌웨어 업데이트가 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="f1d46-118">업데이트를 해제 하는 즉시 적용할지 (이 옵션을 선택 하는 경우 업데이트를 릴리스된 후 첫 번째 주말에 업데이트가 적용 되는 경우) 또는 업데이트를 릴리스한 후 30 일 또는 90 일간 할 것인지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="f1d46-119">기본적으로 디바이스 펌웨어 업데이트는 1 번 릴리스된 30 일이 지나면 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1d46-120">최신 펌웨어 업데이트 릴리스가 팀 장치에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="f1d46-121">대신 장치에 자동으로 적용 되는 업데이트가 한 버전으로 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="f1d46-122">예를 들어 디바이스에 버전 "10"이 적용 되 고 버전이 "11"이 출시 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="f1d46-123">버전 "11"은 아직 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="f1d46-124">대신 "12" 버전이 출시 된 후에만 장치가 버전 "11"로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="f1d46-125">일부 장치는 아직 자동 펌웨어 업데이트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="f1d46-126">자동 업데이트를 지원 하지 않는 장치에서 자동 펌웨어 업데이트 설정을 적용 하는 것은 해당 장치에 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="f1d46-127">장치에서 자동 펌웨어 업데이트를 지원 하는지 여부에 대 한 질문은 장치 제조업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1d46-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="f1d46-128">장치에 대 한 자동 업데이트 동작을 선택 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="f1d46-129">방문 하 여 Microsoft 팀 관리 센터에 로그인 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f1d46-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="f1d46-130">**장치**  >  **전화** 또는 **공동 작업 모음** 탐색</span><span class="sxs-lookup"><span data-stu-id="f1d46-130">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="f1d46-131">하나 이상의 장치를 선택한 다음 **업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-131">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="f1d46-132">**펌웨어 자동 업데이트**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="f1d46-133">**가능한 한 빨리** 두 번째-최신 업데이트를 릴리스한 후 첫 번째 주말에 최신 장치 펌웨어 업데이트가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="f1d46-134">**30 일 연기** 두 번째-최신 업데이트 출시 후 30 일 후에 최신 장치 펌웨어 업데이트가 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="f1d46-135">**90 일 지연** 두 번째-최신 업데이트를 릴리스한 이후 90 일 후에 최신 장치 펌웨어 업데이트가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="f1d46-136">**업데이트** 선택</span><span class="sxs-lookup"><span data-stu-id="f1d46-136">Select **Update**</span></span>

<span data-ttu-id="f1d46-137">어떤 이유로 든 장치 펌웨어 업데이트를 되돌려야 하는 경우 디바이스를 공장 설정으로 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="f1d46-138">해당 제조업체의 지침에 따라 장치를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="f1d46-139">수동으로 원격 장치 업데이트</span><span class="sxs-lookup"><span data-stu-id="f1d46-139">Manually update remote devices</span></span>

<span data-ttu-id="f1d46-140">관리 센터를 사용 하 여 하나 이상의 장치를 업데이트 하는 경우 디바이스를 즉시 업데이트할지 여부를 결정 하거나 이후 날짜 및 시간에 대 한 업데이트를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="f1d46-141">수동으로 원격 장치를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="f1d46-142">방문 하 여 Microsoft 팀 관리 센터에 로그인 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f1d46-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="f1d46-143">**장치**  >  **전화** 또는 **공동 작업 모음** 탐색</span><span class="sxs-lookup"><span data-stu-id="f1d46-143">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="f1d46-144">하나 이상의 장치를 선택한 다음 **업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-144">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="f1d46-145">**수동 업데이트**에서 나중 날짜 및 시간에 대 한 업데이트를 예약 하려면 **일정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="f1d46-146">업데이트는 **timezone**에서 선택한 표준 시간대의 날짜 및 시간에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="f1d46-147">표시 되는 항목은 하나 이상의 장치가 선택 되었는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="f1d46-148">아래 왼쪽 이미지는 여러 장치를 선택 하 고 오른쪽 이미지에는 단일 장치가 선택 되어 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="장치 업데이트 상태 창의 단일 및 다중 장치 보기":::

<span data-ttu-id="f1d46-150">여러 장치를 선택 하는 경우 선택한 각 장치에 적용할 업데이트 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="f1d46-151">적용 하려는 업데이트 유형을 선택 하 고 **업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="f1d46-152">단일 장치를 선택 하면 해당 장치에 사용할 수 있는 업데이트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="f1d46-153">장치에 여러 업데이트 유형을 사용할 수 있는 경우 적용할 각 업데이트 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="f1d46-154">장치에 적용 된 **현재 버전과** 적용할 **새 버전** 을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="f1d46-155">적용 하려는 업데이트를 선택 하 고 **업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="f1d46-156">**업데이트**를 선택한 후 업데이트를 예약한 경우 선택한 날짜 및 시간에 업데이트가 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="f1d46-157">이후 날짜와 시간을 선택 하지 않은 경우 몇 분 내에 업데이트가 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d46-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
