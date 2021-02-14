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
description: 이 Switch-CcVersion cmdlet은 실행 중인 어플라이언스 연결을 끊고 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824152"
---
# <a name="switch-ccversion"></a><span data-ttu-id="269bd-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="269bd-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="269bd-104">이 Switch-CcVersion cmdlet은 실행 중인 어플라이언스 연결을 끊고 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="269bd-105">예</span><span class="sxs-lookup"><span data-stu-id="269bd-105">Examples</span></span>
<span data-ttu-id="269bd-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="269bd-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="269bd-107">예 1</span><span class="sxs-lookup"><span data-stu-id="269bd-107">Example 1</span></span>

<span data-ttu-id="269bd-108">다음 예에서는 현재 실행 중인 어플라이언스의 서비스를 드레인 다음 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="269bd-109">예 2</span><span class="sxs-lookup"><span data-stu-id="269bd-109">Example 2</span></span>

<span data-ttu-id="269bd-110">다음 예제에서는 현재 실행 중인 어플라이언스의 서비스를 드레인하고 서비스 드레인이 실패하면 서비스를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="269bd-111">그런 다음 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="269bd-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="269bd-112">Detailed Description</span></span>
<span data-ttu-id="269bd-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="269bd-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="269bd-114">이 Switch-CcVersion cmdlet은 중재 서버 및 에지 서버에서 클라우드 커넥터 서비스를 드레인합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="269bd-115">실행 중인 모든 통화가 완료되지만 어플라이언스에서 새 통화를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="269bd-116">드레인 후 이 cmdlet은 회사 및 인터넷 네트워크에서 실행 중인 어플라이언스 연결을 끊고 어플라이언스에 속한 모든 가상 컴퓨터를 해제한 다음 회사 및 인터넷 네트워크에 백업 어플라이언스를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="269bd-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="269bd-117">Parameters</span></span>
<span data-ttu-id="269bd-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="269bd-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="269bd-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="269bd-119">**Parameter**</span></span>|<span data-ttu-id="269bd-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="269bd-120">**Required**</span></span>|<span data-ttu-id="269bd-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="269bd-121">**Type**</span></span>|<span data-ttu-id="269bd-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="269bd-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="269bd-123">Force</span><span class="sxs-lookup"><span data-stu-id="269bd-123">Force</span></span> <br/> | <span data-ttu-id="269bd-124">선택</span><span class="sxs-lookup"><span data-stu-id="269bd-124">Optional</span></span> <br/> |<span data-ttu-id="269bd-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="269bd-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="269bd-126">서비스 드레인이 실패하면 서비스를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="269bd-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="269bd-127">입력 형식</span><span class="sxs-lookup"><span data-stu-id="269bd-127">Input Types</span></span>
<span data-ttu-id="269bd-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="269bd-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="269bd-129">없음</span><span class="sxs-lookup"><span data-stu-id="269bd-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="269bd-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="269bd-130">Return Types</span></span>
<span data-ttu-id="269bd-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="269bd-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="269bd-132">없음</span><span class="sxs-lookup"><span data-stu-id="269bd-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="269bd-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="269bd-133">See also</span></span>
<span data-ttu-id="269bd-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="269bd-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="269bd-135">없음</span><span class="sxs-lookup"><span data-stu-id="269bd-135">None</span></span>
  

