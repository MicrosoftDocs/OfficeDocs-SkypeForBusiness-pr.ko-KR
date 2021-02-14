---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 이 Renew-CcServerCertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전에 대한 인증서를 갱신합니다. 이 명령은 클라우드 커넥터 2.0 Update-CcServerCertificate 릴리스에서 이 명령으로 변경되었습니다.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824264"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="276ae-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="276ae-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="276ae-105">이 Renew-CcServerCertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전에 대한 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="276ae-106">이 명령은 클라우드 커넥터 2.0 Update-CcServerCertificate 릴리스에서 이 명령으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="276ae-107">예</span><span class="sxs-lookup"><span data-stu-id="276ae-107">Examples</span></span>
<span data-ttu-id="276ae-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="276ae-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="276ae-109">예 1</span><span class="sxs-lookup"><span data-stu-id="276ae-109">Example 1</span></span>

<span data-ttu-id="276ae-110">다음 예에서는 인증서가 만료 거의 또는 이미 만료된 경우 중앙 관리 저장소, 중재 서버 및 에지 서버의 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="276ae-111">예 2</span><span class="sxs-lookup"><span data-stu-id="276ae-111">Example 2</span></span>

<span data-ttu-id="276ae-112">다음 예에서는 만료 거의 또는 이미 만료된 중재 서버 및 에지 서버에 대한 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="276ae-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="276ae-113">Detailed Description</span></span>
<span data-ttu-id="276ae-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="276ae-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="276ae-115">중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급된 후 2년 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="276ae-116">인증서가 만료 거의 또는 이미 만료된 경우 인증서를 Renew-CcServerCertificate cmdlet을 실행하여 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="276ae-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="276ae-117">Parameters</span></span>
<span data-ttu-id="276ae-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="276ae-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="276ae-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="276ae-119">**Parameter**</span></span>|<span data-ttu-id="276ae-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="276ae-120">**Required**</span></span>|<span data-ttu-id="276ae-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="276ae-121">**Type**</span></span>|<span data-ttu-id="276ae-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="276ae-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="276ae-123">역할</span><span class="sxs-lookup"><span data-stu-id="276ae-123">Roles</span></span>  <br/> |<span data-ttu-id="276ae-124">선택</span><span class="sxs-lookup"><span data-stu-id="276ae-124">Optional</span></span>  <br/> |<span data-ttu-id="276ae-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="276ae-125">System.Array</span></span>  <br/> | <span data-ttu-id="276ae-126">클라우드 커넥터 서버 역할의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="276ae-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="276ae-127">Input Types</span></span>
<span data-ttu-id="276ae-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="276ae-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="276ae-129">없음</span><span class="sxs-lookup"><span data-stu-id="276ae-129">None.</span></span> <span data-ttu-id="276ae-130">이 Renew-CcServerCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="276ae-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="276ae-131">반환 형식</span><span class="sxs-lookup"><span data-stu-id="276ae-131">Return Types</span></span>
<span data-ttu-id="276ae-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="276ae-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="276ae-133">없음</span><span class="sxs-lookup"><span data-stu-id="276ae-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="276ae-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="276ae-134">See also</span></span>
<span data-ttu-id="276ae-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="276ae-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="276ae-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="276ae-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="276ae-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="276ae-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="276ae-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="276ae-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

