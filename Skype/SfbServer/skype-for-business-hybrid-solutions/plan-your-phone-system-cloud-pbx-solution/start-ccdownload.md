---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: 이 Start-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 비트 및 msi 파일을 동기적으로 다운로드합니다.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824182"
---
# <a name="start-ccdownload"></a><span data-ttu-id="0e591-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="0e591-103">Start-CcDownload</span></span>
 
<span data-ttu-id="0e591-104">이 Start-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 비트 및 msi 파일을 동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="0e591-105">클라우드 커넥터 버전 2.0 이상에서는 DownloadBitsOnly 매개 변수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0e591-106">예</span><span class="sxs-lookup"><span data-stu-id="0e591-106">Examples</span></span>
<span data-ttu-id="0e591-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e591-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0e591-108">예 1</span><span class="sxs-lookup"><span data-stu-id="0e591-108">Example 1</span></span>

<span data-ttu-id="0e591-109">다음 예제에서는 Cloud Connector 공용 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="0e591-110">예 2</span><span class="sxs-lookup"><span data-stu-id="0e591-110">Example 2</span></span>

<span data-ttu-id="0e591-111">다음 예제에서는 개인 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="0e591-112">예 3</span><span class="sxs-lookup"><span data-stu-id="0e591-112">Example 3</span></span>

<span data-ttu-id="0e591-113">세 번째 예제에서는 클라우드 커넥터 비트 및 msi 파일을 개인 다운로드 사이트에서 동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="0e591-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="0e591-114">Detailed Description</span></span>
<span data-ttu-id="0e591-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e591-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0e591-116">다운로드 사이트에 사용할 수 있는 새 버전이 있는 경우 Start-CcDownload 사이트에서 msi 파일을 다운로드하여 설치한 다음 클라우드 커넥터 비트를 동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="0e591-117">새 버전의 msi 파일이 없는 경우 Start-CcDownload 클라우드 커넥터 비트만 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="0e591-118">클라우드 커넥터 비트가 이미 다운로드된 경우 Start-CcDownload 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0e591-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0e591-119">Parameters</span></span>
<span data-ttu-id="0e591-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e591-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0e591-121">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="0e591-121">**Parameter**</span></span>|<span data-ttu-id="0e591-122">**필수**</span><span class="sxs-lookup"><span data-stu-id="0e591-122">**Required**</span></span>|<span data-ttu-id="0e591-123">**유형**</span><span class="sxs-lookup"><span data-stu-id="0e591-123">**Type**</span></span>|<span data-ttu-id="0e591-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="0e591-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e591-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="0e591-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="0e591-126">옵션</span><span class="sxs-lookup"><span data-stu-id="0e591-126">Optional</span></span> <br/> |<span data-ttu-id="0e591-127">System.String</span><span class="sxs-lookup"><span data-stu-id="0e591-127">System.String</span></span>  <br/> | <span data-ttu-id="0e591-128">개인 다운로드 사이트에 있는 특정 버전의 클라우드 커넥터의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="0e591-129">이 매개 변수는 주의하여 사용하세요. 다운로드하는 클라우드 커넥터 버전을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="0e591-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="0e591-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="0e591-131">선택</span><span class="sxs-lookup"><span data-stu-id="0e591-131">Optional</span></span>  <br/> |<span data-ttu-id="0e591-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0e591-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0e591-133">다운로드 사이트에서 MSI를 다운로드하고 설치하는 단계를 건너뛰고 클라우드 커넥터 비트만 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0e591-134">입력 형식</span><span class="sxs-lookup"><span data-stu-id="0e591-134">Input Types</span></span>
<span data-ttu-id="0e591-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e591-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0e591-136">없음</span><span class="sxs-lookup"><span data-stu-id="0e591-136">None.</span></span> <span data-ttu-id="0e591-137">이 Start-CcDownload cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e591-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0e591-138">반환 형식</span><span class="sxs-lookup"><span data-stu-id="0e591-138">Return Types</span></span>
<span data-ttu-id="0e591-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e591-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0e591-140">없음</span><span class="sxs-lookup"><span data-stu-id="0e591-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e591-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e591-141">See also</span></span>
<span data-ttu-id="0e591-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e591-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0e591-143">없음</span><span class="sxs-lookup"><span data-stu-id="0e591-143">None</span></span>
  

