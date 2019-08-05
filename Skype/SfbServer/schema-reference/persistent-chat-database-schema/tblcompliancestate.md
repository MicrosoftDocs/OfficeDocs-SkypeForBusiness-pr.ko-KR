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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196638"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="d666e-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="d666e-103">tblComplianceState</span></span>
 
<span data-ttu-id="d666e-104">tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d666e-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="d666e-105">**열**</span><span class="sxs-lookup"><span data-stu-id="d666e-105">**Columns**</span></span>

|<span data-ttu-id="d666e-106">**열**</span><span class="sxs-lookup"><span data-stu-id="d666e-106">**Column**</span></span>|<span data-ttu-id="d666e-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="d666e-107">**Type**</span></span>|<span data-ttu-id="d666e-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="d666e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d666e-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="d666e-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="d666e-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d666e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="d666e-111">최근 처리 된 준수 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d666e-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="d666e-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="d666e-112">activeServerID</span></span>  <br/> |<span data-ttu-id="d666e-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="d666e-113">int, not null</span></span>  <br/> |<span data-ttu-id="d666e-114">데이터베이스에 대 한 단독 잠금을 보유 하는 규정 준수 서버의 ID 이거나, 없으면-1입니다.</span><span class="sxs-lookup"><span data-stu-id="d666e-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="d666e-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="d666e-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="d666e-116">datetime2, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d666e-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="d666e-117">잠금 만료 시간 (activeServerID가-1이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="d666e-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

