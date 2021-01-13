---
title: 사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '요약: 사용자가 비즈니스용 Skype 서버에서 사용자를 사용하여 전화를 걸고 Enterprise Voice 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830878"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="517c5-103">사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="517c5-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="517c5-104">**요약:** 사용자가 비즈니스용 Skype 서버에서 전화를 걸고 받을 수 있도록 하는 Enterprise Voice 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="517c5-105">2016 또는 Enterprise Voice 통화를 배포한 후 다음 절차에 따라 사용자가 다음 절차를 사용하여 다음 절차를 사용하여 전화를 걸 수 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="517c5-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="517c5-106">다음 절차 중 첫 번째 절차만 비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="517c5-107">나머지 절차에서는 비즈니스용 Skype 서버 관리 셸만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="517c5-108">사용자 계정에서 사용자 계정을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="517c5-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="517c5-109">(선택 사항) 사용자 계정에 사용자별 음성 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="517c5-110">(선택 사항) 사용자 계정에 사용자별 다이얼 플랜을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="517c5-111">사용자 계정에서 사용자 계정을 사용하도록 설정하려면 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="517c5-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="517c5-112">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator,** **CsServerAdministrator 또는 CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="517c5-113">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="517c5-114">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="517c5-115">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="517c5-116">표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="517c5-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="517c5-117">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="517c5-118">비즈니스용 **Skype 서버** 사용자 편집 페이지의 전화 **통신에서** **Enterprise Voice.**</span><span class="sxs-lookup"><span data-stu-id="517c5-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="517c5-119">줄 **URI를** 클릭한 다음 정규화된 고유한 전화 번호(예: tel:+14255550200)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="517c5-120">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-120">Click **Commit**.</span></span>
    
<span data-ttu-id="517c5-121">사용자에 대한 사용자 Enterprise Voice 설정이 끝나면 사용자에게 음성 정책 및 다이얼 플랜(기본적으로 할당)이나 사용자별이 할당되어 있는지를 확인해야 합니다. 기본적으로 모든 사용자에게는 전역 음성 정책 및 다이얼 플랜이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="517c5-122">음성 정책 또는 다이얼 플랜이 사용자 계정이 있는 사이트의 사이트 수준에 있는 경우 해당 사이트 정책이 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="517c5-123">사용자당 음성 정책 또는 다이얼 플랜을 사용자에게 적용하려면 **Grant-CsVoicePolicy** 및 **Grant-CsDialPlan** cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="517c5-124">자세한 내용은 이 항목의 다음 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="517c5-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="517c5-125">음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="517c5-125">Voice Policy Assignment</span></span>

<span data-ttu-id="517c5-126">전역 및 사이트 수준 음성 정책은 전역 및 사이트 수준 음성 정책에 대해 사용하도록 설정된 모든 사용자 계정에 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="517c5-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="517c5-127">특정 사용자 또는 그룹에 적용되는 음성 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="517c5-128">이러한 사용자당 정책은 사용자 또는 그룹에 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="517c5-129">전역 또는 사이트 음성 정책을 사용하도록 설정된 모든 사용자에 대해 전역 Enterprise Voice 사용하려는 경우 이 [](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) 섹션을 건너뛰고 이 항목의 부분에 있는 다이얼 플랜 할당 섹션을 계속 진행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="517c5-130">사용자별 음성 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="517c5-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="517c5-131">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="517c5-132">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="517c5-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="517c5-133">기존 사용자 음성 정책을 사용자에게 할당하려면 명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="517c5-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="517c5-135">이 예에서는 표시 이름이 Bob Kelly인 사용자에게 **VoicePolicyJapan** 이름이 지정된 음성 정책이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="517c5-136">다이얼 플랜 할당</span><span class="sxs-lookup"><span data-stu-id="517c5-136">Dial Plan Assignment</span></span>
<span data-ttu-id="517c5-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="517c5-137"><a name="BKMK_DialPlanAssignment"> </a></span></span>

<span data-ttu-id="517c5-138">Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대한 사용자 계정 구성을 완료하려면 사용자에게 다이얼 플랜이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="517c5-139">사용자 계정은 기존 사용자당 다이얼 플랜을 명시적으로 할당하지 않을 때 전역 다이얼 플랜 또는 사이트 수준 다이얼 플랜이 있는 경우 자동으로 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="517c5-140">전역 또는 사이트 다이얼 플랜을 사용하도록 설정된 모든 사용자에 대해 전역 또는 사이트 Enterprise Voice 이 섹션을 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="517c5-141">사용자별 다이얼 플랜을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="517c5-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="517c5-142">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="517c5-143">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="517c5-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="517c5-144">사용자별 다이얼 플랜을 할당하려면 명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="517c5-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="517c5-146">이 예에서는 표시 이름이 Bob Kelly인 사용자에게 **DialPlanJapan** 이름이 지정된 사용자 다이얼 플랜이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="517c5-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

