---
title: 장치 업데이트
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft는 정기적으로 비즈니스용 Skype Phone Edition에 대한 새로운 장치 펌웨어 업데이트 집합을 릴리스하여 서버로 가져와 사용자에게 배포할 수 있습니다. Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동하고Phone Edition을 검색하여 최신 장치 업데이트 규칙 집합을 얻을 수 있습니다.최신 업데이트 패키지를 다운로드하고 업데이트를 업로드할 컴퓨터의 폴더에 파일을 추출합니다. 파일을 추출한 후 Import-CsDeviceUpdate cmdlet을 사용하여 추출된 찾은 장치 업데이트 규칙을 가져올 수 있습니다. CAB 파일(이름을 사용할 수 UCUpdates.cab. 자세한 내용은 Import-CsDeviceUpdate를 참조합니다.
ms.openlocfilehash: 375069d5812d5aa13ebd63dd02eaa3cdd6151cc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811058"
---
# <a name="device-update"></a><span data-ttu-id="113b2-106">장치 업데이트</span><span class="sxs-lookup"><span data-stu-id="113b2-106">Device Update</span></span>

<span data-ttu-id="113b2-107">Microsoft는 정기적으로 비즈니스용 Skype Phone Edition에 대한 새로운 장치 펌웨어 업데이트 집합을 릴리스하여 서버로 가져와 사용자에게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="113b2-108">Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동하고 "Phone Edition"을 검색하여 최신 장치 업데이트 규칙 집합을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="113b2-109">최신 업데이트 패키지를 다운로드하고 업데이트를 업로드할 컴퓨터의 폴더에 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="113b2-110">파일을 추출한 후 **Import-CsDeviceUpdate** cmdlet을 사용하여 추출된 찾은 장치 업데이트 규칙을 가져올 수 있습니다. CAB 파일(이름을 사용할 수 UCUpdates.cab.</span><span class="sxs-lookup"><span data-stu-id="113b2-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="113b2-111">자세한 내용은 [Import-CsDeviceUpdate를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="113b2-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="113b2-112">장치 업데이트 규칙을 가져온 후 장치 업데이트  페이지를 사용하여 조직의 장치에 대한 이러한 규칙을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="113b2-113">펌웨어 업데이트를 테스트한 다음 테스트가 성공한 경우 조직에서 사용되는 모든 관련 장치에서 업데이트를 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="113b2-114">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="113b2-114">Tasks you can perform</span></span>

<span data-ttu-id="113b2-115">장치 업데이트 페이지에서는 다음 **작업을 수행할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="113b2-116">목록에서 장치 업데이트를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="113b2-117">보류 중인 장치 업데이트를 취소하거나 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="113b2-118">목록에서 장치 업데이트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="113b2-119">UI 참조</span><span class="sxs-lookup"><span data-stu-id="113b2-119">UI Reference</span></span>

<span data-ttu-id="113b2-120">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="113b2-121">**편집** 이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="113b2-122">**모두 선택** 이 옵션은 목록의 모든 장치 업데이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="113b2-123">**삭제** 이 옵션은 선택한 모든 장치 업데이트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="113b2-124">**작업** 목록에서 업데이트를 하나 이상 선택하고 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="113b2-125">**보류 중인 업데이트 취소** 이 옵션을 사용하면 선택한 업데이트가 조직의 장치에 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="113b2-126">**승인** 이 옵션을 사용하면 선택한 업데이트를 조직의 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="113b2-127">**복원** 이 옵션을 사용하면 이전에 승인된 업데이트를 조직의 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="113b2-128">**새로 고침** 목록을 새로 고쳐 모든 장치 업데이트의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b2-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="113b2-129">장치 업데이트 웹 서비스에 대한 [](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) 자세한 내용은 계획 설명서에서 조직에서 장치용 소프트웨어 업데이트 보기를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="113b2-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="113b2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="113b2-130">See also</span></span>

[<span data-ttu-id="113b2-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="113b2-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
