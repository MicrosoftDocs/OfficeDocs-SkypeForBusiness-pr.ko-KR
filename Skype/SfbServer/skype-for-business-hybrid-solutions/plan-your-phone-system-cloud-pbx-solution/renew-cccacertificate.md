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
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: CcCACertificate cmdlet은 거의 만료 되거나 이미 만료 된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신 합니다. 이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcCACertificate로 변경 되었습니다.
ms.openlocfilehash: 493b733eab9cbd8331a93d72dc4a865f3574fbe8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003278"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="39a48-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="39a48-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="39a48-105">CcCACertificate cmdlet은 거의 만료 되거나 이미 만료 된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="39a48-106">이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 업데이트-CcCACertificate로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="39a48-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39a48-107">Parameters</span></span>

<span data-ttu-id="39a48-108">없음</span><span class="sxs-lookup"><span data-stu-id="39a48-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="39a48-109">예제</span><span class="sxs-lookup"><span data-stu-id="39a48-109">Examples</span></span>
<span data-ttu-id="39a48-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39a48-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="39a48-111">예제 1</span><span class="sxs-lookup"><span data-stu-id="39a48-111">Example 1</span></span>

<span data-ttu-id="39a48-112">다음 예제에서는 루트 CA 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="39a48-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="39a48-113">Detailed Description</span></span>
<span data-ttu-id="39a48-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="39a48-114"></span></span>

<span data-ttu-id="39a48-115">클라우드 커넥터 루트 CA 인증서는 인증 기관 서비스를 설치한 날짜 로부터 5 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="39a48-116">루트 인증서가 거의 만료 되거나 이미 만료 된 경우 갱신 CcCACertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="39a48-117">루트 인증서가 갱신 된 후 광고 서버, 중앙 관리 저장소 및 Edge 서버에 새 인증서가 자동으로 발급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="39a48-118">동일한 PSTN 사이트에 여러 기기가 있는 경우 동일한 PSTN 사이트의 모든 기기에서 CcCACertificate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="39a48-119">마지막 단계로 내보내기-CcRootCertificate를 실행 하 여 루트 인증서를 첫 번째 기기의 로컬 파일로 내보낸 다음, 내보낸 인증서를 PSTN 게이트웨이에 복사 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="39a48-120">입력 형식</span><span class="sxs-lookup"><span data-stu-id="39a48-120">Input Types</span></span>
<span data-ttu-id="39a48-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39a48-121"></span></span>

<span data-ttu-id="39a48-122">없음.</span><span class="sxs-lookup"><span data-stu-id="39a48-122">None.</span></span> <span data-ttu-id="39a48-123">CcCACertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39a48-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="39a48-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="39a48-124">Return Types</span></span>
<span data-ttu-id="39a48-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39a48-125"></span></span>

<span data-ttu-id="39a48-126">없음</span><span class="sxs-lookup"><span data-stu-id="39a48-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39a48-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39a48-127">See also</span></span>
<span data-ttu-id="39a48-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39a48-128"></span></span>

[<span data-ttu-id="39a48-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="39a48-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="39a48-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="39a48-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="39a48-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="39a48-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

