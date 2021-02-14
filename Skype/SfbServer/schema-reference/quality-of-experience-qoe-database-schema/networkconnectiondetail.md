---
title: NetworkConnectionDetail 테이블
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 테이블은 네트워크 연결 유형을 환경 품질 데이터베이스의 다른 곳에서 사용되는 네트워크 연결 식별자에 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806308"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="6e83b-104">NetworkConnectionDetail 테이블</span><span class="sxs-lookup"><span data-stu-id="6e83b-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="6e83b-105">NetworkConnectionDetail 테이블은 네트워크 연결 유형을 환경 품질 데이터베이스의 다른 곳에서 사용되는 네트워크 연결 식별자에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6e83b-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="6e83b-106">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e83b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6e83b-107">**열**</span><span class="sxs-lookup"><span data-stu-id="6e83b-107">**Column**</span></span>|<span data-ttu-id="6e83b-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="6e83b-108">**Data Type**</span></span>|<span data-ttu-id="6e83b-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="6e83b-109">**Key/Index**</span></span>|<span data-ttu-id="6e83b-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="6e83b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e83b-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="6e83b-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="6e83b-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="6e83b-112">tinyint</span></span>  <br/> |<span data-ttu-id="6e83b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6e83b-113">Primary</span></span>  <br/> |<span data-ttu-id="6e83b-114">네트워크 연결 유형의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6e83b-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="6e83b-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="6e83b-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="6e83b-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="6e83b-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="6e83b-117">고유</span><span class="sxs-lookup"><span data-stu-id="6e83b-117">Unique</span></span>  <br/> |<span data-ttu-id="6e83b-118">NetworkConnectionDetailKey에 해당하는 네트워크 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6e83b-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="6e83b-119">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e83b-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="6e83b-120">0 -- 유선</span><span class="sxs-lookup"><span data-stu-id="6e83b-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="6e83b-121">1 -- WiFi</span><span class="sxs-lookup"><span data-stu-id="6e83b-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="6e83b-122">2 -- 이더넷</span><span class="sxs-lookup"><span data-stu-id="6e83b-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="6e83b-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="6e83b-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="6e83b-124">4 -- 기타</span><span class="sxs-lookup"><span data-stu-id="6e83b-124">4 -- Other</span></span>  <br/> <span data-ttu-id="6e83b-125">5 -- 터널</span><span class="sxs-lookup"><span data-stu-id="6e83b-125">5 -- Tunnel</span></span>  <br/> |
   

