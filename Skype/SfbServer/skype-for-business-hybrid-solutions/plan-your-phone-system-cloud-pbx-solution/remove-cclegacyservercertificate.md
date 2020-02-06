---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: CcLegacyServerCertificate cmdlet은 CcCACertificate 갱신 또는 CcServerCertificate cmdlet 갱신을 실행 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에서 레거시 서버 인증서를 제거 합니다.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824284"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="ef7f9-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ef7f9-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="ef7f9-104">CcLegacyServerCertificate cmdlet은 CcCACertificate 갱신 또는 CcServerCertificate cmdlet 갱신을 실행 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에서 레거시 서버 인증서를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7f9-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="ef7f9-105">예제</span><span class="sxs-lookup"><span data-stu-id="ef7f9-105">Examples</span></span>
<span data-ttu-id="ef7f9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7f9-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ef7f9-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="ef7f9-107">Example 1</span></span>

<span data-ttu-id="ef7f9-108">다음 예제에서는 인증서를 갱신 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에 대해 발급 된 레거시 인증서를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7f9-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="ef7f9-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="ef7f9-109">Example 2</span></span>

<span data-ttu-id="ef7f9-110">다음 예제에서는 인증서를 갱신 한 후 중재 서버와 Edge 서버에 대해 발급 된 인증서를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7f9-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="ef7f9-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef7f9-111">Parameters</span></span>
<span data-ttu-id="ef7f9-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7f9-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="ef7f9-113">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="ef7f9-113">**Parameter**</span></span>|<span data-ttu-id="ef7f9-114">**필수**</span><span class="sxs-lookup"><span data-stu-id="ef7f9-114">**Required**</span></span>|<span data-ttu-id="ef7f9-115">**유형**</span><span class="sxs-lookup"><span data-stu-id="ef7f9-115">**Type**</span></span>|<span data-ttu-id="ef7f9-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="ef7f9-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ef7f9-117">역할</span><span class="sxs-lookup"><span data-stu-id="ef7f9-117">Roles</span></span> <br/> |<span data-ttu-id="ef7f9-118">선택</span><span class="sxs-lookup"><span data-stu-id="ef7f9-118">Optional</span></span>  <br/> |<span data-ttu-id="ef7f9-119">System. Array</span><span class="sxs-lookup"><span data-stu-id="ef7f9-119">System.Array</span></span>  <br/> | <span data-ttu-id="ef7f9-120">클라우드 커넥터 서버 역할의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ef7f9-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ef7f9-121">입력 형식</span><span class="sxs-lookup"><span data-stu-id="ef7f9-121">Input Types</span></span>
<span data-ttu-id="ef7f9-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7f9-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ef7f9-123">없음.</span><span class="sxs-lookup"><span data-stu-id="ef7f9-123">None.</span></span> <span data-ttu-id="ef7f9-124">CcLegacyServerCertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7f9-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ef7f9-125">반환 형식</span><span class="sxs-lookup"><span data-stu-id="ef7f9-125">Return Types</span></span>
<span data-ttu-id="ef7f9-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7f9-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ef7f9-127">없음</span><span class="sxs-lookup"><span data-stu-id="ef7f9-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef7f9-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef7f9-128">See also</span></span>
<span data-ttu-id="ef7f9-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7f9-129"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ef7f9-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ef7f9-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="ef7f9-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef7f9-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="ef7f9-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef7f9-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="ef7f9-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef7f9-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

