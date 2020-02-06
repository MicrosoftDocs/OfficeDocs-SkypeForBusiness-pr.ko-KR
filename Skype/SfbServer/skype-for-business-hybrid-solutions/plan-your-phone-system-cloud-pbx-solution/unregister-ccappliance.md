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
description: 비 CcAppliance cmdlet은 온라인 테 넌 트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 등록을 취소 합니다.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824132"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="20b4f-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="20b4f-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="20b4f-104">비 CcAppliance cmdlet은 온라인 테 넌 트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="20b4f-105">예제</span><span class="sxs-lookup"><span data-stu-id="20b4f-105">Examples</span></span>
<span data-ttu-id="20b4f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="20b4f-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="20b4f-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="20b4f-107">Example 1</span></span>

<span data-ttu-id="20b4f-108">다음 예에서는 온라인 테 넌 트 구성에서 현재 기기의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="20b4f-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="20b4f-109">Example 2</span></span>

<span data-ttu-id="20b4f-110">다음 예제에서는 온라인 테 넌 트 구성에 연결 하지 않고 로컬로 등록 취소 하는 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="20b4f-111">예제 3</span><span class="sxs-lookup"><span data-stu-id="20b4f-111">Example 3</span></span>

<span data-ttu-id="20b4f-112">다음 예제에서는 "Appliance1" 라는 이름으로 현재 기기를 "Site1" PSTN 사이트로 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="20b4f-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="20b4f-113">Detailed Description</span></span>
<span data-ttu-id="20b4f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="20b4f-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="20b4f-115">CcAppliance cmdlet과 유사 하 게, CloudConnector .ini 파일의 Edge 서버 외부 FQDN과 결합 된 SiteName은 PSTN 사이트 id로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="20b4f-116">마찬가지로, CloudConnector .ini 파일의 중재 서버 FQDN과 결합 한 ApplianceName는 기기 id로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="20b4f-117">기기의 등록을 취소 한 후에는 클라우드 커넥터 관리 서비스를 다시 시작 하 고 NetworkService 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="20b4f-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20b4f-118">Parameters</span></span>
<span data-ttu-id="20b4f-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="20b4f-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="20b4f-120">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="20b4f-120">**Parameter**</span></span>|<span data-ttu-id="20b4f-121">**필수**</span><span class="sxs-lookup"><span data-stu-id="20b4f-121">**Required**</span></span>|<span data-ttu-id="20b4f-122">**유형**</span><span class="sxs-lookup"><span data-stu-id="20b4f-122">**Type**</span></span>|<span data-ttu-id="20b4f-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="20b4f-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="20b4f-124">Name</span><span class="sxs-lookup"><span data-stu-id="20b4f-124">SiteName</span></span> <br/> |<span data-ttu-id="20b4f-125">선택</span><span class="sxs-lookup"><span data-stu-id="20b4f-125">Optional</span></span>  <br/> |<span data-ttu-id="20b4f-126">System.String</span><span class="sxs-lookup"><span data-stu-id="20b4f-126">System.String</span></span>  <br/> |<span data-ttu-id="20b4f-127">기기가 등록 된 PSTN 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="20b4f-128">기본 값은 CloudConnector .ini 파일의 SiteName 값입니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="20b4f-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="20b4f-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="20b4f-130">선택</span><span class="sxs-lookup"><span data-stu-id="20b4f-130">Optional</span></span>  <br/> |<span data-ttu-id="20b4f-131">System.String</span><span class="sxs-lookup"><span data-stu-id="20b4f-131">System.String</span></span>  <br/> |<span data-ttu-id="20b4f-132">현재 기기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-132">Name of the current appliance.</span></span> <span data-ttu-id="20b4f-133">Default 값은 호스트 서버의 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="20b4f-134">로컬</span><span class="sxs-lookup"><span data-stu-id="20b4f-134">Local</span></span>  <br/> |<span data-ttu-id="20b4f-135">선택</span><span class="sxs-lookup"><span data-stu-id="20b4f-135">Optional</span></span>  <br/> |<span data-ttu-id="20b4f-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="20b4f-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="20b4f-137">온라인 테 넌 트 구성에 연결 하지 않고 로컬에서 등록에 대 한 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="20b4f-138">입력 형식</span><span class="sxs-lookup"><span data-stu-id="20b4f-138">Input Types</span></span>
<span data-ttu-id="20b4f-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20b4f-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="20b4f-140">없음.</span><span class="sxs-lookup"><span data-stu-id="20b4f-140">None.</span></span> <span data-ttu-id="20b4f-141">CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20b4f-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="20b4f-142">반환 형식</span><span class="sxs-lookup"><span data-stu-id="20b4f-142">Return Types</span></span>
<span data-ttu-id="20b4f-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20b4f-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="20b4f-144">없음</span><span class="sxs-lookup"><span data-stu-id="20b4f-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20b4f-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20b4f-145">See also</span></span>
<span data-ttu-id="20b4f-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20b4f-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="20b4f-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="20b4f-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="20b4f-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="20b4f-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="20b4f-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="20b4f-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="20b4f-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="20b4f-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

