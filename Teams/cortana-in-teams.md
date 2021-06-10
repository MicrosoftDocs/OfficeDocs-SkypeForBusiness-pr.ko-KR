---
title: Cortana 음성 지원에서 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Cortana 음성 지원을 사용하는 방법을 Teams
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
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886737"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="5bef1-103">Cortana 음성 지원에서 Teams</span><span class="sxs-lookup"><span data-stu-id="5bef1-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="5bef1-104">Cortana 음성 지원은 iOS 및 android용 Microsoft Teams 앱 및 미국, 영국Microsoft Teams 캐나다, 인도 및 오스트레일리아의 사용자에 대한 Microsoft Teams 디스플레이에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span>  <span data-ttu-id="5bef1-105">Microsoft Teams 룸 Windows 미국 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="5bef1-106">Cortana 음성 지원은 현재 GCC, GCC, DoD, EDU 테넌트에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="5bef1-107">추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-107">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="5bef1-108">Microsoft Teams 룸의 Cortana 음성 지원은 미리 보기에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-108">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="5bef1-109">미리 보기 릴리스에서 Cortana는 Rally 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-109">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="5bef1-110">Teams 모바일 앱의 Cortana 음성 지원, Microsoft Teams 룸 Windows 및 Microsoft Teams Microsoft 365 Enterprise 디스플레이 디바이스에서 사용자가 음성 언어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-110">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="5bef1-111">사용자는 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Teams 또는 &#8220;&#8221; 또는 Microsoft Teams 디스플레이를 사용할 때 Cortana에 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-111">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="5bef1-112">핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;.</span><span class="sxs-lookup"><span data-stu-id="5bef1-112">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="5bef1-113">또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-113">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="5bef1-114">이러한 음성 지원 환경은 [OST(Online Services](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)약관)에 Office 365, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 엔터프라이즈급 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-114">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="5bef1-115">이미지는 모바일 장치에서 Cortana를 사용하여 채팅을 보내는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-115">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Cortana 채팅 세션을 보여주는 일련의 모바일 화면](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="5bef1-117">관리자 제어 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5bef1-117">Admin control and limitations</span></span>

<span data-ttu-id="5bef1-118">OST(Online Services Teams 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 이 서비스의 Cortana 음성 지원이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-118">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="5bef1-119">이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-119">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="5bef1-120">테넌트 관리자는 정책(TeamsCortanaPolicy)을 사용하여 테넌트에서 Cortana 음성 지원을 사용할 Teams 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-120">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="5bef1-121">이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-121">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="5bef1-122">관리자는 이 정책 컨트롤 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출도 사용할 수 있는지 여부를 확인할 수 있습니다(예: Microsoft Teams 표시).</span><span class="sxs-lookup"><span data-stu-id="5bef1-122">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="5bef1-123">관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 관리 센터에서 정책을 Microsoft Teams 없습니다).</span><span class="sxs-lookup"><span data-stu-id="5bef1-123">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="5bef1-124">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5bef1-124">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5bef1-125">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5bef1-125">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5bef1-126">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5bef1-126">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5bef1-127">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5bef1-127">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5bef1-128">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5bef1-128">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="5bef1-129">예를 들어 아래 명령은 &#8220;CortanaPolicy&#8221; Cortana voice assistance를 사용하지 않도록 Microsoft Teams 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-129">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="5bef1-130">이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 푸시 단추 호출만 사용하여 Microsoft Teams Cortana 음성 지원을 사용하도록 설정하는 것이 보여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-130">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="5bef1-131">사용자는 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="5bef1-131">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="5bef1-132">절전 모드 해제 &#8220;Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-132">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="5bef1-133">이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출을 모두 사용하여 Cortana 음성 지원을 사용하도록 설정하는 기능을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-133">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="5bef1-134">당시 영어로 미국의 Microsoft 365 Enterprise 초기 릴리스의 사용 가능한 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-134">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="5bef1-135">Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-135">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="5bef1-136">Microsoft Teams 룸 Windows Microsoft Teams 표시 디바이스에서 절전 모드 해제 단어 활성화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-136">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="5bef1-137">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="5bef1-137">User control</span></span>

<span data-ttu-id="5bef1-138">개별 사용자는 다른 장치에서 Cortana 음성 지원을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-138">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="5bef1-139">모바일 앱에서 마이크 Teams 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-139">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="5bef1-140">마이크 단추를 선택하거나"Cortana"라고 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="5bef1-140">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="5bef1-141">디스플레이 디바이스에 "Cortana"라고 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-141">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="5bef1-142">디바이스에서 설정을 사용하여 디바이스에 Teams Cortana를 사용하도록 설정하는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-142">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="5bef1-143">Teams 앱 또는 Microsoft Teams 표시</span><span class="sxs-lookup"><span data-stu-id="5bef1-143">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="5bef1-144">모바일 앱을 Teams 를 하세요.</span><span class="sxs-lookup"><span data-stu-id="5bef1-144">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="5bef1-145">**Cortana 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bef1-145">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="5bef1-146">토글을 On 또는 **Off로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bef1-146">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="5bef1-147">Microsoft Teams 표시</span><span class="sxs-lookup"><span data-stu-id="5bef1-147">Microsoft Teams display</span></span>

  1. <span data-ttu-id="5bef1-148">화면의 앰비언트(홈) 화면으로 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5bef1-148">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="5bef1-149">사용자 아바타를 선택한 다음 을 **설정.**</span><span class="sxs-lookup"><span data-stu-id="5bef1-149">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="5bef1-150">Cortana를 사용하도록 설정하면 "Cortana, 설정."</span><span class="sxs-lookup"><span data-stu-id="5bef1-150">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="5bef1-151">토글을 On 또는 **Off로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bef1-151">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="5bef1-152">Microsoft Teams 룸 Windows</span><span class="sxs-lookup"><span data-stu-id="5bef1-152">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="5bef1-153">테넌트 수준에서 Cortana를 사용하도록 설정한 경우 디바이스 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-153">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="5bef1-154">Cortana는 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-154">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="5bef1-155">디바이스 수준에서 Cortana를 사용하도록 설정하려면 SkypeSettings XML 파일에 이러한 XML 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-155">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="5bef1-156">디바이스 수준에서 Cortana를 사용하도록 설정한 경우 모임 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-156">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="5bef1-157">모임 중에 Cortana 음성 지원을 사용하도록 설정하려면 토글 **설정** 또는 끄기 를 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bef1-157">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="5bef1-158">모임이 종료된 후 Cortana는 디바이스 수준 설정 집합으로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="5bef1-158">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
