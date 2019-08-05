---
title: 체감 품질 보기 세부 정보
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 보기는 체감 품질 SQL 데이터베이스에서 데이터를 반환 하는 가장 일반적인 시나리오를 다룹니다. 데이터베이스 테이블에 직접 액세스 하는 대신 사용자 지정 보고서를 작성 하는 데 사용 하는 것이 좋습니다. 이는 뷰가 향후 릴리스에서 이전 버전과의 호환성을 유지 하는 것이 더 많을 수 있기 때문입니다.
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196538"
---
# <a name="qoe-view-details"></a><span data-ttu-id="27136-104">체감 품질 보기 세부 정보</span><span class="sxs-lookup"><span data-stu-id="27136-104">QoE view details</span></span>
 
<span data-ttu-id="27136-105">보기는 체감 품질 SQL 데이터베이스에서 데이터를 반환 하는 가장 일반적인 시나리오를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="27136-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="27136-106">데이터베이스 테이블에 직접 액세스 하는 대신 사용자 지정 보고서를 작성 하는 데 사용 하는 것이 좋습니다. 이는 뷰가 향후 릴리스에서 이전 버전과의 호환성을 유지 하는 것이 더 많을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="27136-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="27136-107">**이름 보기**</span><span class="sxs-lookup"><span data-stu-id="27136-107">**View Name**</span></span>|<span data-ttu-id="27136-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="27136-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="27136-109">오디오 Streamdetail 보기</span><span class="sxs-lookup"><span data-stu-id="27136-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="27136-110">데이터베이스에 각 오디오 스트림에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="27136-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="27136-111">MediaLine</span><span class="sxs-lookup"><span data-stu-id="27136-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="27136-112">데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="27136-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="27136-113">일반적으로 하나의 오디오 세션에 오디오 미디어 선이 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27136-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="27136-114">하나의 오디오 및 비디오 (A/V) 세션에는 일반적으로 오디오 미디어 회선 하 나와 비디오 미디어 라인 하나가 포함 됩니다. 그러나 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우에는 세션에 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27136-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="27136-115">NetworkConfigurationSettings 보기</span><span class="sxs-lookup"><span data-stu-id="27136-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="27136-116">네트워크 구성에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="27136-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="27136-117">세션 보기</span><span class="sxs-lookup"><span data-stu-id="27136-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="27136-118">데이터베이스에 레코드가 있는 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="27136-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="27136-119">UserAgent 보기</span><span class="sxs-lookup"><span data-stu-id="27136-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="27136-120">데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="27136-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="27136-121">VideoStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="27136-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="27136-122">데이터베이스의 각 비디오 스트림에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="27136-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

