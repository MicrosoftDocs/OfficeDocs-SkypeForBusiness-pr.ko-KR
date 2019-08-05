---
title: CcAppliance 등록 취소
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: 비 CcAppliance cmdlet은 온라인 테 넌 트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 등록을 취소 합니다.
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190587"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="fc821-103">CcAppliance 등록 취소</span><span class="sxs-lookup"><span data-stu-id="fc821-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="fc821-104">비 CcAppliance cmdlet은 온라인 테 넌 트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="fc821-105">예제</span><span class="sxs-lookup"><span data-stu-id="fc821-105">Examples</span></span>
<span data-ttu-id="fc821-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fc821-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="fc821-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="fc821-107">Example 1</span></span>

<span data-ttu-id="fc821-108">다음 예에서는 온라인 테 넌 트 구성에서 현재 기기의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="fc821-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="fc821-109">Example 2</span></span>

<span data-ttu-id="fc821-110">다음 예제에서는 온라인 테 넌 트 구성에 연결 하지 않고 로컬로 등록 취소 하는 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="fc821-111">예제 3</span><span class="sxs-lookup"><span data-stu-id="fc821-111">Example 3</span></span>

<span data-ttu-id="fc821-112">다음 예제에서는 "Appliance1" 라는 이름으로 현재 기기를 "Site1" PSTN 사이트로 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="fc821-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="fc821-113">Detailed Description</span></span>
<span data-ttu-id="fc821-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fc821-114"></span></span>

<span data-ttu-id="fc821-115">CcAppliance cmdlet과 유사 하 게, CloudConnector .ini 파일의 Edge 서버 외부 FQDN과 결합 된 SiteName은 PSTN 사이트 id로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="fc821-116">마찬가지로, CloudConnector .ini 파일의 중재 서버 FQDN과 결합 한 ApplianceName는 기기 id로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="fc821-117">기기의 등록을 취소 한 후에는 클라우드 커넥터 관리 서비스를 다시 시작 하 고 NetworkService 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fc821-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc821-118">Parameters</span></span>
<span data-ttu-id="fc821-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fc821-119"></span></span>

|<span data-ttu-id="fc821-120">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="fc821-120">**Parameter**</span></span>|<span data-ttu-id="fc821-121">**필수**</span><span class="sxs-lookup"><span data-stu-id="fc821-121">**Required**</span></span>|<span data-ttu-id="fc821-122">**유형**</span><span class="sxs-lookup"><span data-stu-id="fc821-122">**Type**</span></span>|<span data-ttu-id="fc821-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="fc821-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fc821-124">Name</span><span class="sxs-lookup"><span data-stu-id="fc821-124">SiteName</span></span> <br/> |<span data-ttu-id="fc821-125">선택</span><span class="sxs-lookup"><span data-stu-id="fc821-125">Optional</span></span>  <br/> |<span data-ttu-id="fc821-126">System.String</span><span class="sxs-lookup"><span data-stu-id="fc821-126">System.String</span></span>  <br/> |<span data-ttu-id="fc821-127">기기가 등록 된 PSTN 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="fc821-128">기본 값은 CloudConnector .ini 파일의 SiteName 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="fc821-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="fc821-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="fc821-130">선택</span><span class="sxs-lookup"><span data-stu-id="fc821-130">Optional</span></span>  <br/> |<span data-ttu-id="fc821-131">System.String</span><span class="sxs-lookup"><span data-stu-id="fc821-131">System.String</span></span>  <br/> |<span data-ttu-id="fc821-132">현재 기기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-132">Name of the current appliance.</span></span> <span data-ttu-id="fc821-133">Default 값은 호스트 서버의 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="fc821-134">로컬</span><span class="sxs-lookup"><span data-stu-id="fc821-134">Local</span></span>  <br/> |<span data-ttu-id="fc821-135">선택</span><span class="sxs-lookup"><span data-stu-id="fc821-135">Optional</span></span>  <br/> |<span data-ttu-id="fc821-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fc821-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fc821-137">온라인 테 넌 트 구성에 연결 하지 않고 로컬에서 등록에 대 한 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fc821-138">입력 형식</span><span class="sxs-lookup"><span data-stu-id="fc821-138">Input Types</span></span>
<span data-ttu-id="fc821-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc821-139"></span></span>

<span data-ttu-id="fc821-140">없음.</span><span class="sxs-lookup"><span data-stu-id="fc821-140">None.</span></span> <span data-ttu-id="fc821-141">CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc821-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fc821-142">반환 형식</span><span class="sxs-lookup"><span data-stu-id="fc821-142">Return Types</span></span>
<span data-ttu-id="fc821-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc821-143"></span></span>

<span data-ttu-id="fc821-144">없음</span><span class="sxs-lookup"><span data-stu-id="fc821-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc821-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc821-145">See also</span></span>
<span data-ttu-id="fc821-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc821-146"></span></span>

[<span data-ttu-id="fc821-147">등록-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fc821-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="fc821-148">설치-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fc821-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="fc821-149">제거-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fc821-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="fc821-150">게시-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fc821-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

