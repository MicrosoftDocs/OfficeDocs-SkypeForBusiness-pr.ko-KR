---
title: 다운로드-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 클라우드 커넥터 기기의 버전을 반환 합니다. Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190749"
---
# <a name="get-ccversion"></a><span data-ttu-id="46a4d-104">다운로드-CcVersion</span><span class="sxs-lookup"><span data-stu-id="46a4d-104">Get-CcVersion</span></span>
 
<span data-ttu-id="46a4d-105">클라우드 커넥터 기기의 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="46a4d-106">Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="46a4d-107">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="46a4d-107">Detailed Description</span></span>

<span data-ttu-id="46a4d-108">설치 된 PowerShell 스크립트, 기기 디렉터리의 파일, 호스트 서버에 배포 된 가상 컴퓨터에 따라 클라우드 커넥터 기기의 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="46a4d-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46a4d-109">Parameters</span></span>

|<span data-ttu-id="46a4d-110">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="46a4d-110">**Parameter**</span></span>|<span data-ttu-id="46a4d-111">**필수**</span><span class="sxs-lookup"><span data-stu-id="46a4d-111">**Required**</span></span>|<span data-ttu-id="46a4d-112">**유형**</span><span class="sxs-lookup"><span data-stu-id="46a4d-112">**Type**</span></span>|<span data-ttu-id="46a4d-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="46a4d-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46a4d-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="46a4d-114">VersionType</span></span>  <br/> |<span data-ttu-id="46a4d-115">선택</span><span class="sxs-lookup"><span data-stu-id="46a4d-115">Optional</span></span>  <br/> |<span data-ttu-id="46a4d-116">System.String</span><span class="sxs-lookup"><span data-stu-id="46a4d-116">System.String</span></span>  <br/> |<span data-ttu-id="46a4d-117">버전 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-117">Type of version.</span></span> <span data-ttu-id="46a4d-118">매개 변수 값은 RunningScripts, RunningBits, BackupBits 또는 All 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="46a4d-119">기본값은 RunningScripts입니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="46a4d-120">예제</span><span class="sxs-lookup"><span data-stu-id="46a4d-120">Examples</span></span>
<span data-ttu-id="46a4d-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46a4d-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="46a4d-122">예제 1</span><span class="sxs-lookup"><span data-stu-id="46a4d-122">Example 1</span></span>

<span data-ttu-id="46a4d-123">다음 예제에서는 열려 있는 PowerShell 콘솔에서 현재 실행 중인 스크립트의 클라우드 커넥터 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="46a4d-124">예제 2</span><span class="sxs-lookup"><span data-stu-id="46a4d-124">Example 2</span></span>

<span data-ttu-id="46a4d-125">다음 예제에서는 가상 컴퓨터에 배포 된 현재 실행 중인 이진 파일의 클라우드 커넥터 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="46a4d-126">Hyper-v 관리자의 실행 중인 가상 컴퓨터 이름에서 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="46a4d-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="46a4d-127">Input Types</span></span>
<span data-ttu-id="46a4d-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46a4d-128"></span></span>

<span data-ttu-id="46a4d-129">없음.</span><span class="sxs-lookup"><span data-stu-id="46a4d-129">None.</span></span> <span data-ttu-id="46a4d-130">Get-CcVersion cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46a4d-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="46a4d-131">반환 형식</span><span class="sxs-lookup"><span data-stu-id="46a4d-131">Return Types</span></span>
<span data-ttu-id="46a4d-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46a4d-132"></span></span>

<span data-ttu-id="46a4d-133">없음.</span><span class="sxs-lookup"><span data-stu-id="46a4d-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46a4d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46a4d-134">See also</span></span>
<span data-ttu-id="46a4d-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46a4d-135"></span></span>

<span data-ttu-id="46a4d-136">없음.</span><span class="sxs-lookup"><span data-stu-id="46a4d-136">None.</span></span>
  

