---
title: 비즈니스용 Skype 서버 2015의 장치 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: 장치 테이블은 지원 테이블입니다. 각 레코드는 한 장치 (일반 전화기)에 대 한 정보를 저장 합니다.
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196766"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="940eb-104">비즈니스용 Skype 서버 2015의 장치 테이블</span><span class="sxs-lookup"><span data-stu-id="940eb-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="940eb-105">장치 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="940eb-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="940eb-106">각 레코드는 한 장치 (일반 전화기)에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="940eb-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="940eb-107">**열**</span><span class="sxs-lookup"><span data-stu-id="940eb-107">**Column**</span></span>|<span data-ttu-id="940eb-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="940eb-108">**Data Type**</span></span>|<span data-ttu-id="940eb-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="940eb-109">**Key/Index**</span></span>|<span data-ttu-id="940eb-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="940eb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="940eb-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="940eb-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="940eb-112">int</span><span class="sxs-lookup"><span data-stu-id="940eb-112">int</span></span>  <br/> |<span data-ttu-id="940eb-113">주요한</span><span class="sxs-lookup"><span data-stu-id="940eb-113">Primary</span></span>  <br/> |<span data-ttu-id="940eb-114">이 하드웨어 버전을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="940eb-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="940eb-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="940eb-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="940eb-116">int</span><span class="sxs-lookup"><span data-stu-id="940eb-116">int</span></span>  <br/> |<span data-ttu-id="940eb-117">외부</span><span class="sxs-lookup"><span data-stu-id="940eb-117">Foreign</span></span>  <br/> |<span data-ttu-id="940eb-118">이 장치에 대 한 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="940eb-118">Manufacturer of this device.</span></span> <span data-ttu-id="940eb-119">자세한 내용은 [비즈니스용 Skype 서버 2015의 제조업체 표](manufacturers.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="940eb-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="940eb-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="940eb-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="940eb-121">int</span><span class="sxs-lookup"><span data-stu-id="940eb-121">int</span></span>  <br/> |<span data-ttu-id="940eb-122">외부</span><span class="sxs-lookup"><span data-stu-id="940eb-122">Foreign</span></span>  <br/> |<span data-ttu-id="940eb-123">이 장치에 대 한 하드웨어 버전.</span><span class="sxs-lookup"><span data-stu-id="940eb-123">Hardware version of this device.</span></span> <span data-ttu-id="940eb-124">자세한 내용은 [비즈니스용 Skype 서버 2015에서 HardwareVersions 테이블](hardwareversions.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="940eb-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="940eb-125">**Mac**</span><span class="sxs-lookup"><span data-stu-id="940eb-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="940eb-126">bigint</span><span class="sxs-lookup"><span data-stu-id="940eb-126">bigint</span></span>  <br/> ||<span data-ttu-id="940eb-127">MAC 주소</span><span class="sxs-lookup"><span data-stu-id="940eb-127">MAC Address</span></span>  <br/> |
   

