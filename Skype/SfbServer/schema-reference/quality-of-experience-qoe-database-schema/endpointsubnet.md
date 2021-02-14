---
title: EndpointSubnet 테이블
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
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 테이블은 지원 테이블입니다. 각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: 9671c7dc269b7f13f0679c6da12b46ea7d7c8b5f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815828"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="b531e-104">EndpointSubnet 테이블</span><span class="sxs-lookup"><span data-stu-id="b531e-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="b531e-p102">EndpointSubnet 테이블은 지원 테이블입니다. 각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b531e-p102">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="b531e-107">**열**</span><span class="sxs-lookup"><span data-stu-id="b531e-107">**Column**</span></span>|<span data-ttu-id="b531e-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="b531e-108">**Data Type**</span></span>|<span data-ttu-id="b531e-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="b531e-109">**Key/Index**</span></span>|<span data-ttu-id="b531e-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="b531e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b531e-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="b531e-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="b531e-112">int</span><span class="sxs-lookup"><span data-stu-id="b531e-112">int</span></span>  <br/> |<span data-ttu-id="b531e-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="b531e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b531e-114">정수로 표시된 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="b531e-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="b531e-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b531e-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b531e-116">datetime</span><span class="sxs-lookup"><span data-stu-id="b531e-116">datetime</span></span>  <br/> ||<span data-ttu-id="b531e-117">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b531e-117">For internal use only.</span></span>  <br/> |
   

