---
title: 가상화 된 데스크톱 인프라 팀
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: VDI (가상화 데스크톱 인프라) 환경에서 Microsoft 팀을 실행 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fa560347d7263dafafc4f98e031b3b267f8fb12
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570226"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="9faea-103">가상화 된 데스크톱 인프라 팀</span><span class="sxs-lookup"><span data-stu-id="9faea-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="9faea-104">이 문서에서는 가상화 된 환경에서 Microsoft 팀을 사용 하는 데 필요한 요구 사항과 제한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="9faea-105">VDI 란?</span><span class="sxs-lookup"><span data-stu-id="9faea-105">What is VDI?</span></span>

<span data-ttu-id="9faea-106">VDI (가상 데스크톱 인프라)는 데스크톱 운영 체제 및 응용 프로그램을 데이터 센터의 중앙 집중식 서버에 호스팅하는 가상화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="9faea-107">이렇게 하면 완전히 안전한 중앙 집중화 된 원본을 사용 하 여 사용자에 게 개인 설정 된 데스크톱 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="9faea-108">현재 가상화 된 환경의 팀은 전용 영구 가상화 컴퓨터 (VM)의 공동 작업 및 채팅 기능에 대 한 지원으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="9faea-109">최적의 사용자 환경을 보장 하려면이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9faea-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="9faea-110">팀 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9faea-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="9faea-111">팀에서 통화 및 모임 기능을 끄려면 정책 설정</span><span class="sxs-lookup"><span data-stu-id="9faea-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="9faea-112">팀 통화 및 모임 환경은 VDI 환경에 최적화 되어 있지 않습니다 (곧 출시 예정).</span><span class="sxs-lookup"><span data-stu-id="9faea-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="9faea-113">팀에서 통화 및 모임 기능을 끄려면 사용자 수준 정책을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="9faea-114">팀 데스크톱 앱 또는 웹 앱을 사용 하 여 VDI에서 팀을 완전히 실행 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="9faea-115">그러나 사용자 환경을 손상 시 키 지 않도록 정책을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="9faea-116">정책 변경 내용을 전파 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="9faea-117">지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="9faea-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="9faea-118">팀 통화 및 회의가 가상 데스크톱 환경에서 사용 하도록 최적화 된 경우 이러한 정책을 전환 하 고 사용자가 평소 대로 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="9faea-119">전화</span><span class="sxs-lookup"><span data-stu-id="9faea-119">Calling</span></span>

<span data-ttu-id="9faea-120">**CSTeamsCallingPolicy** cmdlet을 사용 하 여 사용자가 개인 및 그룹 채팅에서 통화 및 통화 옵션을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="9faea-121">정책 설정 및 권장 값 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="9faea-122">정책 이름</span><span class="sxs-lookup"><span data-stu-id="9faea-122">Policy name</span></span>  |<span data-ttu-id="9faea-123">설명</span><span class="sxs-lookup"><span data-stu-id="9faea-123">Description</span></span> |<span data-ttu-id="9faea-124">권장 값</span><span class="sxs-lookup"><span data-stu-id="9faea-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9faea-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="9faea-125">AllowCalling</span></span>    |<span data-ttu-id="9faea-126">Interop 호출 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="9faea-127">이 기능을 켜면 비즈니스용 Skype 사용자가 팀 사용자와 일대일 통화를 하거나 그 반대의 경우도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="9faea-128">False로 설정 하면 비즈니스용 Skype 사용자가 팀에서 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="9faea-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="9faea-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="9faea-130">팀 클라이언트의 왼쪽에 있는 앱 바에서 호출 앱을 사용할 수 있는지 여부와 사용자가 비공개 채팅의 통화 및 비디오 통화 옵션을 볼 것인지를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="9faea-131">팀의 왼쪽에 있는 앱 표시줄에서 호출 앱을 제거 하 고 개인 채팅에서 통화 및 비디오 통화 옵션을 제거 하려면 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="9faea-132">호출 정책 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="9faea-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="9faea-133">관리자 권한으로 Windows PowerShell 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="9faea-134">Skype Online 커넥터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="9faea-135">호출 정책 옵션의 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="9faea-136">모든 통화 정책을 사용 하지 않도록 설정 하는 기본 제공 정책 옵션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="9faea-137">다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="9faea-138">가상화 된 환경에서 팀을 사용할 모든 사용자에 게 DisallowCalling 기본 제공 정책 옵션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="9faea-139">팀 호출 정책에 대 한 자세한 내용은 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9faea-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="9faea-140">Meeting</span><span class="sxs-lookup"><span data-stu-id="9faea-140">Meetings</span></span>

<span data-ttu-id="9faea-141">**CsTeamsMeetingPolicy** cmdlet을 사용 하 여 사용자가 만들 수 있는 모임의 유형, 모임 중에 액세스할 수 있는 기능, 익명 사용자와 외부 사용자가 사용할 수 있는 모임 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="9faea-142">정책 설정 및 권장 값 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="9faea-143">정책 이름</span><span class="sxs-lookup"><span data-stu-id="9faea-143">Policy Name</span></span> |<span data-ttu-id="9faea-144">설명</span><span class="sxs-lookup"><span data-stu-id="9faea-144">Description</span></span>|<span data-ttu-id="9faea-145">권장 값</span><span class="sxs-lookup"><span data-stu-id="9faea-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="9faea-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9faea-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="9faea-147">사용자가 비공개 모임을 예약할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="9faea-148">사용자가 비공개 모임을 예약할 수 없도록 하려면 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="9faea-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9faea-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="9faea-150">사용자가 채널 회의를 예약할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="9faea-151">사용자가 채널 모임을 예약할 수 없도록 하려면 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="9faea-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="9faea-152">AllowMeetNow</span></span> |<span data-ttu-id="9faea-153">사용자가 임시 모임을 만들거나 시작 하도록 허용 되었는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="9faea-154">사용자가 임시 모임을 시작할 수 없도록 하려면이를 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="9faea-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="9faea-155">ScreenSharingMode</span></span> | <span data-ttu-id="9faea-156">사용자가 통화 또는 모임에서 화면을 공유할 수 있는 모드를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="9faea-157">사용자가 화면을 공유할 수 없도록 하려면 사용 안 함으로 설정</span><span class="sxs-lookup"><span data-stu-id="9faea-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="9faea-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="9faea-158">AllowIPVideo</span></span> |<span data-ttu-id="9faea-159">사용자의 모임 또는 통화에서 비디오를 사용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="9faea-160">사용자가 비디오를 공유 하지 못하도록 하려면 False로 설정</span><span class="sxs-lookup"><span data-stu-id="9faea-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="9faea-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="9faea-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="9faea-162">익명 사용자가 PSTN 번호로 전화를 걸 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="9faea-163">False로 설정 하 여 익명 사용자가 전화를 걸지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="9faea-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="9faea-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="9faea-165">익명 사용자가 모임을 시작할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="9faea-166">사용자가 모임을 시작할 수 없도록 하려면 False로 설정</span><span class="sxs-lookup"><span data-stu-id="9faea-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="9faea-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="9faea-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="9faea-168">사용자가 Outlook 데스크톱 클라이언트에서 팀 모임을 예약할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="9faea-169">False로 설정 하 여 사용자가 Outlook 데스크톱 클라이언트에서 팀 모임 일정을 예약 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="9faea-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="9faea-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="9faea-171">참가자가 화면 공유를 요청 하거나 제어권을 부여할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="9faea-172">사용자가 모임에서 제어권을 제공 하 고 요청 하지 못하도록 하려면 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="9faea-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="9faea-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="9faea-174">외부 참가자가 화면 공유를 요청 하거나 제어권을 부여할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="9faea-175">False로 설정 하면 외부 사용자가 모임에서 제어권을 요청 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="9faea-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="9faea-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="9faea-177">사용자의 모임에서 PowerPoint 공유를 허용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="9faea-178">False로 설정 하 여 사용자가 모임에서 PowerPoint 파일을 공유 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="9faea-179">AllowWhiteboard 보드</span><span class="sxs-lookup"><span data-stu-id="9faea-179">AllowWhiteboard</span></span> | <span data-ttu-id="9faea-180">사용자의 모임에서 화이트 보드를 사용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="9faea-181">False로 설정 하면 모임에서 화이트 보드를 금지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="9faea-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="9faea-182">AllowTranscription</span></span> |<span data-ttu-id="9faea-183">사용자의 모임에서 실시간 및/또는 모임에 대 한 캡션과/또는 게시물을 사용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="9faea-184">False로 설정 하 여 모임에서의 기록 및 캡션을 금지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="9faea-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="9faea-185">AllowSharedNotes</span></span> | <span data-ttu-id="9faea-186">사용자가 공유 노트를 사용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="9faea-187">False로 설정 하 여 사용자가 공유 메모를 작성 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="9faea-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="9faea-188">MediaBitRateKB</span></span> |<span data-ttu-id="9faea-189">모임에서 오디오/비디오/앱 공유 전송에 대 한 미디어 비트 전송률을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="9faea-190">제안 값은 5000 (5 MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="9faea-191">조직의 요구 사항에 따라 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="9faea-192">모임 정책 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="9faea-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="9faea-193">관리자 권한으로 Windows PowerShell 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="9faea-194">Skype Online 커넥터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="9faea-195">모임 정책 옵션 목록 보기</span><span class="sxs-lookup"><span data-stu-id="9faea-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="9faea-196">모든 모임 정책이 비활성화 되어 있는 기본 제공 정책 옵션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="9faea-197">다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="9faea-198">가상화 된 환경에서 팀을 사용할 모든 사용자에 게 AllOff 기본 제공 정책 옵션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="9faea-199">팀 모임 정책에 대 한 자세한 내용은 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9faea-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="9faea-200">가상화 공급자 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9faea-200">Virtualization provider requirements</span></span>

<span data-ttu-id="9faea-201">주요 가상화 솔루션 공급자에서 팀 앱의 유효성을 검사 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="9faea-202">여러 시장 공급자를 사용 하는 경우 가상화 솔루션 공급자에 게 문의 하 여 최소 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="9faea-203">가상 컴퓨터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9faea-203">Virtual Machine requirements</span></span>

<span data-ttu-id="9faea-204">가상화 된 환경에서 다양 한 작업 부하와 사용자 요구를 사용 하 여 권장 되는 최소 VM 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="9faea-205">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9faea-205">Parameter</span></span>  |<span data-ttu-id="9faea-206">측정값과</span><span class="sxs-lookup"><span data-stu-id="9faea-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="9faea-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="9faea-207">vCPU</span></span>    |  <span data-ttu-id="9faea-208">2 코어</span><span class="sxs-lookup"><span data-stu-id="9faea-208">2 cores</span></span>       |
|<span data-ttu-id="9faea-209">할당할</span><span class="sxs-lookup"><span data-stu-id="9faea-209">RAM</span></span>     |  <span data-ttu-id="9faea-210">4GB</span><span class="sxs-lookup"><span data-stu-id="9faea-210">4 GB</span></span>      |
|<span data-ttu-id="9faea-211">용량</span><span class="sxs-lookup"><span data-stu-id="9faea-211">Storage</span></span>     | <span data-ttu-id="9faea-212">8gb</span><span class="sxs-lookup"><span data-stu-id="9faea-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="9faea-213">가상 컴퓨터 운영 체제 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9faea-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="9faea-214">VM에 대해 지원 되는 운영 체제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="9faea-215">Windows 10 이상</span><span class="sxs-lookup"><span data-stu-id="9faea-215">Windows 10 and later</span></span>
- <span data-ttu-id="9faea-216">Windows Server 2012 R2 이상</span><span class="sxs-lookup"><span data-stu-id="9faea-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="9faea-217">VDI에 팀 설치</span><span class="sxs-lookup"><span data-stu-id="9faea-217">Install Teams on VDI</span></span>

<span data-ttu-id="9faea-218">팀 데스크톱 앱을 배포 하는 프로세스와 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="9faea-219">환경에 따라 다음 링크 중 하나를 사용 하 여 팀 MSI 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="9faea-220">64 비트 운영 체제와 함께 VDI VM에 대 한 64 비트 버전을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="9faea-221">32 비트 버전</span><span class="sxs-lookup"><span data-stu-id="9faea-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="9faea-222">64 비트 버전</span><span class="sxs-lookup"><span data-stu-id="9faea-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="9faea-223">다음 명령을 실행 하 여 VDI VM에 MSI를 설치 하거나 업데이트를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="9faea-224">이렇게 하면 프로그램 파일에 팀이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="9faea-225">이 시점에서 골든 이미지 설정이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="9faea-226">다음 대화형 로그온 세션에서 팀을 시작 하 고 자격 증명을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="9faea-227">ALLUSER 속성을 사용 하 여 VDI에 팀을 설치할 때는 팀의 자동 실행을 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="9faea-228">다음 명령을 실행 하 여 VDI VM에서 MSI를 제거 하거나 업데이트 준비를 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="9faea-229">이렇게 하면 프로그램 파일에서 팀이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="9faea-230">알려진 문제점 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="9faea-230">Known issues and limitations</span></span>

<span data-ttu-id="9faea-231">다음은 VDI의 팀에 대해 알려진 문제점 및 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="9faea-232">**공유 세션 호스트 형식 배포**: 공유 세션 호스트 형식 배포 (예를 들어 공유 비영구 VM 구성)가 범위를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="9faea-233">**통화 및 모임**:</span><span class="sxs-lookup"><span data-stu-id="9faea-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="9faea-234">통화 및 모임 시나리오는 VDI에 최적화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="9faea-235">이러한 시나리오는 제대로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="9faea-236">[팀에서 통화 및 모임 기능을 해제 하려면 설정 정책](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) 에 설명 된 대로 사용자 수준 정책을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="9faea-237">이 문서에 설명 된 정책 적용은 다른 정책에 따라 호출 및 모임 기능을 사용 하는 기능에 영향을 미치며 조직의 다른 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="9faea-238">조직의 사용자가 비 VDI 클라이언트를 사용 하는 경우 정책을 적용 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="9faea-239">**다른 사용자가 만든 통화와 모임 참가**: 정책은 사용자가 모임을 만들 수 없도록 제한 하지만 다른 사용자가 모임에서 전화를 거는 경우에도 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="9faea-240">이러한 모임에서 비디오를 공유 하 고, 화이트 보드와 기타 기능을 사용 하는 것은 TeamsMeetingPolicy를 사용 하 여 해당 기능을 비활성화 했는지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="9faea-241">**캐시 된 콘텐츠**: 팀이 실행 중인 가상 환경이 영구적이 지 않으며 각 사용자 세션이 끝날 때 데이터가 정리 되는 경우 사용자가 동일 하 게 액세스 했는지 여부에 관계 없이 콘텐츠 새로 고침으로 인해 성능이 저하 될 수 있습니다. 이전 세션의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="9faea-242">**클라이언트 업데이트**: VDI의 팀이 컴퓨터별 MSI 설치에 따라 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-242">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="9faea-243">[VDI에 팀 설치](#install-teams-on-vdi) 섹션에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="9faea-244">최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="9faea-245">**사용자 환경**: Vdi 환경의 팀 사용자 환경은 비 vdi 환경과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="9faea-246">환경의 정책 설정 및/또는 기능 지원 때문에 차이점이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9faea-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="9faea-247">VDI와 관련 되지 않은 팀의 알려진 문제에 대해서는 [Microsoft 팀의 알려진 문제점](Known-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9faea-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9faea-248">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9faea-248">Related topics</span></span>

- [<span data-ttu-id="9faea-249">MSI를 사용 하 여 Microsoft 팀 설치</span><span class="sxs-lookup"><span data-stu-id="9faea-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
