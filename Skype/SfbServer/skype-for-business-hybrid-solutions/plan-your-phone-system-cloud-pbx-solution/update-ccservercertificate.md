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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 이 Update-CcServerCertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전에 대한 인증서를 갱신합니다.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824112"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="dc8ae-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="dc8ae-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="dc8ae-104">이 Update-CcServerCertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전에 대한 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="dc8ae-105">예</span><span class="sxs-lookup"><span data-stu-id="dc8ae-105">Examples</span></span>
<span data-ttu-id="dc8ae-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="dc8ae-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="dc8ae-107">예 1</span><span class="sxs-lookup"><span data-stu-id="dc8ae-107">Example 1</span></span>

<span data-ttu-id="dc8ae-108">다음 예에서는 인증서가 만료 거의 또는 이미 만료된 경우 중앙 관리 저장소, 중재 서버 및 에지 서버의 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="dc8ae-109">예 2</span><span class="sxs-lookup"><span data-stu-id="dc8ae-109">Example 2</span></span>

<span data-ttu-id="dc8ae-110">다음 예에서는 만료 거의 또는 이미 만료된 중재 서버 및 에지 서버에 대한 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="dc8ae-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="dc8ae-111">Detailed Description</span></span>
<span data-ttu-id="dc8ae-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dc8ae-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="dc8ae-113">중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급된 후 2년 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="dc8ae-114">인증서가 만료 거의 또는 이미 만료된 경우 인증서를 Update-CcServerCertificate cmdlet을 실행하여 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="dc8ae-115">이 명령은 Cloud Connector 2.0 Renew-CcServerCertificate 릴리스의 cmdlet을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="dc8ae-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc8ae-116">Parameters</span></span>
<span data-ttu-id="dc8ae-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dc8ae-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="dc8ae-118">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="dc8ae-118">**Parameter**</span></span>|<span data-ttu-id="dc8ae-119">**필수**</span><span class="sxs-lookup"><span data-stu-id="dc8ae-119">**Required**</span></span>|<span data-ttu-id="dc8ae-120">**유형**</span><span class="sxs-lookup"><span data-stu-id="dc8ae-120">**Type**</span></span>|<span data-ttu-id="dc8ae-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="dc8ae-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc8ae-122">역할</span><span class="sxs-lookup"><span data-stu-id="dc8ae-122">Roles</span></span>  <br/> |<span data-ttu-id="dc8ae-123">선택</span><span class="sxs-lookup"><span data-stu-id="dc8ae-123">Optional</span></span>  <br/> |<span data-ttu-id="dc8ae-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="dc8ae-124">System.Array</span></span>  <br/> | <span data-ttu-id="dc8ae-125">클라우드 커넥터 서버 역할의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="dc8ae-126">입력 형식</span><span class="sxs-lookup"><span data-stu-id="dc8ae-126">Input Types</span></span>
<span data-ttu-id="dc8ae-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc8ae-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="dc8ae-128">없음</span><span class="sxs-lookup"><span data-stu-id="dc8ae-128">None.</span></span> <span data-ttu-id="dc8ae-129">이 Update-CcServerCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc8ae-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="dc8ae-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="dc8ae-130">Return Types</span></span>
<span data-ttu-id="dc8ae-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc8ae-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="dc8ae-132">없음</span><span class="sxs-lookup"><span data-stu-id="dc8ae-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc8ae-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc8ae-133">See also</span></span>
<span data-ttu-id="dc8ae-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc8ae-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="dc8ae-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="dc8ae-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="dc8ae-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="dc8ae-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="dc8ae-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="dc8ae-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

