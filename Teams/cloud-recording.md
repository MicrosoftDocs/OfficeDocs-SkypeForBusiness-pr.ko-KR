---
title: Teams 클라우드 모임 녹음/녹화
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
localization_priority: Priority
f1.keywords:
- NOCSH
description: Teams 모임 및 그룹 통화를 녹음하여 오디오, 비디오 및 화면 공유 활동을 캡처하는 Teams 내 클라우드 음성 기능을 배치하기 위한 실제 지침입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad5cb2c6bd1abd394d23d68c6636274a6cd1447
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486148"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화

Microsoft Teams에서 사용자는 Teams 모임 및 그룹 통화를 녹음/녹화하여 오디오, 비디오 및 화면 공유 활동을 캡처할 수 있습니다. 사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검토할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 제공됩니다. 녹음/녹화는 클라우드에서 발생하고 Microsoft 비즈니스용 OneDrive 및 Microsoft SharePoint Online에 저장되므로, 조직 전체에서 안전하게 공유할 수 있습니다.

모임이 기록되면 자동으로 다음이 수행됩니다.

- 비즈니스용 OneDrive 또는 SharePoint Online에 업로드됨
- 모임에 초대된 사용자에게 사용 권한이 부여됨
- 모임에 대한 채팅에 연결됨
- Teams 일정에서 모임에 대한 녹음/녹화 및 기록 탭에 표시됨
- Microsoft 365 전반에 다양한 파일 목록(나와 공유됨, office.com, 권장, 최근에 사용한 항목 등)이 추가됨
- Microsoft 365 Search에 대해 인덱싱됨

관련: [Teams 모임 녹음/녹화 최종 사용자 문서](https://aka.ms/recordmeeting)

>[!Note]
> 모임 녹음/녹화에 사용하는 방법에 대해 Microsoft Stream(클래식)에서 비즈니스용 OneDrive 및 SharePoint Online으로의 변경은 2021년 8월에 자동으로 수행됩니다. 자세한 정보는 [모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용](tmr-meeting-recording-change.md)을 참조하세요.

> [!NOTE]
> Teams 모임의 역할 사용 및 사용자 역할 변경 방법에 대한 자세한 내용은 [Teams 모임의 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조하세요. 실시간 이벤트 기록 옵션은 [Teams의 실시간 이벤트 기록 정책](teams-live-events/live-events-recording-policies.md)을 참조하세요.

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화 필수 구성 요소

Teams 사용자의 모임을 녹음/녹화하려면 테넌트에서 비즈니스용 OneDrive 및 SharePoint Online을 사용하도록 설정해야 합니다. 또한 모임 이끌이 및 녹음/녹화를 시작하는 사용자 모두는 다음과 같은 필수 조건을 충족해야 합니다.

- 비 채널 모임 녹음/녹화를 저장할 수 있도록 비즈니스용 OneDrive에 충분한 저장 공간이 있어야 합니다.

- 채널 모임 녹음/녹화를 저장할 수 있도록 Teams 채널에는 SharePoint Online에 충분한 저장 공간이 있습니다.

- 사용자가 모임 및 그룹 통화를 녹음/녹화하기 위해 `CsTeamsMeetingPolicy -AllowCloudRecording` 설정을 true로 설정했습니다.

- 사용자가 1:1 통화를 기록하기 위해 `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` 설정을 true로 설정했습니다.

- 사용자가 모임에서 익명, 게스트 또는 페더레이션 사용자가 아닙니다.

- 사용자 모임에 대한 기록을 사용 가능으로 설정하려면, 할당된 Teams 모임 정책에 `-AllowTranscription` 설정이 true로 설정되어 있어야 합니다.

- 채널 구성원이 녹음/녹화를 편집하거나 다운로드할 수 없도록 채널 모임 녹음/녹화를 저장하려면 `CSTeamsMeetingPolicy -ChannelRecordingDownload` 설정을 차단으로 설정해야 합니다.

> [!IMPORTANT]
>
> 녹음/녹화만 기록하고 다운로드하도록 설정하려면 비즈니스용 OneDrive 또는 SharePoint Online을 사용하도록 설정할 필요가 없습니다. 이는 녹음/녹화가 비즈니스용 OneDrive 또는 SharePoint Online에 저장되지 않지만, 삭제되기 전에 21일 제한으로 임시 Teams 저장소에 저장됨을 의미합니다. 관리자가 현재 제어, 관리 또는 삭제할 수 있는 것은 아닙니다.
>
> [임시 모임 녹음/녹화 저장소가 작동하는 방식에 대한 자세한 내용](#temp-storage)은 아래를 참조하세요.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>조직의 사용자를 위해 Teams 클라우드 모임 녹음/녹화 설정

이 섹션에서는 [Teams 모임 정책](./assign-policies.md)을 통해 Teams 모임 녹음/녹화를 설정하고 계획하는 방법을 설명합니다.

### <a name="turn-on-or-turn-off-cloud-recording"></a>클라우드 녹음/녹화 설정 또는 해제

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자 모임을 녹음/녹화할 수 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **클라우드 녹음/녹화 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오의 모임 정책 설정](meeting-policies-audio-and-video.md#allow-cloud-recording)을 참조하세요.

PowerShell을 사용하여 TeamsMeetingPolicy에서 AllowCloudRecording 설정을 구성할 수 있습니다. 자세한 내용은 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조하세요.

모임 이끌이 및 녹음/녹화 개시자 모두에게 모임을 녹음/녹화하는 데 필요한 녹음/녹화 권한이 있어야 합니다. 사용자에게 사용자 지정 정책을 할당한 경우 사용자는 기본적으로 AllowCloudRecording을 해제한 전역 정책을 받게됩니다.

> [!NOTE]
> Teams 역할을 사용하여 모임 기록 권한을 가진 사용자를 구성하는 방법에 대한 자세한 내용은 [Teams 모임의 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조하세요.

사용자에 대한 전역 정책으로 변경하기 위해 다음과 같은 cmdlet를 사용하여 사용자에 대한 특정 정책 과제를 제거합니다.

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

전역 정책의 AllowCloudRecording 값을 변경하려면 다음과 같은 cmdlet를 사용합니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|시나리오|단계|
|--|--|
| 회사의 모든 사용자가 모임을 녹음/녹화할 수 있게 하려고 합니다. | <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = True가 있는지 확인합니다.<li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다.</ol> |
| 대부분의 사용자가 모임을 녹음/녹화할 수 있게하고 녹음/녹화를 허용하지 않는 특정 사용자를 선택적으로 해제하려고 합니다. | <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = True인지 확인합니다.<li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다.<li>다른 모든 사용자에게 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다.</ol> |
| 녹음/녹화를 100% 사용하지 않도록 설정하려고 합니다. | <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인합니다.<li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. |
| 대부분의 사용자에게 녹음/녹화를 사용하지 않도록 설정하고 선택적으로 특정 사용자에게 녹음/녹화를 사용하도록 설정하려고 합니다. | <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인합니다.<li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다.<li>다른 모든 사용자에게 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. <ol> |


<a name="bd-channel"></a>
### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>채널 모임 녹음/녹화의 다운로드 차단 또는 허용

이 설정은 채널 모임이 채널의 "녹음/녹화" 폴더 또는 "녹음/녹화\보기 전용" 폴더에 저장되는지 여부를 제어합니다.

이 설정의 두 값은 다음과 같습니다.

- **허용**(기본값) - 채널의 "녹음/ 녹화" 폴더에 채널 모임 녹음/녹화를 저장합니다. 녹음/ 녹화 파일에 대한 사용 권한은 채널 SharePoint Online 사용 권한을 기반으로 합니다. 이는 채널에 대해 업로드된 다른 파일과 동일합니다.

- **차단** - 채널의 "녹음/녹화\보기 전용" 폴더에 채널 모임 녹음/녹화를 저장합니다. 채널 소유자는 이 폴더의 녹음/녹화에 대한 모든 권한을 가지지만, 채널 멤버는 다운로드할 수 없는 읽기 권한을 갖습니다.

PowerShell을 사용하여 TeamsMeetingPolicy에서 ChannelRecordingDownload 설정을 구성합니다. 자세한 내용은 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조하세요.

사용자에게 사용자 지정 정책을 할당하지 않은 경우 기본적으로 ChannelRecordingDownload가 허용으로 설정된 전역 정책을 받습니다.

사용자에 대한 전역 정책으로 변경하기 위해 다음과 같은 cmdlet을 사용하여 사용자에 대한 특정 정책 과제를 제거합니다.

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

글로벌 정책에서 ChannelRecordingDownload의 값을 변경하려면 다음 cmdlet을 사용합니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> ChannelRecordingDownload 설정은 Teams PowerShell 모듈 버전 2.4.1-preview 이상에서만 사용할 수 있습니다. 모듈의 최신 미리 보기 버전을 다운로드하려면 다음 명령을 사용합니다.
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>녹음/녹화 기록 설정 또는 해제

이 설정은 모임 녹음/녹화 재생 중에 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 이 옵션을 해제하면 모임 녹음/녹화를 재생하는 동안 **검색** 및 **CC** 옵션을 사용할 수 없습니다. 녹음/녹화를 시작한 사용자는 녹음/녹화에 전사도 포함되도록 이 설정을 설정해야 합니다.

> [!NOTE]
> 녹음/녹화된 모임에 대한 문서 작성은 현재 Teams 언어를 영어로 설정한 사용자와 모임에서 영어가 사용되는 경우에만 지원됩니다. 비즈니스용 OneDrive 및 SharePoint Online 클라우드 저장소에 모임 녹음/녹화와 함께 저장됩니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 녹음/녹화 개시자에게 모임 녹음/녹화를 기록할 수 있는 선택권이 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **기록 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오의 모임 정책 설정](meeting-policies-audio-and-video.md#allow-transcription)을 참조하세요.

PowerShell을 사용하여 TeamsMeetingPolicy에서 AllowTranscription 설정을 구성할 수 있습니다. 자세한 내용은 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조하세요.

사용자에게 사용자 지정 정책을 할당하지 않은 경우 사용자는 기본적으로 AllowTranscription을 해제한 전역 정책을 받게됩니다.

사용자에 대한 전역 정책으로 변경하기 위해 다음과 같은 cmdlet를 사용하여 사용자에 대한 특정 정책 과제를 제거합니다.

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

전역 정책의 AllowCloudRecording 값을 변경하려면 다음과 같은 cmdlet를 사용합니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

</br>
</br>

|시나리오|단계 |
|---|---|
|모임 녹음/녹화를 시작할 때 회사의 모든 사용자가 기록할 수 있게 하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = True가 있는지 확인합니다. <li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. </ol>|
|대부분의 사용자가 모임 녹음/녹화를 기록할 수 있게하고 기록을 허용하지 않는 특정 사용자를 선택적으로 해제하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = True가 있는지 확인합니다. <li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. <li>다른 모든 사용자에게 AllowTranscription = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|녹음/녹화에 대한 기록을 100% 사용하지 않도록 설정하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = False가 있는지 확인합니다. <li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|대부분의 사용자에게 기록을 사용하지 않도록 설정하고 선택적으로 특정 사용자에게 기록을 사용하도록 설정하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인합니다. <li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. <li>다른 모든 사용자에게 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|


## <a name="permissions-and-storage"></a>사용 권한 및 저장소

모임 녹음/녹화는 비즈니스용 OneDrive 및 SharePoint Online 클라우드 저장소에 저장됩니다. 위치 및 사용 권한은 모임 유형과 모임에서 사용자의 역할에 따라 달라집니다. 녹화에 적용되는 기본 사용 권한은 아래에 나열되어 있습니다. 비디오 녹화 파일에 대한 전체 편집 권한이 있는 사용자는 사용 권한을 변경하고 필요에 따라 나중에 다른 사용자와 공유할 수 있습니다.

### <a name="non-channel-meetings"></a>비 채널 모임

- 녹음/녹화는 레코드를 클릭한 사용자의 비즈니스용 OneDrive에 있는 **녹음/녹화** 폴더에 저장됩니다. 

  예: <i>레코더의 비즈니스용 OneDrive</i>/**녹음/녹화**

- 외부 사용자를 제외하고 모임에 초대된 사용자에게는 다운로드할 수 없는 보기 액세스 권한이 있는 녹음/녹화 파일에 대한 사용 권한이 자동으로 부여됩니다.

- 모임 소유자와 레코드를 클릭한 사람은 사용 권한을 변경하고 다른 사용자와 공유할 수 있는 모든 편집 권한을 얻습니다.

### <a name="channel-meetings"></a>채널 모임

`Set-CsTeamsMeetingPolicy -ChannelRecordingDownload`이(가) 허용(기본값)으로 설정된 경우:

- 녹음/녹화는 **녹음/녹화** 폴더의 Teams 사이트 설명서 라이브러리에 저장됩니다. 

  예:  <i>Teams 이름 - 채널 이름</i>/**문서**/**녹음/녹화**

- 레코드를 클릭한 멤버에게 녹음/녹화에 대한 편집 권한이 있습니다.

- 다른 모든 구성원의 권한은 채널 SharePoint Online 권한을 기반으로 합니다.

`Set-CsTeamsMeetingPolicy -ChannelRecordingDownload`이(가) 차단으로 설정된 경우:

- 녹음/녹화는 **녹음/녹화/보기 전용** 폴더의 Teams 사이트 설명서 라이브러리에 저장됩니다. 

  예: <i>Teams 이름 - 채널 이름</i>/**문서/녹음/녹화/보기 전용**

- 채널 소유자는 이 폴더의 녹음/녹화에 대한 전체 편집 및 다운로드 권한을 갖습니다.

- 채널 멤버는 다운로드할 수 없는 보기 전용 액세스 권한을 갖게 됩니다.

특정 모임 유형에 대한 자세한 내용은 다음 표를 참조하세요.

| 모임 유형  | 누가 레코드를 클릭했나요?| 녹음은 어디에 있나요? | 액세스 가능한 사용자 R/W, R 또는 공유  |
|-------------|-----------------------|------------------------|------------------------|
|내부 파티와의 1:1 통화             |발신자                 |발신자의 비즈니스용 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다. <br /><br />수신자(동일한 테넌트에 있는 경우)는 읽기 전용 액세스 권한이 있습니다. 공유 액세스 권한이 없습니다. <br /><br /> 수신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|내부 파티와의 1:1 통화             |수신자                 |수신자의 비즈니스용 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다. <br /><br />호출자(동일한 테넌트에 있으며 읽기 전용 액세스 권한이 있는 경우) 공유 액세스 권한이 없습니다. <br /><br />발신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
|외부 통화로 1:1 통화             |발신자                 |발신자의 비즈니스용 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다.<br /> <br />수신자에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|외부 통화로 1:1 통화             |수신자                 |수신자의 비즈니스용 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다.<br /><br />발신자에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
|그룹 통화                                 |통화의 모든 구성원 |레코드의 비즈니스용 OneDrive 계정을 클릭한 그룹 구성원  |레코드를 클릭한 구성원은 모든 권한이 있습니다. <br /><br /> 동일한 테넌트에 있는 다른 멤버는 읽기 권한을 갖습니다. <br /><br /> 다른 테넌트에 있는 다른 그룹 구성원은 이 그룹에 대한 권한이 없습니다.|
|임시/예약된 모임                    |이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 가집니다. <br /><br /> 모임의 다른 모든 구성원은 다운로드할 수 없는 읽기 권한이 있습니다.|
|임시/예약된 모임                    |다른 모임 구성원   |레코드를 클릭한 모임 구성원                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. <br /><br />이끌이는 편집 권한이 있으며 공유할 수 있습니다.<br /><br /> 다른 모든 모임 구성원은 다운로드할 수 없는 읽기 권한이 있습니다.|
|외부 사용자와 임시/예약된 모임|이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 가집니다.<br /> <br /> 이끌이와 동일한 테넌트에 있는 모임의 다른 모든 구성원은 다운로드할 수 없는 읽기 권한을 갖습니다. <br /><br /> 다른 모든 외부 구성원은 액세스 권한이 없으며, 이끌이는 해당 구성원과 공유해야 합니다.|
|외부 사용자와 임시/예약된 모임|다른 모임 구성원   |레코드를 클릭한 구성원                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. 이끌이는 편집 권한이 있으며 공유할 수 있습니다. <br /><br /> 이끌이와 동일한 테넌트에 있는 모임의 다른 모든 구성원은 다운로드할 수 없는 읽기 권한을 갖습니다. <br /><br />다른 모든 외부 구성원은 액세스 권한이 없으며, 이끌이는 해당 구성원과 공유해야 합니다.|
|채널 모임                            |채널 구성원         |해당 채널에 대한 Teams의 SharePoint Online 위치                   |Set-CsTeamsMeetingPolicy -ChannelRecordingDownload가 허용(기본값)으로 설정된 경우, 레코드를 클릭한 구성원은 녹음/녹화에 대한 편집 권한을 가집니다. 다른 모든 구성원의 권한은 채널 SharePoint Online 권한을 기반으로 합니다.<Br><Br>Set-CsTeamsMeetingPolicy -ChannelRecordingDownload가 차단으로 설정된 경우, 채널 소유자는 녹음/녹화에 대한 모든 권한이 있지만 채널 멤버는 다운로드할 수 없는 읽기 권한을 갖습니다.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-for-business-and-sharepoint-online"></a>비즈니스용 OneDrive 및 SharePoint Online에 업로드할 수 없는 경우 임시 저장소

모임 녹음/녹화를 비즈니스용 OneDrive 및 SharePoint Online에 업로드할 수 없는 경우, 삭제되기 전에 21일 동안 Teams에서 일시적으로 다운로드할 수 있습니다. 이는 현재 관리자가 삭제하는 기능을 포함하여 제어하거나 관리할 수 있는 사항이 아닙니다.

모임 녹음/녹화는 다음과 같은 이유로 이 임시 저장소에 저장될 수 있습니다.

- 비 채널 모임에서 사용자 녹음/녹화에 비즈니스용 OneDrive 설정이 없거나 비즈니스용 OneDrive가 저장소 할당량에 도달한 경우 
- 채널 모임에서 SharePoint Online 사이트가 저장소 할당량에 도달했거나 사이트가 아직 프로비저닝되지 않은 경우
- 특정 비즈니스용 OneDrive 및 SharePoint Online 정책을 사용하도록 설정하면 특정 IP 범위 등에 없는 경우 사용자가 파일을 업로드하지 못하도록 제한할 수 있습니다.

이에 대한 녹음/녹화 보존은 임시 스토리지이며 채팅 메시지 자체의 영향을 받습니다. 따라서 녹음/녹화에 대한 원래 채팅 메시지를 삭제하면 사용자가 녹음/녹화에 액세스할 수 없게 됩니다. 다음과 같은 두 가지 시나리오가 있습니다.

- **사용자가 채팅 메시지를 수동으로 삭제합니다** - 이 시나리오에서는 원본 메시지가 사라지면 사용자는 더 이상 녹음/녹화에 액세스할 수 없으며 더 이상 다운로드할 수 없습니다. 그러나 녹음/녹화 자체는 Microsoft의 내부 시스템 내에서 원래 21일을 초과하지 않는 기간 동안 계속 유지될 수 있습니다.

- **채팅 메시지 녹음/녹화가 채팅 보존 정책에 의해 삭제됩니다** - 임시 저장소 녹음/녹화는 채팅 보존 정책과 직접적인 관련이 있습니다. 따라서 Teams 임시 저장소에 있는 녹음/녹화는 삭제되기 전에 기본적으로 21일 동안 유지되지만, 21일 전에 채팅 메시지가 삭제되면 채팅 메시지 보존 정책으로 인해 해당 녹음/녹화도 삭제됩니다. 이 경우 녹음/녹화를 복구할 방법이 없습니다.

### <a name="planning-for-storage"></a>저장소 계획

1시간 녹음/녹화 크기는 400MB입니다. 녹음/녹화된 파일에 대한 필요한 용량을 알고 있어야 하며 비즈니스용 OneDrive 및 SharePoint Online에서 충분한 저장소를 사용할 수 있는지 확인합니다.  구독에 포함된 기본 저장소 및 추가 저장소를 구입하는 방법을 이해하려면 [비즈니스용 OneDrive의 기본 저장 공간 설정](/onedrive/set-default-storage-space) 및 [SharePoint Online 사이트 저장소 제한 관리](/sharepoint/manage-site-collection-storage-limits)를 참조하세요.

## <a name="manage-meeting-recordings"></a>모임 녹음/녹화 관리

모임 녹음/녹화는 비즈니스용 OneDrive 및 SharePoint Online에 비디오 파일로 저장되며 해당 플랫폼에서 사용할 수 있는 관리 및 거버넌스 옵션을 따릅니다. 자세한 내용은 [SharePoint Online 거버넌스 개요](/sharepoint/governance-overview), [엔터프라이즈용 비즈니스용 OneDrive 가이드](/onedrive/plan-onedrive-enterprise) 또는 [중소기업용 비즈니스용 OneDrive 가이드](/onedrive/one-drive-quickstart-small-business)를 참조하세요.

비 채널 모임의 경우, 녹음/녹화는 레코더의 비즈니스용 OneDrive 저장되므로 직원이 퇴사한 후 소유권 및 보존에 대한 처리는 일반적인 [비즈니스용 OneDrive 및 SharePoint Online 프로세스](/onedrive/retention-and-deletion#the-onedrive-deletion-process)를 따릅니다.

## <a name="closed-captions-for-recordings"></a>녹음/녹화를 위한 선택 자막

Teams 모임 녹음/녹화에 대한 선택 자막은 사용자가 녹음/녹화 시 필사 기능을 켠 경우에만 재생 중에 사용할 수 있습니다. 관리자는 사용자가 필사 기능을 사용하여 모임을 녹음/녹화할 수 있도록 [정책을 통해 녹음/녹화 필사를 켜야](#turn-on-or-turn-off-recording-transcription) 합니다.

캡션은 장애가 있는 뷰어를 위해 포괄적인 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 모임 녹음/녹화에서 캡션을 숨길 수 있지만, 모임 대본을 삭제하지 않는 한 Teams에서 계속 사용할 수 있습니다.

오늘 녹화 비디오 파일의 선택 자막은 Teams 모임 대본에 연결됩니다. 이 링크는 대부분의 경우 파일의 수명 동안 유지되지만, 비디오 파일이 동일한 비즈니스용 OneDrive 또는 SharePoint Online 사이트 내에서 복사되면 끊어질 수 있으며, 이로 인해 복사된 비디오 파일에서 캡션을 사용할 수 없게 됩니다.

Teams의 대본과 녹음/녹화 간의 링크에 대한 향후 변경 사항은 여기와 메시지 센터 알림에서 명확히 설명됩니다. 나중에 변경하면 60일이 안 된 녹음/녹화 파일에 모임의 대본이 캡션으로 표시됩니다.

> [!NOTE]
> 영어 전용 선택 자막이 있습니다(GCC에서는 모임 필사를 아직 사용할 수 없음).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>모임 녹음/녹화에 대한 규정 준수 및 eDiscovery

### <a name="ediscovery"></a>eDiscovery

모임 녹음/녹화는 비즈니스용 OneDrive 및 SharePoint Online에 저장되며 Microsoft 365 Office 365 Tier-D를 준수합니다. 모임 또는 통화 녹음/녹화에 관심이 있는 규정 준수 관리자에 대한 e-Discovery 요청을 지원하기 위해, Microsoft Teams의 준수 콘텐츠 검색 기능에서는 녹음/녹화 완료 메시지를 제공합니다. 준수 관리자는 준수 콘텐츠 검색 미리 보기에서 항목의 제목 줄에서 “녹음/녹화” 키워드를 찾을 수 있으며 조직에서 모임 및 통화 녹음/녹화를 검색할 수 있습니다.

또한 eDiscovery를 통해 SharePoint Online 및 비즈니스용 OneDrive에서 파일을 검색하여 모임 녹음/녹화 비디오 파일을 찾을 수 있습니다.

eDiscovery에 대한 자세한 내용은 [Microsoft 365용 eDiscovery 솔루션](/microsoft-365/compliance/ediscovery) 문서를 참조하세요.

### <a name="retention-policies"></a>보존 정책

ProgID 속성을 통해 Teams 모임 녹음/녹화 비디오 파일만 대상으로 지정하도록 자동 보존 레이블을 적용할 수 있습니다. 자세한 내용은 [Teams 모임 녹음/녹화에 대한 보존 레이블을 자동으로 적용하는 방법](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)을 참조하세요.

### <a name="data-loss-prevention-dlp-policies"></a>DLP(데이터 손실 방지) 정책

ProgID 속성별로 모임 녹음/녹화 파일에 DLP 정책을 적용할 수도 있습니다. SharePoint Online 및 비즈니스용 OneDrive 파일에 대한 DLP 규칙에서 조건을 다음으로 설정합니다.

- 문서 속성 = *ProgID*
- 값 = *Media.Meeting*

DLP에 대한 자세한 내용은 [데이터 손실 방지에 대한 자세한 정보](/microsoft-365/compliance/dlp-learn-about-dlp) 문서를 참조하세요.

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
