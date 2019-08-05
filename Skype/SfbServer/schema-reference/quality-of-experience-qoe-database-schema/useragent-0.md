---
title: UserAgent 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 보기는 데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196515"
---
# <a name="useragent-view"></a><span data-ttu-id="6d649-104">UserAgent 보기</span><span class="sxs-lookup"><span data-stu-id="6d649-104">UserAgent view</span></span>
 
<span data-ttu-id="6d649-105">UserAgent 보기는 데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="6d649-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6d649-107">**열**</span><span class="sxs-lookup"><span data-stu-id="6d649-107">**Column**</span></span>|<span data-ttu-id="6d649-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="6d649-108">**Data Type**</span></span>|<span data-ttu-id="6d649-109">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="6d649-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d649-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="6d649-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="6d649-111">int</span><span class="sxs-lookup"><span data-stu-id="6d649-111">int</span></span>  <br/> |<span data-ttu-id="6d649-112">이 사용자 에이전트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="6d649-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="6d649-113">UserAgent</span></span>  <br/> |<span data-ttu-id="6d649-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6d649-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6d649-115">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="6d649-116">UAType</span><span class="sxs-lookup"><span data-stu-id="6d649-116">UAType</span></span>  <br/> |<span data-ttu-id="6d649-117">smallint</span><span class="sxs-lookup"><span data-stu-id="6d649-117">smallint</span></span>  <br/> |<span data-ttu-id="6d649-118">사용자 에이전트의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-118">Type of user agent.</span></span> <span data-ttu-id="6d649-119">자세한 내용은 [UserAgent 테이블](useragent.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d649-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="6d649-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="6d649-120">UACategory</span></span>  <br/> |<span data-ttu-id="6d649-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6d649-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="6d649-122">사용자 에이전트가 속한 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="6d649-123">예를 들어 사용자 에이전트 Conferencing_Attendant_ 1.0은 UACategory CAA에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6d649-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

