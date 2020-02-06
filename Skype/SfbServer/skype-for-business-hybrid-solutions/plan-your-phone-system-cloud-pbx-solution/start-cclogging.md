---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: 시작-CcLogging cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 대 한 수신 및 발신 통화 로그를 생성 합니다.
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824172"
---
# <a name="start-cclogging"></a><span data-ttu-id="d22b7-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="d22b7-103">Start-CcLogging</span></span>
 
<span data-ttu-id="d22b7-104">시작-CcLogging cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 대 한 수신 및 발신 통화 로그를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d22b7-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="d22b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d22b7-105">Parameters</span></span>

<span data-ttu-id="d22b7-106">없음</span><span class="sxs-lookup"><span data-stu-id="d22b7-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d22b7-107">예제</span><span class="sxs-lookup"><span data-stu-id="d22b7-107">Examples</span></span>
<span data-ttu-id="d22b7-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d22b7-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d22b7-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="d22b7-109">Example 1</span></span>

<span data-ttu-id="d22b7-110">다음 예에서는 수신 및 발신 통화 로그를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d22b7-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="d22b7-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d22b7-111">Detailed Description</span></span>
<span data-ttu-id="d22b7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d22b7-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d22b7-113">시작-CcLogging cmdlet은 관리자가 클라우드 커넥터 기기에서 수신 및 발신 전화 기록을 시작할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d22b7-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="d22b7-114">기본적으로 로깅이 4 시간 후에 자동으로 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d22b7-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d22b7-115">입력 형식</span><span class="sxs-lookup"><span data-stu-id="d22b7-115">Input Types</span></span>
<span data-ttu-id="d22b7-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d22b7-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d22b7-117">없음.</span><span class="sxs-lookup"><span data-stu-id="d22b7-117">None.</span></span> <span data-ttu-id="d22b7-118">시작-CcLogging cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d22b7-118">The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d22b7-119">반환 형식</span><span class="sxs-lookup"><span data-stu-id="d22b7-119">Return Types</span></span>
<span data-ttu-id="d22b7-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d22b7-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d22b7-121">없음</span><span class="sxs-lookup"><span data-stu-id="d22b7-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d22b7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d22b7-122">See also</span></span>
<span data-ttu-id="d22b7-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d22b7-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d22b7-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="d22b7-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="d22b7-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="d22b7-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

