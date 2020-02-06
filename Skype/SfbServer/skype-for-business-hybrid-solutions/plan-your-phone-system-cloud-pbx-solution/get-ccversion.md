---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 클라우드 커넥터 기기의 버전을 반환 합니다. Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799848"
---
# <a name="get-ccversion"></a><span data-ttu-id="eb77c-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="eb77c-104">Get-CcVersion</span></span>
 
<span data-ttu-id="eb77c-105">클라우드 커넥터 기기의 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="eb77c-106">Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="eb77c-107">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="eb77c-107">Detailed Description</span></span>

<span data-ttu-id="eb77c-108">설치 된 PowerShell 스크립트, 기기 디렉터리의 파일, 호스트 서버에 배포 된 가상 컴퓨터에 따라 클라우드 커넥터 기기의 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="eb77c-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb77c-109">Parameters</span></span>

|<span data-ttu-id="eb77c-110">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="eb77c-110">**Parameter**</span></span>|<span data-ttu-id="eb77c-111">**필수**</span><span class="sxs-lookup"><span data-stu-id="eb77c-111">**Required**</span></span>|<span data-ttu-id="eb77c-112">**유형**</span><span class="sxs-lookup"><span data-stu-id="eb77c-112">**Type**</span></span>|<span data-ttu-id="eb77c-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="eb77c-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb77c-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="eb77c-114">VersionType</span></span>  <br/> |<span data-ttu-id="eb77c-115">선택</span><span class="sxs-lookup"><span data-stu-id="eb77c-115">Optional</span></span>  <br/> |<span data-ttu-id="eb77c-116">System.String</span><span class="sxs-lookup"><span data-stu-id="eb77c-116">System.String</span></span>  <br/> |<span data-ttu-id="eb77c-117">버전 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-117">Type of version.</span></span> <span data-ttu-id="eb77c-118">매개 변수 값은 RunningScripts, RunningBits, BackupBits 또는 All 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="eb77c-119">기본값은 RunningScripts입니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="eb77c-120">예제</span><span class="sxs-lookup"><span data-stu-id="eb77c-120">Examples</span></span>
<span data-ttu-id="eb77c-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="eb77c-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="eb77c-122">예제 1</span><span class="sxs-lookup"><span data-stu-id="eb77c-122">Example 1</span></span>

<span data-ttu-id="eb77c-123">다음 예제에서는 열려 있는 PowerShell 콘솔에서 현재 실행 중인 스크립트의 클라우드 커넥터 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="eb77c-124">예제 2</span><span class="sxs-lookup"><span data-stu-id="eb77c-124">Example 2</span></span>

<span data-ttu-id="eb77c-125">다음 예제에서는 가상 컴퓨터에 배포 된 현재 실행 중인 이진 파일의 클라우드 커넥터 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="eb77c-126">Hyper-v 관리자의 실행 중인 가상 컴퓨터 이름에서 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="eb77c-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="eb77c-127">Input Types</span></span>
<span data-ttu-id="eb77c-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="eb77c-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="eb77c-129">없음.</span><span class="sxs-lookup"><span data-stu-id="eb77c-129">None.</span></span> <span data-ttu-id="eb77c-130">Get-CcVersion cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb77c-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="eb77c-131">반환 형식</span><span class="sxs-lookup"><span data-stu-id="eb77c-131">Return Types</span></span>
<span data-ttu-id="eb77c-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="eb77c-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="eb77c-133">없음.</span><span class="sxs-lookup"><span data-stu-id="eb77c-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb77c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb77c-134">See also</span></span>
<span data-ttu-id="eb77c-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="eb77c-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="eb77c-136">없음.</span><span class="sxs-lookup"><span data-stu-id="eb77c-136">None.</span></span>
  

