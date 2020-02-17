---
title: 'Lync Server 2013: 사용자가 Enterprise Voice를 사용할 수 있도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c48f701f9396c43337e2723f0dc83a8eda8d96ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d0898-102">Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="d0898-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0898-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d0898-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d0898-104">하나 이상의 중재 서버에 대 한 파일을 설치 하 고, 아웃 바운드 호출 라우팅을 구성 하 고, 필요에 따라 하나 이상의 고급 Enterprise Voice 기능을 배포 하는 경우 다음 절차를 사용 하 여 사용자가 Enterprise Voice를 사용 하 여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0898-105">다음 절차 중 첫 번째 방법은 Lync Server 제어판을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="d0898-106">나머지 절차는 Lync Server 관리 셸을 사용 하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="d0898-107">Enterprise Voice에 대 한 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="d0898-108">반드시 사용자 계정에 사용자별 음성 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="d0898-109">반드시 사용자 계정에 사용자별 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="d0898-110">Enterprise Voice에 대해 사용자 계정을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0898-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="d0898-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0898-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0898-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0898-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0898-114">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d0898-115">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d0898-116">테이블에서 Enterprise Voice를 사용 하도록 설정 하려는 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="d0898-117">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="d0898-118">**Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="d0898-119">**줄 URI**를 클릭 하 고 정규화 된 고유 전화 번호를 입력 합니다 (예: tel-+ 14255550200).</span><span class="sxs-lookup"><span data-stu-id="d0898-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="d0898-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-120">Click **Commit**.</span></span>

<span data-ttu-id="d0898-121">사용자가 Enterprise Voice를 사용할 수 있도록 설정 하는 작업을 완료 하려면 사용자에 게 전역 (기본적으로 할당 됨) 인지 또는 사용자 마다 고유한 음성 정책 및 다이얼 플랜을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="d0898-122">기본적으로 모든 사용자에 게는 전역 음성 정책 및 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="d0898-123">사용자 계정이 홈으로 설정 된 사이트의 사이트 수준에 음성 정책 또는 다이얼 플랜이 있는 경우 해당 사이트 정책이 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="d0898-124">사용자에 게 사용자별 음성 정책 또는 다이얼 플랜을 적용 하려면 **set-csvoicepolicy** 및 **Grant-csdialplan 플랜** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="d0898-125">자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0898-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="d0898-126">음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="d0898-126">Voice Policy Assignment</span></span>

<span data-ttu-id="d0898-127">전역 및 사이트 수준 음성 정책은 Enterprise Voice를 사용 하도록 설정 된 모든 사용자 계정에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="d0898-128">특정 사용자 또는 그룹에 적용 되는 음성 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="d0898-129">이러한 사용자별 정책을 사용자 또는 그룹에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="d0898-130">Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 음성 정책을 사용 하려면이 항목의 뒷부분에 나오는이 섹션을 건너뛰고 다이얼 플랜 할당을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="d0898-131">사용자 관련 음성 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="d0898-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="d0898-132">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0898-133">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d0898-134">기존 사용자 음성 정책을 사용자에게 할당하려면 명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="d0898-135">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="d0898-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="d0898-136">이 예에서 표시 이름이 Bob 최소라 인 사용자에 게는 이름이 **voicepolicyjapan 인**인 음성 정책이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="d0898-137">사용자 관련 음성 정책을 할당 하거나 **set-csvoicepolicy** cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0898-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="d0898-138">다이얼 플랜 할당</span><span class="sxs-lookup"><span data-stu-id="d0898-138">Dial Plan Assignment</span></span>

<span data-ttu-id="d0898-139">Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대한 사용자 계정 구성을 완료하려면 사용자에게 다이얼 플랜이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="d0898-140">사용자 계정은 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않을 때 전역 다이얼 플랜을 자동으로 사용 하거나, 한 경우에는 사이트 수준 다이얼 플랜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="d0898-141">Enterprise Voice를 사용할 수 있는 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려면이 섹션을 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="d0898-142">다이얼 플랜을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="d0898-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="d0898-143">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0898-144">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d0898-145">사용자별 다이얼 플랜을 할당하려면 명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="d0898-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="d0898-147">이 예에서는 표시 이름이 Bob 최소라 인 사용자에 게 이름이 **DialPlanJapan**사용자 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0898-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="d0898-148">사용자 다이얼 플랜을 할당 하거나 **Grant-CsDialPlan 플랜** cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0898-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0898-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0898-149">See Also</span></span>


[<span data-ttu-id="d0898-150">Lync Server 2013에서 Enterprise Voice에 대 한 사용자 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d0898-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

