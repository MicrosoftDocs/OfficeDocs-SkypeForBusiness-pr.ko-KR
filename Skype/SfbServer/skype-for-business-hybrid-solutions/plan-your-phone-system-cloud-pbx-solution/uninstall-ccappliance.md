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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 이 Uninstall-CcAppliance cmdlet은 호스트 서버에서 실행 중인 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 제거합니다.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824142"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="acfa1-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acfa1-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="acfa1-104">이 Uninstall-CcAppliance cmdlet은 호스트 서버에서 실행 중인 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="acfa1-105">예</span><span class="sxs-lookup"><span data-stu-id="acfa1-105">Examples</span></span>
<span data-ttu-id="acfa1-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="acfa1-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="acfa1-107">예 1</span><span class="sxs-lookup"><span data-stu-id="acfa1-107">Example 1</span></span>

<span data-ttu-id="acfa1-108">다음 예에서는 호스트 서버에서 Cloud Connector 어플라이언스를 드레인 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="acfa1-109">예 2</span><span class="sxs-lookup"><span data-stu-id="acfa1-109">Example 2</span></span>

<span data-ttu-id="acfa1-110">다음 예제에서는 드레인 프로세스가 실패한 경우에도 호스트 서버에서 실행 중인 Cloud Connector 어플라이언스를 드레인 및 강요하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="acfa1-111">예 3</span><span class="sxs-lookup"><span data-stu-id="acfa1-111">Example 3</span></span>

<span data-ttu-id="acfa1-112">다음 예에서는 사용자의 확인 없이 클라우드 커넥터 백업 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="acfa1-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="acfa1-113">Detailed Description</span></span>
<span data-ttu-id="acfa1-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="acfa1-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="acfa1-115">현재 실행 중인 버전의 클라우드 커넥터를 설치하는 경우 드레인 서비스가 먼저 중재 서버 및 에지 서버에서 실행되어 가상 컴퓨터를 설치하기 전에 동시 통화가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="acfa1-116">백업 버전을 설치하는 경우 드레인이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="acfa1-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acfa1-117">Parameters</span></span>
<span data-ttu-id="acfa1-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="acfa1-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="acfa1-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="acfa1-119">**Parameter**</span></span>|<span data-ttu-id="acfa1-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="acfa1-120">**Required**</span></span>|<span data-ttu-id="acfa1-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="acfa1-121">**Type**</span></span>|<span data-ttu-id="acfa1-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="acfa1-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="acfa1-123">버전</span><span class="sxs-lookup"><span data-stu-id="acfa1-123">Version</span></span> <br/> | <span data-ttu-id="acfa1-124">옵션</span><span class="sxs-lookup"><span data-stu-id="acfa1-124">Optional</span></span> <br/> |<span data-ttu-id="acfa1-125">System.String</span><span class="sxs-lookup"><span data-stu-id="acfa1-125">System.String</span></span>  <br/> | <span data-ttu-id="acfa1-126">호스트 서버에서 제거될 클라우드 커넥터 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="acfa1-127">지정하지 않으면 현재 실행 중인 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="acfa1-128">Force</span><span class="sxs-lookup"><span data-stu-id="acfa1-128">Force</span></span>  <br/> |<span data-ttu-id="acfa1-129">선택</span><span class="sxs-lookup"><span data-stu-id="acfa1-129">Optional</span></span>  <br/> |<span data-ttu-id="acfa1-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="acfa1-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="acfa1-131">현재 실행 중인 버전을 지우는 경우 가상 컴퓨터를 설치하기 전에 중재 서버 및 에지 서버에서 서버를 드레인합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="acfa1-132">"강제" 스위치를 지정하면 드레인 서비스가 실패한 경우에도 가상 컴퓨터는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="acfa1-133">이 매개 변수는 현재 실행 중인 버전을 제거하기 위해만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="acfa1-134">확인</span><span class="sxs-lookup"><span data-stu-id="acfa1-134">Confirm</span></span>  <br/> |<span data-ttu-id="acfa1-135">선택</span><span class="sxs-lookup"><span data-stu-id="acfa1-135">Optional</span></span>  <br/> |<span data-ttu-id="acfa1-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="acfa1-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="acfa1-137">가상 컴퓨터를 제거하도록 사용자의 확인을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="acfa1-138">기본값은 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="acfa1-139">입력 형식</span><span class="sxs-lookup"><span data-stu-id="acfa1-139">Input Types</span></span>
<span data-ttu-id="acfa1-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acfa1-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="acfa1-141">없음</span><span class="sxs-lookup"><span data-stu-id="acfa1-141">None.</span></span> <span data-ttu-id="acfa1-142">이 Uninstall-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acfa1-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="acfa1-143">반환 형식</span><span class="sxs-lookup"><span data-stu-id="acfa1-143">Return Types</span></span>
<span data-ttu-id="acfa1-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acfa1-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="acfa1-145">없음</span><span class="sxs-lookup"><span data-stu-id="acfa1-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="acfa1-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acfa1-146">See also</span></span>
<span data-ttu-id="acfa1-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="acfa1-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="acfa1-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acfa1-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="acfa1-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acfa1-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="acfa1-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acfa1-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="acfa1-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="acfa1-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

