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
# <a name="cortana-voice-assistance-in-teams"></a>Teams의 Cortana 음성 지원

> [!Note]
> Cortana 음성 지원은 Microsoft Teams iOS 및 Android 모바일 앱, Windows의 Microsoft Teams Rooms 및 Microsoft Teams 디스플레이에서 미국의 사용자만 지원됩니다. 현재 GCC, GCC-High, DoD, EDU 테넌트에서는 사용할 수 없습니다. 추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.

> [!Note]
> Microsoft Teams Rooms의 Cortana 음성 지원은 미리 보기에서 릴리스됩니다. 미리 보기 릴리스에서 Cortana는 Rally 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.

Teams 모바일 앱, Windows의 Microsoft Teams Rooms 및 Microsoft Teams 디스플레이 디바이스에서 Cortana 음성 지원을 사용하면 Microsoft 365 Enterprise 사용자가 음성 자연어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다. 사용자는 Teams 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Microsoft Teams &#8220;Microsoft Teams&#8221; Microsoft Teams 디스플레이를 사용할 때 Cortana에 대해 말할 수 있습니다. 핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;. 또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다. 이러한 음성 지원 환경은 [OST(Online Services 약관)에](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)반영된 Office 365의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 엔터프라이즈급 서비스를 사용하여 전달됩니다.

이미지는 모바일 장치에서 Cortana를 사용하여 채팅을 보내는 방법을 보여줍니다.

![Cortana 채팅 세션을 보여주는 일련의 모바일 화면](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>관리자 제어 및 제한 사항

Teams의 Cortana 음성 지원은 OST(Online Services 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다. 이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.

테넌트 관리자는 테넌트에서 정책을 사용하여 Teams에서 Cortana 음성 지원을 사용할 수 있는 사용자(TeamsCortanaPolicy)를 제어할 수 있습니다. 이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정할 수 있습니다. 관리자는 이 정책 제어 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출을 사용하는지 여부를 확인할 수 있습니다(Microsoft Teams 표시와 같이 해당 기능을 지원하는 디바이스에 해당).

관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 Microsoft Teams 관리 센터에서 정책을 사용할 수 없습니다).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 Microsoft Teams의 Cortana 음성 지원을 사용할 &#8220;EmployeeCortanaPolicy&#8221; 새 정책을 만듭니다.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 단추 호출만 사용하여 Microsoft Teams에서 Cortana 음성 지원을 사용하도록 설정하는 기능을 보여 합니다. 사용자는 Teams에서 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 있습니다. 절전 모드 해제 &#8220;Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출을 모두 사용하여 Cortana 음성 지원을 사용하도록 설정하는 기능을 보여줍니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

당시 미국의 Microsoft 365 Enterprise 사용자에 대한 초기 릴리스의 영어로 사용할 수 있는 함수는 다음과 같습니다.

- Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.  

- Windows 및 Microsoft Teams 디스플레이 디바이스의 Microsoft Teams Rooms는 절전 모드 해제 단어 활성화를 지원합니다.

## <a name="user-control"></a>사용자 제어

개별 사용자는 다른 장치에서 Cortana 음성 지원을 사용해 볼 수 있습니다.

- Teams 모바일 앱에서 마이크 단추를 선택합니다.

- 마이크 단추를 선택하거나 Microsoft Teams Rooms에서 "Cortana"라고 말할 수 있습니다.

- Microsoft Teams 디스플레이 디바이스에서 "Cortana"라고 말합니다.

디바이스에서 설정을 사용하여 Teams의 Cortana를 디바이스에 사용할 수 있는지 여부를 제어할 수 있습니다.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams 모바일 앱 또는 Microsoft Teams 표시

  1. Teams 모바일 앱을 하세요.

  2. 설정   >  **Cortana를 선택합니다.**

  3. 토글을 On 또는 **Off로** **이동합니다.**

### <a name="microsoft-teams-display"></a>Microsoft Teams 표시

  1. Microsoft Teams 표시의 앰비언트(홈) 화면으로 이동합니다.

  2. 사용자 아바타를 선택한 다음 설정을 **선택합니다.** Cortana를 사용하도록 설정한 경우 "Cortana, 설정으로 이동합니다."

  3. 토글을 On 또는 **Off로** **이동합니다.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Windows의 Microsoft Teams Rooms

테넌트 수준에서 Cortana를 사용하도록 설정한 경우 디바이스 수준에서 변경을 사용할 수 있습니다. Cortana는 기본적으로 해제됩니다.

디바이스 수준에서 Cortana를 사용하도록 설정하려면 SkypeSettings XML 파일에 이러한 XML 특성을 추가해야 합니다.

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

디바이스 수준에서 Cortana를 사용하도록 설정한 경우 모임 수준에서 변경을 사용할 수 있습니다.

모임 중에 Cortana 음성 지원을 사용하도록 설정하려면 토글 **설정** 또는 끄기 를 **이동합니다.** 모임이 종료된 후 Cortana는 디바이스 수준 설정 집합으로 돌아온다.