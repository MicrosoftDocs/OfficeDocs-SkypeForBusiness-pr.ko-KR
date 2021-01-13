---
title: 테스트 장치 새로 만들기 또는 기존 데이터 편집
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
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: 테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다. 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가하면 비즈니스용 Skype 서버 제어판의 테스트 장치 페이지에 있는 목록에 장치가 표시됩니다.
ms.openlocfilehash: cf4895e84e486939515094042010383854587f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819068"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="4e5c2-107">테스트 장치: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="4e5c2-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="4e5c2-108">테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="4e5c2-109">테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="4e5c2-110">장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="4e5c2-111">MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="4e5c2-112">장치를 추가하면 비즈니스용 Skype 서버 제어판의 테스트 장치 페이지에 있는 목록에 장치가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="4e5c2-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4e5c2-113">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="4e5c2-113">Tasks you can perform</span></span>

<span data-ttu-id="4e5c2-114">**새 테스트 장치** 또는 **테스트 장치 편집** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="4e5c2-115">새 테스트 장치 추가</span><span class="sxs-lookup"><span data-stu-id="4e5c2-115">Add a new test device.</span></span>

- <span data-ttu-id="4e5c2-116">기존 테스트 장치의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="4e5c2-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4e5c2-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="4e5c2-117">UI Reference</span></span>

<span data-ttu-id="4e5c2-118">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="4e5c2-119">**범위** 테스트 장치의 범위(전역 또는 사이트)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="4e5c2-120">**이름** 테스트 장치의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="4e5c2-121">**장치 이름** 테스트 장치의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="4e5c2-122">**식별자 유형** 다음 중 하나를 선택하여 디바이스를 식별하는 데 사용할 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="4e5c2-123">**MAC 주소**</span><span class="sxs-lookup"><span data-stu-id="4e5c2-123">**MAC address**</span></span>

  - <span data-ttu-id="4e5c2-124">**일련 번호**</span><span class="sxs-lookup"><span data-stu-id="4e5c2-124">**Serial number**</span></span>

- <span data-ttu-id="4e5c2-125">**고유 식별자** 장치의 MAC 주소 또는 일련 번호를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="4e5c2-126">장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서에서 [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e5c2-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="4e5c2-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e5c2-127">See also</span></span>

[<span data-ttu-id="4e5c2-128">장치 테스트</span><span class="sxs-lookup"><span data-stu-id="4e5c2-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="4e5c2-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="4e5c2-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="4e5c2-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="4e5c2-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="4e5c2-131">조직에서 장치에 대한 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="4e5c2-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
