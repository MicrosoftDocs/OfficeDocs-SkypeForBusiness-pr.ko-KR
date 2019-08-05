---
title: 갱신-CcServerCertificate
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
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190674"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="84d20-104">갱신-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="84d20-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="84d20-105">사용자가 만료 되거나 이미 만료 된 경우이를 갱신 하는 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="84d20-106">이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcServerCertificate로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="84d20-107">예제</span><span class="sxs-lookup"><span data-stu-id="84d20-107">Examples</span></span>
<span data-ttu-id="84d20-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="84d20-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="84d20-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="84d20-109">Example 1</span></span>

<span data-ttu-id="84d20-110">다음 예제에서는 인증서가 거의 만료 되었거나 이미 만료 된 경우 중앙 관리 저장소, 중재 서버 및 Edge 서버의 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="84d20-111">예제 2</span><span class="sxs-lookup"><span data-stu-id="84d20-111">Example 2</span></span>

<span data-ttu-id="84d20-112">다음 예에서는 중재 서버 및 Edge 서버의 인증서가 거의 만료 되거나 이미 만료 된 경우이를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="84d20-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="84d20-113">Detailed Description</span></span>
<span data-ttu-id="84d20-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="84d20-114"></span></span>

<span data-ttu-id="84d20-115">중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급 된 후 2 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="84d20-116">인증서가 거의 만료 되거나 이미 만료 된 경우 인증서 갱신을 위해-CcServerCertificate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="84d20-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84d20-117">Parameters</span></span>
<span data-ttu-id="84d20-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="84d20-118"></span></span>

|<span data-ttu-id="84d20-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="84d20-119">**Parameter**</span></span>|<span data-ttu-id="84d20-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="84d20-120">**Required**</span></span>|<span data-ttu-id="84d20-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="84d20-121">**Type**</span></span>|<span data-ttu-id="84d20-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="84d20-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84d20-123">역할</span><span class="sxs-lookup"><span data-stu-id="84d20-123">Roles</span></span>  <br/> |<span data-ttu-id="84d20-124">선택</span><span class="sxs-lookup"><span data-stu-id="84d20-124">Optional</span></span>  <br/> |<span data-ttu-id="84d20-125">System. Array</span><span class="sxs-lookup"><span data-stu-id="84d20-125">System.Array</span></span>  <br/> | <span data-ttu-id="84d20-126">클라우드 커넥터 서버 역할의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="84d20-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="84d20-127">Input Types</span></span>
<span data-ttu-id="84d20-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84d20-128"></span></span>

<span data-ttu-id="84d20-129">없음.</span><span class="sxs-lookup"><span data-stu-id="84d20-129">None.</span></span> <span data-ttu-id="84d20-130">' CcServerCertificate ' 갱신 cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84d20-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="84d20-131">반환 형식</span><span class="sxs-lookup"><span data-stu-id="84d20-131">Return Types</span></span>
<span data-ttu-id="84d20-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84d20-132"></span></span>

<span data-ttu-id="84d20-133">없음</span><span class="sxs-lookup"><span data-stu-id="84d20-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84d20-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84d20-134">See also</span></span>
<span data-ttu-id="84d20-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84d20-135"></span></span>

[<span data-ttu-id="84d20-136">다시 설정-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="84d20-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="84d20-137">갱신-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="84d20-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="84d20-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="84d20-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

