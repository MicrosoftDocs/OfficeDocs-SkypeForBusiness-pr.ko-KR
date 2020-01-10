---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 업데이트가 거의 만료 되거나 이미 만료 된 경우 업데이트-CcServerCertificate cmdlet이 비즈니스용 Skype 클라우드 커넥터 에디션의 인증서를 갱신 합니다.
ms.openlocfilehash: 920770b4ce77e893a7195d1326ea13ac73e0cc70
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003118"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="ec36c-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ec36c-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="ec36c-104">업데이트가 거의 만료 되거나 이미 만료 된 경우 업데이트-CcServerCertificate cmdlet이 비즈니스용 Skype 클라우드 커넥터 에디션의 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="ec36c-105">예제</span><span class="sxs-lookup"><span data-stu-id="ec36c-105">Examples</span></span>
<span data-ttu-id="ec36c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ec36c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="ec36c-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="ec36c-107">Example 1</span></span>

<span data-ttu-id="ec36c-108">다음 예제에서는 인증서가 거의 만료 되었거나 이미 만료 된 경우 중앙 관리 저장소, 중재 서버 및 Edge 서버의 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="ec36c-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="ec36c-109">Example 2</span></span>

<span data-ttu-id="ec36c-110">다음 예에서는 중재 서버 및 Edge 서버의 인증서가 거의 만료 되거나 이미 만료 된 경우이를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="ec36c-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ec36c-111">Detailed Description</span></span>
<span data-ttu-id="ec36c-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ec36c-112"></span></span>

<span data-ttu-id="ec36c-113">중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급 된 후 2 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="ec36c-114">인증서가 거의 만료 되거나 이미 만료 된 경우 업데이트-CcServerCertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="ec36c-115">이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 갱신-CcServerCertificate cmdlet을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ec36c-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec36c-116">Parameters</span></span>
<span data-ttu-id="ec36c-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ec36c-117"></span></span>

|<span data-ttu-id="ec36c-118">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="ec36c-118">**Parameter**</span></span>|<span data-ttu-id="ec36c-119">**필수**</span><span class="sxs-lookup"><span data-stu-id="ec36c-119">**Required**</span></span>|<span data-ttu-id="ec36c-120">**유형**</span><span class="sxs-lookup"><span data-stu-id="ec36c-120">**Type**</span></span>|<span data-ttu-id="ec36c-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="ec36c-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ec36c-122">역할</span><span class="sxs-lookup"><span data-stu-id="ec36c-122">Roles</span></span>  <br/> |<span data-ttu-id="ec36c-123">선택</span><span class="sxs-lookup"><span data-stu-id="ec36c-123">Optional</span></span>  <br/> |<span data-ttu-id="ec36c-124">System. Array</span><span class="sxs-lookup"><span data-stu-id="ec36c-124">System.Array</span></span>  <br/> | <span data-ttu-id="ec36c-125">클라우드 커넥터 서버 역할의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ec36c-126">입력 형식</span><span class="sxs-lookup"><span data-stu-id="ec36c-126">Input Types</span></span>
<span data-ttu-id="ec36c-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec36c-127"></span></span>

<span data-ttu-id="ec36c-128">없음.</span><span class="sxs-lookup"><span data-stu-id="ec36c-128">None.</span></span> <span data-ttu-id="ec36c-129">업데이트-CcServerCertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec36c-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ec36c-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="ec36c-130">Return Types</span></span>
<span data-ttu-id="ec36c-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec36c-131"></span></span>

<span data-ttu-id="ec36c-132">없음</span><span class="sxs-lookup"><span data-stu-id="ec36c-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec36c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec36c-133">See also</span></span>
<span data-ttu-id="ec36c-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec36c-134"></span></span>

[<span data-ttu-id="ec36c-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ec36c-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="ec36c-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ec36c-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="ec36c-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="ec36c-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

