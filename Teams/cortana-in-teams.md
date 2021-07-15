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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428214"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="c2540-103">Cortana 음성 지원 Teams</span><span class="sxs-lookup"><span data-stu-id="c2540-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="c2540-104">Cortana 음성 지원은 iOS Microsoft Teams Android용 모바일 앱 및 미국, 영국Microsoft Teams 인도 및 오스트레일리아의 사용자에 대한 Microsoft Teams 디스플레이에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="c2540-105">Microsoft Teams 룸 Windows 미국 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="c2540-106">Cortana 음성 지원은 현재 GCC, GCC-High, DoD 및 미국 EDU가 아닌 테넌트에 대해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="c2540-107">Cortana 모바일 앱에서 Teams 음성 지원을 이제 미국 내 EDU 고객에게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="c2540-108">추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="c2540-109">Cortana 음성 Microsoft Teams 룸 미리 보기에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="c2540-110">미리 보기 릴리스에서는 Cortana 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="c2540-111">Cortana 모바일 앱에서 음성 Teams 음성 Microsoft Teams 룸 Windows 및 Microsoft Teams 디스플레이 디바이스에서 음성 언어를 사용하여 Microsoft 365 Enterprise, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="c2540-112">사용자는 Cortana 모바일 앱의 오른쪽 위에 Teams 마이크 단추를 선택하거나 &#8220;Cortana&#8221; 또는 Microsoft Teams 디스플레이를 사용할 때 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="c2540-113">핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;.</span><span class="sxs-lookup"><span data-stu-id="c2540-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="c2540-114">또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="c2540-115">이러한 음성 지원 환경은 [OST(Online](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Services Cortana 약관)에 Office 365 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 엔터프라이즈급 서비스를 사용하여 [전달됩니다.](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="c2540-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="c2540-116">관리자 제어 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c2540-116">Admin control and limitations</span></span>

<span data-ttu-id="c2540-117">Cortana 음성 Teams OST(Online Services 약관)에 Office 365 엔터프라이즈 수준의 개인 정보 보호, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="c2540-118">이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="c2540-119">테넌트 관리자는 테넌트에서 정책(TeamsCortanaPolicy)을 사용하여 Cortana 음성 지원을 Teams 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="c2540-120">이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="c2540-121">관리자는 이 정책 제어 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana 해제되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출과 함께 사용할 수 있는지 여부를 확인할 수 있습니다(예: Microsoft Teams 표시).</span><span class="sxs-lookup"><span data-stu-id="c2540-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="c2540-122">관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 관리 센터에서 정책을 Microsoft Teams 없습니다).</span><span class="sxs-lookup"><span data-stu-id="c2540-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="c2540-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c2540-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c2540-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c2540-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c2540-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c2540-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c2540-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c2540-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="c2540-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="c2540-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="c2540-128">예를 들어 아래 명령은 &#8220;EmployeeCortanaPolicy&#8221; 음성 지원을 사용할 Cortana 새 정책을 Microsoft Teams 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="c2540-129">이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 푸시 단추 호출만 사용하여 Cortana 음성 Microsoft Teams 음성 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="c2540-130">사용자는 Cortana 마이크 단추를 선택하여 Cortana 호출할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="c2540-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="c2540-131">절전 모드 해제 &#8220;(Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="c2540-132">이 예제에서는 정책을 업데이트하고 푸시 단추 및 절전 모드 해제 Cortana 음성 지원을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="c2540-133">당시 영어로 미국의 Microsoft 365 Enterprise 초기 릴리스의 사용 가능한 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="c2540-134">Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="c2540-135">Microsoft Teams 룸 Windows Microsoft Teams 표시 디바이스에서 절전 모드 해제 단어 활성화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="c2540-136">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="c2540-136">User control</span></span>

<span data-ttu-id="c2540-137">개별 사용자는 다양한 디바이스에서 Cortana 음성 지원을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="c2540-138">모바일 앱에서 마이크 Teams 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="c2540-139">마이크 단추를 선택하거나 Cortana "Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="c2540-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="c2540-140">디바이스가 Cortana "Microsoft Teams"라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="c2540-141">디바이스에서 설정을 사용하여 Cortana Teams 디바이스에 대해 사용할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="c2540-142">Microsoft Teams 룸 Windows</span><span class="sxs-lookup"><span data-stu-id="c2540-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="c2540-143">테넌트 수준에서 Cortana 디바이스 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="c2540-144">Cortana 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="c2540-145">디바이스 Cortana 설정하려면 SkypeSettings XML 파일에 이러한 XML 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="c2540-146">디바이스 수준에서 변경을 사용할 수 Cortana 경우 모임 수준에서 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2540-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="c2540-147">모임 Cortana 음성 지원을 사용하도록 설정하려면 토글 **설정** 또는 끄기 를 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c2540-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="c2540-148">모임이 끝나면 Cortana 설정으로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="c2540-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
