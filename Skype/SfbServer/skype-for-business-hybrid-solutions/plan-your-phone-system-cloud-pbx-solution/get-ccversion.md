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
description: Cloud Connector 어플라이언스 버전을 반환합니다. Get-CCVersion 클라우드 커넥터의 호스트 컴퓨터만 사용할 수 있습니다.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799848"
---
# <a name="get-ccversion"></a><span data-ttu-id="07b58-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="07b58-104">Get-CcVersion</span></span>
 
<span data-ttu-id="07b58-105">Cloud Connector 어플라이언스 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="07b58-106">Get-CCVersion 클라우드 커넥터의 호스트 컴퓨터만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="07b58-107">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="07b58-107">Detailed Description</span></span>

<span data-ttu-id="07b58-108">설치된 PowerShell 스크립트, Appliance 디렉터리의 파일 및 호스트 서버에 배포된 가상 컴퓨터를 기반으로 하는 Cloud Connector 어플라이언스 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="07b58-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07b58-109">Parameters</span></span>

|<span data-ttu-id="07b58-110">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="07b58-110">**Parameter**</span></span>|<span data-ttu-id="07b58-111">**필수**</span><span class="sxs-lookup"><span data-stu-id="07b58-111">**Required**</span></span>|<span data-ttu-id="07b58-112">**유형**</span><span class="sxs-lookup"><span data-stu-id="07b58-112">**Type**</span></span>|<span data-ttu-id="07b58-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="07b58-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07b58-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="07b58-114">VersionType</span></span>  <br/> |<span data-ttu-id="07b58-115">옵션</span><span class="sxs-lookup"><span data-stu-id="07b58-115">Optional</span></span>  <br/> |<span data-ttu-id="07b58-116">System.String</span><span class="sxs-lookup"><span data-stu-id="07b58-116">System.String</span></span>  <br/> |<span data-ttu-id="07b58-117">버전 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-117">Type of version.</span></span> <span data-ttu-id="07b58-118">매개 변수 값은 RunningScripts, RunningBits, BackupBits 또는 All일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="07b58-119">기본값은 RunningScripts입니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="07b58-120">예</span><span class="sxs-lookup"><span data-stu-id="07b58-120">Examples</span></span>
<span data-ttu-id="07b58-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07b58-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="07b58-122">예 1</span><span class="sxs-lookup"><span data-stu-id="07b58-122">Example 1</span></span>

<span data-ttu-id="07b58-123">다음 예에서는 열려 있는 PowerShell 콘솔에서 현재 실행 중인 스크립트의 클라우드 커넥터 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="07b58-124">예 2</span><span class="sxs-lookup"><span data-stu-id="07b58-124">Example 2</span></span>

<span data-ttu-id="07b58-125">다음 예에서는 가상 컴퓨터로 배포된 현재 실행 중인 이진의 클라우드 커넥터 버전을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="07b58-126">Hyper-v 관리자에서 실행 중인 가상 컴퓨터 이름에서 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="07b58-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="07b58-127">Input Types</span></span>
<span data-ttu-id="07b58-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07b58-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="07b58-129">없음</span><span class="sxs-lookup"><span data-stu-id="07b58-129">None.</span></span> <span data-ttu-id="07b58-130">이 Get-CcVersion cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07b58-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="07b58-131">반환 형식</span><span class="sxs-lookup"><span data-stu-id="07b58-131">Return Types</span></span>
<span data-ttu-id="07b58-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07b58-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="07b58-133">없음</span><span class="sxs-lookup"><span data-stu-id="07b58-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07b58-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07b58-134">See also</span></span>
<span data-ttu-id="07b58-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07b58-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="07b58-136">없음</span><span class="sxs-lookup"><span data-stu-id="07b58-136">None.</span></span>
  

