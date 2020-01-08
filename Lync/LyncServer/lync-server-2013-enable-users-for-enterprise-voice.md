---
title: 'Lync Server 2013: Enterprise Voice 사용자 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="1d530-102">Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 활성화</span><span class="sxs-lookup"><span data-stu-id="1d530-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d530-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1d530-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1d530-104">하나 이상의 중재 서버에 대 한 파일을 설치 하 고, 아웃 바운드 호출 라우팅을 구성 하 고, 선택적으로 하나 이상의 고급 엔터프라이즈 음성 기능을 배포 하는 경우 다음 절차를 사용 하 여 사용자가 엔터프라이즈 음성을 사용 하 여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d530-105">다음 절차 중 첫 번째는 Lync Server 제어판을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="1d530-106">나머지 절차는 Lync Server 관리 셸로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="1d530-107">엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="1d530-108">) 사용자 계정에 사용자 특정 음성 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="1d530-109">) 사용자 계정에 사용자 특정 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="1d530-110">엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1d530-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="1d530-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d530-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d530-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d530-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d530-114">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1d530-115">**사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="1d530-116">표에서 Enterprise Voice에 사용할 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="1d530-117">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="1d530-118">**Lync Server 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="1d530-119">**줄 URI**를 클릭 한 다음 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="1d530-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="1d530-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-120">Click **Commit**.</span></span>

<span data-ttu-id="1d530-121">사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 하려면 사용자에 게 음성 정책 및 다이얼 플랜 (전역 (기본적으로 할당 됨) 인지 여부) 또는 사용자 관련 기능을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="1d530-122">기본적으로 모든 사용자에 게는 전역 음성 정책 및 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="1d530-123">사용자 계정이 속한 사이트의 사이트 수준에 음성 정책 또는 다이얼 플랜이 있는 경우 해당 사이트 정책이 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="1d530-124">사용자 단위 음성 정책 또는 다이얼 플랜을 사용자에 게 적용 하려면 **CsVoicePolicy** 및 **부여-csdialplan 다이얼** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="1d530-125">자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d530-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="1d530-126">음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1d530-126">Voice Policy Assignment</span></span>

<span data-ttu-id="1d530-127">전역 및 사이트 수준 음성 정책은 Enterprise Voice에 대해 사용 하도록 설정 된 모든 사용자 계정에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="1d530-128">특정 사용자 또는 그룹에 적용 되는 음성 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="1d530-129">이러한 사용자별 정책은 사용자 또는 그룹에 명시적으로 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="1d530-130">Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 음성 정책을 사용 하려는 경우이 섹션을 건너뛰고이 항목의 뒷부분에 나오는 다이얼 플랜 할당 섹션을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="1d530-131">사용자 관련 음성 정책 지정</span><span class="sxs-lookup"><span data-stu-id="1d530-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="1d530-132">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d530-133">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d530-134">사용자에 게 기존 사용자 음성 정책을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="1d530-135">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="1d530-136">이 예제에서 표시 이름이 Bob 최소라 인 사용자에 게는 이름 **VoicePolicyJapan**음성 정책이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="1d530-137">사용자 관련 음성 정책 지정 또는 **CsVoicePolicy** cmdlet 실행에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d530-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="1d530-138">다이얼 플랜 배정</span><span class="sxs-lookup"><span data-stu-id="1d530-138">Dial Plan Assignment</span></span>

<span data-ttu-id="1d530-139">Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대 한 사용자 계정 구성을 완료 하려면 사용자에 게 다이얼 플랜을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="1d530-140">사용자 계정에 글로벌 다이얼 플랜 (있는 경우)이 자동으로 사용 되며, 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않은 경우에는 사이트 수준 다이얼 플랜입니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="1d530-141">Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려는 경우이 섹션을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="1d530-142">다이얼 플랜 지정</span><span class="sxs-lookup"><span data-stu-id="1d530-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="1d530-143">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d530-144">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d530-145">사용자 지정 다이얼 플랜을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="1d530-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="1d530-147">이 예제에서 표시 이름이 Bob 최소라 인 사용자는 이름 **DialPlanJapan**를 사용 하 여 사용자 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d530-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="1d530-148">사용자 다이얼 플랜 또는 **부여-CsDialPlan 다이얼** cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d530-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d530-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d530-149">See Also</span></span>


[<span data-ttu-id="1d530-150">Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1d530-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

