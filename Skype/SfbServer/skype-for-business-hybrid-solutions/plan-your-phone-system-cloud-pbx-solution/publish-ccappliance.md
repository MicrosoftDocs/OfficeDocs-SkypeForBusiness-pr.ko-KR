---
title: 게시-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 게시-CcAppliance cmdlet는 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져와 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 게시 합니다.
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190707"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="f107a-103">게시-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f107a-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="f107a-104">게시-CcAppliance cmdlet는 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져와 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f107a-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="f107a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f107a-105">Parameters</span></span>

<span data-ttu-id="f107a-106">없음</span><span class="sxs-lookup"><span data-stu-id="f107a-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f107a-107">예제</span><span class="sxs-lookup"><span data-stu-id="f107a-107">Examples</span></span>
<span data-ttu-id="f107a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f107a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="f107a-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="f107a-109">Example 1</span></span>

<span data-ttu-id="f107a-110">다음 예제에서는 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져오고 호스트 서버의 클라우드 커넥터 기기에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f107a-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="f107a-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f107a-111">Detailed Description</span></span>
<span data-ttu-id="f107a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f107a-112"></span></span>

<span data-ttu-id="f107a-113">고가용성 정보에는 PSTN 사이트의 중재 서버 Fqdn 및 IP 주소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f107a-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="f107a-114">새 DNS 중재 서버 IP 주소에 대 한 레코드가 광고 서버에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f107a-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="f107a-115">새 토폴로지 항목이 중재 서버 Fqdn과 IP 주소에 대 한 중앙 관리 저장소로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f107a-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="f107a-116">입력 형식</span><span class="sxs-lookup"><span data-stu-id="f107a-116">Input Types</span></span>
<span data-ttu-id="f107a-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f107a-117"></span></span>

<span data-ttu-id="f107a-118">없음.</span><span class="sxs-lookup"><span data-stu-id="f107a-118">None.</span></span> <span data-ttu-id="f107a-119">게시-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f107a-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f107a-120">반환 형식</span><span class="sxs-lookup"><span data-stu-id="f107a-120">Return Types</span></span>
<span data-ttu-id="f107a-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f107a-121"></span></span>

<span data-ttu-id="f107a-122">없음</span><span class="sxs-lookup"><span data-stu-id="f107a-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f107a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f107a-123">See also</span></span>
<span data-ttu-id="f107a-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f107a-124"></span></span>

[<span data-ttu-id="f107a-125">설치-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f107a-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="f107a-126">제거-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f107a-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="f107a-127">등록-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f107a-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="f107a-128">CcAppliance 등록 취소</span><span class="sxs-lookup"><span data-stu-id="f107a-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

