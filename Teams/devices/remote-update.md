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
ms.openlocfilehash: f7607da002be7f038e4cafe5b4b6026ea2d99ddf
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125951"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="f916f-103">Microsoft 팀 장치를 원격으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="f916f-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="f916f-104">Microsoft 팀 관리 센터를 사용 하 여 전화 및 공동 작업 표시줄과 같은 팀 장치를 원격으로 업데이트할 수 있으며 디바이스 펌웨어 자동 업데이트 동작을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="f916f-105">팀 관리 센터를 사용 하 여 장치에서 다음을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="f916f-106">팀 앱 및 팀 관리 에이전트</span><span class="sxs-lookup"><span data-stu-id="f916f-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="f916f-107">회사 포털 앱</span><span class="sxs-lookup"><span data-stu-id="f916f-107">Company portal app</span></span>
- <span data-ttu-id="f916f-108">OEM 에이전트 앱</span><span class="sxs-lookup"><span data-stu-id="f916f-108">OEM agent app</span></span>
- <span data-ttu-id="f916f-109">장치 펌웨어</span><span class="sxs-lookup"><span data-stu-id="f916f-109">Device firmware</span></span>

<span data-ttu-id="f916f-110">장치 펌웨어 업데이트는 이후 날짜 및 시간에 자동으로 적용 되거나 예약 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="f916f-111">다른 사용 가능한 장치 업데이트는 자동으로 적용 되지 않지만 수동으로 적용 하거나 나중에 날짜와 시간에 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="f916f-112">장치 펌웨어 업데이트를 예약할 수 있는 동안, 예약 된 날짜와 시간이 구성 된 최대 30 또는 90 일 지연 이후 이면 펌웨어 업데이트가 최대 지연에 도달할 때 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="f916f-113">예약 된 날짜와 시간은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="f916f-114">또한 Microsoft 팀 디바이스를 원격으로 업데이트 하는 기능은 미국 정부 클라우드 테 넌 트 (GCC-높음)에서 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="f916f-115">자동 장치 펌웨어 업데이트 동작 선택</span><span class="sxs-lookup"><span data-stu-id="f916f-115">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="f916f-116">장치 펌웨어 업데이트가 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-116">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="f916f-117">업데이트를 릴리스할 때 한 번에 업데이트를 적용할지, 아니면 30 개 또는 90 일 후에 업데이트가 릴리스된 지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-117">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="f916f-118">기본적으로 디바이스 펌웨어 업데이트는 1 번 릴리스된 30 일이 지나면 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-118">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f916f-119">최신 펌웨어 업데이트 릴리스가 팀 장치에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-119">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="f916f-120">대신 장치에 자동으로 적용 되는 업데이트가 한 버전으로 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-120">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="f916f-121">예를 들어 디바이스에 버전 "10"이 적용 되 고 버전이 "11"이 출시 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-121">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="f916f-122">버전 "11"은 아직 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-122">Version "11" won't be applied yet.</span></span> <span data-ttu-id="f916f-123">대신 "12" 버전이 출시 된 후에만 장치가 버전 "11"로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-123">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="f916f-124">장치에 대 한 자동 업데이트 동작을 선택 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-124">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="f916f-125">방문 하 여 Microsoft 팀 관리 센터에 로그인https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f916f-125">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="f916f-126">**장치**  >  **전화** 또는 **공동 작업 모음** 탐색</span><span class="sxs-lookup"><span data-stu-id="f916f-126">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="f916f-127">하나 이상의 장치를 선택한 다음 **업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-127">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="f916f-128">**펌웨어 자동 업데이트**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-128">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="f916f-129">**가능한 한 빨리** 두 번째-최신 업데이트를 릴리스한 후 최대한 빨리 적용 되는 장치 펌웨어 업데이트.</span><span class="sxs-lookup"><span data-stu-id="f916f-129">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="f916f-130">**30 일 연기** 두 번째-최신 업데이트 출시 후 30 일 후에 최신 장치 펌웨어 업데이트가 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-130">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="f916f-131">**90 일 지연** 두 번째-최신 업데이트를 릴리스한 이후 90 일 후에 최신 장치 펌웨어 업데이트가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-131">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="f916f-132">**업데이트** 선택</span><span class="sxs-lookup"><span data-stu-id="f916f-132">Select **Update**</span></span>

<span data-ttu-id="f916f-133">어떤 이유로 든 장치 펌웨어 업데이트를 되돌려야 하는 경우 디바이스를 공장 설정으로 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-133">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="f916f-134">해당 제조업체의 지침에 따라 장치를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-134">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="f916f-135">수동으로 원격 장치 업데이트</span><span class="sxs-lookup"><span data-stu-id="f916f-135">Manually update remote devices</span></span>

<span data-ttu-id="f916f-136">관리 센터를 사용 하 여 하나 이상의 장치를 업데이트 하는 경우 디바이스를 즉시 업데이트할지 여부를 결정 하거나 이후 날짜 및 시간에 대 한 업데이트를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-136">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="f916f-137">수동으로 원격 장치를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-137">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="f916f-138">방문 하 여 Microsoft 팀 관리 센터에 로그인https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f916f-138">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="f916f-139">**장치**  >  **전화** 또는 **공동 작업 모음** 탐색</span><span class="sxs-lookup"><span data-stu-id="f916f-139">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="f916f-140">하나 이상의 장치를 선택한 다음 **업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-140">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="f916f-141">**수동 업데이트**에서 나중 날짜 및 시간에 대 한 업데이트를 예약 하려면 **일정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-141">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="f916f-142">업데이트는 **timezone**에서 선택한 표준 시간대의 날짜 및 시간에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-142">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="f916f-143">표시 되는 항목은 하나 이상의 장치가 선택 되었는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-143">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="f916f-144">아래 왼쪽 이미지는 여러 장치를 선택 하 고 오른쪽 이미지에는 단일 장치가 선택 되어 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-144">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="장치 업데이트 상태 창의 단일 및 다중 장치 보기":::

<span data-ttu-id="f916f-146">여러 장치를 선택 하는 경우 선택한 각 장치에 적용할 업데이트 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-146">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="f916f-147">적용 하려는 업데이트 유형을 선택 하 고 **업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-147">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="f916f-148">단일 장치를 선택 하면 해당 장치에 사용할 수 있는 업데이트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-148">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="f916f-149">장치에 여러 업데이트 유형을 사용할 수 있는 경우 적용할 각 업데이트 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-149">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="f916f-150">장치에 적용 된 **현재 버전과** 적용할 **새 버전** 을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-150">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="f916f-151">적용 하려는 업데이트를 선택 하 고 **업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-151">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="f916f-152">**업데이트**를 선택한 후 업데이트를 예약한 경우 선택한 날짜 및 시간에 업데이트가 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-152">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="f916f-153">이후 날짜와 시간을 선택 하지 않은 경우 몇 분 내에 업데이트가 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f916f-153">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
