---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 대 한 로그가 저장 되어 있는 현재 디렉터리를 표시 합니다.
ms.openlocfilehash: 675e89f49c7c1384edc7cfa5944c8aee3f236c79
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190794"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="b627d-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="b627d-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="b627d-104">CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 대 한 로그가 저장 되어 있는 현재 디렉터리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="b627d-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="b627d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b627d-106">Parameters</span></span>

<span data-ttu-id="b627d-107">없음</span><span class="sxs-lookup"><span data-stu-id="b627d-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b627d-108">예제</span><span class="sxs-lookup"><span data-stu-id="b627d-108">Examples</span></span>
<span data-ttu-id="b627d-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b627d-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="b627d-110">예제 1</span><span class="sxs-lookup"><span data-stu-id="b627d-110">Example 1</span></span>

<span data-ttu-id="b627d-111">다음 예에서는 클라우드 커넥터의 현재 기기에 대 한 로그가 저장 되어 있는 현재 폴더를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="b627d-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b627d-112">Detailed Description</span></span>
<span data-ttu-id="b627d-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b627d-113"></span></span>

<span data-ttu-id="b627d-114">CcApplianceLogDirectory cmdlet은 클라우드 커넥터 기기에 대 한 로그가 저장 되는 현재 디렉터리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="b627d-115">기본 폴더는 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="b627d-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="b627d-116">Set-CcApplianceDirectory cmdlet을 사용 하 여 디렉터리를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="b627d-117">참고: 기기 디렉터리를 변경 하지 않고 로그 폴더 위치만 변경 하는 cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b627d-118">입력 형식</span><span class="sxs-lookup"><span data-stu-id="b627d-118">Input Types</span></span>
<span data-ttu-id="b627d-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b627d-119"></span></span>

<span data-ttu-id="b627d-120">없음.</span><span class="sxs-lookup"><span data-stu-id="b627d-120">None.</span></span> <span data-ttu-id="b627d-121">Get-CcApplianceLogDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b627d-122">반환 형식</span><span class="sxs-lookup"><span data-stu-id="b627d-122">Return Types</span></span>
<span data-ttu-id="b627d-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b627d-123"></span></span>

<span data-ttu-id="b627d-124">이 명령은 파일 경로를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b627d-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b627d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b627d-125">See also</span></span>
<span data-ttu-id="b627d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b627d-126"></span></span>

[<span data-ttu-id="b627d-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b627d-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

