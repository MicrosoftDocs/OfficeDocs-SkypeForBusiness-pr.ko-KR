---
title: 테스트 장치 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: 테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다. 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가 하면 비즈니스용 Skype Server 제어판의 테스트 장치 페이지에 있는 목록에 표시 됩니다.
ms.openlocfilehash: 56f5c7b43f55f50c5fa5e73cade3f74bea752778
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699470"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="eb1e6-107">테스트 장치: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="eb1e6-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="eb1e6-108">테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="eb1e6-109">테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="eb1e6-110">장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="eb1e6-111">MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="eb1e6-112">장치를 추가 하면 비즈니스용 Skype Server 제어판의 **테스트 장치** 페이지에 있는 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="eb1e6-113">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="eb1e6-113">Tasks you can perform</span></span>

<span data-ttu-id="eb1e6-114">**새 테스트 장치** 또는 **테스트 장치 편집** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="eb1e6-115">새 테스트 장치 추가</span><span class="sxs-lookup"><span data-stu-id="eb1e6-115">Add a new test device.</span></span>

- <span data-ttu-id="eb1e6-116">기존 테스트 장치의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="eb1e6-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="eb1e6-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="eb1e6-117">UI Reference</span></span>

<span data-ttu-id="eb1e6-118">다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="eb1e6-119">**범위** 테스트 장치의 범위 (전역 또는 사이트)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="eb1e6-120">**이름** 테스트 디바이스의 이름을 추가 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="eb1e6-121">**장치 이름** 테스트 디바이스의 이름을 추가 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="eb1e6-122">**식별자 형식** 다음 중 하나를 선택 하 여 장치를 식별 하는 데 사용할 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="eb1e6-123">**MAC 주소**</span><span class="sxs-lookup"><span data-stu-id="eb1e6-123">**MAC address**</span></span>

  - <span data-ttu-id="eb1e6-124">**일련 번호**</span><span class="sxs-lookup"><span data-stu-id="eb1e6-124">**Serial number**</span></span>

- <span data-ttu-id="eb1e6-125">**고유 식별자** 디바이스의 MAC 주소 또는 일련 번호를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="eb1e6-126">장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서의 [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb1e6-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="eb1e6-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb1e6-127">See also</span></span>

[<span data-ttu-id="eb1e6-128">장치 테스트</span><span class="sxs-lookup"><span data-stu-id="eb1e6-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="eb1e6-129">신규-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="eb1e6-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="eb1e6-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="eb1e6-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="eb1e6-131">조직의 디바이스에 대 한 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="eb1e6-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
