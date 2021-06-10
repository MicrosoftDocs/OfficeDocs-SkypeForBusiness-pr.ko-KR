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
# <a name="cortana-voice-assistance-in-teams"></a>Cortana 음성 지원에서 Teams

> [!Note]
> Cortana 음성 지원은 iOS 및 android용 Microsoft Teams 앱 및 미국, 영국Microsoft Teams 캐나다, 인도 및 오스트레일리아의 사용자에 대한 Microsoft Teams 디스플레이에서 지원됩니다.  Microsoft Teams 룸 Windows 미국 사용자만 지원됩니다. Cortana 음성 지원은 현재 GCC, GCC, DoD, EDU 테넌트에 사용할 수 없습니다. 추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.

> [!Note]
> Microsoft Teams 룸의 Cortana 음성 지원은 미리 보기에서 릴리스됩니다. 미리 보기 릴리스에서 Cortana는 Rally 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.

Teams 모바일 앱의 Cortana 음성 지원, Microsoft Teams 룸 Windows 및 Microsoft Teams Microsoft 365 Enterprise 디스플레이 디바이스에서 사용자가 음성 언어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다. 사용자는 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Teams 또는 &#8220;&#8221; 또는 Microsoft Teams 디스플레이를 사용할 때 Cortana에 Microsoft Teams 수 있습니다. 핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;. 또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다. 이러한 음성 지원 환경은 [OST(Online Services](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)약관)에 Office 365, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 엔터프라이즈급 서비스를 사용하여 전달됩니다.

이미지는 모바일 장치에서 Cortana를 사용하여 채팅을 보내는 방법을 보여줍니다.

![Cortana 채팅 세션을 보여주는 일련의 모바일 화면](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>관리자 제어 및 제한 사항

OST(Online Services Teams 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 이 서비스의 Cortana 음성 지원이 전달됩니다. 이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.

테넌트 관리자는 정책(TeamsCortanaPolicy)을 사용하여 테넌트에서 Cortana 음성 지원을 사용할 Teams 제어할 수 있습니다. 이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정할 수 있습니다. 관리자는 이 정책 컨트롤 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출도 사용할 수 있는지 여부를 확인할 수 있습니다(예: Microsoft Teams 표시).

관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 관리 센터에서 정책을 Microsoft Teams 없습니다).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 &#8220;CortanaPolicy&#8221; Cortana voice assistance를 사용하지 않도록 Microsoft Teams 새 정책을 만듭니다.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 푸시 단추 호출만 사용하여 Microsoft Teams Cortana 음성 지원을 사용하도록 설정하는 것이 보여 됩니다. 사용자는 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 Teams. 절전 모드 해제 &#8220;Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출을 모두 사용하여 Cortana 음성 지원을 사용하도록 설정하는 기능을 보여줍니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

당시 영어로 미국의 Microsoft 365 Enterprise 초기 릴리스의 사용 가능한 함수는 다음과 같습니다.

- Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.  

- Microsoft Teams 룸 Windows Microsoft Teams 표시 디바이스에서 절전 모드 해제 단어 활성화를 지원합니다.

## <a name="user-control"></a>사용자 제어

개별 사용자는 다른 장치에서 Cortana 음성 지원을 사용해 볼 수 있습니다.

- 모바일 앱에서 마이크 Teams 선택합니다.

- 마이크 단추를 선택하거나"Cortana"라고 Microsoft Teams 룸.

- 디스플레이 디바이스에 "Cortana"라고 Microsoft Teams 있습니다.

디바이스에서 설정을 사용하여 디바이스에 Teams Cortana를 사용하도록 설정하는지 여부를 제어할 수 있습니다.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams 앱 또는 Microsoft Teams 표시

  1. 모바일 앱을 Teams 를 하세요.

  2. **Cortana 설정**  >  **선택합니다.**

  3. 토글을 On 또는 **Off로** **이동합니다.**

### <a name="microsoft-teams-display"></a>Microsoft Teams 표시

  1. 화면의 앰비언트(홈) 화면으로 Microsoft Teams.

  2. 사용자 아바타를 선택한 다음 을 **설정.** Cortana를 사용하도록 설정하면 "Cortana, 설정."

  3. 토글을 On 또는 **Off로** **이동합니다.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 룸 Windows

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
