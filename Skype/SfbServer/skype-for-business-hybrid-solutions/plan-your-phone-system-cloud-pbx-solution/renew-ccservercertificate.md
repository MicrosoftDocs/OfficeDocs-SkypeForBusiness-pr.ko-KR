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
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 사용자가 만료 되거나 이미 만료 된 경우이를 갱신 하는 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 인증서를 갱신 합니다. 이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcServerCertificate로 변경 되었습니다.
ms.openlocfilehash: 47f2bbefa6510ae49e2e4a3ddc321e288dee266e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003268"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="9dd01-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9dd01-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="9dd01-105">사용자가 만료 되거나 이미 만료 된 경우이를 갱신 하는 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="9dd01-106">이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcServerCertificate로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="9dd01-107">예제</span><span class="sxs-lookup"><span data-stu-id="9dd01-107">Examples</span></span>
<span data-ttu-id="9dd01-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9dd01-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="9dd01-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="9dd01-109">Example 1</span></span>

<span data-ttu-id="9dd01-110">다음 예제에서는 인증서가 거의 만료 되었거나 이미 만료 된 경우 중앙 관리 저장소, 중재 서버 및 Edge 서버의 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="9dd01-111">예제 2</span><span class="sxs-lookup"><span data-stu-id="9dd01-111">Example 2</span></span>

<span data-ttu-id="9dd01-112">다음 예에서는 중재 서버 및 Edge 서버의 인증서가 거의 만료 되거나 이미 만료 된 경우이를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="9dd01-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9dd01-113">Detailed Description</span></span>
<span data-ttu-id="9dd01-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9dd01-114"></span></span>

<span data-ttu-id="9dd01-115">중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급 된 후 2 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="9dd01-116">인증서가 거의 만료 되거나 이미 만료 된 경우 인증서 갱신을 위해-CcServerCertificate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="9dd01-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9dd01-117">Parameters</span></span>
<span data-ttu-id="9dd01-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9dd01-118"></span></span>

|<span data-ttu-id="9dd01-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="9dd01-119">**Parameter**</span></span>|<span data-ttu-id="9dd01-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="9dd01-120">**Required**</span></span>|<span data-ttu-id="9dd01-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="9dd01-121">**Type**</span></span>|<span data-ttu-id="9dd01-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="9dd01-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9dd01-123">역할</span><span class="sxs-lookup"><span data-stu-id="9dd01-123">Roles</span></span>  <br/> |<span data-ttu-id="9dd01-124">선택</span><span class="sxs-lookup"><span data-stu-id="9dd01-124">Optional</span></span>  <br/> |<span data-ttu-id="9dd01-125">System. Array</span><span class="sxs-lookup"><span data-stu-id="9dd01-125">System.Array</span></span>  <br/> | <span data-ttu-id="9dd01-126">클라우드 커넥터 서버 역할의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9dd01-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="9dd01-127">Input Types</span></span>
<span data-ttu-id="9dd01-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9dd01-128"></span></span>

<span data-ttu-id="9dd01-129">없음.</span><span class="sxs-lookup"><span data-stu-id="9dd01-129">None.</span></span> <span data-ttu-id="9dd01-130">' CcServerCertificate ' 갱신 cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd01-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9dd01-131">반환 형식</span><span class="sxs-lookup"><span data-stu-id="9dd01-131">Return Types</span></span>
<span data-ttu-id="9dd01-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9dd01-132"></span></span>

<span data-ttu-id="9dd01-133">없음</span><span class="sxs-lookup"><span data-stu-id="9dd01-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9dd01-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dd01-134">See also</span></span>
<span data-ttu-id="9dd01-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9dd01-135"></span></span>

[<span data-ttu-id="9dd01-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9dd01-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="9dd01-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9dd01-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="9dd01-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="9dd01-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

