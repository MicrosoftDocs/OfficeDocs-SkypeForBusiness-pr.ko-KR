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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 하나의 Edge 서버에 대 한 정보를 저장 합니다.
ms.openlocfilehash: 7a1621e3416b6cff48c430e7bc2e45057ecb3e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815266"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9bd17-104">비즈니스용 Skype 서버 2015의 EdgeServers 테이블</span><span class="sxs-lookup"><span data-stu-id="9bd17-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9bd17-105">EdgeServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd17-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="9bd17-106">각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 하나의 Edge 서버에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd17-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="9bd17-107">**열**</span><span class="sxs-lookup"><span data-stu-id="9bd17-107">**Column**</span></span>|<span data-ttu-id="9bd17-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="9bd17-108">**Data Type**</span></span>|<span data-ttu-id="9bd17-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="9bd17-109">**Key/Index**</span></span>|<span data-ttu-id="9bd17-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="9bd17-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bd17-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="9bd17-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="9bd17-112">int</span><span class="sxs-lookup"><span data-stu-id="9bd17-112">int</span></span>  <br/> |<span data-ttu-id="9bd17-113">주요한</span><span class="sxs-lookup"><span data-stu-id="9bd17-113">Primary</span></span>  <br/> |<span data-ttu-id="9bd17-114">이 Edge 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd17-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="9bd17-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="9bd17-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="9bd17-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bd17-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9bd17-117">Edge 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd17-117">Edge Server name.</span></span>  <br/> |
   

