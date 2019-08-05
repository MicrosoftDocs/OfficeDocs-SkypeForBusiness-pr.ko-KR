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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 루트 CA 인증서를 로컬 파일로 내보냅니다.
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190797"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="6e9d7-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="6e9d7-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="6e9d7-104">Export-CcRootCertificate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 루트 CA 인증서를 로컬 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="6e9d7-105">예제</span><span class="sxs-lookup"><span data-stu-id="6e9d7-105">Examples</span></span>
<span data-ttu-id="6e9d7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e9d7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="6e9d7-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="6e9d7-107">Example 1</span></span>

<span data-ttu-id="6e9d7-108">다음 예제에서는 경로 매개 변수를 디렉터리 경로로 설정 합니다 (파일 경로는 아님).</span><span class="sxs-lookup"><span data-stu-id="6e9d7-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="6e9d7-109">파일 c:\test\CCERootCertificates.p7b.를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="6e9d7-110">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="6e9d7-110">Detailed Description</span></span>
<span data-ttu-id="6e9d7-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6e9d7-111"></span></span>

<span data-ttu-id="6e9d7-112">Export-CcRootCertificate cmdlet을 사용 하면 루트 및 중개 인증서를 파일 경로에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="6e9d7-113">이는 재해 복구 시나리오의 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="6e9d7-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e9d7-114">Parameters</span></span>
<span data-ttu-id="6e9d7-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6e9d7-115"></span></span>

|<span data-ttu-id="6e9d7-116">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="6e9d7-116">**Parameter**</span></span>|<span data-ttu-id="6e9d7-117">**필수**</span><span class="sxs-lookup"><span data-stu-id="6e9d7-117">**Required**</span></span>|<span data-ttu-id="6e9d7-118">**유형**</span><span class="sxs-lookup"><span data-stu-id="6e9d7-118">**Type**</span></span>|<span data-ttu-id="6e9d7-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="6e9d7-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e9d7-120">패스가</span><span class="sxs-lookup"><span data-stu-id="6e9d7-120">Path</span></span>  <br/> |<span data-ttu-id="6e9d7-121">필수</span><span class="sxs-lookup"><span data-stu-id="6e9d7-121">Required</span></span>  <br/> |<span data-ttu-id="6e9d7-122">System.String</span><span class="sxs-lookup"><span data-stu-id="6e9d7-122">System.String</span></span>  <br/> |<span data-ttu-id="6e9d7-123">인증서가 저장 되는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6e9d7-124">입력 형식</span><span class="sxs-lookup"><span data-stu-id="6e9d7-124">Input Types</span></span>
<span data-ttu-id="6e9d7-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e9d7-125"></span></span>

<span data-ttu-id="6e9d7-126">없음.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-126">None.</span></span> <span data-ttu-id="6e9d7-127">Export-CcRootCertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9d7-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="6e9d7-128">반환 형식</span><span class="sxs-lookup"><span data-stu-id="6e9d7-128">Return Types</span></span>
<span data-ttu-id="6e9d7-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e9d7-129"></span></span>

<span data-ttu-id="6e9d7-130">없음</span><span class="sxs-lookup"><span data-stu-id="6e9d7-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e9d7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e9d7-131">See also</span></span>
<span data-ttu-id="6e9d7-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e9d7-132"></span></span>

<span data-ttu-id="6e9d7-133">없음</span><span class="sxs-lookup"><span data-stu-id="6e9d7-133">None</span></span>
  

