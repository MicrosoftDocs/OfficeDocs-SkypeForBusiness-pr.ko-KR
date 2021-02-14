---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 이 Export-CcRootCertificate cmdlet은 루트 CA 인증서를 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버의 로컬 파일로 내보낼 수 있습니다.
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800918"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="74771-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="74771-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="74771-104">이 Export-CcRootCertificate cmdlet은 루트 CA 인증서를 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버의 로컬 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74771-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="74771-105">예</span><span class="sxs-lookup"><span data-stu-id="74771-105">Examples</span></span>
<span data-ttu-id="74771-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="74771-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="74771-107">예 1</span><span class="sxs-lookup"><span data-stu-id="74771-107">Example 1</span></span>

<span data-ttu-id="74771-108">다음은 Path 매개 변수를 파일 경로가 아니라 디렉터리 경로로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="74771-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="74771-109">c:\test\CCERootCertificates.p7b 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="74771-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="74771-110">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="74771-110">Detailed Description</span></span>
<span data-ttu-id="74771-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="74771-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="74771-112">이 Export-CcRootCertificate cmdlet을 사용하면 루트 및 중간 인증서를 파일 경로에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74771-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="74771-113">이는 재해 복구 시나리오의 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74771-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="74771-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74771-114">Parameters</span></span>
<span data-ttu-id="74771-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="74771-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="74771-116">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="74771-116">**Parameter**</span></span>|<span data-ttu-id="74771-117">**필수**</span><span class="sxs-lookup"><span data-stu-id="74771-117">**Required**</span></span>|<span data-ttu-id="74771-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="74771-118">**Type**</span></span>|<span data-ttu-id="74771-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="74771-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="74771-120">경로</span><span class="sxs-lookup"><span data-stu-id="74771-120">Path</span></span>  <br/> |<span data-ttu-id="74771-121">필수</span><span class="sxs-lookup"><span data-stu-id="74771-121">Required</span></span>  <br/> |<span data-ttu-id="74771-122">System.String</span><span class="sxs-lookup"><span data-stu-id="74771-122">System.String</span></span>  <br/> |<span data-ttu-id="74771-123">인증서를 저장할 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="74771-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="74771-124">입력 형식</span><span class="sxs-lookup"><span data-stu-id="74771-124">Input Types</span></span>
<span data-ttu-id="74771-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="74771-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="74771-126">없음</span><span class="sxs-lookup"><span data-stu-id="74771-126">None.</span></span> <span data-ttu-id="74771-127">이 Export-CcRootCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74771-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="74771-128">반환 형식</span><span class="sxs-lookup"><span data-stu-id="74771-128">Return Types</span></span>
<span data-ttu-id="74771-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="74771-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="74771-130">없음</span><span class="sxs-lookup"><span data-stu-id="74771-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74771-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74771-131">See also</span></span>
<span data-ttu-id="74771-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="74771-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="74771-133">없음</span><span class="sxs-lookup"><span data-stu-id="74771-133">None</span></span>
  

