---
title: NetworkConnectionDetail 테이블
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 테이블은 환경 데이터베이스의 다른 곳에서 사용 되는 네트워크 연결 식별자에 네트워크 연결 유형을 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807506"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="beafc-104">NetworkConnectionDetail 테이블</span><span class="sxs-lookup"><span data-stu-id="beafc-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="beafc-105">NetworkConnectionDetail 테이블은 환경 데이터베이스의 다른 곳에서 사용 되는 네트워크 연결 식별자에 네트워크 연결 유형을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="beafc-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="beafc-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="beafc-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="beafc-107">**열**</span><span class="sxs-lookup"><span data-stu-id="beafc-107">**Column**</span></span>|<span data-ttu-id="beafc-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="beafc-108">**Data Type**</span></span>|<span data-ttu-id="beafc-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="beafc-109">**Key/Index**</span></span>|<span data-ttu-id="beafc-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="beafc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="beafc-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="beafc-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="beafc-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="beafc-112">tinyint</span></span>  <br/> |<span data-ttu-id="beafc-113">주요한</span><span class="sxs-lookup"><span data-stu-id="beafc-113">Primary</span></span>  <br/> |<span data-ttu-id="beafc-114">네트워크 연결 형식의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="beafc-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="beafc-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="beafc-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="beafc-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="beafc-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="beafc-117">독특한</span><span class="sxs-lookup"><span data-stu-id="beafc-117">Unique</span></span>  <br/> |<span data-ttu-id="beafc-118">NetworkConnectionDetailKey에 해당 하는 네트워크 연결 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="beafc-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="beafc-119">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="beafc-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="beafc-120">0--유선</span><span class="sxs-lookup"><span data-stu-id="beafc-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="beafc-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="beafc-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="beafc-122">2--이더넷</span><span class="sxs-lookup"><span data-stu-id="beafc-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="beafc-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="beafc-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="beafc-124">4--기타</span><span class="sxs-lookup"><span data-stu-id="beafc-124">4 -- Other</span></span>  <br/> <span data-ttu-id="beafc-125">5--터널</span><span class="sxs-lookup"><span data-stu-id="beafc-125">5 -- Tunnel</span></span>  <br/> |
   

