---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809728"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="dbe81-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="dbe81-103">tblComplianceState</span></span>
 
<span data-ttu-id="dbe81-104">tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe81-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="dbe81-105">**열**</span><span class="sxs-lookup"><span data-stu-id="dbe81-105">**Columns**</span></span>

|<span data-ttu-id="dbe81-106">**열**</span><span class="sxs-lookup"><span data-stu-id="dbe81-106">**Column**</span></span>|<span data-ttu-id="dbe81-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="dbe81-107">**Type**</span></span>|<span data-ttu-id="dbe81-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="dbe81-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dbe81-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="dbe81-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="dbe81-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="dbe81-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="dbe81-111">처리된 최신 준수 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe81-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="dbe81-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="dbe81-112">activeServerID</span></span>  <br/> |<span data-ttu-id="dbe81-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="dbe81-113">int, not null</span></span>  <br/> |<span data-ttu-id="dbe81-114">데이터베이스에 대한 배타적 잠금을 보유하는 준수 서버의 ID 또는 없음인 경우 -1입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe81-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="dbe81-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="dbe81-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="dbe81-116">datetime2, null이 아닌</span><span class="sxs-lookup"><span data-stu-id="dbe81-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="dbe81-117">잠금 만료 시간(activeServerID가 -1이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="dbe81-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

