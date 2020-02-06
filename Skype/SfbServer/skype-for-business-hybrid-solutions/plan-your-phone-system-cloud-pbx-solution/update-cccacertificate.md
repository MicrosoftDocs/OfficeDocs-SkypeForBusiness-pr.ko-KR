---
title: Update-CcCACertificate
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
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 업데이트 CcCACertificate cmdlet은 거의 만료 되거나 이미 만료 된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신 합니다.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824122"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="6c987-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6c987-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="6c987-104">업데이트 CcCACertificate cmdlet은 거의 만료 되거나 이미 만료 된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="6c987-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c987-105">Parameters</span></span>

<span data-ttu-id="6c987-106">없음.</span><span class="sxs-lookup"><span data-stu-id="6c987-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="6c987-107">예제</span><span class="sxs-lookup"><span data-stu-id="6c987-107">Examples</span></span>
<span data-ttu-id="6c987-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6c987-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6c987-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="6c987-109">Example 1</span></span>

<span data-ttu-id="6c987-110">다음 예제에서는 루트 CA 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="6c987-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="6c987-111">Detailed Description</span></span>
<span data-ttu-id="6c987-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6c987-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="6c987-113">클라우드 커넥터 루트 CA 인증서는 인증 기관 서비스를 설치한 날짜 로부터 5 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="6c987-114">루트 인증서가 거의 만료 되거나 이미 만료 된 경우 업데이트 CcCACertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="6c987-115">루트 인증서가 갱신 된 후 광고 서버, 중앙 관리 저장소 및 Edge 서버에 새 인증서가 자동으로 발급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="6c987-116">동일한 PSTN 사이트에 여러 기기가 있는 경우 동일한 PSTN 사이트의 모든 기기에서 CcCACertificate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="6c987-117">마지막 단계로 내보내기-CcRootCertificate를 실행 하 여 루트 인증서를 첫 번째 기기의 로컬 파일로 내보낸 다음, 내보낸 인증서를 PSTN 게이트웨이에 복사 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="6c987-118">이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 CcCACertificate cmdlet을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6c987-119">입력 형식</span><span class="sxs-lookup"><span data-stu-id="6c987-119">Input Types</span></span>
<span data-ttu-id="6c987-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6c987-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6c987-121">없음.</span><span class="sxs-lookup"><span data-stu-id="6c987-121">None.</span></span> <span data-ttu-id="6c987-122">업데이트 CcCACertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c987-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6c987-123">반환 형식</span><span class="sxs-lookup"><span data-stu-id="6c987-123">Return Types</span></span>
<span data-ttu-id="6c987-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6c987-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6c987-125">없음.</span><span class="sxs-lookup"><span data-stu-id="6c987-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6c987-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c987-126">See also</span></span>
<span data-ttu-id="6c987-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6c987-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6c987-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6c987-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="6c987-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6c987-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="6c987-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="6c987-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

