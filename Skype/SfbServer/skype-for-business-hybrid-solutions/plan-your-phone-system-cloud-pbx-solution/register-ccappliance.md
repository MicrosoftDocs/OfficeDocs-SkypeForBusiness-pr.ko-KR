---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: 등록-CcAppliance cmdlet는 온라인 테 넌 트 구성의 PSTN 사이트에 기기 정보를 등록 합니다. 비즈니스용 Skype 클라우드 커넥터 에디션 관리 서비스에서 기기를 배포 하 고 관리 하기 전에 먼저 등록 해야 합니다.
ms.openlocfilehash: 93f1fe59a199214615c5ecdf8445f6c363ce6bbe
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003308"
---
# <a name="register-ccappliance"></a><span data-ttu-id="7d4d4-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7d4d4-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="7d4d4-105">등록-CcAppliance cmdlet는 온라인 테 넌 트 구성의 PSTN 사이트에 기기 정보를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="7d4d4-106">비즈니스용 Skype 클라우드 커넥터 에디션 관리 서비스에서 기기를 배포 하 고 관리 하기 전에 먼저 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="7d4d4-107">예제</span><span class="sxs-lookup"><span data-stu-id="7d4d4-107">Examples</span></span>
<span data-ttu-id="7d4d4-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7d4d4-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="7d4d4-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="7d4d4-109">Example 1</span></span>

<span data-ttu-id="7d4d4-110">다음 예에서는 현재 기기 정보를 온라인 테 넌 트 구성에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="7d4d4-111">예제 2</span><span class="sxs-lookup"><span data-stu-id="7d4d4-111">Example 2</span></span>

<span data-ttu-id="7d4d4-112">다음 예제에서는 온라인 테 넌 트 구성에 연결 하지 않고 로컬로 등록 구성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="7d4d4-113">예제 3</span><span class="sxs-lookup"><span data-stu-id="7d4d4-113">Example 3</span></span>

<span data-ttu-id="7d4d4-114">다음 예에서는 "Appliance1" 라는 이름의 현재 기기를 PSTN 사이트 "Site1"에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="7d4d4-115">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="7d4d4-115">Detailed Description</span></span>
<span data-ttu-id="7d4d4-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d4d4-116"></span></span>

<span data-ttu-id="7d4d4-117">테 넌 트 관리 계정 이름 및 암호를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="7d4d4-118">클라우드 커넥터 온라인 관리에 대해 만든 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="7d4d4-119">릴리스 1.4.2 및 이전 버전의 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호, VM 관리자 암호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="7d4d4-120">릴리스 2.0 이상에서는 지침에 따라 외부 인증서 암호, CceService password 및 CABackupFile 암호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="7d4d4-121">등록이 종료 되 면 클라우드 커넥터 관리 서비스를 다시 시작 하 고 서비스에 CceService 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="7d4d4-122">CloudConnector .ini 파일의 Edge 서버 외부 FQDN과 결합 된 SiteName은 PSTN 사이트 id로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="7d4d4-123">사이트를 등록 하는 데 SiteName 또는 Edge 서버 외부 FQDN을 사용 하지 않은 경우 온라인 테 넌 트 구성에서이 기기에 대 한 새 사이트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="7d4d4-124">PSTN 사이트 id가 발견 되 면 PSTN 사이트는이 id를 사용 하 고 기기는이 PSTN 사이트에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="7d4d4-125">다음과 같은 경우에는 cmdlet이 실패 하 고 Site1가 이미 등록 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="7d4d4-126">SiteName은 Site1이 고 Edge 서버 외부 FQDN은 edgserver1.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="7d4d4-127">SiteName이 Site1 및 Edge 서버 외부 FQDN 인 PSTN 사이트는 edgserver.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="7d4d4-128">SiteName이 NewSite 및 Edge 서버 외부 FQDN 인 PSTN 사이트는 edgserver1.contoso.com 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="7d4d4-129">ApplianceName는 CloudConnector .ini 파일의 중재 서버 FQDN과 결합 된 것을 기기 Id로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="7d4d4-130">기기를 등록 하는 데 ApplianceName 또는 중재 서버 FQDN이 모두 사용 되지 않은 경우, 온라인 테 넌 트 구성에서 새 기기가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="7d4d4-131">기기가 이미 등록 되어 있으면 cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="7d4d4-132">다음과 같은 경우에는 cmdlet이 실패 하 고 기기가 이미 등록 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="7d4d4-133">ApplianceName는 Appliance1이 고 중재 서버 FQDN은 ms1.vdomain.com입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="7d4d4-134">현재 PSTN 사이트에서 이름이 Appliance1이 고, 중재 서버 FQDN이 ms.vdomain.com 이거나, 이름 NewAppliance 및 중재 서버 FQDN이 ms1.vdomain.com 인 기기가 등록 되어 있는 경우에는이를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="7d4d4-135">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d4d4-135">Parameters</span></span>
<span data-ttu-id="7d4d4-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d4d4-136"></span></span>

|<span data-ttu-id="7d4d4-137">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="7d4d4-137">**Parameter**</span></span>|<span data-ttu-id="7d4d4-138">**필수**</span><span class="sxs-lookup"><span data-stu-id="7d4d4-138">**Required**</span></span>|<span data-ttu-id="7d4d4-139">**유형**</span><span class="sxs-lookup"><span data-stu-id="7d4d4-139">**Type**</span></span>|<span data-ttu-id="7d4d4-140">**설명**</span><span class="sxs-lookup"><span data-stu-id="7d4d4-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d4d4-141">Name</span><span class="sxs-lookup"><span data-stu-id="7d4d4-141">SiteName</span></span>  <br/> |<span data-ttu-id="7d4d4-142">선택</span><span class="sxs-lookup"><span data-stu-id="7d4d4-142">Optional</span></span>  <br/> |<span data-ttu-id="7d4d4-143">System.String</span><span class="sxs-lookup"><span data-stu-id="7d4d4-143">System.String</span></span>  <br/> |<span data-ttu-id="7d4d4-144">기기가 등록 된 PSTN 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="7d4d4-145">기본값은 CloudConnector .ini 파일의 SiteName 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="7d4d4-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="7d4d4-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="7d4d4-147">선택</span><span class="sxs-lookup"><span data-stu-id="7d4d4-147">Optional</span></span>  <br/> |<span data-ttu-id="7d4d4-148">System.String</span><span class="sxs-lookup"><span data-stu-id="7d4d4-148">System.String</span></span>  <br/> |<span data-ttu-id="7d4d4-149">현재 기기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-149">Name of the current appliance.</span></span> <span data-ttu-id="7d4d4-150">Default 값은 호스트 서버의 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="7d4d4-151">로컬</span><span class="sxs-lookup"><span data-stu-id="7d4d4-151">Local</span></span>  <br/> |<span data-ttu-id="7d4d4-152">선택</span><span class="sxs-lookup"><span data-stu-id="7d4d4-152">Optional</span></span>  <br/> |<span data-ttu-id="7d4d4-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7d4d4-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7d4d4-154">온라인 테 넌 트 구성에 연결 하지 않고 로컬에서 등록을 위한 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7d4d4-155">입력 형식</span><span class="sxs-lookup"><span data-stu-id="7d4d4-155">Input Types</span></span>
<span data-ttu-id="7d4d4-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d4d4-156"></span></span>

<span data-ttu-id="7d4d4-157">없음.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-157">None.</span></span> <span data-ttu-id="7d4d4-158">등록-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d4d4-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7d4d4-159">반환 형식</span><span class="sxs-lookup"><span data-stu-id="7d4d4-159">Return Types</span></span>
<span data-ttu-id="7d4d4-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d4d4-160"></span></span>

<span data-ttu-id="7d4d4-161">없음</span><span class="sxs-lookup"><span data-stu-id="7d4d4-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d4d4-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d4d4-162">See also</span></span>
<span data-ttu-id="7d4d4-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d4d4-163"></span></span>

[<span data-ttu-id="7d4d4-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7d4d4-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="7d4d4-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7d4d4-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="7d4d4-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7d4d4-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="7d4d4-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7d4d4-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

