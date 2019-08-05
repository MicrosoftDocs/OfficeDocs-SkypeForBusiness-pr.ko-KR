---
title: 비즈니스용 Skype 서버 2015의 EdgeServers 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 하나의 Edge 서버에 대 한 정보를 저장 합니다.
ms.openlocfilehash: a78acd3b6297bbef3348ef87047c8cb7f0893231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196762"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9c753-104">비즈니스용 Skype 서버 2015의 EdgeServers 테이블</span><span class="sxs-lookup"><span data-stu-id="9c753-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9c753-105">EdgeServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9c753-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="9c753-106">각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 하나의 Edge 서버에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c753-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="9c753-107">**열**</span><span class="sxs-lookup"><span data-stu-id="9c753-107">**Column**</span></span>|<span data-ttu-id="9c753-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="9c753-108">**Data Type**</span></span>|<span data-ttu-id="9c753-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="9c753-109">**Key/Index**</span></span>|<span data-ttu-id="9c753-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="9c753-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c753-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="9c753-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="9c753-112">int</span><span class="sxs-lookup"><span data-stu-id="9c753-112">int</span></span>  <br/> |<span data-ttu-id="9c753-113">주요한</span><span class="sxs-lookup"><span data-stu-id="9c753-113">Primary</span></span>  <br/> |<span data-ttu-id="9c753-114">이 Edge 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9c753-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="9c753-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="9c753-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="9c753-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c753-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9c753-117">Edge 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9c753-117">Edge Server name.</span></span>  <br/> |
   

