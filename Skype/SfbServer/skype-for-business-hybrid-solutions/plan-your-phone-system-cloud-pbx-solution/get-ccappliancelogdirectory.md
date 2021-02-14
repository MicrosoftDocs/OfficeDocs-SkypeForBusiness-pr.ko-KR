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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: 이 Get-CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 보여줍니다.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800828"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="4549d-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="4549d-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="4549d-104">이 Get-CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="4549d-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="4549d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4549d-106">Parameters</span></span>

<span data-ttu-id="4549d-107">없음</span><span class="sxs-lookup"><span data-stu-id="4549d-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4549d-108">예</span><span class="sxs-lookup"><span data-stu-id="4549d-108">Examples</span></span>
<span data-ttu-id="4549d-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4549d-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4549d-110">예 1</span><span class="sxs-lookup"><span data-stu-id="4549d-110">Example 1</span></span>

<span data-ttu-id="4549d-111">다음 예에서는 Cloud Connector의 현재 어플라이언스에 대한 로그가 저장되는 현재 폴더를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="4549d-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4549d-112">Detailed Description</span></span>
<span data-ttu-id="4549d-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4549d-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4549d-114">이 Get-CcApplianceLogDirectory cmdlet은 클라우드 커넥터 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="4549d-115">기본 폴더는 C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs입니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="4549d-116">이 cmdlet을 사용하여 디렉터리를 변경할 Set-CcApplianceDirectory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="4549d-117">참고: 어플라이언스 디렉터리를 변경하지 않고 로그 폴더 위치만 변경하는 cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4549d-118">입력 형식</span><span class="sxs-lookup"><span data-stu-id="4549d-118">Input Types</span></span>
<span data-ttu-id="4549d-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4549d-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4549d-120">없음</span><span class="sxs-lookup"><span data-stu-id="4549d-120">None.</span></span> <span data-ttu-id="4549d-121">이 Get-CcApplianceLogDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4549d-122">반환 형식</span><span class="sxs-lookup"><span data-stu-id="4549d-122">Return Types</span></span>
<span data-ttu-id="4549d-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4549d-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4549d-124">이 명령은 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4549d-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4549d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4549d-125">See also</span></span>
<span data-ttu-id="4549d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4549d-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4549d-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4549d-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

