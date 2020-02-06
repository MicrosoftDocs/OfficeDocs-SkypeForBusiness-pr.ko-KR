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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 중재 서버 하나에 대 한 정보를 저장 합니다.
ms.openlocfilehash: 74c1095044bd9bb7183202d115236eba863c62da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815026"
---
# <a name="mediationservers-table"></a><span data-ttu-id="5a55c-104">MediationServers 테이블</span><span class="sxs-lookup"><span data-stu-id="5a55c-104">MediationServers table</span></span>
 
<span data-ttu-id="5a55c-105">MediationServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="5a55c-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="5a55c-106">각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 중재 서버 하나에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a55c-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="5a55c-107">**열**</span><span class="sxs-lookup"><span data-stu-id="5a55c-107">**Column**</span></span>|<span data-ttu-id="5a55c-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="5a55c-108">**Data Type**</span></span>|<span data-ttu-id="5a55c-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="5a55c-109">**Key/Index**</span></span>|<span data-ttu-id="5a55c-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="5a55c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5a55c-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="5a55c-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="5a55c-112">int</span><span class="sxs-lookup"><span data-stu-id="5a55c-112">int</span></span>  <br/> |<span data-ttu-id="5a55c-113">주요한</span><span class="sxs-lookup"><span data-stu-id="5a55c-113">Primary</span></span>  <br/> |<span data-ttu-id="5a55c-114">이 중재 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a55c-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="5a55c-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="5a55c-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="5a55c-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5a55c-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="5a55c-117">중재 서버 이름.</span><span class="sxs-lookup"><span data-stu-id="5a55c-117">Mediation Server name.</span></span>  <br/> |
   

