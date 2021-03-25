---
title: Microsoft Teams의 Cortana 음성 지원
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams에서 Cortana 음성 지원을 사용하는 방법에 대해 자세히 알아보십시오.
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118477"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="c0ae7-103">Teams의 Cortana 음성 지원</span><span class="sxs-lookup"><span data-stu-id="c0ae7-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="c0ae7-104">Cortana 음성 지원은 Microsoft Teams iOS 및 Android 모바일 앱, Windows의 Microsoft Teams Rooms 및 Microsoft Teams 디스플레이에서 미국의 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="c0ae7-105">현재 GCC, GCC-High, DoD, EDU 테넌트에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="c0ae7-106">추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="c0ae7-107">Microsoft Teams Rooms의 Cortana 음성 지원은 미리 보기에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="c0ae7-108">미리 보기 릴리스에서 Cortana는 Rally 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="c0ae7-109">Teams 모바일 앱, Windows의 Microsoft Teams Rooms 및 Microsoft Teams 디스플레이 디바이스에서 Cortana 음성 지원을 사용하면 Microsoft 365 Enterprise 사용자가 음성 자연어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="c0ae7-110">사용자는 Teams 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Microsoft Teams &#8220;Microsoft Teams&#8221; Microsoft Teams 디스플레이를 사용할 때 Cortana에 대해 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="c0ae7-111">핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="c0ae7-112">또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="c0ae7-113">이러한 음성 지원 환경은 [OST(Online Services 약관)에](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)반영된 Office 365의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 엔터프라이즈급 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="c0ae7-114">이미지는 모바일 장치에서 Cortana를 사용하여 채팅을 보내는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Cortana 채팅 세션을 보여주는 일련의 모바일 화면](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="c0ae7-116">관리자 제어 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c0ae7-116">Admin control and limitations</span></span>

<span data-ttu-id="c0ae7-117">Teams의 Cortana 음성 지원은 OST(Online Services 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="c0ae7-118">이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="c0ae7-119">테넌트 관리자는 테넌트에서 정책을 사용하여 Teams에서 Cortana 음성 지원을 사용할 수 있는 사용자(TeamsCortanaPolicy)를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="c0ae7-120">이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="c0ae7-121">관리자는 이 정책 제어 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출을 사용하는지 여부를 확인할 수 있습니다(Microsoft Teams 표시와 같이 해당 기능을 지원하는 디바이스에 해당).</span><span class="sxs-lookup"><span data-stu-id="c0ae7-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="c0ae7-122">관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 Microsoft Teams 관리 센터에서 정책을 사용할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="c0ae7-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="c0ae7-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c0ae7-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c0ae7-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c0ae7-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c0ae7-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c0ae7-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c0ae7-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c0ae7-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c0ae7-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c0ae7-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="c0ae7-128">예를 들어 아래 명령은 Microsoft Teams의 Cortana 음성 지원을 사용할 &#8220;EmployeeCortanaPolicy&#8221; 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="c0ae7-129">이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 단추 호출만 사용하여 Microsoft Teams에서 Cortana 음성 지원을 사용하도록 설정하는 기능을 보여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="c0ae7-130">사용자는 Teams에서 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="c0ae7-131">절전 모드 해제 &#8220;Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="c0ae7-132">이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출을 모두 사용하여 Cortana 음성 지원을 사용하도록 설정하는 기능을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="c0ae7-133">당시 미국의 Microsoft 365 Enterprise 사용자에 대한 초기 릴리스의 영어로 사용할 수 있는 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="c0ae7-134">Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="c0ae7-135">Windows 및 Microsoft Teams 디스플레이 디바이스의 Microsoft Teams Rooms는 절전 모드 해제 단어 활성화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="c0ae7-136">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="c0ae7-136">User control</span></span>

<span data-ttu-id="c0ae7-137">개별 사용자는 다른 장치에서 Cortana 음성 지원을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="c0ae7-138">Teams 모바일 앱에서 마이크 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="c0ae7-139">마이크 단추를 선택하거나 Microsoft Teams Rooms에서 "Cortana"라고 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="c0ae7-140">Microsoft Teams 디스플레이 디바이스에서 "Cortana"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="c0ae7-141">디바이스에서 설정을 사용하여 Teams의 Cortana를 디바이스에 사용할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="c0ae7-142">Teams 모바일 앱 또는 Microsoft Teams 표시</span><span class="sxs-lookup"><span data-stu-id="c0ae7-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="c0ae7-143">Teams 모바일 앱을 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="c0ae7-144">설정   >  **Cortana를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ae7-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="c0ae7-145">토글을 On 또는 **Off로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ae7-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="c0ae7-146">Microsoft Teams 표시</span><span class="sxs-lookup"><span data-stu-id="c0ae7-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="c0ae7-147">Microsoft Teams 표시의 앰비언트(홈) 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="c0ae7-148">사용자 아바타를 선택한 다음 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ae7-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="c0ae7-149">Cortana를 사용하도록 설정한 경우 "Cortana, 설정으로 이동합니다."</span><span class="sxs-lookup"><span data-stu-id="c0ae7-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="c0ae7-150">토글을 On 또는 **Off로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ae7-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="c0ae7-151">Windows의 Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="c0ae7-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="c0ae7-152">테넌트 수준에서 Cortana를 사용하도록 설정한 경우 디바이스 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="c0ae7-153">Cortana는 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="c0ae7-154">디바이스 수준에서 Cortana를 사용하도록 설정하려면 SkypeSettings XML 파일에 이러한 XML 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="c0ae7-155">디바이스 수준에서 Cortana를 사용하도록 설정한 경우 모임 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="c0ae7-156">모임 중에 Cortana 음성 지원을 사용하도록 설정하려면 토글 **설정** 또는 끄기 를 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0ae7-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="c0ae7-157">모임이 종료된 후 Cortana는 디바이스 수준 설정 집합으로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="c0ae7-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>