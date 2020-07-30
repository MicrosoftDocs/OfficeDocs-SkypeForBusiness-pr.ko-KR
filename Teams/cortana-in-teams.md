---
title: Microsoft 팀의 Cortana 음성 도우미
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 팀에서 Cortana 음성 도우미를 사용 하는 방법 알아보기
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522324"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="f6937-103">팀의 Cortana 음성 지원</span><span class="sxs-lookup"><span data-stu-id="f6937-103">Cortana voice assistance in Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> <span data-ttu-id="f6937-104">Cortana 음성 지원은 미국 사용자 용 Microsoft 팀 iOS 및 Android 모바일 앱에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="f6937-105">현재 GCC, GCC-High, DoD, .EDU 테 넌 트에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="f6937-106">이후 릴리스의 일부로 추가 언어 및 지역으로 확장이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="f6937-107">팀 모바일 앱의 Cortana 음성 지원은 Microsoft 365 Enterprise 사용자가 음성 자연어를 사용 하 여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="f6937-108">사용자는 팀 모바일 앱의 오른쪽 위에 있는 마이크 단추를 클릭 하 여 Cortana에 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="f6937-109">이동 중에 팀과 빠르게 연결 하기 위해 사용자는 "call Megan" 또는 "다음 모임에 메시지 보내기"와 같은 쿼리를 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-109">To quickly connect with their team while on the go, users can say queries such as “call Megan” or “send a message to my next meeting.”</span></span> <span data-ttu-id="f6937-110">사용자는 "다음 모임 참가" 라고 말하여 모임에 참가 하 고, 음성 도우미를 사용 하 여 파일을 공유 하 고, 일정을 확인 하는 등의 기능을 할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="f6937-110">Users can also join meetings by saying “join my next meeting” and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="f6937-111">이러한 음성 지원 환경은 [OST (온라인 서비스 사용 약관)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)에 반영 된 Office 365의 개인 정보 취급, 보안 및 준수 약속을 완벽 하 게 준수 하는 [Cortana 엔터프라이즈 등급 서비스](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 를 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="f6937-112">이 이미지는 모바일 장치에서 Cortana에 채팅을 전송 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![이미지는 Cortana 채팅 세션을 보여 주는 모바일 화면 순서를 표시 합니다.](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="f6937-114">관리 제어 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f6937-114">Admin control and Limitations</span></span>

<span data-ttu-id="f6937-115">팀의 Cortana 음성 지원은 OST (온라인 서비스 사용 약관)에 반영 된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 준수 약속을 완벽 하 게 준수 하는 서비스를 사용 하 여 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="f6937-116">이 기능은 테 넌 트에 대해 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="f6937-117">테 넌 트 관리자는 정책 (TeamsCortanaPolicy)을 사용 하 여 팀에서 Cortana 음성 지원을 사용할 수 있는 테 넌 트의 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="f6937-118">이 정책은 사용자 계정 수준 또는 테 넌 트 수준 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="f6937-119">관리자는이 정책 컨트롤 내에서 CortanaVoiceInvocationMode 필드를 사용 하 여 Cortana를 사용 하지 않도록 설정할지, 푸시 단추 호출을 사용 하거나, 절전 모드 종료 단어를 지원 하도록 (이 기능을 지 원하는 장치에 해당)를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="f6937-120">관리자는 다음 PowerShell cmdlet을 사용 하 여이 정책을 관리할 수 있습니다 (현재 Microsoft 팀 관리 센터에서는 정책을 사용할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="f6937-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="f6937-121">새로운 CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f6937-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f6937-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f6937-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f6937-123">부여-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f6937-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f6937-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f6937-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f6937-125">제거-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f6937-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="f6937-126">예를 들어 아래 명령은 Microsoft 팀에서 Cortana 음성 도우미를 사용할 수 없게 되는 "EmployeeCortanaPolicy" 라는 이름을 가진 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-126">For example, the command below creates a new policy with name "EmployeeCortanaPolicy" where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="f6937-127">이 예제에서는 "EmployeeCortanaPolicy" 이름을 사용 하 여 기존 정책을 업데이트 하 고, 푸시 단추 호출만 있는 Microsoft 팀에서 Cortana 음성 도우미를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-127">This example shows updating an existing policy with name "EmployeeCortanaPolicy" and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="f6937-128">사용자는 팀에서 Cortana 마이크 단추를 탭 하 여 Cortana를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="f6937-129">깨우기 단어 ("안녕 코타 나") 호출이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-129">Wake word ("Hey Cortana”) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="f6937-130">이 예제에서는 푸시 단추와 깨우기 단어 호출을 모두 사용 하 여 정책을 업데이트 하 고 Cortana 음성 도우미를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="f6937-131">미국에서 Microsoft 365 Enterprise 사용자를 처음 릴리스할 때 팀 모바일 앱은 깨우기 단어 활성화를 지원 하지 않지만 향후 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="f6937-132">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="f6937-132">User control</span></span>

<span data-ttu-id="f6937-133">개별 사용자는 마이크 단추를 클릭 하 여 팀 모바일 앱에서 Cortana 음성 지원을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="f6937-134">팀 모바일 앱의 설정을 사용 하 여 디바이스에 대해 팀의 Cortana를 사용할 수 있는지 여부를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="f6937-135">팀 모바일 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="f6937-136">**설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="f6937-137">**Cortana**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="f6937-138">장치에서 Cortana 음성 지원이 필요한 지 여부에 따라 설정/ **해제** **로 이동** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6937-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>
