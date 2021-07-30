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
ms.openlocfilehash: 368cb8b0c2d34e985d10adf11a405fb0603f1aff
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646419"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana 음성 지원 Teams

> [!Note]
> Cortana 음성 지원은 iOS Microsoft Teams Android용 모바일 앱 및 미국, 영국Microsoft Teams 인도 및 오스트레일리아의 사용자에 대한 Microsoft Teams 디스플레이에서 지원됩니다. Microsoft Teams 룸 Windows 미국 사용자만 지원됩니다. Cortana 음성 지원은 현재 GCC, GCC-High, DoD 및 미국 EDU가 아닌 테넌트에 대해 사용할 수 없습니다. Cortana 모바일 앱에서 Teams 음성 지원을 이제 미국 내 EDU 고객에게 사용할 수 있습니다. 추가 언어 및 지역으로 확장은 향후 릴리스의 일부로 발생하게 됩니다.

> [!Note]
> Cortana 음성 Microsoft Teams 룸 미리 보기에서 릴리스됩니다. 미리 보기 릴리스에서는 Cortana 마이크가 연결된 디바이스에서 언어 EN-US를 사용하여 미국에서만 지원됩니다.

Cortana 모바일 앱에서 음성 Teams 음성 Microsoft Teams 룸 Windows 및 Microsoft Teams 디스플레이 디바이스에서 음성 언어를 사용하여 Microsoft 365 Enterprise, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다. 사용자는 Cortana 모바일 앱의 오른쪽 위에 Teams 마이크 단추를 선택하거나 &#8220;Cortana&#8221; 또는 Microsoft Teams 디스플레이를 사용할 때 Microsoft Teams 있습니다. 핸즈프리 팀과 빠르게 연결하고 이동하는 동안 사용자는 Megan &#8220;호출 또는&#8221; &#8220;메시지 보내기 등의 쿼리를&#8221;. 또한 사용자는 다음 모임에 &#8220;모임에 참가할 수&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 검사하는 등 모임에 참가할 수 있습니다. 이러한 음성 지원 환경은 [OST(Online](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Services Cortana 약관)에 Office 365 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 엔터프라이즈급 서비스를 사용하여 [전달됩니다.](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>관리자 제어 및 제한 사항

Cortana 음성 Teams OST(Online Services 약관)에 Office 365 엔터프라이즈 수준의 개인 정보 보호, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다. 이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.

테넌트 관리자는 테넌트에서 정책(TeamsCortanaPolicy)을 사용하여 Cortana 음성 지원을 Teams 제어할 수 있습니다. 이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정됩니다. 관리자는 이 정책 제어 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana 해제되어 있는지, 푸시 단추 호출만 사용하도록 설정되어 있는지 또는 절전 모드 해제 단어 호출과 함께 사용할 수 있는지 여부를 확인할 수 있습니다(예: Microsoft Teams 표시).

관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 관리 센터에서 정책을 Microsoft Teams 없습니다).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 &#8220;EmployeeCortanaPolicy&#8221; 음성 지원을 사용할 Cortana 새 정책을 Microsoft Teams 만듭니다.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 푸시 단추 호출만 사용하여 Cortana 음성 Microsoft Teams 음성 지원을 사용할 수 있습니다. 사용자는 Cortana 마이크 단추를 선택하여 Cortana 호출할 수 Teams. 절전 모드 해제 &#8220;(Cortana&#8221; 또는 &#8220;Cortana&#8221;) 호출이 비활성화됩니다.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 정책을 업데이트하고 푸시 단추 및 절전 모드 해제 Cortana 음성 지원을 사용하도록 설정하는 것입니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

당시 영어로 미국의 Microsoft 365 Enterprise 초기 릴리스의 사용 가능한 함수는 다음과 같습니다.

- Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원됩니다.  

- Microsoft Teams 룸 Windows Microsoft Teams 표시 디바이스에서 절전 모드 해제 단어 활성화를 지원합니다.

## <a name="user-control"></a>사용자 제어

개별 사용자는 다양한 디바이스에서 Cortana 음성 지원을 시도할 수 있습니다.

- 모바일 앱에서 마이크 Teams 선택합니다.

- 마이크 단추를 선택하거나 Cortana "Microsoft Teams 룸.

- 디바이스가 Cortana "Microsoft Teams"라고 말합니다.

디바이스에서 설정을 사용하여 Cortana Teams 디바이스에 대해 사용할 수 있는지 여부를 제어할 수 있습니다.

![모바일 창을 사용하도록 설정할 때 모바일 창의 진행률을 Cortana](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 룸 Windows

테넌트 수준에서 Cortana 디바이스 수준에서 변경을 사용할 수 있습니다. Cortana 해제됩니다.

디바이스 Cortana 설정하려면 SkypeSettings XML 파일에 이러한 XML 특성을 추가해야 합니다.

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

디바이스 수준에서 변경을 사용할 수 Cortana 경우 모임 수준에서 변경을 사용할 수 있습니다.

모임 Cortana 음성 지원을 사용하도록 설정하려면 토글 **설정** 또는 끄기 를 **이동합니다.** 모임이 끝나면 Cortana 설정으로 돌아온다.
