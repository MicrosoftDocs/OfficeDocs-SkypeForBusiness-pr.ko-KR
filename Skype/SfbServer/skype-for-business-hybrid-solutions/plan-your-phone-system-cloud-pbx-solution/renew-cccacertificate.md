---
title: Renew-CcCACertificate
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
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: 이 Renew-CcCACertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신합니다. 이 명령은 클라우드 커넥터 2.0 Update-CcCACertificate 릴리스에서 이 명령으로 변경되었습니다.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824274"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="ef7a0-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef7a0-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="ef7a0-105">이 Renew-CcCACertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="ef7a0-106">이 명령은 클라우드 커넥터 2.0 Update-CcCACertificate 릴리스에서 이 명령으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="ef7a0-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef7a0-107">Parameters</span></span>

<span data-ttu-id="ef7a0-108">없음</span><span class="sxs-lookup"><span data-stu-id="ef7a0-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ef7a0-109">예</span><span class="sxs-lookup"><span data-stu-id="ef7a0-109">Examples</span></span>
<span data-ttu-id="ef7a0-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7a0-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ef7a0-111">예 1</span><span class="sxs-lookup"><span data-stu-id="ef7a0-111">Example 1</span></span>

<span data-ttu-id="ef7a0-112">다음 예에서는 루트 CA 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="ef7a0-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ef7a0-113">Detailed Description</span></span>
<span data-ttu-id="ef7a0-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7a0-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ef7a0-115">클라우드 커넥터 루트 CA 인증서는 인증 기관 서비스가 설치된 날짜로부터 5년 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="ef7a0-116">루트 인증서가 만료에 가까운 경우 또는 이미 만료된 경우 Renew-CcCACertificate cmdlet을 실행하여 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="ef7a0-117">루트 인증서가 갱신된 후 AD Server, 중앙 관리 저장소 및 에지 서버는 자동으로 새 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="ef7a0-118">동일한 PSTN 사이트에 여러 어플라이언스가 있는 경우 동일한 PSTN 사이트의 모든 어플라이언스에서 Renew-CcCACertificate cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="ef7a0-119">마지막 Export-CcRootCertificate 실행하여 루트 인증서를 첫 번째 어플라이언스의 로컬 파일로 내보냈다가 내보냈던 인증서를 PSTN 게이트웨이에 복사하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ef7a0-120">입력 형식</span><span class="sxs-lookup"><span data-stu-id="ef7a0-120">Input Types</span></span>
<span data-ttu-id="ef7a0-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7a0-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ef7a0-122">없음</span><span class="sxs-lookup"><span data-stu-id="ef7a0-122">None.</span></span> <span data-ttu-id="ef7a0-123">이 Renew-CcCACertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7a0-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ef7a0-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="ef7a0-124">Return Types</span></span>
<span data-ttu-id="ef7a0-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7a0-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ef7a0-126">없음</span><span class="sxs-lookup"><span data-stu-id="ef7a0-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef7a0-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef7a0-127">See also</span></span>
<span data-ttu-id="ef7a0-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7a0-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ef7a0-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef7a0-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="ef7a0-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ef7a0-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="ef7a0-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="ef7a0-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

