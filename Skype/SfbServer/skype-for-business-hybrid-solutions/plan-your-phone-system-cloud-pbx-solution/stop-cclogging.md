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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: 이 Stop-CcLogging cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 수신 및 발신 통화 로그 생성을 중지합니다.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824162"
---
# <a name="stop-cclogging"></a><span data-ttu-id="71b37-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="71b37-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="71b37-104">이 Stop-CcLogging cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 수신 및 발신 통화 로그 생성을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="71b37-105">예</span><span class="sxs-lookup"><span data-stu-id="71b37-105">Examples</span></span>
<span data-ttu-id="71b37-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71b37-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="71b37-107">예 1</span><span class="sxs-lookup"><span data-stu-id="71b37-107">Example 1</span></span>

<span data-ttu-id="71b37-108">다음 예에서는 수신 및 발신 통화 로그 생성을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="71b37-109">예 2</span><span class="sxs-lookup"><span data-stu-id="71b37-109">Example 2</span></span>

<span data-ttu-id="71b37-110">다음 예제에서는 수신 및 발신 호출 로그 생성을 중지하고 캐시 파일을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="71b37-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="71b37-111">Detailed Description</span></span>
<span data-ttu-id="71b37-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="71b37-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="71b37-113">이 Stop-CcLogging cmdlet은 어플라이언스에서 수신 및 발신 전화 로깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="71b37-114">기본적으로 로깅은 4시간 후에 자동으로 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="71b37-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71b37-115">Parameters</span></span>
<span data-ttu-id="71b37-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="71b37-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="71b37-117">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="71b37-117">**Parameter**</span></span>|<span data-ttu-id="71b37-118">**필수**</span><span class="sxs-lookup"><span data-stu-id="71b37-118">**Required**</span></span>|<span data-ttu-id="71b37-119">**유형**</span><span class="sxs-lookup"><span data-stu-id="71b37-119">**Type**</span></span>|<span data-ttu-id="71b37-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="71b37-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="71b37-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="71b37-121">RemoveCache</span></span> <br/> | <span data-ttu-id="71b37-122">선택</span><span class="sxs-lookup"><span data-stu-id="71b37-122">Optional</span></span> <br/> | <span data-ttu-id="71b37-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="71b37-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="71b37-124">로깅 캐시 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="71b37-125">입력 형식</span><span class="sxs-lookup"><span data-stu-id="71b37-125">Input Types</span></span>
<span data-ttu-id="71b37-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="71b37-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="71b37-127">없음</span><span class="sxs-lookup"><span data-stu-id="71b37-127">None.</span></span> <span data-ttu-id="71b37-128">이 Stop-CcLogging cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b37-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="71b37-129">반환 형식</span><span class="sxs-lookup"><span data-stu-id="71b37-129">Return Types</span></span>
<span data-ttu-id="71b37-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="71b37-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="71b37-131">없음</span><span class="sxs-lookup"><span data-stu-id="71b37-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71b37-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71b37-132">See also</span></span>
<span data-ttu-id="71b37-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="71b37-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="71b37-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="71b37-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="71b37-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="71b37-135">Start-CcLogging</span></span>](start-cclogging.md)
  

