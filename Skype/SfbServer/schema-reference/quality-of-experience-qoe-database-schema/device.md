---
title: Device 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814748"
---
# <a name="device-table"></a><span data-ttu-id="209b4-104">Device 테이블</span><span class="sxs-lookup"><span data-stu-id="209b4-104">Device table</span></span>
 
<span data-ttu-id="209b4-p102">Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="209b4-p102">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="209b4-107">**열**</span><span class="sxs-lookup"><span data-stu-id="209b4-107">**Column**</span></span>|<span data-ttu-id="209b4-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="209b4-108">**Data Type**</span></span>|<span data-ttu-id="209b4-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="209b4-109">**Key/Index**</span></span>|<span data-ttu-id="209b4-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="209b4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="209b4-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="209b4-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="209b4-112">int</span><span class="sxs-lookup"><span data-stu-id="209b4-112">int</span></span>  <br/> |<span data-ttu-id="209b4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="209b4-113">Primary</span></span>  <br/> |<span data-ttu-id="209b4-114">이 장치를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="209b4-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="209b4-115">**장치 이름**</span><span class="sxs-lookup"><span data-stu-id="209b4-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="209b4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209b4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="209b4-117">DeviceName + DeviceType은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="209b4-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="209b4-118">장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="209b4-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="209b4-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="209b4-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="209b4-120">bit</span><span class="sxs-lookup"><span data-stu-id="209b4-120">bit</span></span>  <br/> |<span data-ttu-id="209b4-121">DeviceName + DeviceType은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="209b4-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="209b4-p103">장치 유형입니다. 1은 캡처 장치이고 0은 렌더링 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="209b4-p103">Device type. 1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

