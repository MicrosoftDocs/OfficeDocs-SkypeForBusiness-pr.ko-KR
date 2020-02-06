---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 스위치용 버전 cmdlet은 실행 중인 기기의 연결을 끊고 새로 배포 또는 백업 기기로 전환 합니다.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824152"
---
# <a name="switch-ccversion"></a><span data-ttu-id="0c490-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="0c490-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="0c490-104">스위치용 버전 cmdlet은 실행 중인 기기의 연결을 끊고 새로 배포 또는 백업 기기로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="0c490-105">예제</span><span class="sxs-lookup"><span data-stu-id="0c490-105">Examples</span></span>
<span data-ttu-id="0c490-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0c490-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0c490-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="0c490-107">Example 1</span></span>

<span data-ttu-id="0c490-108">다음 예에서는 현재 실행 중인 기기의 서비스를 고갈 한 다음 새로 배포 또는 백업 기기로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="0c490-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="0c490-109">Example 2</span></span>

<span data-ttu-id="0c490-110">다음 예에서는 현재 실행 중인 기기의 서비스를 드레이닝 하 고 서비스를 드레이닝 하지 못하면 서비스를 강제로 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="0c490-111">그런 다음 새 배포 또는 백업 기기로 명령을 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="0c490-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="0c490-112">Detailed Description</span></span>
<span data-ttu-id="0c490-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c490-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0c490-114">이 스위치를 사용 하는 경우에는 중재 서버와 Edge 서버에서 클라우드 커넥터 서비스를 드레이닝 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="0c490-115">실행 중인 모든 통화가 완료 되지만 기기는 새로운 통화를 거부 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="0c490-116">드레이닝이 완료 되 면 cmdlet이 회사 및 인터넷 네트워크에서 실행 중인 기기의 연결을 끊고 기기에 속한 모든 가상 머신을 끈 다음, 백업 기기를 회사 및 인터넷 네트워크에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0c490-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c490-117">Parameters</span></span>
<span data-ttu-id="0c490-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c490-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0c490-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="0c490-119">**Parameter**</span></span>|<span data-ttu-id="0c490-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="0c490-120">**Required**</span></span>|<span data-ttu-id="0c490-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="0c490-121">**Type**</span></span>|<span data-ttu-id="0c490-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="0c490-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0c490-123">Force</span><span class="sxs-lookup"><span data-stu-id="0c490-123">Force</span></span> <br/> | <span data-ttu-id="0c490-124">선택</span><span class="sxs-lookup"><span data-stu-id="0c490-124">Optional</span></span> <br/> |<span data-ttu-id="0c490-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c490-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="0c490-126">서비스 드레이닝이 실패 하는 경우 서비스를 강제로 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c490-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0c490-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="0c490-127">Input Types</span></span>
<span data-ttu-id="0c490-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c490-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0c490-129">없음</span><span class="sxs-lookup"><span data-stu-id="0c490-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0c490-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="0c490-130">Return Types</span></span>
<span data-ttu-id="0c490-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c490-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0c490-132">없음</span><span class="sxs-lookup"><span data-stu-id="0c490-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c490-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c490-133">See also</span></span>
<span data-ttu-id="0c490-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c490-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0c490-135">없음</span><span class="sxs-lookup"><span data-stu-id="0c490-135">None</span></span>
  

