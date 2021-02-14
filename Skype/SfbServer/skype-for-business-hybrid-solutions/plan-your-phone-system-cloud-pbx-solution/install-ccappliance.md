---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 이 Install-CcAppliance cmdlet은 호스트 서버에 AD, 중앙 관리 저장소, 중재 서버 및 에지 서버 가상 컴퓨터를 비롯한 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 설치합니다.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799878"
---
# <a name="install-ccappliance"></a><span data-ttu-id="3cf10-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf10-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="3cf10-104">이 Install-CcAppliance cmdlet은 호스트 서버에 AD, 중앙 관리 저장소, 중재 서버 및 에지 서버 가상 컴퓨터를 비롯한 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3cf10-105">예</span><span class="sxs-lookup"><span data-stu-id="3cf10-105">Examples</span></span>
<span data-ttu-id="3cf10-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3cf10-107">예 1</span><span class="sxs-lookup"><span data-stu-id="3cf10-107">Example 1</span></span>

<span data-ttu-id="3cf10-108">다음 예에서는 호스트 서버에 새 Cloud Connector 어플라이언스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="3cf10-109">예 2</span><span class="sxs-lookup"><span data-stu-id="3cf10-109">Example 2</span></span>

<span data-ttu-id="3cf10-110">다음 예에서는 Cloud Connector를 최신 버전으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="3cf10-111">예 3</span><span class="sxs-lookup"><span data-stu-id="3cf10-111">Example 3</span></span>

<span data-ttu-id="3cf10-112">다음 예에서는 호스트 서버에 캐시된 모든 클라우드 커넥터 자격 증명을 제거하고 사용자에게 모든 자격 증명 정보를 다시 지정하라는 메시지를 표시한 다음 클라우드 커넥터를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="3cf10-113">예 4</span><span class="sxs-lookup"><span data-stu-id="3cf10-113">Example 4</span></span>

<span data-ttu-id="3cf10-114">다음 예제에서는 PowerShell 콘솔의 모든 배포 단계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="3cf10-115">-ShowStepsOnly 매개 변수는 문제 해결 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="3cf10-116">예 5</span><span class="sxs-lookup"><span data-stu-id="3cf10-116">Example 5</span></span>

<span data-ttu-id="3cf10-117">다음 예제에서는 호스트 서버의 각 배포 단계에 대한 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="3cf10-118">구성 파일은 호스트 서버의 \< ApplianceRoot \> \Instances<\\ \> -default\ExportedConfig 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="3cf10-119">어플라이언스 루트를 확인하기 위해 Get-CcApplianceDirectory 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="3cf10-120">예 6</span><span class="sxs-lookup"><span data-stu-id="3cf10-120">Example 6</span></span>

<span data-ttu-id="3cf10-121">다음 예에서 Cloud Connector는 배포 1, 2 및 3단계를 실행하여 가상 스위치를 만들고 AD 가상 머신을 만들고 AD 서버에 도메인 서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="3cf10-122">단계가 이미 실행된 경우 이 단계를 건너뜁습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="3cf10-123">SkipExistingObjects 매개 변수는 Steps 매개 변수와 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cf10-124">Steps 매개 변수는 문제 해결 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="3cf10-125">이 매개 변수를 사용하여 어플라이언스를 배포하거나 서비스에 있는 어플라이언스를 업그레이드하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3cf10-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="3cf10-126">배포 단계를 결정하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="3cf10-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="3cf10-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="3cf10-128">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="3cf10-128">Detailed Description</span></span>
<span data-ttu-id="3cf10-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3cf10-130">이 Install-CcAppliance cmdlet은 클라우드 커넥터를 새 어플라이언스에 배포하거나 기존 어플라이언스를 최신 버전으로 업그레이드하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="3cf10-131">새 어플라이언스가 있는 경우 먼저 클라우드 커넥터에 대한 환경 준비를 읽고 Register-CcAppliance cmdlet을 실행하여 어플라이언스를 등록한 다음 Install-CcAppliance cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="3cf10-132">자세한 내용은 [클라우드](deploy-a-single-site-in-cloud-connector.md) 커넥터에서 단일 사이트 배포 및 클라우드 커넥터에서 여러 사이트 [배포를 참조하세요.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3cf10-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="3cf10-133">기존 클라우드 커넥터 배포가 있으며 업그레이드하려는 경우 새 버전의 클라우드 커넥터로 업그레이드의 [지침을 따르세요.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3cf10-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3cf10-134">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3cf10-134">Parameters</span></span>
<span data-ttu-id="3cf10-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="3cf10-136">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3cf10-136">**Parameter**</span></span>|<span data-ttu-id="3cf10-137">**필수**</span><span class="sxs-lookup"><span data-stu-id="3cf10-137">**Required**</span></span>|<span data-ttu-id="3cf10-138">**유형**</span><span class="sxs-lookup"><span data-stu-id="3cf10-138">**Type**</span></span>|<span data-ttu-id="3cf10-139">**설명**</span><span class="sxs-lookup"><span data-stu-id="3cf10-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3cf10-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="3cf10-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="3cf10-141">선택</span><span class="sxs-lookup"><span data-stu-id="3cf10-141">Optional</span></span>  <br/> |<span data-ttu-id="3cf10-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3cf10-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="3cf10-143">각 배포 단계에 대한 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="3cf10-144">이 매개 변수는 문제 해결 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="3cf10-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="3cf10-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="3cf10-146">선택</span><span class="sxs-lookup"><span data-stu-id="3cf10-146">Optional</span></span>  <br/> |<span data-ttu-id="3cf10-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3cf10-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3cf10-148">배포 단계 이름만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-148">Display deployment step names only.</span></span> <span data-ttu-id="3cf10-149">이 매개 변수는 문제 해결 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="3cf10-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="3cf10-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="3cf10-151">선택</span><span class="sxs-lookup"><span data-stu-id="3cf10-151">Optional</span></span>  <br/> |<span data-ttu-id="3cf10-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3cf10-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3cf10-153">이 매개 변수는 Steps 매개 변수와 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="3cf10-154">이 매개 변수는 문제 해결 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="3cf10-155">단계</span><span class="sxs-lookup"><span data-stu-id="3cf10-155">Steps</span></span>  <br/> |<span data-ttu-id="3cf10-156">선택</span><span class="sxs-lookup"><span data-stu-id="3cf10-156">Optional</span></span>  <br/> |<span data-ttu-id="3cf10-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="3cf10-157">System.Array</span></span>  <br/> |<span data-ttu-id="3cf10-158">배포 단계를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-158">Run the deployment steps.</span></span> <span data-ttu-id="3cf10-159">이 매개 변수는 문제 해결 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="3cf10-160">업그레이드</span><span class="sxs-lookup"><span data-stu-id="3cf10-160">Upgrade</span></span>  <br/> |<span data-ttu-id="3cf10-161">선택</span><span class="sxs-lookup"><span data-stu-id="3cf10-161">Optional</span></span>  <br/> |<span data-ttu-id="3cf10-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3cf10-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3cf10-163">기존 클라우드 커넥터를 최신 버전으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="3cf10-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="3cf10-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="3cf10-165">선택</span><span class="sxs-lookup"><span data-stu-id="3cf10-165">Optional</span></span>  <br/> |<span data-ttu-id="3cf10-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3cf10-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3cf10-167">캐시에서 모든 클라우드 커넥터 자격 증명을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="3cf10-168">사용자에게 설치에 대한 새 자격 증명 정보를 지정하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3cf10-169">입력 형식</span><span class="sxs-lookup"><span data-stu-id="3cf10-169">Input Types</span></span>
<span data-ttu-id="3cf10-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3cf10-171">없음</span><span class="sxs-lookup"><span data-stu-id="3cf10-171">None.</span></span> <span data-ttu-id="3cf10-172">이 Install-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf10-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3cf10-173">반환 형식</span><span class="sxs-lookup"><span data-stu-id="3cf10-173">Return Types</span></span>
<span data-ttu-id="3cf10-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3cf10-175">없음</span><span class="sxs-lookup"><span data-stu-id="3cf10-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3cf10-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cf10-176">See also</span></span>
<span data-ttu-id="3cf10-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3cf10-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf10-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="3cf10-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf10-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="3cf10-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf10-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="3cf10-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf10-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

