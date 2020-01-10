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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 작업 디렉터리를 설정 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.
ms.openlocfilehash: 1dfc85a08709fd550b91dbecdb5d4186f265ca67
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003228"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="acf7e-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="acf7e-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="acf7e-105">CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 작업 디렉터리를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf7e-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="acf7e-106">모든 배포 파일은이 디렉터리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf7e-106">All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="acf7e-107">예제</span><span class="sxs-lookup"><span data-stu-id="acf7e-107">Examples</span></span>
<span data-ttu-id="acf7e-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="acf7e-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="acf7e-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="acf7e-109">Example 1</span></span>

<span data-ttu-id="acf7e-110">다음 예에서는 호스트 서버의 작업 디렉터리를 c:\cloudconnector\applianceroot로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf7e-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="acf7e-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acf7e-111">Parameters</span></span>
<span data-ttu-id="acf7e-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="acf7e-112"></span></span>

|<span data-ttu-id="acf7e-113">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="acf7e-113">**Parameter**</span></span>|<span data-ttu-id="acf7e-114">**필수**</span><span class="sxs-lookup"><span data-stu-id="acf7e-114">**Required**</span></span>|<span data-ttu-id="acf7e-115">**유형**</span><span class="sxs-lookup"><span data-stu-id="acf7e-115">**Type**</span></span>|<span data-ttu-id="acf7e-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="acf7e-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="acf7e-117">패스가</span><span class="sxs-lookup"><span data-stu-id="acf7e-117">Path</span></span> <br/> | <span data-ttu-id="acf7e-118">필수</span><span class="sxs-lookup"><span data-stu-id="acf7e-118">Required</span></span> <br/> |<span data-ttu-id="acf7e-119">System.String</span><span class="sxs-lookup"><span data-stu-id="acf7e-119">System.String</span></span>  <br/> | <span data-ttu-id="acf7e-120">모든 배포 파일이 저장 되는 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf7e-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="acf7e-121">입력 형식</span><span class="sxs-lookup"><span data-stu-id="acf7e-121">Input Types</span></span>
<span data-ttu-id="acf7e-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acf7e-122"></span></span>

<span data-ttu-id="acf7e-123">없음.</span><span class="sxs-lookup"><span data-stu-id="acf7e-123">None.</span></span> <span data-ttu-id="acf7e-124">CcApplianceDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf7e-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="acf7e-125">반환 형식</span><span class="sxs-lookup"><span data-stu-id="acf7e-125">Return Types</span></span>
<span data-ttu-id="acf7e-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acf7e-126"></span></span>

<span data-ttu-id="acf7e-127">없음</span><span class="sxs-lookup"><span data-stu-id="acf7e-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="acf7e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acf7e-128">See also</span></span>
<span data-ttu-id="acf7e-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acf7e-129"></span></span>

<span data-ttu-id="acf7e-130">없음</span><span class="sxs-lookup"><span data-stu-id="acf7e-130">None</span></span>
  

