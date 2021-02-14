---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: 이 Convert-CcIsoToVhdx cmdlet은 고객이 R2 ISO 파일로 제공한 기본 VHDX(Windows Server 2012 하드 디스크 파일)를 만듭니다. VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 버전 배포 중에 사용됩니다.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802428"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="3bb75-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="3bb75-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="3bb75-105">이 Convert-CcIsoToVhdx cmdlet은 고객이 R2 ISO 파일로 제공한 기본 VHDX(Windows Server 2012 하드 디스크 파일)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="3bb75-106">VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 버전 배포 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="3bb75-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bb75-107">Parameters</span></span>

|<span data-ttu-id="3bb75-108">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3bb75-108">**Parameter**</span></span>|<span data-ttu-id="3bb75-109">**필수**</span><span class="sxs-lookup"><span data-stu-id="3bb75-109">**Required**</span></span>|<span data-ttu-id="3bb75-110">**유형**</span><span class="sxs-lookup"><span data-stu-id="3bb75-110">**Type**</span></span>|<span data-ttu-id="3bb75-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="3bb75-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3bb75-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="3bb75-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="3bb75-113">필수</span><span class="sxs-lookup"><span data-stu-id="3bb75-113">Required</span></span> <br/> |<span data-ttu-id="3bb75-114">System.String</span><span class="sxs-lookup"><span data-stu-id="3bb75-114">System.String</span></span>  <br/> | <span data-ttu-id="3bb75-115">R2 ISO Windows Server 2012 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="3bb75-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="3bb75-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="3bb75-117">선택</span><span class="sxs-lookup"><span data-stu-id="3bb75-117">Optional</span></span>  <br/> |<span data-ttu-id="3bb75-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3bb75-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3bb75-119">Windows 업데이트 중에 변환 프로세스가 실패하면 네트워크/프록시를 구성하고 Windows를 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="3bb75-120">수동 작업이 완료되면 -GeneralizeOnly 매개 변수를 사용하여 이 cmdlet을 실행할 수 있으며 나머지 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="3bb75-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="3bb75-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="3bb75-122">선택</span><span class="sxs-lookup"><span data-stu-id="3bb75-122">Optional</span></span>  <br/> |<span data-ttu-id="3bb75-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3bb75-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3bb75-124">Windows를 업데이트하려면 기본 VM의 일부 수동 네트워크/프록시 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="3bb75-125">이 매개 변수를 제공하는 경우 Windows 업데이트 전에 변환 프로세스가 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="3bb75-126">수동 구성이 완료되면 프로세스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="3bb75-127">예</span><span class="sxs-lookup"><span data-stu-id="3bb75-127">Examples</span></span>
<span data-ttu-id="3bb75-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3bb75-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3bb75-129">예 1</span><span class="sxs-lookup"><span data-stu-id="3bb75-129">Example 1</span></span>

<span data-ttu-id="3bb75-130">다음 예제에서는 "C:\Windows_Server_2012_R2-EN-US-x64.ISO"에 있는 Windows Server 2012 R2 ISO 파일을 사용하여 기본 VHDX 파일을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="3bb75-131">예 2</span><span class="sxs-lookup"><span data-stu-id="3bb75-131">Example 2</span></span>

<span data-ttu-id="3bb75-132">Windows 업데이트 Convert-CcIsoToVhdx cmdlet이 실패하는 경우 잘못된 네트워크/프록시 구성으로인 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="3bb75-133">오류 메시지의 지침에 따라 기본 가상 머신에 로그온하여 문제를 해결하고 Windows를 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="3bb75-134">수동 작업이 완료되면 -GeneralizeOnly 매개 변수를 사용하여 cmdlet을 다시 실행하여 나머지 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="3bb75-135">예 3</span><span class="sxs-lookup"><span data-stu-id="3bb75-135">Example 3</span></span>

<span data-ttu-id="3bb75-136">Windows를 업데이트하는 데 수동 구성이 필요한 경우 -PauseBeforeUpdate 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="3bb75-137">이 매개 변수를 사용하면 클라우드 커넥터가 Windows 업데이트 프로세스 전에 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="3bb75-138">그런 다음 수동 구성을 완료하고 다음과 같이 변환 프로세스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="3bb75-139">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="3bb75-139">Detailed Description</span></span>
<span data-ttu-id="3bb75-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3bb75-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3bb75-141">이 Convert-CcIsoToVhdx 먼저 기본 VM을 만들고 클라우드 커넥터가 사용하는 몇 가지 기본 구성 요소를 설치한 다음 Windows 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="3bb75-142">마지막으로 가상 컴퓨터(sysprep)를 일반화하여 클라우드 커넥터 어플라이언스의 가상 머신에서 사용할 기본 VHDX 파일을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="3bb75-143">입력 형식</span><span class="sxs-lookup"><span data-stu-id="3bb75-143">Input Types</span></span>
<span data-ttu-id="3bb75-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3bb75-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3bb75-145">없음</span><span class="sxs-lookup"><span data-stu-id="3bb75-145">None.</span></span> <span data-ttu-id="3bb75-146">이 Convert-CcIsoToVhdx cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb75-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="3bb75-147">반환 형식</span><span class="sxs-lookup"><span data-stu-id="3bb75-147">Return Types</span></span>
<span data-ttu-id="3bb75-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3bb75-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3bb75-149">없음</span><span class="sxs-lookup"><span data-stu-id="3bb75-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bb75-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bb75-150">See also</span></span>
<span data-ttu-id="3bb75-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3bb75-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3bb75-152">없음</span><span class="sxs-lookup"><span data-stu-id="3bb75-152">None</span></span>
  

