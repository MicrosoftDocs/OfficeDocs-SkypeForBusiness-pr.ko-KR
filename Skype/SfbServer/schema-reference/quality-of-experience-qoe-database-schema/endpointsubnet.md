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
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 테이블은 지원 테이블입니다. 각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: b8a8e62178919da72082f99acad7798f3935a5ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196566"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="93205-104">EndpointSubnet 테이블</span><span class="sxs-lookup"><span data-stu-id="93205-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="93205-105">EndpointSubnet 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="93205-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="93205-106">각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93205-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="93205-107">**열**</span><span class="sxs-lookup"><span data-stu-id="93205-107">**Column**</span></span>|<span data-ttu-id="93205-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="93205-108">**Data Type**</span></span>|<span data-ttu-id="93205-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="93205-109">**Key/Index**</span></span>|<span data-ttu-id="93205-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="93205-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93205-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="93205-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="93205-112">int</span><span class="sxs-lookup"><span data-stu-id="93205-112">int</span></span>  <br/> |<span data-ttu-id="93205-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="93205-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="93205-114">서브넷에 대 한 정수 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="93205-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="93205-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="93205-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="93205-116">dmtf</span><span class="sxs-lookup"><span data-stu-id="93205-116">datetime</span></span>  <br/> ||<span data-ttu-id="93205-117">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93205-117">For internal use only.</span></span>  <br/> |
   

