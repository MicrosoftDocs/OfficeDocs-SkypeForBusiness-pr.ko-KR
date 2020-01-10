---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: CcLogging 중지 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 수신 및 발신 통화 로그 생성을 중지 합니다.
ms.openlocfilehash: 4528f7c1458093874f59f347585a736666a9ea08
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003168"
---
# <a name="stop-cclogging"></a><span data-ttu-id="1b410-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="1b410-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="1b410-104">CcLogging 중지 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 수신 및 발신 통화 로그 생성을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="1b410-105">예제</span><span class="sxs-lookup"><span data-stu-id="1b410-105">Examples</span></span>
<span data-ttu-id="1b410-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1b410-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="1b410-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="1b410-107">Example 1</span></span>

<span data-ttu-id="1b410-108">다음 예제에서는 수신 및 발신 통화 로그의 생성을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="1b410-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="1b410-109">Example 2</span></span>

<span data-ttu-id="1b410-110">다음 예제에서는 수신 및 발신 통화 로그 생성을 중지 하 고 캐시 파일을 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="1b410-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="1b410-111">Detailed Description</span></span>
<span data-ttu-id="1b410-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1b410-112"></span></span>

<span data-ttu-id="1b410-113">CcLogging을 중지 하는 cmdlet은 기기의 수신 및 발신 통화 기록을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="1b410-114">기본적으로 로깅이 4 시간 후에 자동으로 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1b410-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b410-115">Parameters</span></span>
<span data-ttu-id="1b410-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1b410-116"></span></span>

|<span data-ttu-id="1b410-117">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="1b410-117">**Parameter**</span></span>|<span data-ttu-id="1b410-118">**필수**</span><span class="sxs-lookup"><span data-stu-id="1b410-118">**Required**</span></span>|<span data-ttu-id="1b410-119">**유형**</span><span class="sxs-lookup"><span data-stu-id="1b410-119">**Type**</span></span>|<span data-ttu-id="1b410-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="1b410-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1b410-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="1b410-121">RemoveCache</span></span> <br/> | <span data-ttu-id="1b410-122">선택</span><span class="sxs-lookup"><span data-stu-id="1b410-122">Optional</span></span> <br/> | <span data-ttu-id="1b410-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1b410-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="1b410-124">로깅 캐시 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1b410-125">입력 형식</span><span class="sxs-lookup"><span data-stu-id="1b410-125">Input Types</span></span>
<span data-ttu-id="1b410-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b410-126"></span></span>

<span data-ttu-id="1b410-127">없음.</span><span class="sxs-lookup"><span data-stu-id="1b410-127">None.</span></span> <span data-ttu-id="1b410-128">' CcLogging 중지 ' cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b410-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1b410-129">반환 형식</span><span class="sxs-lookup"><span data-stu-id="1b410-129">Return Types</span></span>
<span data-ttu-id="1b410-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b410-130"></span></span>

<span data-ttu-id="1b410-131">없음</span><span class="sxs-lookup"><span data-stu-id="1b410-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b410-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b410-132">See also</span></span>
<span data-ttu-id="1b410-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b410-133"></span></span>

[<span data-ttu-id="1b410-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="1b410-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="1b410-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="1b410-135">Start-CcLogging</span></span>](start-cclogging.md)
  

