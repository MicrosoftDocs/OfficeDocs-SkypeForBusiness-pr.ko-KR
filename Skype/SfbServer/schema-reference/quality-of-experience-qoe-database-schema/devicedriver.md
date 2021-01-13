---
title: DeviceDriver 테이블
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver 테이블은 지원 테이블입니다. 각 레코드는 캡처 장치 또는 렌더링 장치에서 사용되는 드라이버를 나타냅니다.
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823078"
---
# <a name="devicedriver-table"></a><span data-ttu-id="d3e8d-104">DeviceDriver 테이블</span><span class="sxs-lookup"><span data-stu-id="d3e8d-104">DeviceDriver table</span></span>
 
<span data-ttu-id="d3e8d-p102">DeviceDriver 테이블은 지원 테이블입니다. 각 레코드는 캡처 장치 또는 렌더링 장치에서 사용되는 드라이버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-p102">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="d3e8d-107">**열**</span><span class="sxs-lookup"><span data-stu-id="d3e8d-107">**Column**</span></span>|<span data-ttu-id="d3e8d-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d3e8d-108">**Data Type**</span></span>|<span data-ttu-id="d3e8d-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="d3e8d-109">**Key/Index**</span></span>|<span data-ttu-id="d3e8d-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="d3e8d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3e8d-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="d3e8d-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="d3e8d-112">int</span><span class="sxs-lookup"><span data-stu-id="d3e8d-112">int</span></span>  <br/> |<span data-ttu-id="d3e8d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d3e8d-113">Primary</span></span>  <br/> |<span data-ttu-id="d3e8d-114">이 장치 드라이버 레코드를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="d3e8d-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="d3e8d-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="d3e8d-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="d3e8d-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="d3e8d-117">unique</span><span class="sxs-lookup"><span data-stu-id="d3e8d-117">unique</span></span>  <br/> |<span data-ttu-id="d3e8d-118">장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d3e8d-118">Device driver name.</span></span>  <br/> |
   

