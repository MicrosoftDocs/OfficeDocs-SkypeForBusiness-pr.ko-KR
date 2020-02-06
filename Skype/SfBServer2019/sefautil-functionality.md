---
title: 비즈니스용 Skype Server 2019에서 PowerShell의 SEFAUtil 기능 사용에 대 한 지원
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: PowerShell을 사용 하 여 SEFAUtil 기능을 가져오는 방법에 대 한 자세한 내용은 누적 업데이트 1을 설치한 후 비즈니스용 Skype 서버 2019을 확인 하세요.'
ms.openlocfilehash: 91958d466a2f51b45ef933d21bfce10f5c61790d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824022"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="0936c-103">비즈니스용 Skype 서버 2019에서 PowerShell을 통해 SEFAUtil 기능 사용</span><span class="sxs-lookup"><span data-stu-id="0936c-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="0936c-104">SEFAUtil (보조 확장 기능 활성화) 비즈니스용 skype server 관리자와 헬프데스크 상담원은 비즈니스용 Skype 서버 사용자를 대신 하 여 대리인 링, 착신 전환, 그룹 통화 픽업 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="0936c-105">또한 관리자는이 도구를 사용 하 여 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="0936c-106">비즈니스용 Skype Server 2019 7 월 누적 업데이트를 설치한 후에는 현재 SEFAUtil를 통해서만 관리할 수 있는 다음 기능은 PowerShell을 통해서도 관리도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="0936c-107">착신 전환 설정</span><span class="sxs-lookup"><span data-stu-id="0936c-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="0936c-108">위임 설정</span><span class="sxs-lookup"><span data-stu-id="0936c-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="0936c-109">팀 구성원 및 관련 설정</span><span class="sxs-lookup"><span data-stu-id="0936c-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="0936c-110">착신 전환 설정</span><span class="sxs-lookup"><span data-stu-id="0936c-110">Call forwarding settings</span></span>

<span data-ttu-id="0936c-111">관리자는 PowerShell에서 다음 cmdlet을 사용 하 여 착신 전환 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="0936c-112">이 cmdlet은 지정 된 사용자의 착신 전환 설정을 개체로 반환 하 고 화면에 동일 하 게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="0936c-113">이 cmdlet은 지정 된 사용자의 착신 전환 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="0936c-114">이 cmdlet은 지정 된 사용자의 착신 전환 설정을 개체로 반환 하 고 성공의 경우 화면에 동일 하 게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="0936c-115">오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="0936c-116">이 cmdlet은 사용자의 착신 전환 설정을 사용 하지 않도록 설정 합니다 (여기에는 두 개의 다른 매개 변수 예가 표시 됩니다.).</span><span class="sxs-lookup"><span data-stu-id="0936c-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="0936c-117">이 cmdlet은 사용자의 착신 전환 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="0936c-118">이 cmdlet은 두 개의 매개 변수 예를 사용 하 여 (예를 들어, 보이스 메일에 대 한 응답을 받지 않고, 두 번째는 다른 SimulRing 응답 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="0936c-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="0936c-119">위임 설정</span><span class="sxs-lookup"><span data-stu-id="0936c-119">Delegation settings</span></span>

<span data-ttu-id="0936c-120">관리자는 PowerShell에서 다음 cmdlet을 사용 하 여 위임 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="0936c-121">이 cmdlet은 대리자 목록의 개체를 반환 하 고 성공한 경우 지정 된 사용자의 대리인 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="0936c-122">오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="0936c-123">이 cmdlet은 지정 된 사용자의 위임 설정을 수정 하 고 대리자 목록의 개체를 반환 하며 성공 여부에 대 한 대리자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="0936c-124">오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="0936c-125">이 cmdlet은 대리인을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="0936c-126">이 cmdlet은 대리인 목록을 특정 대리인으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="0936c-127">팀 구성원 및 관련 설정</span><span class="sxs-lookup"><span data-stu-id="0936c-127">Team members and related settings</span></span>

<span data-ttu-id="0936c-128">관리자는 PowerShell에서 다음 cmdlet을 사용 하 여 팀 구성원 및 관련 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="0936c-129">이 cmdlet은 팀 구성원 목록을 포함 하는 개체를 반환 하 고 성공한 경우 화면에 개체를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="0936c-130">오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="0936c-131">이 cmdlet은 지정 된 사용자의 팀 구성원 목록을 수정 하 고 팀 구성원 목록을 포함 하는 개체를 반환 하 고 성공한 경우 화면에 개체를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="0936c-132">오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="0936c-133">이 cmdlet은 팀 구성원을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="0936c-134">이 cmdlet은 팀 목록을 특정 구성원으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="0936c-135">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0936c-135">More information</span></span>

<span data-ttu-id="0936c-136">온-프레미스 배포의 경우이 기능에 도입 된 cmdlet은 아래 지정 된 액세스 수준에 따라 다음 그룹의 구성원만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="0936c-137">CsAdministrator – 모든 cmdlet에 대해 Get 및 Set</span><span class="sxs-lookup"><span data-stu-id="0936c-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="0936c-138">CsVoiceAdministrator-모든 cmdlet을 가져오고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="0936c-139">CsHelpDesk-모든 cmdlet을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="0936c-140">이러한 관리자 역할에 대 한 자세한 내용은 [비즈니스용 Skype 서버 제어판 관리자](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0936c-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="0936c-141">관리자는 서버 컴퓨터에 직접 또는 원격으로 로그인 하 여 이러한 cmdlet에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="0936c-142">하이브리드 배포의 경우 비즈니스용 Skype 관리자는 모든 cmdlet에 대해 Get 및 Set에 대 한 통화를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="0936c-143">전체 역할 목록에 대 한 자세한 내용은 [Office 365 관리자 역할 정보](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0936c-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="0936c-144">서버 자동 검색을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="0936c-145">Cmdlet 사용에 대 한 추가 라이선스 요구 사항이 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0936c-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
