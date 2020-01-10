---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '요약: 비즈니스용 Skype 서버에서 엔터프라이즈 음성을 사용 하 여 사용자가 전화를 걸고 받을 수 있도록 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 441b7a5705268dedea1feb87e01a48d0ef68b32c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002528"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="13433-103">비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화</span><span class="sxs-lookup"><span data-stu-id="13433-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="13433-104">**요약:** 비즈니스용 Skype 서버에서 엔터프라이즈 음성을 사용 하 여 사용자가 전화를 걸고 받을 수 있도록 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="13433-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="13433-105">회사 음성 또는 업무를 통해 전화를 건 후 다음 절차를 사용 하 여 사용자가 엔터프라이즈 음성을 사용 하 여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="13433-106">다음 절차 중 첫 번째는 비즈니스용 Skype Server 제어판을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="13433-107">나머지 절차에서는 비즈니스용 Skype Server Management Shell만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="13433-108">엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="13433-109">) 사용자 계정에 사용자 특정 음성 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="13433-110">) 사용자 계정에 사용자 특정 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="13433-111">엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="13433-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="13433-112">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="13433-113">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="13433-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="13433-114">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="13433-115">**사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="13433-116">표에서 Enterprise Voice에 사용할 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="13433-117">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="13433-118">**비즈니스용 Skype 서버 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="13433-119">**줄 URI**를 클릭 한 다음 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="13433-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="13433-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-120">Click **Commit**.</span></span>
    
<span data-ttu-id="13433-121">사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 하려면 사용자에 게 음성 정책 및 다이얼 플랜 (전역 (기본적으로 할당 됨) 인지 여부) 또는 사용자 관련 기능을 지정 해야 합니다. 기본적으로 모든 사용자에 게는 전역 음성 정책 및 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="13433-122">사용자 계정이 속한 사이트의 사이트 수준에 음성 정책 또는 다이얼 플랜이 있는 경우 해당 사이트 정책이 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13433-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="13433-123">사용자 단위 음성 정책 또는 다이얼 플랜을 사용자에 게 적용 하려면 **CsVoicePolicy** 및 **부여-csdialplan 다이얼** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="13433-124">자세한 내용은이 항목의 다음 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13433-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="13433-125">음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="13433-125">Voice Policy Assignment</span></span>

<span data-ttu-id="13433-126">전역 및 사이트 수준 음성 정책은 Enterprise Voice에 대해 사용 하도록 설정 된 모든 사용자 계정에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13433-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="13433-127">특정 사용자 또는 그룹에 적용 되는 음성 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="13433-128">이러한 사용자별 정책은 사용자 또는 그룹에 명시적으로 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="13433-129">Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 음성 정책을 사용 하려는 경우이 섹션을 건너뛰고이 항목의 뒷부분에 나오는 [다이얼 플랜 할당](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) 섹션을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="13433-130">사용자 관련 음성 정책 지정</span><span class="sxs-lookup"><span data-stu-id="13433-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="13433-131">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="13433-132">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="13433-133">사용자에 게 기존 사용자 음성 정책을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="13433-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="13433-135">이 예제에서 표시 이름이 Bob 최소라 인 사용자에 게는 이름 **VoicePolicyJapan**음성 정책이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13433-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="13433-136">다이얼 플랜 배정</span><span class="sxs-lookup"><span data-stu-id="13433-136">Dial Plan Assignment</span></span>
<span data-ttu-id="13433-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="13433-137"></span></span>

<span data-ttu-id="13433-138">Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대 한 사용자 계정 구성을 완료 하려면 사용자에 게 다이얼 플랜을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="13433-139">사용자 계정에 글로벌 다이얼 플랜 (있는 경우)이 자동으로 사용 되며, 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않은 경우에는 사이트 수준 다이얼 플랜입니다.</span><span class="sxs-lookup"><span data-stu-id="13433-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="13433-140">Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려는 경우이 섹션을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="13433-141">사용자 지정 다이얼 플랜을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="13433-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="13433-142">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="13433-143">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="13433-144">사용자 지정 다이얼 플랜을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="13433-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13433-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="13433-146">이 예제에서 표시 이름이 Bob 최소라 인 사용자는 이름 **DialPlanJapan**를 사용 하 여 사용자 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="13433-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

