---
title: QoE 보기 세부 정보
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 보기에는 QoE 데이터베이스 데이터베이스에서 데이터를 반환하는 가장 일반적인 시나리오가 SQL 있습니다. 데이터베이스 테이블에 직접 액세스하는 대신 사용자 지정 보고서를 작성하는 데 사용되는 보기를 사용하는 것이 좋습니다. 이는 보기가 이후 릴리스와의 호환성을 유지할 가능성이 더 높기 때문에입니다.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834478"
---
# <a name="qoe-view-details"></a><span data-ttu-id="98e4e-104">QoE 보기 세부 정보</span><span class="sxs-lookup"><span data-stu-id="98e4e-104">QoE view details</span></span>
 
<span data-ttu-id="98e4e-105">보기에는 QoE 데이터베이스 데이터베이스에서 데이터를 반환하는 가장 일반적인 시나리오가 SQL 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="98e4e-106">데이터베이스 테이블에 직접 액세스하는 대신 사용자 지정 보고서를 작성하는 데 사용되는 보기를 사용하는 것이 좋습니다. 이는 보기가 이후 릴리스와의 호환성을 유지할 가능성이 더 높기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="98e4e-107">**뷰 이름/View Name**</span><span class="sxs-lookup"><span data-stu-id="98e4e-107">**View Name**</span></span>|<span data-ttu-id="98e4e-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="98e4e-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="98e4e-109">AudioStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="98e4e-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="98e4e-110">데이터베이스에 각 오디오 스트림에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="98e4e-111">MediaLine 보기</span><span class="sxs-lookup"><span data-stu-id="98e4e-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="98e4e-112">데이터베이스에 각 미디어 라인에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="98e4e-113">하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="98e4e-114">하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="98e4e-115">NetworkConfigurationSettings 보기</span><span class="sxs-lookup"><span data-stu-id="98e4e-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="98e4e-116">네트워크 구성에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="98e4e-117">세션 보기</span><span class="sxs-lookup"><span data-stu-id="98e4e-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="98e4e-118">데이터베이스에 레코드가 있는 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="98e4e-119">UserAgent 보기</span><span class="sxs-lookup"><span data-stu-id="98e4e-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="98e4e-120">데이터베이스에 레코드가 있는 세션에 포함된 사용자 에이전트에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="98e4e-121">VideoStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="98e4e-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="98e4e-122">데이터베이스의 각 비디오 스트림에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98e4e-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

