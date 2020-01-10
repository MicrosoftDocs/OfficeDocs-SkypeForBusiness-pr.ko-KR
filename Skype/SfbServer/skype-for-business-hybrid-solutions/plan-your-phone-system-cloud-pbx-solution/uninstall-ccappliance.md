---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 제거-CcAppliance cmdlet는 호스트 서버에서 실행 중인 비즈니스용 Skype 클라우드 커넥터 에디션 기기를 제거 합니다.
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003148"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="9629f-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9629f-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="9629f-104">제거-CcAppliance cmdlet는 호스트 서버에서 실행 중인 비즈니스용 Skype 클라우드 커넥터 에디션 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9629f-105">예제</span><span class="sxs-lookup"><span data-stu-id="9629f-105">Examples</span></span>
<span data-ttu-id="9629f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9629f-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9629f-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="9629f-107">Example 1</span></span>

<span data-ttu-id="9629f-108">다음 예제에서는 호스트 서버에서 클라우드 커넥터 기기를 드레이닝 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="9629f-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="9629f-109">Example 2</span></span>

<span data-ttu-id="9629f-110">다음 예제에서는 드레이닝 프로세스가 실패 한 경우에도 호스트 서버에서 실행 중인 클라우드 커넥터 기기를 드레이닝 및 강제 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="9629f-111">예제 3</span><span class="sxs-lookup"><span data-stu-id="9629f-111">Example 3</span></span>

<span data-ttu-id="9629f-112">다음 예제에서는 사용자의 확인 없이 클라우드 커넥터 백업 버전을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="9629f-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9629f-113">Detailed Description</span></span>
<span data-ttu-id="9629f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9629f-114"></span></span>

<span data-ttu-id="9629f-115">현재 실행 중인 클라우드 커넥터 버전을 제거 하는 경우 조정 서버 및 Edge 서버에서 드레이닝 서비스를 먼저 실행 하 여 가상 컴퓨터를 제거 하기 전에 동시 호출을 완료할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="9629f-116">백업 버전을 제거 하는 경우 드레이닝이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9629f-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9629f-117">Parameters</span></span>
<span data-ttu-id="9629f-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9629f-118"></span></span>

|<span data-ttu-id="9629f-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="9629f-119">**Parameter**</span></span>|<span data-ttu-id="9629f-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="9629f-120">**Required**</span></span>|<span data-ttu-id="9629f-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="9629f-121">**Type**</span></span>|<span data-ttu-id="9629f-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="9629f-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9629f-123">버전</span><span class="sxs-lookup"><span data-stu-id="9629f-123">Version</span></span> <br/> | <span data-ttu-id="9629f-124">선택</span><span class="sxs-lookup"><span data-stu-id="9629f-124">Optional</span></span> <br/> |<span data-ttu-id="9629f-125">System.String</span><span class="sxs-lookup"><span data-stu-id="9629f-125">System.String</span></span>  <br/> | <span data-ttu-id="9629f-126">호스트 서버에서 제거 되는 클라우드 커넥터의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="9629f-127">지정 하지 않은 경우 현재 실행 중인 버전을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="9629f-128">Force</span><span class="sxs-lookup"><span data-stu-id="9629f-128">Force</span></span>  <br/> |<span data-ttu-id="9629f-129">선택</span><span class="sxs-lookup"><span data-stu-id="9629f-129">Optional</span></span>  <br/> |<span data-ttu-id="9629f-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9629f-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9629f-131">현재 실행 중인 버전을 제거 하는 경우 가상 컴퓨터를 제거 하기 전에 중재 서버와 Edge 서버에서 서버를 드레이닝 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="9629f-132">"Force" 스위치를 지정 하면 드레이닝 서비스에 장애가 있는 경우에도 가상 머신이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="9629f-133">이 매개 변수는 현재 실행 중인 버전을 제거 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="9629f-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="9629f-134">Confirm</span></span>  <br/> |<span data-ttu-id="9629f-135">선택</span><span class="sxs-lookup"><span data-stu-id="9629f-135">Optional</span></span>  <br/> |<span data-ttu-id="9629f-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9629f-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9629f-137">사용자의 확인을 요청 하 여 가상 컴퓨터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="9629f-138">기본값은 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9629f-139">입력 형식</span><span class="sxs-lookup"><span data-stu-id="9629f-139">Input Types</span></span>
<span data-ttu-id="9629f-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9629f-140"></span></span>

<span data-ttu-id="9629f-141">없음.</span><span class="sxs-lookup"><span data-stu-id="9629f-141">None.</span></span> <span data-ttu-id="9629f-142">제거-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9629f-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9629f-143">반환 형식</span><span class="sxs-lookup"><span data-stu-id="9629f-143">Return Types</span></span>
<span data-ttu-id="9629f-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9629f-144"></span></span>

<span data-ttu-id="9629f-145">없음</span><span class="sxs-lookup"><span data-stu-id="9629f-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9629f-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9629f-146">See also</span></span>
<span data-ttu-id="9629f-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9629f-147"></span></span>

[<span data-ttu-id="9629f-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9629f-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="9629f-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9629f-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="9629f-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9629f-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="9629f-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9629f-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

