---
title: 테스트 장치
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
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가하면 비즈니스용 Skype 서버 제어판의 테스트 장치 페이지에 있는 목록에 표시됩니다.
ms.openlocfilehash: e48c76237f8d9cafb1642e8ec1e598dcc24453c3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099354"
---
# <a name="test-device"></a><span data-ttu-id="dc5f4-106">테스트 장치</span><span class="sxs-lookup"><span data-stu-id="dc5f4-106">Test Device</span></span>

<span data-ttu-id="dc5f4-107">테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="dc5f4-108">장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="dc5f4-109">MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="dc5f4-110">장치를 추가하면 비즈니스용 Skype 서버 제어판의 테스트 장치 페이지에 있는 목록에 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="dc5f4-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="dc5f4-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="dc5f4-111">Tasks you can perform</span></span>

<span data-ttu-id="dc5f4-112">**테스트 장치** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="dc5f4-113">테스트 장치를 전역적으로 또는 특정 사이트에 대해 추가</span><span class="sxs-lookup"><span data-stu-id="dc5f4-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="dc5f4-114">기존 테스트 장치에 대한 옵션 수정</span><span class="sxs-lookup"><span data-stu-id="dc5f4-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="dc5f4-115">UI 참조</span><span class="sxs-lookup"><span data-stu-id="dc5f4-115">UI Reference</span></span>

<span data-ttu-id="dc5f4-116">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="dc5f4-117">**새로 추가** 다음 범위를 사용하여 새 테스트 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="dc5f4-118">전역</span><span class="sxs-lookup"><span data-stu-id="dc5f4-118">Global</span></span>

  - <span data-ttu-id="dc5f4-119">사이트</span><span class="sxs-lookup"><span data-stu-id="dc5f4-119">Site</span></span>

- <span data-ttu-id="dc5f4-120">**편집** 목록에서 테스트 장치의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="dc5f4-121">이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="dc5f4-122">**세부 정보 표시** 이 옵션을 선택하면 테스트 장치의 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="dc5f4-123">**모두 선택** 이 옵션은 목록의 모든 테스트 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="dc5f4-124">**삭제** 이 옵션은 선택한 모든 테스트 장치를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="dc5f4-125">**새로 고침** 테스트 장치 목록을 새로 고쳐 모든 테스트 장치의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="dc5f4-126">장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서에서 [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc5f4-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="dc5f4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc5f4-127">See also</span></span>

[<span data-ttu-id="dc5f4-128">장치 테스트: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="dc5f4-128">Test Device: Create New or Edit Existing</span></span>](test-device-create-new-or-edit-existing.md)

[<span data-ttu-id="dc5f4-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="dc5f4-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="dc5f4-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="dc5f4-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="dc5f4-131">조직에서 장치에 대한 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="dc5f4-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)