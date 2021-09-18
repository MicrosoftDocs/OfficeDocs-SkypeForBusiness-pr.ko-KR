---
title: 음악
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 845e85fbf7fb4fa9f5ee70769c6a66f49cd8bb4e
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432791"
---
# <a name="music-on-hold"></a>음악

사용자가 Microsoft Teams PSTN(공용 전환 전화 네트워크)에서 들어오는 통화를 보류 중이면 PSTN 호출자에서 선택한 음악을 들을 수 있습니다.

재생된 음악은 Microsoft에서 제공하는 기본 음악 또는 업로드하고 구성하는 사용자 지정 음악입니다. 테넌트 관리자로서 음악 호출 정책을 사용하고 Teams 사용자에게 정책을 할당하여 보류를 사용할 수 Teams 구성합니다. 

PSTN 호출자는 다른 시나리오에서 음악 수신 수신을 수신할 수 있습니다. 예를 들어 클라우드 호출 큐로 호출하거나 사용자가 호출을 Microsoft Teams 있습니다. 이러한 시나리오는 이 문서에서 언급한 기능에 의해 다루거나 제어되지 않습니다. 

## <a name="configure-music-on-hold"></a>보류 음악 설정 구성

보류 음악 구성하는 경우:

1.  관리 센터의 왼쪽 탐색에서 Teams 음성 > **정책으로 이동하세요.**

2.  정책 관리 **탭에서** 기존 정책 중 하나를 선택하거나 새 정책 만들기를 선택합니다.

3.  **PSTN 음악** 호출자 필드에 대한 보류  중에서 드롭다운 메뉴에서 사용하도록 설정을 선택합니다.

또한 PowerShell 음악 사용하여 보류에서 Teams 수 있습니다. TeamsCallingPolicy에서 MusicOnHoldEnabledType 매개 변수를 사용하도록 설정으로 변경한 다음 하나 이상의 사용자에게 해당 정책 인스턴스를 부여합니다.

사용자가 Teams 통화 정책이 Teams 설정이 음악 설정되어 있는 경우 사용자가 통화를 보류 중일 때 Teams 재생되지 않습니다.

## <a name="configure-custom-music"></a>사용자 지정 음악 구성

> [!NOTE]
> 이 기능은 공개 미리 보기 릴리스로 사용할 수 있습니다.

PSTN 발신자에 기본 음악을 재생하는 것 외에도 음악 또는 기타 오디오 콘텐츠로 사용자 지정 오디오 파일을 업로드하고 해당 오디오 파일을 PSTN 호출자에 재생할 수 있도록 구성할 수 있습니다.
예를 들어 부서 또는 조직은 외부 PSTN 호출자에 보류될 때 사용자 지정 공지 또는 사용자 지정 음악을 재생하려는 경우를 예로 들 수 있습니다.  

> [!NOTE]
> 귀하는 사용자 서비스에서 음악 또는 오디오 파일을 사용하는 데 필요한 모든 권한 및 권한을 독립적으로 지우고 Microsoft Teams 책임이 있습니다. 여기에는 모든 관련 권리 소유자의 오디오 파일의 음악, 음향 효과, 오디오, 브랜드, 이름 및 기타 콘텐츠의 지적 재산권 및 기타 권리가 포함됩니다. 보유자는 아티스트, 배우, 공연가, 음악가, 작곡가, 작곡가, 레코드 레이블, 음악 퍼블리셔, 노조, 길드, 권리 사회, 집단 관리 조직 및 음악 저작권, 음향 효과, 오디오 및 기타 지적 재산권을 소유, 제어 또는 라이선스를 보유한 다른 당사자를 포함할 수 있습니다.

사용자 지정 음악 보류하려면 PowerShell 모듈 2.5.0 이상에서 PowerShell cmdlet New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy 및 Import/Get/Get/Remove-CsOnlineAudioFile을 Teams 사용합니다.


1. 사용자가 Teams 통화 정책에서 사용하도록 음악 PSTN 호출자에 대해 보류 중이 Teams 확인합니다. 

2. 업로드 오디오 파일을 저장합니다.

3. 사용자 Teams 오디오 파일을 참조하는 통화 보류 정책을 만들고 사용자 지정 사용자에게 Teams 할당합니다.

### <a name="upload-the-custom-audio-file"></a>업로드 오디오 파일을 저장합니다.

보류 중 음악 사용자 지정 구성은 오디오 파일을 업로드하는 것으로 시작합니다. 이 목적을 위해 PowerShell cmdlet Import-CsOnlineAudioFile 사용할 수 있습니다. PowerShell 인터페이스를 사용하여 MP3 오디오 파일을 업로드하는 예제는 다음과 같습니다.

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>통화 보류 정책에서 오디오 Teams 참조

오디오 파일을 업로드한 후 통화 보류 정책을 만들거나 설정할 때 Teams 통화 보류 정책에서 파일을 참조해야 Teams 있습니다. 예를 들면 다음과 같습니다.

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

새 통화 보류 정책을 만든 Teams 다음과 같이 사용자에 Grant-CsTeamsCallHoldPolicy 수 있습니다.

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

업로드된 오디오 파일에 대한 정보를 얻게하려면 Get-CsOnlineAudioFile cmdlet을 사용하세요.

업로드된 오디오 파일을 제거하려면 Remove-CsOnlineAudioFile cmdlet을 사용 합니다. 오디오 파일을 제거하기 전에 TeamsCallHoldPolicy에서 해당 오디오 파일을 사용하지 않는지 검사합니다.

## <a name="restrictions"></a>제한 사항

- 음악 보류는 상업용 클라우드에서만 사용할 수 있습니다.

- 음악 보류는 사용자가 전용 모드인 Teams 사용할 수 있습니다.

- 음악 사용자가 협의적인 전송을 Teams 보류를 사용할 수 없습니다.

- 호출된 Teams 라우팅에 대해 Location-Based 경우 음악 보류를 호출자에 재생할 수 없습니다.

-   음악 보류는 호출된 Teams 클라이언트의 다음 버전 중 하나를 사용하는 Teams 사용할 수 있습니다.
    -   Microsoft Teams Windows
    -   Microsoft Teams용
    -   Microsoft Teams 웹에서
    -   iOS용 Microsoft Teams
    - Microsoft Teams
<br>
- 업로드한 후 오디오 파일을 내보낼 수 없습니다. 제거만 할 수 있습니다.

- 공유 음악 선 모양(위임)으로 구성된 사용자 및 통화 공원을 사용하는 경우 사용자 지정 보류를 사용할 수 없습니다. 표준 음악 보류가 재생됩니다.

- 일부 시나리오에서 직접 라우팅 미디어 우회 호출은 보류 중 재생을 위해 음악 비미디어 우회 호출로 변환되고 통화가 종료될 때까지 비미디어 우회 통화로 유지됩니다.



## <a name="related-topics"></a>관련 항목

- [사용자에게 정책 할당](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





