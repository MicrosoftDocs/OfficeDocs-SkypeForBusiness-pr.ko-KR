---
title: 시작-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: 시작-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 비트 및 msi 파일을 동기적으로 다운로드 합니다.
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190623"
---
# <a name="start-ccdownload"></a><span data-ttu-id="710b9-103">시작-CcDownload</span><span class="sxs-lookup"><span data-stu-id="710b9-103">Start-CcDownload</span></span>
 
<span data-ttu-id="710b9-104">시작-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="710b9-105">클라우드 커넥터 버전 2.0 이상을 사용 하 여 DownloadBitsOnly 매개 변수만 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="710b9-106">예제</span><span class="sxs-lookup"><span data-stu-id="710b9-106">Examples</span></span>
<span data-ttu-id="710b9-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="710b9-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="710b9-108">예제 1</span><span class="sxs-lookup"><span data-stu-id="710b9-108">Example 1</span></span>

<span data-ttu-id="710b9-109">다음 예제에서는 클라우드 커넥터 공용 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="710b9-110">예제 2</span><span class="sxs-lookup"><span data-stu-id="710b9-110">Example 2</span></span>

<span data-ttu-id="710b9-111">다음 예에서는 사설 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="710b9-112">예제 3</span><span class="sxs-lookup"><span data-stu-id="710b9-112">Example 3</span></span>

<span data-ttu-id="710b9-113">세 번째 예제는 사설 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="710b9-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="710b9-114">Detailed Description</span></span>
<span data-ttu-id="710b9-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="710b9-115"></span></span>

<span data-ttu-id="710b9-116">다운로드 사이트에서 사용할 수 있는 새 버전이 있는 경우 시작 사이트에서 msi 파일을 다운로드 하 여 설치한 다음 클라우드 커넥터 비트를 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="710b9-117">새 버전의 msi 파일이 없는 경우 시작-CcDownload는 클라우드 커넥터 비트만 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="710b9-118">클라우드 커넥터 비트가 이미 다운로드 된 경우 시작-CcDownload 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="710b9-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="710b9-119">Parameters</span></span>
<span data-ttu-id="710b9-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="710b9-120"></span></span>

|<span data-ttu-id="710b9-121">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="710b9-121">**Parameter**</span></span>|<span data-ttu-id="710b9-122">**필수**</span><span class="sxs-lookup"><span data-stu-id="710b9-122">**Required**</span></span>|<span data-ttu-id="710b9-123">**유형**</span><span class="sxs-lookup"><span data-stu-id="710b9-123">**Type**</span></span>|<span data-ttu-id="710b9-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="710b9-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="710b9-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="710b9-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="710b9-126">선택</span><span class="sxs-lookup"><span data-stu-id="710b9-126">Optional</span></span> <br/> |<span data-ttu-id="710b9-127">System.String</span><span class="sxs-lookup"><span data-stu-id="710b9-127">System.String</span></span>  <br/> | <span data-ttu-id="710b9-128">개인 다운로드 사이트에서 특정 버전의 클라우드 커넥터에 대 한 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="710b9-129">이 매개 변수를 사용할 때는 다운로드 하는 클라우드 커넥터의 버전을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="710b9-130">Download비트 Sonly</span><span class="sxs-lookup"><span data-stu-id="710b9-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="710b9-131">선택</span><span class="sxs-lookup"><span data-stu-id="710b9-131">Optional</span></span>  <br/> |<span data-ttu-id="710b9-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="710b9-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="710b9-133">다운로드 사이트에서 MSI를 다운로드 하 고 설치 하는 단계를 건너뛰고 클라우드 커넥터 비트만 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="710b9-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="710b9-134">입력 형식</span><span class="sxs-lookup"><span data-stu-id="710b9-134">Input Types</span></span>
<span data-ttu-id="710b9-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="710b9-135"></span></span>

<span data-ttu-id="710b9-136">없음.</span><span class="sxs-lookup"><span data-stu-id="710b9-136">None.</span></span> <span data-ttu-id="710b9-137">시작-CcDownload cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="710b9-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="710b9-138">반환 형식</span><span class="sxs-lookup"><span data-stu-id="710b9-138">Return Types</span></span>
<span data-ttu-id="710b9-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="710b9-139"></span></span>

<span data-ttu-id="710b9-140">없음</span><span class="sxs-lookup"><span data-stu-id="710b9-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="710b9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="710b9-141">See also</span></span>
<span data-ttu-id="710b9-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="710b9-142"></span></span>

<span data-ttu-id="710b9-143">없음</span><span class="sxs-lookup"><span data-stu-id="710b9-143">None</span></span>
  

