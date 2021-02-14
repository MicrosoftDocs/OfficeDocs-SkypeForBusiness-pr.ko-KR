---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 이 Publish-CcAppliance cmdlet은 온라인 테넌트 구성에서 고가용성 정보를 얻었다가 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 게시합니다.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824314"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="24da5-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="24da5-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="24da5-104">이 Publish-CcAppliance cmdlet은 온라인 테넌트 구성에서 고가용성 정보를 얻었다가 호스트 서버의 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="24da5-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="24da5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24da5-105">Parameters</span></span>

<span data-ttu-id="24da5-106">없음</span><span class="sxs-lookup"><span data-stu-id="24da5-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="24da5-107">예</span><span class="sxs-lookup"><span data-stu-id="24da5-107">Examples</span></span>
<span data-ttu-id="24da5-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24da5-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="24da5-109">예 1</span><span class="sxs-lookup"><span data-stu-id="24da5-109">Example 1</span></span>

<span data-ttu-id="24da5-110">다음 예에서는 온라인 테넌트 구성에서 고가용성 정보를 확인하여 호스트 서버의 Cloud Connector 어플라이언스에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="24da5-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="24da5-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="24da5-111">Detailed Description</span></span>
<span data-ttu-id="24da5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="24da5-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="24da5-113">고가용성 정보에는 PSTN 사이트의 중재 서버 FQDN 및 IP 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24da5-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="24da5-114">중재 서버 IP 주소에 대한 AD Server에 새 DNS A 레코드가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="24da5-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="24da5-115">새 토폴로지 항목이 중재 서버 FQDNS 및 IP 주소의 중앙 관리 저장소로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="24da5-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="24da5-116">입력 형식</span><span class="sxs-lookup"><span data-stu-id="24da5-116">Input Types</span></span>
<span data-ttu-id="24da5-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="24da5-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="24da5-118">없음</span><span class="sxs-lookup"><span data-stu-id="24da5-118">None.</span></span> <span data-ttu-id="24da5-119">이 Publish-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24da5-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="24da5-120">반환 형식</span><span class="sxs-lookup"><span data-stu-id="24da5-120">Return Types</span></span>
<span data-ttu-id="24da5-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="24da5-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="24da5-122">없음</span><span class="sxs-lookup"><span data-stu-id="24da5-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24da5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24da5-123">See also</span></span>
<span data-ttu-id="24da5-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="24da5-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="24da5-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="24da5-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="24da5-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="24da5-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="24da5-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="24da5-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="24da5-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="24da5-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

