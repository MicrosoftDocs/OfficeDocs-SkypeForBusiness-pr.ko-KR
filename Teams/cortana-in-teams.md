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
description: Teams에서 Cortana 음성 지원을 사용하는 방법
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
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686444"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="fbddb-103">Teams의 Cortana 음성 지원</span><span class="sxs-lookup"><span data-stu-id="fbddb-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="fbddb-104">Cortana 음성 지원은 Microsoft Teams iOS 및 Android 모바일 앱, Windows의 Microsoft Teams 회의실 및 Microsoft Teams 디스플레이에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="fbddb-105">현재 GCC, GCC-High, DoD, EDU 테넌트에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="fbddb-106">추가 언어 및 지역으로의 확장은 향후 릴리스의 일부로 발생될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="fbddb-107">Microsoft Teams 회의실의 Cortana 음성 지원은 미리 보기로 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="fbddb-108">미리 보기 릴리스에서 Cortana는 Rally 마이크가 연결된 디바이스에서 EN-US 언어를 사용하여 미국에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="fbddb-109">Teams 모바일 앱, Windows의 Microsoft Teams 회의실 및 Microsoft Teams 디스플레이 장치에서 Cortana 음성 지원을 통해 Microsoft 365 Enterprise 사용자는 음성 자연어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="fbddb-110">사용자는 Teams 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Microsoft Teams &#8220;또는 Microsoft Teams 디스플레이를&#8221; Cortana에게 말하여 Cortana에게 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="fbddb-111">이동 중에는 핸즈프리로 팀과 빠르게 연결하기 위해 사용자는 Megan &#8220;&#8221; 또는 &#8220;모임 팀에 메시지를 보내는 등의 쿼리를&#8221;.</span><span class="sxs-lookup"><span data-stu-id="fbddb-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="fbddb-112">사용자는 다음 모임에 참가하고&#8220;모임에 참가하고&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 확인하여 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="fbddb-113">이러한 음성 지원 환경은 [OST(온라인](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)서비스 약관)에 반영된 Office 365의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 엔터프라이즈급 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="fbddb-114">이미지는 모바일 장치에서 Cortana를 사용하여 채팅을 보내는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Cortana 채팅 세션을 보여주는 모바일 화면 시퀀스](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="fbddb-116">관리자 제어 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="fbddb-116">Admin control and limitations</span></span>

<span data-ttu-id="fbddb-117">Teams의 Cortana 음성 지원은 OST(온라인 서비스 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="fbddb-118">이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="fbddb-119">테넌트 관리자는 정책(TeamsCortanaPolicy)을 사용하여 Teams에서 Cortana 음성 지원을 사용할 수 있는 테넌트의 사용자들을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="fbddb-120">이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="fbddb-121">관리자는 이 정책 컨트롤 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되어 있는지, 푸시 버튼 호출만 사용 또는 해제 단어 호출을 사용할지(Microsoft Teams 디스플레이와 같이 이를 지원하는 디바이스에 적용 가능) 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="fbddb-122">관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 Microsoft Teams 관리 센터에서는 정책을 사용할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="fbddb-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="fbddb-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fbddb-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fbddb-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fbddb-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fbddb-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fbddb-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fbddb-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fbddb-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fbddb-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fbddb-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="fbddb-128">예를 들어 아래 명령은 Microsoft Teams에서 Cortana 음성 지원을 사용할 &#8220;EmployeeCortanaPolicy&#8221; 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="fbddb-129">이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 단추 호출만 사용하여 Microsoft Teams에서 Cortana 음성 지원을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="fbddb-130">사용자는 Teams에서 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="fbddb-131">절전 모드 해제 단어(&#8220;Cortana&#8221; 또는 Corta&#8221; na &#8220;) 호출이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="fbddb-132">이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출 모두에서 Cortana 음성 지원을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="fbddb-133">미국에 있는 Microsoft 365 Enterprise 사용자에 대한 초기 릴리스의 현재 사용 가능한 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="fbddb-134">Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="fbddb-135">Windows 및 Microsoft Teams 디스플레이 장치의 Microsoft Teams 회의실은 절전 모드 해제 단어 활성화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="fbddb-136">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="fbddb-136">User control</span></span>

<span data-ttu-id="fbddb-137">개별 사용자는 다른 장치에서 Cortana 음성 지원을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="fbddb-138">Teams 모바일 앱에서 마이크 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="fbddb-139">Microsoft Teams 회의실에서 마이크 단추를 선택하거나 "Cortana"라고 말하세요.</span><span class="sxs-lookup"><span data-stu-id="fbddb-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="fbddb-140">Microsoft Teams 디스플레이 장치에서 "Cortana"라고 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbddb-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="fbddb-141">장치의 설정을 사용하여 Teams의 Cortana를 장치에 사용할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="fbddb-142">Teams 모바일 앱 또는 Microsoft Teams 디스플레이</span><span class="sxs-lookup"><span data-stu-id="fbddb-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="fbddb-143">Teams 모바일 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="fbddb-144">설정   >  **Cortana를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbddb-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="fbddb-145">**토글을 끄거나** **끄기**</span><span class="sxs-lookup"><span data-stu-id="fbddb-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="fbddb-146">Microsoft Teams 디스플레이</span><span class="sxs-lookup"><span data-stu-id="fbddb-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="fbddb-147">Microsoft Teams 디스플레이의 앰비언트(홈) 화면으로 이동</span><span class="sxs-lookup"><span data-stu-id="fbddb-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="fbddb-148">사용자 아바타를 선택한 다음 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbddb-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="fbddb-149">Cortana를 사용하도록 설정되면 "Cortana, 설정으로 이동"이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="fbddb-150">**토글을 끄거나** **끄기**</span><span class="sxs-lookup"><span data-stu-id="fbddb-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="fbddb-151">Windows의 Microsoft Teams 회의실</span><span class="sxs-lookup"><span data-stu-id="fbddb-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="fbddb-152">테넌트 수준에서 Cortana를 사용하도록 설정한 경우 디바이스 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="fbddb-153">Cortana는 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="fbddb-154">장치 수준에서 Cortana를 사용하려면 SkypeSettings XML 파일에 다음 XML 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="fbddb-155">장치 수준에서 Cortana를 사용하도록 설정한 경우 모임 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="fbddb-156">모임 중에 Cortana 음성 지원을 사용하도록 설정하려면 토글 설정 또는 **해제를** **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fbddb-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="fbddb-157">모임이 종료된 후 Cortana는 장치 수준 설정 집합으로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="fbddb-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
