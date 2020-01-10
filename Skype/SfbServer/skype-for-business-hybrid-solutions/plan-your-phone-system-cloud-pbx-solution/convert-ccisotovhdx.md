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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: 변환-CcIsoToVhdx cmdlet은 고객이 제공 하는 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX (virtual 하드 디스크 파일)를 만듭니다. VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 에디션을 배포 하는 동안 사용 됩니다.
ms.openlocfilehash: 780002c54a77746c51f418cae077ffcc9b1fb608
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001348"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="05f38-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="05f38-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="05f38-105">변환-CcIsoToVhdx cmdlet은 고객이 제공 하는 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX (virtual 하드 디스크 파일)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="05f38-106">VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 에디션을 배포 하는 동안 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="05f38-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05f38-107">Parameters</span></span>

|<span data-ttu-id="05f38-108">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="05f38-108">**Parameter**</span></span>|<span data-ttu-id="05f38-109">**필수**</span><span class="sxs-lookup"><span data-stu-id="05f38-109">**Required**</span></span>|<span data-ttu-id="05f38-110">**유형**</span><span class="sxs-lookup"><span data-stu-id="05f38-110">**Type**</span></span>|<span data-ttu-id="05f38-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="05f38-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05f38-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="05f38-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="05f38-113">필수</span><span class="sxs-lookup"><span data-stu-id="05f38-113">Required</span></span> <br/> |<span data-ttu-id="05f38-114">System.String</span><span class="sxs-lookup"><span data-stu-id="05f38-114">System.String</span></span>  <br/> | <span data-ttu-id="05f38-115">Windows Server 2012 R2 ISO 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="05f38-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="05f38-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="05f38-117">선택</span><span class="sxs-lookup"><span data-stu-id="05f38-117">Optional</span></span>  <br/> |<span data-ttu-id="05f38-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="05f38-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="05f38-119">Windows 업데이트 중에 변환 프로세스가 실패 하는 경우 네트워크/프록시를 구성 하 고 Windows를 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="05f38-120">수동 작업이 완료 되 면-GeneralizeOnly 매개 변수를 사용 하 여이 cmdlet을 실행 하 고 나머지 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="05f38-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="05f38-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="05f38-122">선택</span><span class="sxs-lookup"><span data-stu-id="05f38-122">Optional</span></span>  <br/> |<span data-ttu-id="05f38-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="05f38-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="05f38-124">Windows를 업데이트 하려면 기본 VM의 일부 수동 네트워크/프록시 구성이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="05f38-125">이 매개 변수를 제공 하는 경우 Windows 업데이트 전에 변환 프로세스가 일시 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="05f38-126">수동 구성이 완료 된 후에는 프로세스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="05f38-127">예제</span><span class="sxs-lookup"><span data-stu-id="05f38-127">Examples</span></span>
<span data-ttu-id="05f38-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="05f38-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="05f38-129">예제 1</span><span class="sxs-lookup"><span data-stu-id="05f38-129">Example 1</span></span>

<span data-ttu-id="05f38-130">다음 예에서는 "C:\ Windows_Server_2012_R2-EN-US-x64: .ISO"에 있는 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX 파일을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="05f38-131">예제 2</span><span class="sxs-lookup"><span data-stu-id="05f38-131">Example 2</span></span>

<span data-ttu-id="05f38-132">Windows 업데이트 중에 Convert-CcIsoToVhdx cmdlet이 실패 하는 경우에는 잘못 된 네트워크/프록시 구성 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="05f38-133">오류 메시지의 지침에 따라 기본 가상 컴퓨터에 로그온 하 여 문제를 해결 하 고 Windows를 수동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="05f38-134">수동 작업이 완료 되 면-GeneralizeOnly 매개 변수를 사용 하 여 cmdlet을 다시 실행 하 여 나머지 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="05f38-135">예제 3</span><span class="sxs-lookup"><span data-stu-id="05f38-135">Example 3</span></span>

<span data-ttu-id="05f38-136">Windows를 업데이트 하는 데 수동 구성이 필요한 경우-PauseBeforeUpdate 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="05f38-137">이 매개 변수를 사용 하면 Windows 업데이트 프로세스 전에 클라우드 커넥터가 일시 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="05f38-138">그런 다음 수동 구성을 완료 하 고 다음과 같이 변환 프로세스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="05f38-139">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="05f38-139">Detailed Description</span></span>
<span data-ttu-id="05f38-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="05f38-140"></span></span>

<span data-ttu-id="05f38-141">Convert-CcIsoToVhdx cmdlet은 기본 VM을 먼저 만들고 클라우드 커넥터에 종속 된 몇 가지 기본 구성 요소를 설치한 다음 Windows 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="05f38-142">마지막으로, 클라우드 커넥터 기기의 가상 머신에서 사용 되는 기본 VHDX 파일을 가져오기 위해 virtual machine (sysprep)을 generalizes.</span><span class="sxs-lookup"><span data-stu-id="05f38-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="05f38-143">입력 형식</span><span class="sxs-lookup"><span data-stu-id="05f38-143">Input Types</span></span>
<span data-ttu-id="05f38-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="05f38-144"></span></span>

<span data-ttu-id="05f38-145">없음.</span><span class="sxs-lookup"><span data-stu-id="05f38-145">None.</span></span> <span data-ttu-id="05f38-146">Convert-CcIsoToVhdx cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05f38-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="05f38-147">반환 형식</span><span class="sxs-lookup"><span data-stu-id="05f38-147">Return Types</span></span>
<span data-ttu-id="05f38-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="05f38-148"></span></span>

<span data-ttu-id="05f38-149">없음</span><span class="sxs-lookup"><span data-stu-id="05f38-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="05f38-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05f38-150">See also</span></span>
<span data-ttu-id="05f38-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="05f38-151"></span></span>

<span data-ttu-id="05f38-152">없음</span><span class="sxs-lookup"><span data-stu-id="05f38-152">None</span></span>
  

