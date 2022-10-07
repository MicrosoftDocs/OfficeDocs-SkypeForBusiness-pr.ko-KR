---
title: 보류 중인 음악
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
ms.custom: ''
description: 전화 시스템에서 음악 보류 기능을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 9e2a2aa352a1fd65955b35d4175b831653c694cb
ms.sourcegitcommit: 52450514880fe72af0d0b2fab1419eadfc3a583f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68499452"
---
# <a name="music-on-hold"></a>보류 중인 음악

Microsoft Teams 사용자가 수신 전화를 보류하면 발신자가 선택한 음악을 들을 수 있습니다.

재생되는 음악은 Microsoft에서 제공하는 기본 음악 또는 업로드하고 구성하는 사용자 지정 음악입니다. 테넌트 관리자는 Teams 통화 정책을 만들고 Teams 사용자에게 정책을 할당하여 Music on Hold를 사용할 수 있는지 여부를 구성합니다.

Microsoft Teams 통화 시나리오에서 제공되는 기본 음악은 조직에서 지불하는 로열티가 없습니다.

호출자는 다른 시나리오에서도 대기 중인 음악을 들을 수 있습니다. 예를 들어 클라우드 통화 큐에 호출하거나 Microsoft Teams 사용자가 통화를 대기하는 경우를 예로 들어 보겠습니다. 이러한 시나리오는 이 문서에 언급된 기능에 의해 다루거나 제어되지 않습니다.

## <a name="configure-music-on-hold"></a>보류 중인 음악 구성

보류 중인 음악을 구성하려면 다음을 수행합니다.

1. Teams 관리 센터의 왼쪽 탐색 영역에서 **음성 > 통화 정책** 으로 이동합니다.

2. **정책 관리** 탭에서 기존 정책 중 하나를 선택하거나 새 정책을 만듭니다.

3. **PSTN 호출자에 대한 보류 중인 음악** 필드에서 드롭다운 메뉴에서 **[사용]** 을 선택합니다.

Teams PowerShell 모듈을 사용하여 Music on Hold를 구성할 수도 있습니다. TeamsCallingPolicy에서 MusicOnHoldEnabledType 매개 변수를 Enabled로 변경한 다음 해당 정책 인스턴스를 하나 이상의 사용자에게 부여합니다.

Teams 사용자에게 Music on Hold가 사용 안 함으로 설정된 Teams 통화 정책이 있는 경우 Teams 사용자가 통화를 보류할 때 음악이 재생되지 않습니다.

## <a name="configure-custom-music"></a>사용자 지정 음악 구성

발신자에게 기본 음악을 재생하는 것 외에도 음악 또는 기타 오디오 콘텐츠가 포함된 사용자 지정 오디오 파일을 업로드하고 호출자에게 재생되도록 오디오 파일을 구성할 수 있습니다.
예를 들어 부서 또는 조직은 외부 PSTN 발신자가 대기 중인 경우 사용자 지정 공지 또는 사용자 지정 음악을 재생하려고 할 수 있습니다.

구성은 통화 보류 정책을 사용하여 수행됩니다.

> [!NOTE]
> Microsoft Teams 서비스에서 음악 또는 오디오 파일을 사용하는 데 필요한 모든 권한과 권한을 독립적으로 지우고 보호해야 합니다. 여기에는 모든 관련 권리 보유자의 오디오 파일에서 음악, 음향 효과, 오디오, 브랜드, 이름 및 기타 콘텐츠의 지적 재산권 및 기타 권한이 포함될 수 있습니다. 소지자는 아티스트, 배우, 공연자, 음악가, 작곡가, 작곡가, 음반 레이블, 음악 출판사, 노조, 길드, 권리 사회, 집단 관리 조직 및 음악 저작권, 음향 효과, 오디오 및 기타 지적 재산권을 소유, 제어 또는 허가하는 기타 당사자를 포함할 수 있습니다.

### <a name="use-the-teams-admin-center"></a>Teams 관리 센터 사용
Teams 관리 센터를 사용하여 통화 보류 정책을 만들거나 편집하여 사용자에 대해 보류 중인 사용자 지정 음악을 구성할 수 있습니다.

새 통화 보류 정책을 구성하려면 다음을 수행합니다.

1. Teams 관리 센터에서 **음성** > **통화 대기 정책** 으로 이동합니다.

2. **추가** 탭을 선택합니다.

3. 정책에 이름과 설명을 지정합니다.

4. **파일 업로드** 를 선택하여 사용자 지정 음악 오디오 파일을 업로드합니다.

5. **적용** 을 선택합니다.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>사용자에게 사용자 지정 통화 보류 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>PowerShell 사용
보류 중인 사용자 지정 음악을 구성하려면 Teams PowerShell 모듈 3.0.0 이상에서 PowerShell cmdlet New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy 및 Import/Get/Remove/Export-CsOnlineAudioFile을 사용합니다.

지원되는 오디오 형식 및 최대 파일 크기는 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)을 참조하세요.

1. Teams 사용자에게 Teams 통화 정책에서 PSTN 발신자에 대한 음악이 사용되도록 설정되어 있는지 확인합니다. 

2. 사용자 지정 오디오 파일을 업로드합니다.

3. 사용자 지정 오디오 파일을 참조하는 Teams 통화 보류 정책을 만들고 Teams 사용자에게 할당합니다.

### <a name="upload-the-custom-audio-file"></a>사용자 지정 오디오 파일 업로드

대기 중인 사용자 지정 음악의 구성은 오디오 파일을 업로드하는 것으로 시작합니다. 이 용도로 PowerShell cmdlet [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) 을 사용합니다.

Windows PowerShell 5.1을 사용하여 MP3 오디오 파일을 업로드하는 예제는 다음과 같습니다. 다른 예제는 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)을 참조하세요.

```PowerShell
C:\> $content = [System.IO.File]::ReadAllBytes('C:\tmp\customMoH1.mp3')
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Teams 통화 보류 정책에서 오디오 파일 참조

오디오 파일을 업로드한 후에는 Teams 통화 보류 정책을 만들거나 설정할 때 파일의 ID를 사용하여 Teams 통화 보류 정책에서 파일을 참조해야 합니다. 예를 들면 다음과 같습니다.

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

새 Teams 통화 보류 정책을 만든 후 다음과 같이 Grant-CsTeamsCallHoldPolicy 사용하여 사용자에게 부여할 수 있습니다.

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

업로드된 오디오 파일에 대한 정보를 얻으려면 Get-CsOnlineAudioFile cmdlet을 사용합니다.

업로드된 오디오 파일을 제거하려면 Remove-CsOnlineAudioFile cmdlet을 사용합니다. 오디오 파일을 제거하기 전에 TeamsCallHoldPolicy에서 해당 오디오 파일을 사용하고 있지 않은지 확인합니다.

업로드된 오디오 파일을 내보내려면 Export-CsOnlineAudioFile cmdlet을 사용합니다.

## <a name="feature-availability"></a>기능 가용성

다음 표에서는 보류 중인 음악과 보류 중인 사용자 지정 음악을 지원하는 클라이언트 및 디바이스의 기능을 나타냅니다. Microsoft는 계속해서 기능 지원을 추가하므로 추가 가용성에 대해 자주 다시 확인하세요.

| 기능 | 데스크톱 <br> Windows/Mac OS | 브라우저 | 모바일 <br> iOS | 모바일 <br> Android | Teams 전화 |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 1:1 PSTN 통화 대기 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 |
| 1:1 Teams 통화 대기 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 |
| 1:1 PSTN 통화에서 전송 보류 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | | |
| 1:1 Teams 통화에서 전송 보류 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악| | | |
| 1:1 PSTN 통화에서 컨설팅 전송 보류 |-음악 보류 중<br>-보류 중인 사용자 지정 음악 || -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 |
| 1:1 Teams 통화에서 컨설팅 전송 보류 |-음악 보류 중<br>-보류 중인 사용자 지정 음악 || -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 | -음악 보류 중<br>-보류 중인 사용자 지정 음악 |

## <a name="restrictions"></a>제한

- 보류 중인 음악은 상업용 및 GCC 클라우드 인스턴스에서만 사용할 수 있습니다.

- 보류 중인 음악은 사용자가 TeamsOnly 모드에 있는 경우에만 사용할 수 있습니다.

- 호출된 Teams 사용자가 Location-Based 라우팅을 사용하도록 설정된 경우 표준 음악 대기 상태만 호출자에게 재생됩니다.

- 공유 회선 모양(위임)에 대해 구성된 사용자 및 통화 대기를 사용하는 경우 사용자 지정 음악 보류를 사용할 수 없습니다. 대기 중인 표준 음악이 재생됩니다.

- 일부 시나리오에서는 직접 라우팅 미디어 바이패스 호출이 대기 중인 음악을 재생하기 위한 비미디어 바이패스로 변환되고 통화가 종료될 때까지 비미디어 바이패스로 통화가 유지됩니다.

## <a name="related-topics"></a>관련 주제

- [사용자에게 정책 할당](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
