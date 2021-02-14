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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: 이 Register-CcAppliance cmdlet은 온라인 테넌트 구성의 PSTN 사이트에 어플라이언스 정보를 등록합니다. 비즈니스용 Skype 클라우드 커넥터 버전 관리 서비스에서 어플라이언스를 배포하고 관리하려면 먼저 어플라이언스를 등록해야 합니다.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824304"
---
# <a name="register-ccappliance"></a><span data-ttu-id="c2279-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c2279-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="c2279-105">이 Register-CcAppliance cmdlet은 온라인 테넌트 구성의 PSTN 사이트에 어플라이언스 정보를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="c2279-106">비즈니스용 Skype 클라우드 커넥터 버전 관리 서비스에서 어플라이언스를 배포하고 관리하려면 먼저 어플라이언스를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="c2279-107">예</span><span class="sxs-lookup"><span data-stu-id="c2279-107">Examples</span></span>
<span data-ttu-id="c2279-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2279-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c2279-109">예 1</span><span class="sxs-lookup"><span data-stu-id="c2279-109">Example 1</span></span>

<span data-ttu-id="c2279-110">다음 예에서는 현재 어플라이언스 정보를 온라인 테넌트 구성에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="c2279-111">예 2</span><span class="sxs-lookup"><span data-stu-id="c2279-111">Example 2</span></span>

<span data-ttu-id="c2279-112">다음 예제에서는 온라인 테넌트 구성에 연결하지 않고 로컬로 등록에 대한 구성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="c2279-113">예 3</span><span class="sxs-lookup"><span data-stu-id="c2279-113">Example 3</span></span>

<span data-ttu-id="c2279-114">다음 예제에서는 이름이 "Appliance1"인 현재 어플라이언스를 PSTN 사이트 "Site1"에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="c2279-115">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c2279-115">Detailed Description</span></span>
<span data-ttu-id="c2279-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c2279-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c2279-117">테넌트 관리자 계정 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="c2279-118">클라우드 커넥터 온라인 관리를 위해 만든 계정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c2279-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="c2279-119">릴리스 1.4.2 이전 버전에서는 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="c2279-120">릴리스 2.0 이상에서 지침에 따라 외부 인증서 암호, CceService 암호 및 CABackupFile 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="c2279-121">등록이 끝나면 클라우드 커넥터 관리 서비스를 다시 시작하고 CceService 계정으로 서비스에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="c2279-122">CloudConnector.ini 에지 서버 외부 FQDN과 결합된 SiteName은 PSTN 사이트 ID로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="c2279-123">사이트를 등록하는 데 SiteName과 에지 서버 외부 FQDN이 모두 사용되지 않은 경우 온라인 테넌트 구성에서 이 어플라이언스에 대한 새 사이트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="c2279-124">PSTN 사이트 ID가 발견되는 경우 PSTN 사이트에서 이 ID를 사용하며 어플라이언스가 이 PSTN 사이트에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="c2279-125">다음 상황에서는 cmdlet이 실패하고 Site1이 이미 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="c2279-126">SiteName은 Site1이고 에지 서버 외부 FQDN은 edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c2279-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="c2279-127">SiteName이 Site1인 PSTN 사이트와 에지 서버 외부 FQDN이 edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c2279-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="c2279-128">SiteName이 NewSite이고 에지 서버 외부 FQDN이 등록된 PSTN edgserver1.contoso.com 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="c2279-129">CloudConnector.ini 중재 서버 FQDN과 결합된 ApplianceName은 Appliance ID로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="c2279-130">ApplianceName과 중재 서버 FQDN을 모두 사용하여 어플라이언스를 등록하지 않은 경우 온라인 테넌트 구성에서 새 어플라이언스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="c2279-131">어플라이언스가 이미 등록되어 있는 경우 cmdlet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="c2279-132">다음 상황에서는 cmdlet이 실패하고 어플라이언스가 이미 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="c2279-133">ApplianceName은 Appliance1이고 중재 서버 FQDN이 ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="c2279-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="c2279-134">현재 PSTN 사이트에서 Appliance1 및 Mediation Server FQDN 이름이 Appliance1인 어플라이언스 또는 ms.vdomain.com 이름이 NewAppliance 및 Mediation 서버 FQDN이 등록된 어플라이언스인 ms1.vdomain.com 경우.</span><span class="sxs-lookup"><span data-stu-id="c2279-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="c2279-135">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2279-135">Parameters</span></span>
<span data-ttu-id="c2279-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c2279-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c2279-137">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="c2279-137">**Parameter**</span></span>|<span data-ttu-id="c2279-138">**필수**</span><span class="sxs-lookup"><span data-stu-id="c2279-138">**Required**</span></span>|<span data-ttu-id="c2279-139">**유형**</span><span class="sxs-lookup"><span data-stu-id="c2279-139">**Type**</span></span>|<span data-ttu-id="c2279-140">**설명**</span><span class="sxs-lookup"><span data-stu-id="c2279-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2279-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="c2279-141">SiteName</span></span>  <br/> |<span data-ttu-id="c2279-142">옵션</span><span class="sxs-lookup"><span data-stu-id="c2279-142">Optional</span></span>  <br/> |<span data-ttu-id="c2279-143">System.String</span><span class="sxs-lookup"><span data-stu-id="c2279-143">System.String</span></span>  <br/> |<span data-ttu-id="c2279-144">어플라이언스가 등록된 PSTN 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="c2279-145">기본값은 사이트 파일에서 SiteName CloudConnector.ini 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="c2279-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="c2279-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="c2279-147">옵션</span><span class="sxs-lookup"><span data-stu-id="c2279-147">Optional</span></span>  <br/> |<span data-ttu-id="c2279-148">System.String</span><span class="sxs-lookup"><span data-stu-id="c2279-148">System.String</span></span>  <br/> |<span data-ttu-id="c2279-149">현재 어플라이언스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-149">Name of the current appliance.</span></span> <span data-ttu-id="c2279-150">기본값은 호스트 서버의 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="c2279-151">로컬</span><span class="sxs-lookup"><span data-stu-id="c2279-151">Local</span></span>  <br/> |<span data-ttu-id="c2279-152">선택</span><span class="sxs-lookup"><span data-stu-id="c2279-152">Optional</span></span>  <br/> |<span data-ttu-id="c2279-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c2279-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c2279-154">온라인 테넌트 구성에 연결하지 않고 로컬로 등록에 대한 구성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c2279-155">입력 형식</span><span class="sxs-lookup"><span data-stu-id="c2279-155">Input Types</span></span>
<span data-ttu-id="c2279-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c2279-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c2279-157">없음</span><span class="sxs-lookup"><span data-stu-id="c2279-157">None.</span></span> <span data-ttu-id="c2279-158">이 Register-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2279-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c2279-159">반환 형식</span><span class="sxs-lookup"><span data-stu-id="c2279-159">Return Types</span></span>
<span data-ttu-id="c2279-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c2279-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c2279-161">없음</span><span class="sxs-lookup"><span data-stu-id="c2279-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c2279-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2279-162">See also</span></span>
<span data-ttu-id="c2279-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c2279-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c2279-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c2279-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="c2279-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c2279-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="c2279-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c2279-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="c2279-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c2279-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

