---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: 이 Unregister-CcAppliance cmdlet은 온라인 테넌트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스 등록을 등록을 해지합니다.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824132"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="acd89-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acd89-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="acd89-104">이 Unregister-CcAppliance cmdlet은 온라인 테넌트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스 등록을 등록을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="acd89-105">예</span><span class="sxs-lookup"><span data-stu-id="acd89-105">Examples</span></span>
<span data-ttu-id="acd89-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="acd89-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="acd89-107">예 1</span><span class="sxs-lookup"><span data-stu-id="acd89-107">Example 1</span></span>

<span data-ttu-id="acd89-108">다음 예에서는 온라인 테넌트 구성에서 현재 어플라이언스 등록을 등록을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="acd89-109">예 2</span><span class="sxs-lookup"><span data-stu-id="acd89-109">Example 2</span></span>

<span data-ttu-id="acd89-110">다음 예제에서는 온라인 테넌트 구성에 연결하지 않고 구성에서 로컬로 등록을 등록을 하지 않는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="acd89-111">예 3</span><span class="sxs-lookup"><span data-stu-id="acd89-111">Example 3</span></span>

<span data-ttu-id="acd89-112">다음 예제에서는 이름이 "Appliance1"인 현재 어플라이언스를 PSTN 사이트 "Site1"에 등록을 등록하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="acd89-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="acd89-113">Detailed Description</span></span>
<span data-ttu-id="acd89-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="acd89-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="acd89-115">Register-CcAppliance cmdlet과 마찬가지로 사이트 이름과 에지 서버 외부 FQDN을 CloudConnector.ini PSTN 사이트 ID로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="acd89-116">마찬가지로, CloudConnector.ini 파일의 중재 서버 FQDN과 결합된 ApplianceName은 어플라이언스 ID로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="acd89-117">어플라이언스가 등록되지 않은 후 클라우드 커넥터 관리 서비스를 다시 시작하고 NetworkService 계정으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="acd89-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acd89-118">Parameters</span></span>
<span data-ttu-id="acd89-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="acd89-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="acd89-120">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="acd89-120">**Parameter**</span></span>|<span data-ttu-id="acd89-121">**필수**</span><span class="sxs-lookup"><span data-stu-id="acd89-121">**Required**</span></span>|<span data-ttu-id="acd89-122">**유형**</span><span class="sxs-lookup"><span data-stu-id="acd89-122">**Type**</span></span>|<span data-ttu-id="acd89-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="acd89-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="acd89-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="acd89-124">SiteName</span></span> <br/> |<span data-ttu-id="acd89-125">옵션</span><span class="sxs-lookup"><span data-stu-id="acd89-125">Optional</span></span>  <br/> |<span data-ttu-id="acd89-126">System.String</span><span class="sxs-lookup"><span data-stu-id="acd89-126">System.String</span></span>  <br/> |<span data-ttu-id="acd89-127">어플라이언스가 등록된 PSTN 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="acd89-128">기본값은 파일에서 SiteName CloudConnector.ini 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="acd89-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="acd89-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="acd89-130">옵션</span><span class="sxs-lookup"><span data-stu-id="acd89-130">Optional</span></span>  <br/> |<span data-ttu-id="acd89-131">System.String</span><span class="sxs-lookup"><span data-stu-id="acd89-131">System.String</span></span>  <br/> |<span data-ttu-id="acd89-132">현재 어플라이언스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-132">Name of the current appliance.</span></span> <span data-ttu-id="acd89-133">기본값은 호스트 서버의 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="acd89-134">로컬</span><span class="sxs-lookup"><span data-stu-id="acd89-134">Local</span></span>  <br/> |<span data-ttu-id="acd89-135">선택</span><span class="sxs-lookup"><span data-stu-id="acd89-135">Optional</span></span>  <br/> |<span data-ttu-id="acd89-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="acd89-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="acd89-137">온라인 테넌트 구성에 연결하지 않고 로컬로 등록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="acd89-138">입력 형식</span><span class="sxs-lookup"><span data-stu-id="acd89-138">Input Types</span></span>
<span data-ttu-id="acd89-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acd89-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="acd89-140">없음</span><span class="sxs-lookup"><span data-stu-id="acd89-140">None.</span></span> <span data-ttu-id="acd89-141">이 Unregister-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acd89-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="acd89-142">반환 형식</span><span class="sxs-lookup"><span data-stu-id="acd89-142">Return Types</span></span>
<span data-ttu-id="acd89-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acd89-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="acd89-144">없음</span><span class="sxs-lookup"><span data-stu-id="acd89-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="acd89-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acd89-145">See also</span></span>
<span data-ttu-id="acd89-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acd89-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="acd89-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acd89-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="acd89-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acd89-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="acd89-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acd89-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="acd89-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acd89-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

