---
title: 비즈니스용 Skype 서버에서 직장을 통한 통화 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '요약: 일부 또는 전체 사용자에 대해 비즈니스용 Skype 서버에서 직장 전화 서비스를 배포하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825008"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="0bf43-103">비즈니스용 Skype 서버에서 직장을 통한 통화 배포</span><span class="sxs-lookup"><span data-stu-id="0bf43-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="0bf43-104">**요약:** 일부 또는 모든 사용자를 위해 비즈니스용 Skype 서버에서 직장을 통한 통화를 배포하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="0bf43-105">다음 단계에 따라 사용자를 위해 직장 전화 기능을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="0bf43-106">계획 고려 사항은 비즈니스용 Skype 서버의 직장 [전화 계획에서 논의됩니다.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)</span><span class="sxs-lookup"><span data-stu-id="0bf43-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="0bf43-107">이전 버전의 Lync Server 원격 통화 제어는 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="0bf43-108">비즈니스용 Skype 서버에서는 이 기능이 직장 전화로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="0bf43-109">업무를 통한 전화에 대한 선행 작업</span><span class="sxs-lookup"><span data-stu-id="0bf43-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="0bf43-110">UCWA(Unified Communications Web API)를 사용하여 모든 비즈니스용 Skype 서버 프런트 엔드 서버에 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="0bf43-111">사용자가 직장에서 전화를 걸 수 있도록 설정하려면 다음과 같은 선행 사항도 준비되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="0bf43-112">중재 서버는 프런트 엔드 서버의 일부로 또는 독립 실행형 역할로 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="0bf43-113">IP-PBX 게이트웨이도 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="0bf43-114">직장에서 전화 기능을 사용하도록 설정하는 모든 사용자는 PBX 전화 시스템에서 DID(Direct Inward Dialing)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="0bf43-115">사용자에 대해 모든 업무용 통화 사용자를 사용하도록 설정해야 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0bf43-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="0bf43-116">이렇게 하는 경우 각 사용자에 대한 비즈니스용 Skype DID 번호를 해당 PBX 전화 시스템에 대한 해당 DID 번호로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="0bf43-117">업무를 통해 전화를 사용할 모든  사용자는 비즈니스용  Skype 클라이언트의 고급 연결 옵션에서 자동 구성을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="0bf43-118">이렇게 하면 클라이언트가 UCWA URL을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="0bf43-119">**자동 구성이** 기본 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="0bf43-120">각 업무용 전화 사용자에 대해 통화 전달 및 동시 전화 울림을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="0bf43-121">각 업무용 전화 사용자에 대해 전화 접속 회의 및 회의 전화 접속이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="0bf43-122">이렇게 하면 이러한 사용자가 비즈니스용 Skype 회의에 들어와서 회의에서 에서 나서야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="0bf43-123">모든 통화 사용자에 대해 위임, 팀 통화 및 응답 그룹을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="0bf43-124">회사번호로 전화</span><span class="sxs-lookup"><span data-stu-id="0bf43-124">Deploy Call Via Work</span></span>

<span data-ttu-id="0bf43-125">선행 작업을 준비한 후 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="0bf43-126">비즈니스용 Skype가 업무번호로 전화를 걸고 있는 사용자의 PBX 발신자 번호에 표시하는 배포에 대한 전역 전화 번호를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="0bf43-127">하나 이상의 업무로 전화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0bf43-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="0bf43-128">직장에서 전화 기능을 사용할 각 사용자에게 직장 전화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0bf43-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="0bf43-129">직장번호로 전화 걸기 전역 전화 번호 만들기</span><span class="sxs-lookup"><span data-stu-id="0bf43-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="0bf43-130">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="0bf43-131">예를 들어 다음 cmdlet은 전역 전화 번호를 1-555-123-4567로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="0bf43-132">직장 전화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0bf43-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="0bf43-133">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="0bf43-134">예를 들어 다음 cmdlet은 ContosoUser1CvWP라는 업무용 통화 정책을 만들고, 사용자가 관리자 콜백 번호를 사용하도록 요구하고, 해당 콜백 번호를 1-555-789-1234로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="0bf43-135">사용자에게 직장 전화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0bf43-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="0bf43-136">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf43-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="0bf43-137">예를 들어 다음 cmdlet은 ContosoUser1이라는 사용자에게 업무 시간 전화 정책 "ContosoUser1CvWP"를 **할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="0bf43-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="0bf43-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bf43-138">See also</span></span>

[<span data-ttu-id="0bf43-139">비즈니스용 Skype 서버의 직장 전화 계획</span><span class="sxs-lookup"><span data-stu-id="0bf43-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

