---
title: EndpointSubnet 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 테이블은 지원 테이블입니다. 각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: dcb80256a8a1fb1fb880021e140a0f037142087f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809346"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="7f9c0-104">EndpointSubnet 테이블</span><span class="sxs-lookup"><span data-stu-id="7f9c0-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="7f9c0-105">EndpointSubnet 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="7f9c0-106">각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="7f9c0-107">**열**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-107">**Column**</span></span>|<span data-ttu-id="7f9c0-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-108">**Data Type**</span></span>|<span data-ttu-id="7f9c0-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-109">**Key/Index**</span></span>|<span data-ttu-id="7f9c0-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7f9c0-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="7f9c0-112">int</span><span class="sxs-lookup"><span data-stu-id="7f9c0-112">int</span></span>  <br/> |<span data-ttu-id="7f9c0-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="7f9c0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7f9c0-114">서브넷에 대 한 정수 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="7f9c0-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7f9c0-116">dmtf</span><span class="sxs-lookup"><span data-stu-id="7f9c0-116">datetime</span></span>  <br/> ||<span data-ttu-id="7f9c0-117">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-117">For internal use only.</span></span>  <br/> |
   

