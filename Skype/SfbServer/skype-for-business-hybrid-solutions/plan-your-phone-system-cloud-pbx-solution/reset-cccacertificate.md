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
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: CcCACertificate cmdlet은 인증 기관 서비스 광고 서버를 다시 설치 하 여 새 루트 CA 인증서를 만듭니다.
ms.openlocfilehash: 50c3b1afc29503b2b292ce578ea01b03aeeba368
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003258"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="c1571-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="c1571-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="c1571-104">CcCACertificate cmdlet은 인증 기관 서비스 광고 서버를 다시 설치 하 여 새 루트 CA 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1571-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="c1571-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1571-105">Parameters</span></span>

<span data-ttu-id="c1571-106">없음</span><span class="sxs-lookup"><span data-stu-id="c1571-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c1571-107">예제</span><span class="sxs-lookup"><span data-stu-id="c1571-107">Examples</span></span>
<span data-ttu-id="c1571-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c1571-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="c1571-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="c1571-109">Example 1</span></span>

<span data-ttu-id="c1571-110">다음 예제에서는 새 루트 CA 인증서를 만들기 위해 인증 기관 서비스 광고 서버를 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1571-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="c1571-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c1571-111">Detailed Description</span></span>
<span data-ttu-id="c1571-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c1571-112"></span></span>

<span data-ttu-id="c1571-113">루트 CA 인증서가 손상 되거나 더 이상 안전 하지 않은 경우 루트 ca 인증서와 루트 CA가 발급 한 모든 인증서를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1571-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="c1571-114">CcCACertificate cmdlet은 모든 인증서를 해지 하 고 인증 기관을 제거 하 고 다시 설치 하 고 이전 인증 기관 서비스와 관련 된 모든 인증서를 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1571-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="c1571-115">자세한 내용은 클라우드 커넥터 배포 문제 해결에서 "CMS, 중재 서버 및 Edge 서버에 발급 된 인증 기관 인증서 또는 내부 인증서가 거의 만료 되었거나 손상 되었습니다."를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1571-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c1571-116">입력 형식</span><span class="sxs-lookup"><span data-stu-id="c1571-116">Input Types</span></span>
<span data-ttu-id="c1571-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c1571-117"></span></span>

<span data-ttu-id="c1571-118">없음.</span><span class="sxs-lookup"><span data-stu-id="c1571-118">None.</span></span> <span data-ttu-id="c1571-119">CcCACertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1571-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c1571-120">반환 형식</span><span class="sxs-lookup"><span data-stu-id="c1571-120">Return Types</span></span>
<span data-ttu-id="c1571-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c1571-121"></span></span>

<span data-ttu-id="c1571-122">없음.</span><span class="sxs-lookup"><span data-stu-id="c1571-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c1571-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1571-123">See also</span></span>
<span data-ttu-id="c1571-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c1571-124"></span></span>

<span data-ttu-id="c1571-125">[갱신-CcCACertificate](renew-cccacertificate.md) 버전 1.4.2</span><span class="sxs-lookup"><span data-stu-id="c1571-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="c1571-126">[갱신-CcServerCertificate](renew-ccservercertificate.md) 버전 1.4.2</span><span class="sxs-lookup"><span data-stu-id="c1571-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="c1571-127">[업데이트-CcCACertificate](update-cccacertificate.md) 버전 2.0 이상</span><span class="sxs-lookup"><span data-stu-id="c1571-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="c1571-128">[갱신-CcServerCertificate](renew-ccservercertificate.md) 버전 2.0 이상</span><span class="sxs-lookup"><span data-stu-id="c1571-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="c1571-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="c1571-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

