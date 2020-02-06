---
title: 장치 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가 하면 비즈니스용 Skype Server 제어판의 테스트 장치 페이지에 있는 목록에 표시 됩니다.
ms.openlocfilehash: 547b0f4e0737ab65463dc4b8350fc1050b071a83
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794537"
---
# <a name="test-device"></a><span data-ttu-id="cf5ab-106">장치 테스트</span><span class="sxs-lookup"><span data-stu-id="cf5ab-106">Test Device</span></span>

<span data-ttu-id="cf5ab-107">테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="cf5ab-108">장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="cf5ab-109">MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="cf5ab-110">장치를 추가 하면 비즈니스용 Skype Server 제어판의 **테스트 장치** 페이지에 있는 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cf5ab-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="cf5ab-111">Tasks you can perform</span></span>

<span data-ttu-id="cf5ab-112">**테스트 장치** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="cf5ab-113">전역 또는 특정 사이트에 대 한 테스트 장치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="cf5ab-114">기존 테스트 장치에 대 한 옵션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cf5ab-115">UI 참조</span><span class="sxs-lookup"><span data-stu-id="cf5ab-115">UI Reference</span></span>

<span data-ttu-id="cf5ab-116">다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="cf5ab-117">**새로운** 다음 범위를 사용 하 여 새 테스트 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="cf5ab-118">전역</span><span class="sxs-lookup"><span data-stu-id="cf5ab-118">Global</span></span>

  - <span data-ttu-id="cf5ab-119">사이트</span><span class="sxs-lookup"><span data-stu-id="cf5ab-119">Site</span></span>

- <span data-ttu-id="cf5ab-120">**편집** 목록에서 테스트 장치의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="cf5ab-121">이 옵션을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="cf5ab-122">**세부 정보 표시** 이 옵션은 테스트 장치에 대 한 옵션을 변경할 수 있는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="cf5ab-123">**모두 선택** 이 옵션은 목록의 모든 테스트 장치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="cf5ab-124">**삭제** 이 옵션은 선택한 모든 테스트 장치를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="cf5ab-125">**새로 고침** 테스트 장치 목록을 새로 고쳐 모든 테스트 장치에 대 한 옵션의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="cf5ab-126">장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서의 [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="cf5ab-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf5ab-127">See also</span></span>

[<span data-ttu-id="cf5ab-128">장치 테스트: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="cf5ab-128">Test Device: Create New or Edit Existing</span></span>](ms.lync.lscp.ClientDeviceTestEdit.md)

[<span data-ttu-id="cf5ab-129">신규-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="cf5ab-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="cf5ab-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="cf5ab-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="cf5ab-131">조직의 디바이스에 대 한 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="cf5ab-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
