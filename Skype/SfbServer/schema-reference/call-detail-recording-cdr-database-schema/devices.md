---
title: 비즈니스용 Skype 서버의 Devices 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 테이블은 지원 테이블입니다. 각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831818"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="953a8-104">비즈니스용 Skype 서버의 Devices 테이블</span><span class="sxs-lookup"><span data-stu-id="953a8-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="953a8-105">Devices 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="953a8-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="953a8-106">각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="953a8-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="953a8-107">**열**</span><span class="sxs-lookup"><span data-stu-id="953a8-107">**Column**</span></span>|<span data-ttu-id="953a8-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="953a8-108">**Data Type**</span></span>|<span data-ttu-id="953a8-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="953a8-109">**Key/Index**</span></span>|<span data-ttu-id="953a8-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="953a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="953a8-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="953a8-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="953a8-112">int</span><span class="sxs-lookup"><span data-stu-id="953a8-112">int</span></span>  <br/> |<span data-ttu-id="953a8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="953a8-113">Primary</span></span>  <br/> |<span data-ttu-id="953a8-114">이 하드웨어 버전을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="953a8-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="953a8-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="953a8-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="953a8-116">int</span><span class="sxs-lookup"><span data-stu-id="953a8-116">int</span></span>  <br/> |<span data-ttu-id="953a8-117">외계인</span><span class="sxs-lookup"><span data-stu-id="953a8-117">Foreign</span></span>  <br/> |<span data-ttu-id="953a8-118">이 장치의 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="953a8-118">Manufacturer of this device.</span></span> <span data-ttu-id="953a8-119">자세한 내용은 [비즈니스용 Skype 서버 2015의 Manufacturers](manufacturers.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="953a8-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="953a8-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="953a8-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="953a8-121">int</span><span class="sxs-lookup"><span data-stu-id="953a8-121">int</span></span>  <br/> |<span data-ttu-id="953a8-122">외계인</span><span class="sxs-lookup"><span data-stu-id="953a8-122">Foreign</span></span>  <br/> |<span data-ttu-id="953a8-123">이 장치의 하드웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="953a8-123">Hardware version of this device.</span></span> <span data-ttu-id="953a8-124">자세한 내용은 비즈니스용 [Skype 서버 2015의 HardwareVersions](hardwareversions.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="953a8-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="953a8-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="953a8-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="953a8-126">bigint</span><span class="sxs-lookup"><span data-stu-id="953a8-126">bigint</span></span>  <br/> ||<span data-ttu-id="953a8-127">MAC 주소</span><span class="sxs-lookup"><span data-stu-id="953a8-127">MAC Address</span></span>  <br/> |
   

