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
description: 이 Start-CcLogging cmdlet은 비즈니스용 Skype Cloud Connector Edition 어플라이언스에 대한 수신 및 발신 통화 로그를 생성합니다.
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824172"
---
# <a name="start-cclogging"></a><span data-ttu-id="87120-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="87120-103">Start-CcLogging</span></span>
 
<span data-ttu-id="87120-104">이 Start-CcLogging cmdlet은 비즈니스용 Skype Cloud Connector Edition 어플라이언스에 대한 수신 및 발신 통화 로그를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="87120-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="87120-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87120-105">Parameters</span></span>

<span data-ttu-id="87120-106">없음</span><span class="sxs-lookup"><span data-stu-id="87120-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="87120-107">예</span><span class="sxs-lookup"><span data-stu-id="87120-107">Examples</span></span>
<span data-ttu-id="87120-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="87120-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="87120-109">예 1</span><span class="sxs-lookup"><span data-stu-id="87120-109">Example 1</span></span>

<span data-ttu-id="87120-110">다음 예에서는 수신 및 발신 통화 로그를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="87120-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="87120-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="87120-111">Detailed Description</span></span>
<span data-ttu-id="87120-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="87120-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="87120-113">이 Start-CcLogging cmdlet을 사용하면 관리자가 Cloud Connector 어플라이언스에서 수신 및 발신 전화 로깅을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87120-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="87120-114">기본적으로 로깅은 4시간 후에 자동으로 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="87120-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="87120-115">입력 형식</span><span class="sxs-lookup"><span data-stu-id="87120-115">Input Types</span></span>
<span data-ttu-id="87120-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="87120-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="87120-117">없음</span><span class="sxs-lookup"><span data-stu-id="87120-117">None.</span></span> <span data-ttu-id="87120-118">이 Start-CcLogging cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87120-118">The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="87120-119">반환 형식</span><span class="sxs-lookup"><span data-stu-id="87120-119">Return Types</span></span>
<span data-ttu-id="87120-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="87120-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="87120-121">없음</span><span class="sxs-lookup"><span data-stu-id="87120-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="87120-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87120-122">See also</span></span>
<span data-ttu-id="87120-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="87120-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="87120-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="87120-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="87120-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="87120-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

