---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: 이 Set-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 작업 디렉터리를 설정합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824224"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="d8763-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="d8763-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="d8763-105">이 Set-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 작업 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8763-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="d8763-106">모든 배포 파일은 이 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8763-106">All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="d8763-107">예</span><span class="sxs-lookup"><span data-stu-id="d8763-107">Examples</span></span>
<span data-ttu-id="d8763-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d8763-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d8763-109">예 1</span><span class="sxs-lookup"><span data-stu-id="d8763-109">Example 1</span></span>

<span data-ttu-id="d8763-110">다음 예에서는 호스트 서버의 작업 디렉터리를 c:\cloudconnector\applianceroot로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8763-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="d8763-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8763-111">Parameters</span></span>
<span data-ttu-id="d8763-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d8763-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="d8763-113">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="d8763-113">**Parameter**</span></span>|<span data-ttu-id="d8763-114">**필수**</span><span class="sxs-lookup"><span data-stu-id="d8763-114">**Required**</span></span>|<span data-ttu-id="d8763-115">**유형**</span><span class="sxs-lookup"><span data-stu-id="d8763-115">**Type**</span></span>|<span data-ttu-id="d8763-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="d8763-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d8763-117">경로</span><span class="sxs-lookup"><span data-stu-id="d8763-117">Path</span></span> <br/> | <span data-ttu-id="d8763-118">필수</span><span class="sxs-lookup"><span data-stu-id="d8763-118">Required</span></span> <br/> |<span data-ttu-id="d8763-119">System.String</span><span class="sxs-lookup"><span data-stu-id="d8763-119">System.String</span></span>  <br/> | <span data-ttu-id="d8763-120">모든 배포 파일이 저장되는 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8763-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d8763-121">입력 형식</span><span class="sxs-lookup"><span data-stu-id="d8763-121">Input Types</span></span>
<span data-ttu-id="d8763-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8763-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d8763-123">없음</span><span class="sxs-lookup"><span data-stu-id="d8763-123">None.</span></span> <span data-ttu-id="d8763-124">이 Set-CcApplianceDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8763-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d8763-125">반환 형식</span><span class="sxs-lookup"><span data-stu-id="d8763-125">Return Types</span></span>
<span data-ttu-id="d8763-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8763-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d8763-127">없음</span><span class="sxs-lookup"><span data-stu-id="d8763-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d8763-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8763-128">See also</span></span>
<span data-ttu-id="d8763-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8763-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d8763-130">없음</span><span class="sxs-lookup"><span data-stu-id="d8763-130">None</span></span>
  

