---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버를 유지 관리 모드로 전환 하 여 해당 버전의 업데이트 프로세스를 준비 합니다. 기기는 즉시 모든 서비스를 중지 하 고, 진행 중인 통화를 종료 하 고, 새로운 통화를 거부 합니다.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802178"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="bd2f7-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="bd2f7-104">Enter-CcUpdate</span></span>

<span data-ttu-id="bd2f7-105">Enter-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버를 유지 관리 모드로 전환 하 여 해당 버전의 업데이트 프로세스를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="bd2f7-106">기기는 즉시 모든 서비스를 중지 하 고, 진행 중인 통화를 종료 하 고, 새로운 통화를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="bd2f7-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd2f7-107">Parameters</span></span>

<span data-ttu-id="bd2f7-108">없음</span><span class="sxs-lookup"><span data-stu-id="bd2f7-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="bd2f7-109">예제</span><span class="sxs-lookup"><span data-stu-id="bd2f7-109">Examples</span></span>
<span data-ttu-id="bd2f7-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bd2f7-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="bd2f7-111">예제 1</span><span class="sxs-lookup"><span data-stu-id="bd2f7-111">Example 1</span></span>

<span data-ttu-id="bd2f7-112">다음 예제에서는 유지 관리 모드를 시작 하 여 업데이트 프로세스에 대 한 기기를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="bd2f7-113">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="bd2f7-113">Detailed Description</span></span>
<span data-ttu-id="bd2f7-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bd2f7-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="bd2f7-115">입력-CcUpdate cmdlet은 진행 중인 모든 통화를 종료 하는 모든 서비스를 즉시 중지 하 고, 기기는 다른 생산 기기로 전송 되는 모든 새 통화를 거부 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="bd2f7-116">남아 있는 프로덕션 기기의 용량이 업데이트를 준비 하려는 기기의 호출을 처리 하기에 충분 한지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="bd2f7-117">유지 관리 모드는 기기에서 자동 업데이트를 사용할 수 있도록 설정한 경우, 예를 들어 Microsoft에서 중요 한 핫픽스를 출시 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-117">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix.</span></span> <span data-ttu-id="bd2f7-118">유지 관리 모드는 자동 업데이트를 해제 하기로 결정 한 경우에도 일관 된 방식으로 수동 업데이트를 수행 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-118">Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="bd2f7-119">업데이트를 설치한 후 기기는 끝내기-CcUpdate cmdlet을 실행 하 여 프로덕션 모드로 다시 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd2f7-120">클라우드 커넥터 기기를 수동으로 업데이트 하기로 결정 한 경우, Microsoft가 다음 버전을 릴리스할 때 60 일 내에 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="bd2f7-121">Microsoft는 새 버전이 출시 된 이후 60 일간 이전에 출시 된 클라우드 커넥터 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="bd2f7-122">입력 형식</span><span class="sxs-lookup"><span data-stu-id="bd2f7-122">Input Types</span></span>
<span data-ttu-id="bd2f7-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bd2f7-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="bd2f7-124">없음.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-124">None.</span></span> <span data-ttu-id="bd2f7-125">입력-CCUpdate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2f7-125">The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bd2f7-126">반환 형식</span><span class="sxs-lookup"><span data-stu-id="bd2f7-126">Return Types</span></span>
<span data-ttu-id="bd2f7-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bd2f7-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="bd2f7-128">없음</span><span class="sxs-lookup"><span data-stu-id="bd2f7-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bd2f7-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd2f7-129">See also</span></span>
<span data-ttu-id="bd2f7-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bd2f7-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="bd2f7-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="bd2f7-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

