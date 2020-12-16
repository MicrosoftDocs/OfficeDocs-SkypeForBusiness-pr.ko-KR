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
# <a name="cortana-voice-assistance-in-teams"></a>Teams의 Cortana 음성 지원

> [!Note]
> Cortana 음성 지원은 Microsoft Teams iOS 및 Android 모바일 앱, Windows의 Microsoft Teams 회의실 및 Microsoft Teams 디스플레이에서만 지원됩니다. 현재 GCC, GCC-High, DoD, EDU 테넌트에는 사용할 수 없습니다. 추가 언어 및 지역으로의 확장은 향후 릴리스의 일부로 발생될 예정입니다.

> [!Note]
> Microsoft Teams 회의실의 Cortana 음성 지원은 미리 보기로 릴리스됩니다. 미리 보기 릴리스에서 Cortana는 Rally 마이크가 연결된 디바이스에서 EN-US 언어를 사용하여 미국에서만 지원됩니다.

Teams 모바일 앱, Windows의 Microsoft Teams 회의실 및 Microsoft Teams 디스플레이 장치에서 Cortana 음성 지원을 통해 Microsoft 365 Enterprise 사용자는 음성 자연어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다. 사용자는 Teams 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Microsoft Teams &#8220;또는 Microsoft Teams 디스플레이를&#8221; Cortana에게 말하여 Cortana에게 말할 수 있습니다. 이동 중에는 핸즈프리로 팀과 빠르게 연결하기 위해 사용자는 Megan &#8220;&#8221; 또는 &#8220;모임 팀에 메시지를 보내는 등의 쿼리를&#8221;. 사용자는 다음 모임에 참가하고&#8220;모임에 참가하고&#8221; 음성 지원을 사용하여 파일을 공유하고 일정을 확인하여 모임에 참가할 수 있습니다. 이러한 음성 지원 환경은 [OST(온라인](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)서비스 약관)에 반영된 Office 365의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 엔터프라이즈급 서비스를 사용하여 전달됩니다.

이미지는 모바일 장치에서 Cortana를 사용하여 채팅을 보내는 방법을 보여줍니다.

![Cortana 채팅 세션을 보여주는 모바일 화면 시퀀스](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>관리자 제어 및 제한 사항

Teams의 Cortana 음성 지원은 OST(온라인 서비스 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 전달됩니다. 이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.

테넌트 관리자는 정책(TeamsCortanaPolicy)을 사용하여 Teams에서 Cortana 음성 지원을 사용할 수 있는 테넌트의 사용자들을 제어할 수 있습니다. 이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정할 수 있습니다. 관리자는 이 정책 컨트롤 내에서 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되어 있는지, 푸시 버튼 호출만 사용 또는 해제 단어 호출을 사용할지(Microsoft Teams 디스플레이와 같이 이를 지원하는 디바이스에 적용 가능) 여부를 확인할 수 있습니다.

관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 Microsoft Teams 관리 센터에서는 정책을 사용할 수 없습니다).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 Microsoft Teams에서 Cortana 음성 지원을 사용할 &#8220;EmployeeCortanaPolicy&#8221; 새 정책을 만듭니다.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 EmployeeCortanaPolicy &#8220;이름으로 기존 정책을 업데이트하고&#8221; 단추 호출만 사용하여 Microsoft Teams에서 Cortana 음성 지원을 사용하도록 설정하는 것입니다. 사용자는 Teams에서 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 있습니다. 절전 모드 해제 단어(&#8220;Cortana&#8221; 또는 Corta&#8221; na &#8220;) 호출이 비활성화됩니다.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출 모두에서 Cortana 음성 지원을 사용하도록 설정하는 것입니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

미국에 있는 Microsoft 365 Enterprise 사용자에 대한 초기 릴리스의 현재 사용 가능한 함수는 다음과 같습니다.

- Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원될 예정입니다.  

- Windows 및 Microsoft Teams 디스플레이 장치의 Microsoft Teams 회의실은 절전 모드 해제 단어 활성화를 지원합니다.

## <a name="user-control"></a>사용자 제어

개별 사용자는 다른 장치에서 Cortana 음성 지원을 사용해 볼 수 있습니다.

- Teams 모바일 앱에서 마이크 단추를 선택합니다.

- Microsoft Teams 회의실에서 마이크 단추를 선택하거나 "Cortana"라고 말하세요.

- Microsoft Teams 디스플레이 장치에서 "Cortana"라고 말하십시오.

장치의 설정을 사용하여 Teams의 Cortana를 장치에 사용할 수 있는지 여부를 제어할 수 있습니다.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams 모바일 앱 또는 Microsoft Teams 디스플레이

  1. Teams 모바일 앱을 열 수 있습니다.

  2. 설정   >  **Cortana를 선택합니다.**

  3. **토글을 끄거나** **끄기**

### <a name="microsoft-teams-display"></a>Microsoft Teams 디스플레이

  1. Microsoft Teams 디스플레이의 앰비언트(홈) 화면으로 이동

  2. 사용자 아바타를 선택한 다음 설정을 **선택합니다.** Cortana를 사용하도록 설정되면 "Cortana, 설정으로 이동"이라고 합니다.

  3. **토글을 끄거나** **끄기**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Windows의 Microsoft Teams 회의실

테넌트 수준에서 Cortana를 사용하도록 설정한 경우 디바이스 수준에서 변경을 사용할 수 있습니다. Cortana는 기본적으로 해제됩니다.

장치 수준에서 Cortana를 사용하려면 SkypeSettings XML 파일에 다음 XML 특성을 추가해야 합니다.

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

장치 수준에서 Cortana를 사용하도록 설정한 경우 모임 수준에서 변경을 사용할 수 있습니다.

모임 중에 Cortana 음성 지원을 사용하도록 설정하려면 토글 설정 또는 **해제를** **이동하세요.** 모임이 종료된 후 Cortana는 장치 수준 설정 집합으로 돌아온다.
