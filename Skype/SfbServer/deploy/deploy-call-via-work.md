---
title: 비즈니스용 Skype 서버의 작업을 통해 통화 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '요약: 비즈니스용 Skype 서버에서 일부 또는 모든 사용자에 대해 작업을 통해 통화를 배포 하는 방법을 알아봅니다.'
ms.openlocfilehash: d1c55e44cae944664a51eaddb2ad54e758d4f52c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234523"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="41f05-103">비즈니스용 Skype 서버의 작업을 통해 통화 배포</span><span class="sxs-lookup"><span data-stu-id="41f05-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="41f05-104">**요약:** 비즈니스용 Skype 서버의 작업을 통해 일부 또는 모든 사용자의 통화를 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="41f05-105">이 단계를 사용 하 여 사용자에 대 한 작업을 통해 전화를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="41f05-106">계획 고려 사항에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 작업을 통한 통화 계획](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41f05-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="41f05-107">이전 버전의 Lync Server 원격 통화 제어는 Lync Server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 기능 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="41f05-108">비즈니스용 Skype Server에서이 기능은 업무에의 한 통화를 통해 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="41f05-109">작업을 통한 통화를 위한 필수 조건</span><span class="sxs-lookup"><span data-stu-id="41f05-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="41f05-110">직장을 통한 통화는 모든 비즈니스용 Skype Server 프런트 엔드 서버에 자동으로 설치 되는 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="41f05-111">작업을 통해 사용자에 게 전화를 걸 수 있도록 설정 하려면 다음과 같은 필수 구성 요소도 준비 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="41f05-112">프런트 엔드 서버의 일부로 또는 독립 실행형 역할로 중재 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="41f05-113">또한 IP PBX 게이트웨이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="41f05-114">작업을 통해 전화를 받을 수 있는 모든 사용자에 게는 PBX 전화 시스템의 직접적인 안쪽 전화 접속 ()이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="41f05-115">Enterprise Voice에 대 한 회사 사용자를 통해 모든 통화를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="41f05-116">이 작업을 수행 하는 경우 각 사용자에 대 한 비즈니스용 Skype의 번호를 해당 PBX 전화 시스템의 해당 하는 번호를 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="41f05-117">업무를 통해 전화를 사용 하는 모든 사용자에 게는 비즈니스용 Skype 클라이언트의 **고급 연결** 옵션에서 **자동 구성이** 선택 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="41f05-118">이렇게 하면 클라이언트가 cowa Url을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="41f05-119">**자동 구성은** 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="41f05-120">작업 사용자를 통한 각 통화에 대해 착신 전환 및 동시 연결을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="41f05-121">작업 사용자를 통한 각 통화에 대해 전화 접속 회의 및 회의 전화 걸기를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="41f05-122">이를 통해 이러한 사용자는 비즈니스용 Skype 회의를 시작 하거나 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="41f05-123">업무 사용자를 통한 모든 통화에 대해 위임, 팀 통화 및 응답 그룹을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="41f05-124">회사번호로 전화</span><span class="sxs-lookup"><span data-stu-id="41f05-124">Deploy Call Via Work</span></span>

<span data-ttu-id="41f05-125">필수 구성 요소를 입력 한 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="41f05-126">배포에 대 한 전역 전화 번호를 만듭니다. 비즈니스용 Skype에서 회사 전화를 통해 전화를 걸고 있는 사용자의 PBX 발신자 ID에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="41f05-127">회사 정책을 통해 하나 이상의 통화 만들기</span><span class="sxs-lookup"><span data-stu-id="41f05-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="41f05-128">작업 정책을 통해 전화를 통해 전화를 받을 수 있는 각 사용자에 게 통화를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="41f05-129">회사 전역 전화 번호를 통해 통화 만들기</span><span class="sxs-lookup"><span data-stu-id="41f05-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="41f05-130">다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="41f05-131">예를 들어 다음 cmdlet은 전역 전화 번호를 1-555-123-4567으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="41f05-132">회사 정책을 통해 통화 만들기</span><span class="sxs-lookup"><span data-stu-id="41f05-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="41f05-133">다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="41f05-134">예를 들어 다음 cmdlet은 ContosoUser1CvWP 이라는 작업 정책을 통해 전화를 만들고, 사용자가 관리 콜백 번호를 사용 해야 하며, 해당 콜백 번호를 1-555-789-1234로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="41f05-135">회사 정책을 통해 사용자에 게 전화 할당</span><span class="sxs-lookup"><span data-stu-id="41f05-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="41f05-136">다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="41f05-137">예를 들어 다음 cmdlet은 작업 정책 "ContosoUser1CvWP"를 통해 호출을 **ContosoUser1**라는 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f05-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="41f05-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41f05-138">See also</span></span>

[<span data-ttu-id="41f05-139">비즈니스용 Skype 서버의 작업을 통한 통화 계획</span><span class="sxs-lookup"><span data-stu-id="41f05-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

