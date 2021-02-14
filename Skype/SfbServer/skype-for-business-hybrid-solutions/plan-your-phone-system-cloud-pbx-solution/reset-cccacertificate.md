---
title: Reset-CcCACertificate
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
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: 이 Reset-CcCACertificate cmdlet은 인증 기관 서비스 AD Server를 다시 설치하여 새 루트 CA 인증서를 생성합니다.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824254"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="2c5a2-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2c5a2-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="2c5a2-104">이 Reset-CcCACertificate cmdlet은 인증 기관 서비스 AD Server를 다시 설치하여 새 루트 CA 인증서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="2c5a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c5a2-105">Parameters</span></span>

<span data-ttu-id="2c5a2-106">없음</span><span class="sxs-lookup"><span data-stu-id="2c5a2-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2c5a2-107">예</span><span class="sxs-lookup"><span data-stu-id="2c5a2-107">Examples</span></span>
<span data-ttu-id="2c5a2-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5a2-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2c5a2-109">예 1</span><span class="sxs-lookup"><span data-stu-id="2c5a2-109">Example 1</span></span>

<span data-ttu-id="2c5a2-110">다음 예에서는 인증 기관 서비스 AD Server를 다시 설치하여 새 루트 CA 인증서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="2c5a2-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2c5a2-111">Detailed Description</span></span>
<span data-ttu-id="2c5a2-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5a2-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2c5a2-113">루트 CA 인증서가 손상되거나 더 이상 보안을 유지하지 못하면 루트 CA 인증서와 루트 CA에서 발급한 모든 인증서를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="2c5a2-114">이 Reset-CcCACertificate cmdlet은 모든 인증서를 해지하고 인증 기관을 제거하고 다시 설치한 다음 이전 인증 기관 서비스와 관련된 모든 인증서를 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="2c5a2-115">자세한 내용은 클라우드 커넥터 배포 문제 해결에서 "CMS, 중재 서버 및 에지 서버에 발급된 인증 기관 인증서 또는 내부 인증서가 거의 만료되거나 손상된 경우"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2c5a2-116">입력 형식</span><span class="sxs-lookup"><span data-stu-id="2c5a2-116">Input Types</span></span>
<span data-ttu-id="2c5a2-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5a2-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2c5a2-118">없음</span><span class="sxs-lookup"><span data-stu-id="2c5a2-118">None.</span></span> <span data-ttu-id="2c5a2-119">이 Reset-CcCACertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2c5a2-120">반환 형식</span><span class="sxs-lookup"><span data-stu-id="2c5a2-120">Return Types</span></span>
<span data-ttu-id="2c5a2-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5a2-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2c5a2-122">없음</span><span class="sxs-lookup"><span data-stu-id="2c5a2-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c5a2-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c5a2-123">See also</span></span>
<span data-ttu-id="2c5a2-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5a2-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2c5a2-125">[Renew-CcCACertificate](renew-cccacertificate.md) 버전 1.4.2만</span><span class="sxs-lookup"><span data-stu-id="2c5a2-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="2c5a2-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) 버전 1.4.2만</span><span class="sxs-lookup"><span data-stu-id="2c5a2-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="2c5a2-127">[Update-CcCACertificate](update-cccacertificate.md) 버전 2.0 이상</span><span class="sxs-lookup"><span data-stu-id="2c5a2-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="2c5a2-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) 버전 2.0 이상</span><span class="sxs-lookup"><span data-stu-id="2c5a2-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="2c5a2-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="2c5a2-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

