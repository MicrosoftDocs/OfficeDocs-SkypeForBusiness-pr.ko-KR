---
title: Device 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 장치 테이블은 다양 한 캡처 또는 렌더링 장치에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196574"
---
# <a name="device-table"></a><span data-ttu-id="e6144-104">Device 테이블</span><span class="sxs-lookup"><span data-stu-id="e6144-104">Device table</span></span>
 
<span data-ttu-id="e6144-105">장치 테이블은 다양 한 캡처 또는 렌더링 장치에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="e6144-106">테이블의 각 레코드는 하나의 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="e6144-107">**열**</span><span class="sxs-lookup"><span data-stu-id="e6144-107">**Column**</span></span>|<span data-ttu-id="e6144-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="e6144-108">**Data Type**</span></span>|<span data-ttu-id="e6144-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="e6144-109">**Key/Index**</span></span>|<span data-ttu-id="e6144-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="e6144-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6144-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="e6144-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="e6144-112">int</span><span class="sxs-lookup"><span data-stu-id="e6144-112">int</span></span>  <br/> |<span data-ttu-id="e6144-113">주요한</span><span class="sxs-lookup"><span data-stu-id="e6144-113">Primary</span></span>  <br/> |<span data-ttu-id="e6144-114">이 장치를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="e6144-115">**이름**</span><span class="sxs-lookup"><span data-stu-id="e6144-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="e6144-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6144-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6144-117">장치 이름 + DeviceType는 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="e6144-118">장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="e6144-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="e6144-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="e6144-120">다소</span><span class="sxs-lookup"><span data-stu-id="e6144-120">bit</span></span>  <br/> |<span data-ttu-id="e6144-121">장치 이름 + DeviceType는 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="e6144-122">장치 유형.</span><span class="sxs-lookup"><span data-stu-id="e6144-122">Device type.</span></span> <span data-ttu-id="e6144-123">1은 캡처 장치이 고 0은 렌더링 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="e6144-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

