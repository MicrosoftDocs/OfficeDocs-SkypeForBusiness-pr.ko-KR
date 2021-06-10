---
title: 원격 Microsoft Teams 디바이스 업데이트
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
description: Microsoft Teams 관리 센터를 사용하여 Teams 휴대폰, Teams 및 공동 작업 표시 막대를 원격으로 Teams 업데이트합니다.
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347889"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="87103-103">원격 Microsoft Teams 디바이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="87103-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="87103-104">Microsoft Teams 관리 센터를 사용하여 Teams 휴대폰, Teams 패널 및 공동 작업 막대와 같은 Teams 디바이스를 원격으로 업데이트할 수 있으며 디바이스 펌웨어 자동 업데이트 동작을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as Teams phones, Teams panels, and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="87103-105">관리 센터를 사용하여 디바이스에서 다음을 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="87103-106">Teams 앱 및 팀 관리 에이전트</span><span class="sxs-lookup"><span data-stu-id="87103-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="87103-107">회사 포털 앱</span><span class="sxs-lookup"><span data-stu-id="87103-107">Company portal app</span></span>
- <span data-ttu-id="87103-108">OEM 에이전트 앱</span><span class="sxs-lookup"><span data-stu-id="87103-108">OEM agent app</span></span>
- <span data-ttu-id="87103-109">디바이스 펌웨어</span><span class="sxs-lookup"><span data-stu-id="87103-109">Device firmware</span></span>

<span data-ttu-id="87103-110">디바이스 펌웨어 업데이트는 자동으로 적용되거나 향후 날짜 및 시간으로 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="87103-111">사용 가능한 다른 디바이스 업데이트는 자동으로 적용되지 않지만, 수동으로 적용하거나 향후 날짜 및 시간으로 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="87103-112">디바이스 펌웨어 업데이트를 예약할 수 있는 반면, 예약된 날짜 및 시간이 구성된 최대 30일 또는 90일 지연 후에 떨어지는 경우 최대 지연에 도달하면 펌웨어 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="87103-113">예약된 날짜 및 시간은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="87103-114">또한 원격으로 Microsoft Teams 디바이스 업데이트는 미국 정부 클라우드 테넌트(GCC-High)에서 아직 사용할 수 없는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="87103-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="87103-115">디바이스를 관리하려면 전역 관리자, Teams 서비스 관리자 또는 디바이스 Teams 해야 합니다. 관리자 역할에 대한 자세한 내용은 [관리자](../using-admin-roles.md)Microsoft Teams 관리자 역할 사용 을 Teams.</span><span class="sxs-lookup"><span data-stu-id="87103-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="87103-116">자동 디바이스 펌웨어 업데이트 동작 선택</span><span class="sxs-lookup"><span data-stu-id="87103-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="87103-117">디바이스 펌웨어 업데이트가 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="87103-118">업데이트가 릴리스되는 즉시 업데이트 적용 여부를 결정할 수 있습니다(이 옵션을 선택하면 업데이트가 릴리스된 후 첫 번째 주말에 업데이트가 적용됩니다. 업데이트가 릴리스된 후 30일 또는 90일 후에 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="87103-119">기본적으로 디바이스 펌웨어 업데이트는 릴리스된 후 30일 동안 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87103-120">최신 펌웨어 업데이트 릴리스는 디바이스에 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="87103-121">대신 디바이스에 자동으로 적용되는 업데이트가 한 버전으로 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="87103-122">예를 들어 디바이스에 버전 "10"이 적용되고 버전 "11"이 릴리스되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="87103-123">버전 "11"은 아직 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="87103-124">대신 디바이스는 버전 "12"가 릴리스된 후에 "11"으로만 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="87103-125">일부 디바이스는 아직 자동 펌웨어 업데이트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="87103-126">자동 업데이트를 지원하지 않는 디바이스에 자동 펌웨어 업데이트 설정을 적용하면 해당 디바이스에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="87103-127">디바이스가 자동 펌웨어 업데이트를 지원할지 여부에 대한 질문은 디바이스 제조업체에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="87103-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="87103-128">디바이스에 대한 자동 업데이트 동작을 선택하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="87103-129">를 방문하여 Microsoft Teams 관리 센터에 https://admin.teams.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="87103-130">디바이스 IP 휴대폰 또는 공동 작업 막대 또는 Teams  >   **탐색합니다.** </span><span class="sxs-lookup"><span data-stu-id="87103-130">Navigate **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="87103-131">하나 이상의 디바이스를 선택한 다음 업데이트를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="87103-131">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="87103-132">펌웨어 **자동 업데이트에서** 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="87103-133">**가능한 한 빨리** 최신 업데이트가 릴리스된 후 첫 번째 주말에 두 번째 최신 디바이스 펌웨어 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="87103-134">**30일 연기** 최신 업데이트가 릴리스된 후 30일 후에 최신 디바이스 펌웨어 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="87103-135">**90일 연기** 최신 업데이트가 릴리스된 후 90일 후에 최신 디바이스 펌웨어 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="87103-136">업데이트 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="87103-136">Select **Update**.</span></span>

<span data-ttu-id="87103-137">어떤 이유로든 디바이스 펌웨어 업데이트를 되전해야 하는 경우 디바이스를 공장 설정으로 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="87103-138">제조업체의 지침을 사용하여 디바이스를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="87103-139">원격 디바이스 수동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="87103-139">Manually update remote devices</span></span>

<span data-ttu-id="87103-140">관리 센터를 사용하여 하나 이상의 디바이스를 업데이트할 때 디바이스를 즉시 업데이트할지 또는 향후 날짜 및 시간으로 업데이트를 예약할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="87103-141">원격 디바이스를 수동으로 업데이트하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="87103-142">를 방문하여 Microsoft Teams 관리 센터에 https://admin.teams.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="87103-143">디바이스 IP 휴대폰 또는 공동 작업 막대 또는 Teams  >   **탐색합니다.** </span><span class="sxs-lookup"><span data-stu-id="87103-143">Navigate  **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="87103-144">하나 이상의 디바이스를 선택한 다음 업데이트를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="87103-144">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="87103-145">수동 **업데이트에서** 향후 날짜 및 **시간으로** 업데이트를 예약하려면 예약을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="87103-146">업데이트는 **Timezone에서** 선택한 타임존의 날짜 및 시간에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="87103-147">볼 수 있는 내용은 디바이스가 하나 또는 여러 개 선택되어 있는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="87103-148">아래 왼쪽 이미지는 선택한 여러 디바이스를 보여 주며, 오른쪽 이미지에는 선택한 단일 디바이스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="디바이스 업데이트 상태 창의 단일 및 여러 디바이스 보기":::

<span data-ttu-id="87103-150">여러 디바이스를 선택할 때 선택한 각 디바이스에 적용할 업데이트 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87103-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="87103-151">적용할 업데이트 유형을 선택하고 업데이트를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="87103-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="87103-152">단일 디바이스를 선택하면 디바이스에 사용할 수 있는 업데이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="87103-153">디바이스에 대해 여러 업데이트 형식을 사용할 수 있는 경우 적용할 각 업데이트 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87103-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="87103-154">디바이스에 적용된 현재 버전과 적용될 **새** 버전을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="87103-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="87103-155">적용할 업데이트를 선택하고 업데이트를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="87103-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="87103-156">업데이트를 **선택한** 후 업데이트를 예약한 경우 선택한 날짜 및 시간의 디바이스에 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="87103-157">향후 날짜 및 시간을 선택하지 않은 경우 몇 분 이내에 디바이스에 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87103-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
