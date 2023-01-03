---
title: Microsoft Teams의 Cortana 음성 지원
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams에서 Cortana 음성 지원을 사용하는 방법 알아보기
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
- chat-teams-channels-revamp
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8070644139ebd32157693e941e3206a4e90cdad
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693401"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams의 Cortana 음성 지원

> [!NOTE]
> Cortana 음성 지원은 iOS 및 Android용 Microsoft Teams 모바일 앱, Microsoft Teams 디스플레이 및 미국, 영국, 캐나다, 인도 및 호주의 사용자를 위해 Windows의 Microsoft Teams 룸 지원됩니다. Teams 모바일 앱의 Cortana 음성 지원은 이제 EN-US의 EDU 고객에게 제공됩니다. 추가 언어 및 지역으로의 확장은 향후 릴리스의 일부로 수행됩니다. Cortana 음성 지원은 현재 GCC, GCC-High, DoD 및 미국 이외의 EDU 테넌트에서 사용할 수 없습니다.

Teams 모바일 앱, Windows의 Microsoft Teams 룸 및 Microsoft Teams 디스플레이 디바이스에서 Cortana 음성 지원을 사용하면 Microsoft 365 Enterprise 사용자가 음성 자연어를 사용하여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있습니다. 사용자는 Teams 모바일 앱의 오른쪽 위에 있는 마이크 단추를 선택하거나 Microsoft Teams 룸에서 또는 Microsoft Teams 디스플레이를 사용할 때 "Cortana"라고 말하여 Cortana와 대화할 수 있습니다. 이동 중에도 팀과 빠르게 연결하기 위해 사용자는 "Megan에게 전화" 또는 "다음 모임에 메시지 보내기"와 같은 쿼리를 말할 수 있습니다. 사용자는 "다음 모임에 참가"라고 말하고 음성 지원을 사용하여 파일을 공유하고 일정을 확인하는 등의 작업을 통해 모임에 참가할 수도 있습니다. 이러한 음성 지원 환경은 [OST(온라인 서비스 약관)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true)에 반영된 대로 Office 365 개인 정보, 보안 및 규정 준수 약속을 완전히 준수하는 [Cortana 엔터프라이즈급 서비스를](/microsoft-365/admin/misc/cortana-integration) 사용하여 제공됩니다.

## <a name="admin-control-and-limitations"></a>관리 제어 및 제한 사항

Teams의 Cortana 음성 지원은 OST(온라인 서비스 약관)에 반영된 Office 365 엔터프라이즈 수준의 개인 정보 보호, 보안 및 규정 준수 약속을 완전히 준수하는 서비스를 사용하여 제공됩니다. 이 기능은 테넌트에서 기본적으로 사용하도록 설정됩니다.

테넌트 관리자는 정책을 사용하여 Teams에서 Cortana 음성 지원을 사용할 수 있는 테넌트의 사용자를 제어할 수 있습니다(TeamsCortanaPolicy). 이 정책은 사용자 계정 수준 또는 테넌트 수준에서 설정됩니다. 관리자는 이 정책 컨트롤 내의 CortanaVoiceInvocationMode 필드를 사용하여 Cortana가 비활성화되었는지, 푸시 단추 호출로만 사용하도록 설정되었는지, 절전 모드 해제 단어 호출을 사용할지(Microsoft Teams 디스플레이와 같이 지원하는 디바이스에 적용 가능)를 확인할 수 있습니다.

관리자는 다음 PowerShell cmdlet을 사용하여 이 정책을 관리할 수 있습니다(정책은 현재 Microsoft Teams 관리 센터에서 사용할 수 없음).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 Microsoft Teams의 Cortana 음성 지원을 사용하지 않도록 설정된 "EmployeeCortanaPolicy"라는 이름의 새 정책을 만듭니다.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 이름이 "EmployeeCortanaPolicy"인 기존 정책을 업데이트하고 푸시 단추 호출만 사용하여 Microsoft Teams에서 Cortana 음성 지원을 사용하도록 설정하는 방법을 보여 줍니다. 사용자는 Teams에서 Cortana 마이크 단추를 선택하여 Cortana를 호출할 수 있습니다. 절전 모드 해제 단어("안도 Cortana" 또는 "Cortana") 호출이 비활성화됩니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 정책을 업데이트하고 푸시 단추와 절전 모드 해제 단어 호출을 모두 사용하여 Cortana 음성 지원을 사용하도록 설정하는 방법을 보여 줍니다. (절전 모드 해제 단어 활성화는 Teams 모바일 앱, windows의 Microsoft Teams 룸 및 언어가 영어로 설정된 Microsoft Teams 디스플레이에 대한 미국의 Microsoft 365 Enterprise 사용자에 대해 지원됩니다.)

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

## <a name="user-control"></a>사용자 제어

개별 사용자는 다른 디바이스에서 Cortana 음성 지원을 시도할 수 있습니다.

- Teams 모바일 앱에서 마이크 단추를 선택합니다.

- 마이크 단추를 선택하거나 Microsoft Teams 룸 "Cortana"라고 말합니다.

- Microsoft Teams에서 "Cortana"가 디바이스를 표시한다고 가정해 봅시다.

디바이스의 설정을 사용하여 Teams의 Cortana를 디바이스에 사용할 수 있는지 여부를 제어할 수 있습니다.

![는 Cortana를 사용하도록 설정할 때 모바일 창의 진행 상황을 보여 줍니다.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Windows에서 Microsoft Teams 룸

디바이스 수준에서 변경은 Cortana가 테넌트 수준에서 사용하도록 설정된 경우에만 사용할 수 있습니다.

디바이스 수준에서 Cortana를 두 가지 방법으로 사용하도록 구성할 수 있습니다. 옵션 또는 둘 다를 동시에 사용하도록 설정할 수 있습니다.

- 대화하기 위해 Cortana Push라고 하는 마이크 _를 탭합니다_.
- _Cortana 음성 활성화_ 라고 하는 "Hey, Cortana"라고 말함으로써

채팅방이 en-au(오스트레일리아), en-ca(캐나다), en-gb(영국), en-in(인도), en-us(미국) 언어로 설정된 경우 Cortana _Push to Talk_ 는 기본적으로 사용하도록 설정됩니다. [더 알아보세요.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana 아이콘은 Teams 룸 콘솔의 _자세히..._ 메뉴 아래에 있는 _프레젠테이션_ 단추를 대체합니다. Cortana _푸시를_ 사용하지 않도록 설정하려면 PowerShell을 사용합니다. [더 알아보세요.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1&preserve-view=true)

Cortana _음성 활성화를_ 사용하도록 설정하려면 다음 조건을 충족해야 합니다.

- Cortana 인증 디바이스를 Teams 룸에 연결해야 합니다. 이 문서의 끝부분에서 인증된 디바이스 목록을 찾을 수 있습니다.
- Teams 룸은 en-au(오스트레일리아), en-ca(캐나다), en-gb(영국), en-in(인도), en-us(미국) 언어로 설정해야 합니다. 더 많은 언어는 나중에 사용할 수 있습니다.
- 다음 구성 변경 중 하나를 수행해야 합니다.
  - Teams 관리 센터 [자세한 정보](/microsoftteams/rooms/rooms-manage)에서 기능을 켭니다.
  - SkypeSettings XML 파일에 다음 XML 특성을 추가합니다.

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

모임 수준에서는 장치 수준에서 Cortana _음성 활성화_ 를 사용하도록 설정한 경우에만 변경 내용을 사용할 수 있습니다.  모임 중에 Cortana _음성 활성화_ 를 사용하도록 설정하려면 토글을 **켜** 거나 **끄** 기로 이동하여 사용하지 않도록 설정합니다. 모임이 종료되면 Cortana는 디바이스 수준 설정 집합으로 돌아갑니다.

Cortana가 디바이스 수준에서 사용하도록 설정된 경우 모임 수준에서 변경 작업을 수행할 수 있습니다.

모임 중에 Cortana _음성 활성화_ 를 사용하도록 설정하려면 토글을 **켜** 기 또는 **끄기로** 이동합니다. 모임이 종료되면 Cortana는 디바이스 수준 설정 집합으로 돌아갑니다.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Teams 룸 Cortana 인증 디바이스

Lenovo Hub 500을 사용하거나 채팅방에 연결된 디바이스가 있는 경우 Cortana _음성 활성화_ 를 사용하도록 설정할 수 있습니다.

- 자브라 파나캐스트 50
- Logi Rally Plus 회의 시스템
- Bose Video Bar VB1
- EPOS EXPAND 캡처 5
- Yealink MSpeech
