---
title: 장치 로그 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 장치 업데이트 웹 서비스에서는 장치 업데이트 작업을 기록하는 로그 파일이 자동으로 만들어집니다. 조직의 데이터 관리 전략의 일부로 로그 데이터 캐시 크기, 로그 파일 크기 또는 로그 파일을 삭제하기 전에 보관되는 기간에 대한 임계값을 설정할 수 있습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다. 장치 업데이트 웹 서비스에서 로그 파일을 자동으로 삭제하지 않도록 하려면 필요에 따라 로그 파일을 수동으로 삭제할 수 있습니다. 로그 설정은 전역적으로 또는 사이트별로 변경할 수 있습니다.
ms.openlocfilehash: 118f2e6d90e9c3f7559a5e129c844ccdf1ea9bf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830338"
---
# <a name="device-log-configuration"></a><span data-ttu-id="af073-107">장치 로그 구성</span><span class="sxs-lookup"><span data-stu-id="af073-107">Device Log Configuration</span></span>

<span data-ttu-id="af073-108">장치 업데이트 웹 서비스에서는 장치 업데이트 작업을 기록하는 로그 파일이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="af073-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="af073-109">조직의 데이터 관리 전략의 일부로 로그 데이터 캐시 크기, 로그 파일 크기 또는 로그 파일을 삭제하기 전에 보관되는 기간에 대한 임계값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="af073-110">조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="af073-111">장치 업데이트 웹 서비스에서 로그 파일을 자동으로 삭제하지 않도록 하려면 필요에 따라 로그 파일을 수동으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="af073-112">로그 설정은 전역적으로 또는 사이트별로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="af073-113">장치 업데이트 웹 서비스에서 구성한 로그 파일 유지 기간(일)보다 오래된 로그 파일을 자동으로 삭제할 시간을 구성할 수도 있습니다(기본적으로 10일 이상 된 로그 파일이 자동으로 삭제됨).</span><span class="sxs-lookup"><span data-stu-id="af073-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="af073-114">이 설정은 비즈니스용 Skype 서버 제어판을 사용하여 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="af073-115">대신 비즈니스용 Skype 서버 관리 셸을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af073-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="af073-116">만료된 로그 파일을 삭제할 시간을 지정하려면 -LogCleanUpTimeOfDay 매개 변수와 함께 **New-CsDeviceUpdateConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af073-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="af073-117">자세한 내용은 [New-CsDeviceUpdateConfiguration을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="af073-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="af073-p104">파일을 삭제하면 파일 시스템에서 영구 제거됩니다. 따라서 파일을 삭제한 후 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="af073-120">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="af073-120">Tasks you can perform</span></span>

<span data-ttu-id="af073-121">**장치 로그 구성** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="af073-122">장치 로그 구성을 전역적으로 또는 특정 사이트나 풀에 대해 추가</span><span class="sxs-lookup"><span data-stu-id="af073-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="af073-123">기존 장치 로그 구성에 대한 옵션 수정</span><span class="sxs-lookup"><span data-stu-id="af073-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="af073-124">UI 참조</span><span class="sxs-lookup"><span data-stu-id="af073-124">UI Reference</span></span>

<span data-ttu-id="af073-125">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="af073-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="af073-126">**신규** 다음 범위를 사용하여 새 장치 로그 구성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="af073-127">전역</span><span class="sxs-lookup"><span data-stu-id="af073-127">Global</span></span>

  - <span data-ttu-id="af073-128">사이트</span><span class="sxs-lookup"><span data-stu-id="af073-128">Site</span></span>

- <span data-ttu-id="af073-129">**편집** 목록에서 장치 로그 구성의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="af073-130">이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="af073-131">**세부 정보 표시** 이 옵션을 선택하면 장치 로그 구성에 대한 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="af073-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="af073-132">**모두 선택** 이 옵션은 목록의 모든 장치 로그 구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af073-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="af073-133">**삭제** 이 옵션은 선택한 모든 장치 로그 구성을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="af073-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="af073-134">**새로 고침** 장치 로그 구성 목록을 새로 고쳐 모든 장치 로그 구성의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af073-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="af073-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af073-135">See also</span></span>

[<span data-ttu-id="af073-136">장치 업데이트 작업의 로그 파일 설정 수정</span><span class="sxs-lookup"><span data-stu-id="af073-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
