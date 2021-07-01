---
title: Cortana 음성 지원 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 음성 지원과 함께 Cortana 방법을 Teams
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
ms.openlocfilehash: 0b343a3f69d2b0f97f9d7d3054951719da2e9e43
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219145"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="bdd6b-103">Cortana 음성 지원 Teams</span><span class="sxs-lookup"><span data-stu-id="bdd6b-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="bdd6b-104">Cortana 음성 지원은 iOS Microsoft Teams Android용 모바일 앱 및 미국, 영국Microsoft Teams 인도 및 오스트레일리아의 사용자에 대한 Microsoft Teams 디스플레이에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="bdd6b-105">Microsoft Teams 룸 Windows 미국 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="bdd6b-106">Cortana 음성 지원은 현재 GCC, GCC-High, DoD 및 미국 EDU가 아닌 테넌트에 대해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="bdd6b-107">Cortana 모바일 앱에서 Teams 음성 지원을 이제 미국 내 EDU 고객에게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="bdd6b-108">추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="bdd6b-109">Cortana 음성 Microsoft Teams 룸 미리 보기에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="bdd6b-110">미리 보기 릴리스에서는 Cortana 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="bdd6b-111">Cortana 모바일 앱에서 음성 Teams 음성 Microsoft Teams 룸 Windows 및 Microsoft Teams 디스플레이 디바이스에서 음성 언어를 사용하여 Microsoft 365 Enterprise, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="bdd6b-112">사용자는 Cortana 모바일 앱의 오른쪽 위에 Teams 마이크 단추를 선택하거나 &#8220;Cortana&#8221; 또는 Microsoft Teams 디스플레이를 사용할 때 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="bdd6b-113">핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="bdd6b-114">또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="bdd6b-115">이러한 음성 지원 환경은 [OST(Online](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Services Cortana 약관)에 Office 365 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 엔터프라이즈급 서비스를 사용하여 [전달됩니다.](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="bdd6b-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="bdd6b-116">이미지는 모바일 장치에서 Cortana 사용하여 채팅을 보내는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-116">The image shows sending a chat using Cortana on a mobile device.</span></span>

![채팅 세션을 보여주는 일련의 Cortana 화면](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="bdd6b-118">관리자 제어 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="bdd6b-118">Admin control and limitations</span></span>

<span data-ttu-id="bdd6b-119">Cortana 음성 Teams OST(Online Services 약관)에 Office 365 엔터프라이즈 수준의 개인 정보 보호, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-119">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="bdd6b-120">이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-120">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="bdd6b-121">테넌트 관리자는 테넌트에서 정책(TeamsCortanaPolicy)을 사용하여 Cortana 음성 지원을 Teams 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-121">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="bdd6b-122">이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-122">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="bdd6b-123">관리자는 이 정책 제어 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana 해제되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출과 함께 사용할 수 있는지 여부를 확인할 수 있습니다(예: Microsoft Teams 표시).</span><span class="sxs-lookup"><span data-stu-id="bdd6b-123">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="bdd6b-124">관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 관리 센터에서 정책을 Microsoft Teams 없습니다).</span><span class="sxs-lookup"><span data-stu-id="bdd6b-124">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="bdd6b-125">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="bdd6b-125">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="bdd6b-126">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="bdd6b-126">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="bdd6b-127">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="bdd6b-127">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="bdd6b-128">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="bdd6b-128">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="bdd6b-129">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="bdd6b-129">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="bdd6b-130">예를 들어 아래 명령은 &#8220;EmployeeCortanaPolicy&#8221; 음성 지원을 사용할 Cortana 새 정책을 Microsoft Teams 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-130">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="bdd6b-131">이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 푸시 단추 호출만 사용하여 Cortana 음성 Microsoft Teams 음성 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-131">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="bdd6b-132">사용자는 Cortana 마이크 단추를 선택하여 Cortana 호출할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-132">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="bdd6b-133">절전 모드 해제 &#8220;(Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-133">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="bdd6b-134">이 예제에서는 정책을 업데이트하고 푸시 단추 및 절전 모드 해제 Cortana 음성 지원을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-134">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="bdd6b-135">당시 영어로 미국의 Microsoft 365 Enterprise 초기 릴리스의 사용 가능한 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-135">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="bdd6b-136">Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-136">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="bdd6b-137">Microsoft Teams 룸 Windows Microsoft Teams 표시 디바이스에서 절전 모드 해제 단어 활성화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-137">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="bdd6b-138">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="bdd6b-138">User control</span></span>

<span data-ttu-id="bdd6b-139">개별 사용자는 다양한 디바이스에서 Cortana 음성 지원을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-139">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="bdd6b-140">모바일 앱에서 마이크 Teams 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-140">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="bdd6b-141">마이크 단추를 선택하거나 Cortana "Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-141">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="bdd6b-142">디바이스가 Cortana "Microsoft Teams"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-142">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="bdd6b-143">디바이스에서 설정을 사용하여 Cortana Teams 디바이스에 대해 사용할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-143">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="bdd6b-144">Teams 앱 또는 Microsoft Teams 표시</span><span class="sxs-lookup"><span data-stu-id="bdd6b-144">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="bdd6b-145">모바일 앱을 Teams 를 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-145">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="bdd6b-146">를 **설정**  >  **Cortana.**</span><span class="sxs-lookup"><span data-stu-id="bdd6b-146">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="bdd6b-147">토글을 On 또는 **Off로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="bdd6b-147">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="bdd6b-148">Microsoft Teams 표시</span><span class="sxs-lookup"><span data-stu-id="bdd6b-148">Microsoft Teams display</span></span>

  1. <span data-ttu-id="bdd6b-149">화면의 앰비언트(홈) 화면으로 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-149">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="bdd6b-150">사용자 아바타를 선택한 다음 을 **설정.**</span><span class="sxs-lookup"><span data-stu-id="bdd6b-150">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="bdd6b-151">Cortana 설정되어 있는 경우 "Cortana, 설정."</span><span class="sxs-lookup"><span data-stu-id="bdd6b-151">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="bdd6b-152">토글을 On 또는 **Off로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="bdd6b-152">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="bdd6b-153">Microsoft Teams 룸 Windows</span><span class="sxs-lookup"><span data-stu-id="bdd6b-153">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="bdd6b-154">테넌트 수준에서 Cortana 디바이스 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-154">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="bdd6b-155">Cortana 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-155">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="bdd6b-156">디바이스 Cortana 설정하려면 SkypeSettings XML 파일에 이러한 XML 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-156">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="bdd6b-157">디바이스 수준에서 변경을 사용할 수 Cortana 경우 모임 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-157">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="bdd6b-158">모임 Cortana 음성 지원을 사용하도록 설정하려면 토글 **설정** 또는 끄기 를 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="bdd6b-158">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="bdd6b-159">모임이 끝나면 Cortana 설정으로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-159">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
