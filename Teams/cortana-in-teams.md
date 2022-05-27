---
title: Microsoft Teams 음성 지원 Cortana
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams Cortana 음성 지원을 사용하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b79640b5f9d85b845c8d7c74fa1d6931931a6b50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674990"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams 음성 지원 Cortana

> [!NOTE]
> Cortana 음성 지원은 미국, 영국, 캐나다, 인도 및 오스트레일리아의 사용자에 대한 iOS 및 Android 및 Microsoft Teams 디스플레이용 Microsoft Teams 모바일 앱에서 지원됩니다. Windows Microsoft Teams 룸 로캘이 en-us로 설정된 디바이스에 대해서만 지원됩니다. Cortana 음성 지원은 현재 GCC, GCC High, DoD 및 미국 이외의 EDU 테넌트에 사용할 수 없습니다. Teams 모바일 앱의 Cortana 음성 지원은 이제 en-US의 EDU 고객에게 제공됩니다. 추가 언어 및 지역으로의 확장은 향후 릴리스의 일부로 수행됩니다.

Teams 모바일 앱, Windows Microsoft Teams 룸 및 Microsoft Teams 디스플레이 디바이스에서 음성 지원을 Cortana Microsoft 365 Enterprise  사용자는 음성 자연어를 사용하여 커뮤니케이션, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다. 사용자는 Teams 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Microsoft Teams 회의실에서 "Cortana"라고 말하거나 Microsoft Teams 디스플레이를 사용하는 경우 Cortana 말할 수 있습니다. 핸즈프리로 팀과 빠르게 연결하고 이동 중에 사용자는 "Megan에게 전화" 또는 "다음 모임에 메시지 보내기"와 같은 쿼리를 말할 수 있습니다. 사용자는 "다음 모임에 참가"라고 말하고 음성 지원을 사용하여 파일을 공유하고 일정을 확인하는 등의 작업을 통해 모임에 참가할 수도 있습니다. 이러한 음성 지원 환경은 [OST(온라인 서비스 약관)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true)에 반영된 Office 365 개인 정보 보호, 보안 및 규정 준수 약속을 완전히 준수하는 Cortana [엔터프라이즈급 서비스를](/microsoft-365/admin/misc/cortana-integration) 사용하여 제공됩니다.

## <a name="admin-control-and-limitations"></a>관리 제어 및 제한 사항

Teams Cortana 음성 지원은 OST(온라인 서비스 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보 보호, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 제공됩니다. 이 기능은 테넌트에 대해 기본적으로 사용하도록 설정됩니다.

테넌트 관리자는 정책(TeamsCortanaPolicy)을 사용하여 Teams Cortana 음성 지원을 사용할 수 있는 테넌트의 사용자를 제어할 수 있습니다. 이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정됩니다. 관리자는 이 정책 컨트롤 내의 CortanaVoiceInvocationMode 필드를 사용하여 Cortana 사용하지 않도록 설정되었는지, 푸시 단추 호출로만 활성화되었는지 또는 절전 모드 해제 단어 호출을 사용하는지(Microsoft Teams 표시와 같이 지원하는 디바이스에 적용 가능)를 확인할 수 있습니다.

관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(현재 Microsoft Teams 관리 센터에서 정책을 사용할 수 없음).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 "EmployeeCortanaPolicy"라는 이름의 새 정책을 만듭니다. 여기서 Microsoft Teams Cortana 음성 지원을 사용할 수 없습니다.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 "EmployeeCortanaPolicy"라는 이름으로 기존 정책을 업데이트하고 푸시 단추 호출만 사용하여 Microsoft Teams Cortana 음성 지원을 사용하도록 설정하는 방법을 보여 줍니다. 사용자는 Teams Cortana 마이크 단추를 선택하여 Cortana 호출할 수 있습니다. 절전 모드 해제 단어("안도 Cortana" 또는 "Cortana") 호출이 비활성화됩니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 푸시 단추와 절전 모드 해제 단어 호출을 모두 사용하여 정책을 업데이트하고 Cortana 음성 지원을 사용하도록 설정하는 방법을 보여 줍니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

당시 미국의 Microsoft 365 Enterprise 사용자를 위한 초기 릴리스에서는 다음과 같은 기능을 사용할 수 있습니다.

- Teams 모바일 앱은 절전 모드 해제 단어 활성화를 지원하지 않지만 향후 지원될 예정입니다.

- Windows 및 Microsoft Teams 디스플레이 디바이스의 Microsoft Teams 룸 절전 모드 해제 단어 활성화를 지원합니다.

## <a name="user-control"></a>사용자 제어

개별 사용자는 다른 디바이스에서 음성 지원을 Cortana 수 있습니다.

- Teams 모바일 앱에서 마이크 단추를 선택합니다.

- 마이크 단추를 선택하거나 Microsoft Teams 룸 "Cortana"라고 말합니다.

- 디바이스를 표시하는 Microsoft Teams "Cortana"라고 말합니다.

디바이스의 설정을 사용하여 Teams Cortana 디바이스에 사용할 수 있는지 여부를 제어할 수 있습니다.

![에서는 Cortana 사용하도록 설정할 때 모바일 창의 진행률을 보여 줍니다.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Windows Microsoft Teams 룸

디바이스 수준에서 변경은 테넌트 수준에서 Cortana 사용하도록 설정된 경우에만 사용할 수 있습니다.

디바이스 수준에서 두 가지 방법으로 사용할 Cortana 구성할 수 있습니다. 두 옵션 또는 둘 다를 동시에 사용하도록 설정할 수 있습니다.

- 마이크를 탭하여 _Cortana 푸시_ 라고 합니다.
- Cortana _음성 활성화_ 라고 하는 "이봐, Cortana"라고 말합니다.

Cortana _채팅 푸시_ 는 기본적으로 회의실이 en-au(오스트레일리아), en-ca(캐나다), en-gb(영국), en-in(인도), en-us(미국) 언어로 설정된 경우 사용하도록 설정됩니다. [더 알아보세요.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana 아이콘은 Teams 룸 콘솔의 _자세히..._ 메뉴 아래에 있는 _프레젠테이션_ 단추를 대체합니다. _Cortana 푸시를_ 사용하지 않도록 설정하려면 PowerShell을 사용합니다.[ 더 알아보세요.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Cortana _음성 정품 인증을_ 사용하도록 설정하려면 다음 조건을 충족해야 합니다.

- Cortana 인증된 장치를 Teams 룸에 연결해야 합니다. 이 문서의 끝에서 인증된 디바이스 목록을 찾을 수 있습니다.
- Teams 룸은 en-au (오스트레일리아), en-ca (캐나다), en-gb (영국), en-in (인도), en-us (미국) 언어로 설정해야합니다. 나중에 더 많은 언어를 사용할 수 있습니다.
- 다음 구성 변경 중 하나를 수행해야 합니다.
  - Teams 관리 센터에서 기능을 켭[니다.](/microsoftteams/rooms/rooms-manage)
  - SkypeSettings XML 파일에 다음 XML 특성을 추가합니다.

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

모임 수준에서는 디바이스 수준에서 Cortana _음성 정품 인증_ 을 사용하도록 설정한 경우에만 변경 내용을 사용할 수 있습니다.  모임 중에 Cortana _음성 활성화_ 를 사용하도록 설정하려면 설정/해제를 **이동하거나 해제** 하여 사용하지 않도록 설정합니다. 모임이 종료되면 Cortana 디바이스 수준 설정 집합으로 돌아갑니다.

디바이스 수준에서 Cortana 사용하도록 설정된 경우 모임 수준에서 변경 내용을 적용할 수 있습니다.

모임 중에 Cortana _음성 활성화_ 를 사용하도록 설정하려면 토글을 **켜** 거나 **끕니다**. 모임이 종료되면 Cortana 디바이스 수준 설정 집합으로 돌아갑니다.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Teams 룸 인증된 디바이스 Cortana

lenovo Hub 500을 사용 중이거나 이러한 디바이스가 채팅방에 연결되어 있는 경우 Cortana _음성 정품 인증_ 을 사용하도록 설정할 수 있습니다.

- 자브라 파나캐스트 50
- 랠리 마이크
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
