---
title: MediationServers 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 중재 서버 하나에 대 한 정보를 저장 합니다.
ms.openlocfilehash: a79c7c1d81f220e034e63263ef8dbf81a13d4024
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196713"
---
# <a name="mediationservers-table"></a><span data-ttu-id="d9ba4-104">MediationServers 테이블</span><span class="sxs-lookup"><span data-stu-id="d9ba4-104">MediationServers table</span></span>
 
<span data-ttu-id="d9ba4-105">MediationServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ba4-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="d9ba4-106">각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 중재 서버 하나에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ba4-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="d9ba4-107">**열**</span><span class="sxs-lookup"><span data-stu-id="d9ba4-107">**Column**</span></span>|<span data-ttu-id="d9ba4-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d9ba4-108">**Data Type**</span></span>|<span data-ttu-id="d9ba4-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="d9ba4-109">**Key/Index**</span></span>|<span data-ttu-id="d9ba4-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="d9ba4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9ba4-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="d9ba4-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="d9ba4-112">int</span><span class="sxs-lookup"><span data-stu-id="d9ba4-112">int</span></span>  <br/> |<span data-ttu-id="d9ba4-113">주요한</span><span class="sxs-lookup"><span data-stu-id="d9ba4-113">Primary</span></span>  <br/> |<span data-ttu-id="d9ba4-114">이 중재 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ba4-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="d9ba4-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="d9ba4-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="d9ba4-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9ba4-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d9ba4-117">중재 서버 이름.</span><span class="sxs-lookup"><span data-stu-id="d9ba4-117">Mediation Server name.</span></span>  <br/> |
   

