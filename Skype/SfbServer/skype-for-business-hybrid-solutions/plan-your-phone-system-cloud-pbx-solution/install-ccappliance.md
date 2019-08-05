---
title: 설치-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 설치-CcAppliance cmdlet는 AD, 중앙 관리 저장소, 중재 서버, Edge 서버 가상 컴퓨터 등의 비즈니스용 Skype 클라우드 커넥터 에디션 기기를 호스트 서버에 설치 합니다.
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190734"
---
# <a name="install-ccappliance"></a><span data-ttu-id="d5188-103">설치-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d5188-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="d5188-104">설치-CcAppliance cmdlet는 AD, 중앙 관리 저장소, 중재 서버, Edge 서버 가상 컴퓨터 등의 비즈니스용 Skype 클라우드 커넥터 에디션 기기를 호스트 서버에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="d5188-105">예제</span><span class="sxs-lookup"><span data-stu-id="d5188-105">Examples</span></span>
<span data-ttu-id="d5188-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d5188-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d5188-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="d5188-107">Example 1</span></span>

<span data-ttu-id="d5188-108">다음 예제에서는 호스트 서버에 새 클라우드 커넥터 기기를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="d5188-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="d5188-109">Example 2</span></span>

<span data-ttu-id="d5188-110">다음 예에서는 클라우드 커넥터를 최신 버전으로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="d5188-111">예제 3</span><span class="sxs-lookup"><span data-stu-id="d5188-111">Example 3</span></span>

<span data-ttu-id="d5188-112">다음 예제에서는 호스트 서버에서 캐시 된 모든 클라우드 커넥터 자격 증명을 제거 하 고, 사용자에 게 모든 자격 증명 정보를 다시 지정 하 라는 메시지를 표시 한 후 클라우드 커넥터를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="d5188-113">예제 4</span><span class="sxs-lookup"><span data-stu-id="d5188-113">Example 4</span></span>

<span data-ttu-id="d5188-114">다음 예제에서는 PowerShell 콘솔의 모든 배포 단계를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="d5188-115">-ShowStepsOnly 매개 변수는 문제 해결만을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="d5188-116">예제 5</span><span class="sxs-lookup"><span data-stu-id="d5188-116">Example 5</span></span>

<span data-ttu-id="d5188-117">다음 예제에서는 호스트 서버의 각 배포 단계에 대 한 구성 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="d5188-118">구성 파일은 호스트 \<서버의 ApplianceRoot\>\instances\\<버전\>-default\ExportedConfig 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="d5188-119">기기 루트를 확인 하려면 CcApplianceDirectory cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="d5188-120">예제 6</span><span class="sxs-lookup"><span data-stu-id="d5188-120">Example 6</span></span>

<span data-ttu-id="d5188-121">다음 예제에서 클라우드 커넥터는 배포 단계 1, 2, 3을 실행 하 여 가상 스위치를 만들고, 광고 가상 컴퓨터를 만들고, 광고 서버에 도메인 서비스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="d5188-122">단계가 이미 실행 된 경우 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-122">It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="d5188-123">SkipExistingObjects 매개 변수는 단계 매개 변수와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5188-124">단계 매개 변수는 문제 해결 목적 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="d5188-125">이 매개 변수를 사용 하 여 기기를 배포 하거나 서비스 기기를 업그레이드 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d5188-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="d5188-126">배포의 단계를 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="d5188-127">설치-CcAppliance-ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="d5188-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="d5188-128">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d5188-128">Detailed Description</span></span>
<span data-ttu-id="d5188-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d5188-129"></span></span>

<span data-ttu-id="d5188-130">설치-CcAppliance cmdlet은 새 기기에 클라우드 커넥터를 배포 하거나 기존 기기를 최신 버전으로 업그레이드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="d5188-131">새 기기가 있는 경우 먼저 클라우드 커넥터에 대 한 환경 준비를 읽고, 기기를 등록 하기 위해 등록-CcAppliance cmdlet을 실행 한 다음 Install-CcAppliance cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="d5188-132">자세한 내용은 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) 및 [클라우드 커넥터에 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5188-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="d5188-133">기존 클라우드 커넥터 배포가 있고 업그레이드 하려는 경우 [새 버전의 클라우드 커넥터로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d5188-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d5188-134">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5188-134">Parameters</span></span>
<span data-ttu-id="d5188-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d5188-135"></span></span>

|<span data-ttu-id="d5188-136">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="d5188-136">**Parameter**</span></span>|<span data-ttu-id="d5188-137">**필수**</span><span class="sxs-lookup"><span data-stu-id="d5188-137">**Required**</span></span>|<span data-ttu-id="d5188-138">**유형**</span><span class="sxs-lookup"><span data-stu-id="d5188-138">**Type**</span></span>|<span data-ttu-id="d5188-139">**설명**</span><span class="sxs-lookup"><span data-stu-id="d5188-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5188-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="d5188-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="d5188-141">선택</span><span class="sxs-lookup"><span data-stu-id="d5188-141">Optional</span></span>  <br/> |<span data-ttu-id="d5188-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d5188-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="d5188-143">각 배포 단계에 대 한 구성 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="d5188-144">이 매개 변수는 문제 해결에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="d5188-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="d5188-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="d5188-146">선택</span><span class="sxs-lookup"><span data-stu-id="d5188-146">Optional</span></span>  <br/> |<span data-ttu-id="d5188-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d5188-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d5188-148">배포 단계 이름만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-148">Display deployment step names only.</span></span> <span data-ttu-id="d5188-149">이 매개 변수는 문제 해결에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="d5188-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="d5188-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="d5188-151">선택</span><span class="sxs-lookup"><span data-stu-id="d5188-151">Optional</span></span>  <br/> |<span data-ttu-id="d5188-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d5188-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d5188-153">이 매개 변수는 단계 매개 변수와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="d5188-154">이 매개 변수는 문제 해결에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="d5188-155">방법은</span><span class="sxs-lookup"><span data-stu-id="d5188-155">Steps</span></span>  <br/> |<span data-ttu-id="d5188-156">선택</span><span class="sxs-lookup"><span data-stu-id="d5188-156">Optional</span></span>  <br/> |<span data-ttu-id="d5188-157">System. Array</span><span class="sxs-lookup"><span data-stu-id="d5188-157">System.Array</span></span>  <br/> |<span data-ttu-id="d5188-158">배포 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-158">Run the deployment steps.</span></span> <span data-ttu-id="d5188-159">이 매개 변수는 문제 해결에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="d5188-160">업그레이드</span><span class="sxs-lookup"><span data-stu-id="d5188-160">Upgrade</span></span>  <br/> |<span data-ttu-id="d5188-161">선택</span><span class="sxs-lookup"><span data-stu-id="d5188-161">Optional</span></span>  <br/> |<span data-ttu-id="d5188-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d5188-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d5188-163">기존 클라우드 커넥터를 최신 버전으로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="d5188-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="d5188-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="d5188-165">선택</span><span class="sxs-lookup"><span data-stu-id="d5188-165">Optional</span></span>  <br/> |<span data-ttu-id="d5188-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d5188-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d5188-167">모든 클라우드 커넥터 자격 증명을 캐시에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="d5188-168">사용자에 게 설치에 대 한 새 자격 증명 정보를 지정 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d5188-169">입력 형식</span><span class="sxs-lookup"><span data-stu-id="d5188-169">Input Types</span></span>
<span data-ttu-id="d5188-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d5188-170"></span></span>

<span data-ttu-id="d5188-171">없음.</span><span class="sxs-lookup"><span data-stu-id="d5188-171">None.</span></span> <span data-ttu-id="d5188-172">설치-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5188-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d5188-173">반환 형식</span><span class="sxs-lookup"><span data-stu-id="d5188-173">Return Types</span></span>
<span data-ttu-id="d5188-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d5188-174"></span></span>

<span data-ttu-id="d5188-175">없음</span><span class="sxs-lookup"><span data-stu-id="d5188-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d5188-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5188-176">See also</span></span>
<span data-ttu-id="d5188-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d5188-177"></span></span>

[<span data-ttu-id="d5188-178">게시-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d5188-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="d5188-179">등록-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d5188-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d5188-180">CcAppliance 등록 취소</span><span class="sxs-lookup"><span data-stu-id="d5188-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="d5188-181">제거-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d5188-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

