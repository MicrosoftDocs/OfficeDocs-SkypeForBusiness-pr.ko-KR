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
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: 시작-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 비트 및 msi 파일을 동기적으로 다운로드 합니다.
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003188"
---
# <a name="start-ccdownload"></a><span data-ttu-id="da5cd-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="da5cd-103">Start-CcDownload</span></span>
 
<span data-ttu-id="da5cd-104">시작-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="da5cd-105">클라우드 커넥터 버전 2.0 이상을 사용 하 여 DownloadBitsOnly 매개 변수만 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="da5cd-106">예제</span><span class="sxs-lookup"><span data-stu-id="da5cd-106">Examples</span></span>
<span data-ttu-id="da5cd-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="da5cd-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="da5cd-108">예제 1</span><span class="sxs-lookup"><span data-stu-id="da5cd-108">Example 1</span></span>

<span data-ttu-id="da5cd-109">다음 예제에서는 클라우드 커넥터 공용 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="da5cd-110">예제 2</span><span class="sxs-lookup"><span data-stu-id="da5cd-110">Example 2</span></span>

<span data-ttu-id="da5cd-111">다음 예에서는 사설 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="da5cd-112">예제 3</span><span class="sxs-lookup"><span data-stu-id="da5cd-112">Example 3</span></span>

<span data-ttu-id="da5cd-113">세 번째 예제는 사설 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="da5cd-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="da5cd-114">Detailed Description</span></span>
<span data-ttu-id="da5cd-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="da5cd-115"></span></span>

<span data-ttu-id="da5cd-116">다운로드 사이트에서 사용할 수 있는 새 버전이 있는 경우 시작 사이트에서 msi 파일을 다운로드 하 여 설치한 다음 클라우드 커넥터 비트를 동기적으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="da5cd-117">새 버전의 msi 파일이 없는 경우 시작-CcDownload는 클라우드 커넥터 비트만 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="da5cd-118">클라우드 커넥터 비트가 이미 다운로드 된 경우 시작-CcDownload 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="da5cd-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da5cd-119">Parameters</span></span>
<span data-ttu-id="da5cd-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="da5cd-120"></span></span>

|<span data-ttu-id="da5cd-121">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="da5cd-121">**Parameter**</span></span>|<span data-ttu-id="da5cd-122">**필수**</span><span class="sxs-lookup"><span data-stu-id="da5cd-122">**Required**</span></span>|<span data-ttu-id="da5cd-123">**유형**</span><span class="sxs-lookup"><span data-stu-id="da5cd-123">**Type**</span></span>|<span data-ttu-id="da5cd-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="da5cd-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da5cd-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="da5cd-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="da5cd-126">선택</span><span class="sxs-lookup"><span data-stu-id="da5cd-126">Optional</span></span> <br/> |<span data-ttu-id="da5cd-127">System.String</span><span class="sxs-lookup"><span data-stu-id="da5cd-127">System.String</span></span>  <br/> | <span data-ttu-id="da5cd-128">개인 다운로드 사이트에서 특정 버전의 클라우드 커넥터에 대 한 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="da5cd-129">이 매개 변수를 사용할 때는 다운로드 하는 클라우드 커넥터의 버전을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="da5cd-130">Download비트 Sonly</span><span class="sxs-lookup"><span data-stu-id="da5cd-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="da5cd-131">선택</span><span class="sxs-lookup"><span data-stu-id="da5cd-131">Optional</span></span>  <br/> |<span data-ttu-id="da5cd-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="da5cd-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="da5cd-133">다운로드 사이트에서 MSI를 다운로드 하 고 설치 하는 단계를 건너뛰고 클라우드 커넥터 비트만 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="da5cd-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="da5cd-134">입력 형식</span><span class="sxs-lookup"><span data-stu-id="da5cd-134">Input Types</span></span>
<span data-ttu-id="da5cd-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="da5cd-135"></span></span>

<span data-ttu-id="da5cd-136">없음.</span><span class="sxs-lookup"><span data-stu-id="da5cd-136">None.</span></span> <span data-ttu-id="da5cd-137">시작-CcDownload cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da5cd-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="da5cd-138">반환 형식</span><span class="sxs-lookup"><span data-stu-id="da5cd-138">Return Types</span></span>
<span data-ttu-id="da5cd-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="da5cd-139"></span></span>

<span data-ttu-id="da5cd-140">없음</span><span class="sxs-lookup"><span data-stu-id="da5cd-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da5cd-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da5cd-141">See also</span></span>
<span data-ttu-id="da5cd-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="da5cd-142"></span></span>

<span data-ttu-id="da5cd-143">없음</span><span class="sxs-lookup"><span data-stu-id="da5cd-143">None</span></span>
  

