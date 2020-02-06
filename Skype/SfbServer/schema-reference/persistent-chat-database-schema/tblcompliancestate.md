---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814636"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="f2445-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="f2445-103">tblComplianceState</span></span>
 
<span data-ttu-id="f2445-104">tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2445-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="f2445-105">**열**</span><span class="sxs-lookup"><span data-stu-id="f2445-105">**Columns**</span></span>

|<span data-ttu-id="f2445-106">**열**</span><span class="sxs-lookup"><span data-stu-id="f2445-106">**Column**</span></span>|<span data-ttu-id="f2445-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="f2445-107">**Type**</span></span>|<span data-ttu-id="f2445-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="f2445-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f2445-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="f2445-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="f2445-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="f2445-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f2445-111">최근 처리 된 준수 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f2445-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="f2445-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="f2445-112">activeServerID</span></span>  <br/> |<span data-ttu-id="f2445-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="f2445-113">int, not null</span></span>  <br/> |<span data-ttu-id="f2445-114">데이터베이스에 대 한 단독 잠금을 보유 하는 규정 준수 서버의 ID 이거나, 없으면-1입니다.</span><span class="sxs-lookup"><span data-stu-id="f2445-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="f2445-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="f2445-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="f2445-116">datetime2, null이 아님</span><span class="sxs-lookup"><span data-stu-id="f2445-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="f2445-117">잠금 만료 시간 (activeServerID가-1이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="f2445-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

