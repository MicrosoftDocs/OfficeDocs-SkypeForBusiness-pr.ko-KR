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
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 테이블은 환경 데이터베이스의 다른 곳에서 사용 되는 네트워크 연결 식별자에 네트워크 연결 유형을 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196546"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="13a4d-104">NetworkConnectionDetail 테이블</span><span class="sxs-lookup"><span data-stu-id="13a4d-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="13a4d-105">NetworkConnectionDetail 테이블은 환경 데이터베이스의 다른 곳에서 사용 되는 네트워크 연결 식별자에 네트워크 연결 유형을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="13a4d-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="13a4d-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13a4d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="13a4d-107">**열**</span><span class="sxs-lookup"><span data-stu-id="13a4d-107">**Column**</span></span>|<span data-ttu-id="13a4d-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="13a4d-108">**Data Type**</span></span>|<span data-ttu-id="13a4d-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="13a4d-109">**Key/Index**</span></span>|<span data-ttu-id="13a4d-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="13a4d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13a4d-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="13a4d-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="13a4d-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="13a4d-112">tinyint</span></span>  <br/> |<span data-ttu-id="13a4d-113">주요한</span><span class="sxs-lookup"><span data-stu-id="13a4d-113">Primary</span></span>  <br/> |<span data-ttu-id="13a4d-114">네트워크 연결 형식의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="13a4d-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="13a4d-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="13a4d-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="13a4d-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="13a4d-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="13a4d-117">독특한</span><span class="sxs-lookup"><span data-stu-id="13a4d-117">Unique</span></span>  <br/> |<span data-ttu-id="13a4d-118">NetworkConnectionDetailKey에 해당 하는 네트워크 연결 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="13a4d-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="13a4d-119">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13a4d-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="13a4d-120">0--유선</span><span class="sxs-lookup"><span data-stu-id="13a4d-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="13a4d-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="13a4d-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="13a4d-122">2--이더넷</span><span class="sxs-lookup"><span data-stu-id="13a4d-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="13a4d-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="13a4d-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="13a4d-124">4--기타</span><span class="sxs-lookup"><span data-stu-id="13a4d-124">4 -- Other</span></span>  <br/> <span data-ttu-id="13a4d-125">5--터널</span><span class="sxs-lookup"><span data-stu-id="13a4d-125">5 -- Tunnel</span></span>  <br/> |
   

