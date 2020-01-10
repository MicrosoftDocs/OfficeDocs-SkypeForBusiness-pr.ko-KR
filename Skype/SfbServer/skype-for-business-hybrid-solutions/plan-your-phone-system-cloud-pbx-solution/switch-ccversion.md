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
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 스위치용 버전 cmdlet은 실행 중인 기기의 연결을 끊고 새로 배포 또는 백업 기기로 전환 합니다.
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003158"
---
# <a name="switch-ccversion"></a><span data-ttu-id="4f79f-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="4f79f-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="4f79f-104">스위치용 버전 cmdlet은 실행 중인 기기의 연결을 끊고 새로 배포 또는 백업 기기로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="4f79f-105">예제</span><span class="sxs-lookup"><span data-stu-id="4f79f-105">Examples</span></span>
<span data-ttu-id="4f79f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f79f-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="4f79f-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="4f79f-107">Example 1</span></span>

<span data-ttu-id="4f79f-108">다음 예에서는 현재 실행 중인 기기의 서비스를 고갈 한 다음 새로 배포 또는 백업 기기로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="4f79f-109">예제 2</span><span class="sxs-lookup"><span data-stu-id="4f79f-109">Example 2</span></span>

<span data-ttu-id="4f79f-110">다음 예에서는 현재 실행 중인 기기의 서비스를 드레이닝 하 고 서비스를 드레이닝 하지 못하면 서비스를 강제로 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="4f79f-111">그런 다음 새 배포 또는 백업 기기로 명령을 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="4f79f-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4f79f-112">Detailed Description</span></span>
<span data-ttu-id="4f79f-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4f79f-113"></span></span>

<span data-ttu-id="4f79f-114">이 스위치를 사용 하는 경우에는 중재 서버와 Edge 서버에서 클라우드 커넥터 서비스를 드레이닝 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="4f79f-115">실행 중인 모든 통화가 완료 되지만 기기는 새로운 통화를 거부 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="4f79f-116">드레이닝이 완료 되 면 cmdlet이 회사 및 인터넷 네트워크에서 실행 중인 기기의 연결을 끊고 기기에 속한 모든 가상 머신을 끈 다음, 백업 기기를 회사 및 인터넷 네트워크에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4f79f-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f79f-117">Parameters</span></span>
<span data-ttu-id="4f79f-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4f79f-118"></span></span>

|<span data-ttu-id="4f79f-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f79f-119">**Parameter**</span></span>|<span data-ttu-id="4f79f-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="4f79f-120">**Required**</span></span>|<span data-ttu-id="4f79f-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="4f79f-121">**Type**</span></span>|<span data-ttu-id="4f79f-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="4f79f-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4f79f-123">Force</span><span class="sxs-lookup"><span data-stu-id="4f79f-123">Force</span></span> <br/> | <span data-ttu-id="4f79f-124">선택</span><span class="sxs-lookup"><span data-stu-id="4f79f-124">Optional</span></span> <br/> |<span data-ttu-id="4f79f-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4f79f-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="4f79f-126">서비스 드레이닝이 실패 하는 경우 서비스를 강제로 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f79f-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4f79f-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="4f79f-127">Input Types</span></span>
<span data-ttu-id="4f79f-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4f79f-128"></span></span>

<span data-ttu-id="4f79f-129">없음</span><span class="sxs-lookup"><span data-stu-id="4f79f-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4f79f-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="4f79f-130">Return Types</span></span>
<span data-ttu-id="4f79f-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4f79f-131"></span></span>

<span data-ttu-id="4f79f-132">없음</span><span class="sxs-lookup"><span data-stu-id="4f79f-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f79f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f79f-133">See also</span></span>
<span data-ttu-id="4f79f-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4f79f-134"></span></span>

<span data-ttu-id="4f79f-135">없음</span><span class="sxs-lookup"><span data-stu-id="4f79f-135">None</span></span>
  

