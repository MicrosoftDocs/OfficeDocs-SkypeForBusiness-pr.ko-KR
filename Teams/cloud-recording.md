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
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Teams 모임 및 그룹 통화를 녹음하여 오디오, 비디오 및 화면 공유 활동을 캡처하는 Teams 내 클라우드 음성 기능을 배치하기 위한 실제 지침입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d84d42849667c1cd87a90f9cd8b3480b5ed8bbd
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462392"
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

관련: [Teams 모임 녹음/녹화 최종 사용자 문서](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> 모임 녹음/녹화에 사용하는 방법에 대해 Microsoft Stream(클래식)에서 비즈니스용 OneDrive 및 SharePoint Online으로의 변경은 2021년 8월에 자동으로 수행됩니다. 자세한 정보는 [모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용](tmr-meeting-recording-change.md)을 참조하세요.

> [!NOTE]
> Teams 모임의 역할 사용 및 사용자 역할 변경 방법에 대한 자세한 내용은 [Teams 모임의 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)을 참조하세요. 실시간 이벤트 기록 옵션은 [Teams의 실시간 이벤트 기록 정책](teams-live-events/live-events-recording-policies.md)을 참조하세요.

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

이 섹션에서는 [Teams 모임 정책](policy-assignment-overview.md)을 통해 Teams 모임 녹음/녹화를 설정하고 계획하는 방법을 설명합니다.

### <a name="turn-on-or-turn-off-cloud-recording"></a>클라우드 녹음/녹화 설정 또는 해제

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자 모임을 녹음/녹화할 수 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **클라우드 녹음/녹화 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오의 모임 정책 설정](meetings-policies-recording-and-transcription.md#allow-cloud-recording)을 참조하세요.

PowerShell을 사용하여 TeamsMeetingPolicy에서 AllowCloudRecording 설정을 구성할 수 있습니다. 자세한 내용은 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조하세요.

모임 이끌이 및 녹음/녹화 개시자 모두에게 모임을 녹음/녹화하는 데 필요한 녹음/녹화 권한이 있어야 합니다. 사용자에게 사용자 지정 정책을 할당한 경우 사용자는 기본적으로 AllowCloudRecording을 해제한 전역 정책을 받게됩니다.

> [!NOTE]
> Teams 역할을 사용하여 모임 기록 권한을 가진 사용자를 구성하는 방법에 대한 자세한 내용은 [Teams 모임의 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)을 참조하세요.

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

이 설정은 채널 모임이 채널의 "녹음/녹화" 폴더 또는 "녹음/녹화\보기 전용" 폴더에 저장되는지 여부를 제어합니다. 설정은 채널 모임에 대한 레코드를 선택하는 사용자의 정책에 적용됩니다.

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
> 녹음된 모임에 대한 해당 텍스트 변환은 현재 영어(미국), 영어(캐나다), 영어(인도), 영어(영국), 영어(호주), 영어(뉴질랜드), 독일어(독일), 포르투갈어(브라질), 네덜란드어(네덜란드), 네덜란드어(벨기에), 프랑스어(프랑스), 스페인어(스페인), 일본어(일본), 프랑스어(캐나다), 중국어(광둥어, 번체), 중국어(북경어, 간체), 힌디어(인도), 이탈리아어(이탈리아), 한국어(한국), 스페인어(멕시코), 스웨덴어(스웨덴), 폴란드어(폴란드), 아랍어(아랍에미리트), 아랍어(사우디아라비아), 덴마크어(덴마크), 핀란드어(핀란드), 노르웨이어(노르웨이) 및 러시아어(러시아)에 대해서만 지원됩니다. 해당 항목들은 비즈니스용 OneDrive 및 SharePoint Online 클라우드 저장소의 모임 레코딩과 함께 저장됩니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 녹음/녹화 개시자에게 모임 녹음/녹화를 기록할 수 있는 선택권이 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **기록 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오의 모임 정책 설정](meetings-policies-recording-and-transcription.md#allow-transcription)을 참조하세요.

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

### <a name="terms-of-use-acceptance"></a>사용 약관 동의
조직에서 모임을 녹음/녹화하기 전에 사용자가 동의하도록 하는 모임 녹음/녹화 정책이 있는 경우, [Azure Active Directory 사용 약관](/azure/active-directory/conditional-access/terms-of-use) 기능을 사용하세요. 이 기능을 사용하면 Microsoft Teams에 액세스하기 전에 조직의 사용자 정책에 동의할 수 있습니다. 이 기능은 녹음/녹화 단추를 클릭하는 것과 관련이 없지만 Teams나 기타 Microsoft 365 앱을 전체적으로 사용하는 것과 관련이 있습니다. Teams나 Microsoft 365 사용에 대한 전반적인 이용 약관에 회의 기록 정보를 추가하는 것이 좋습니다. 

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
|내부 파티와의 1:1 통화             |발신자                 |발신자의 비즈니스용 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다. <br /><br />수신자(동일한 테넌트에 있는 경우)는 읽기 전용 액세스 권한이 있지만, 공유 액세스 권한은 없습니다. <br /><br /> 수신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|내부 파티와의 1:1 통화             |수신자                 |수신자의 비즈니스용 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다. <br /><br />호출자(동일한 테넌트에 있는 경우)는 읽기 전용 액세스 권한이 있지만, 공유 액세스 권한은 없습니다. <br /><br />발신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
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

모임 녹음/녹화를 비즈니스용 OneDrive 및 SharePoint Online에 업로드할 수 없는 경우, 삭제되기 전에 21일 동안 Teams에서 일시적으로 다운로드할 수 있습니다. 이는 이 시점에서 관리자가 삭제하는 기능을 포함하도록 제어하거나 관리할 수 있는 것이 아닙니다.

모임 녹음/녹화는 다음과 같은 이유로 이 임시 저장소에 저장될 수 있습니다.

- 비 채널 모임에서 사용자 녹음/녹화에 비즈니스용 OneDrive 설정이 없거나 비즈니스용 OneDrive가 저장소 할당량에 도달한 경우
- 채널 모임에서 SharePoint Online 사이트가 저장소 할당량에 도달했거나 사이트가 아직 프로비저닝되지 않은 경우
- 특정 비즈니스용 OneDrive 및 SharePoint Online 정책을 사용하도록 설정하면 특정 IP 범위 등에 없는 경우 사용자가 파일을 업로드하지 못하도록 제한할 수 있습니다.

이에 대한 녹음/녹화 보존은 임시 스토리지이며 채팅 메시지 자체의 영향을 받습니다. 따라서 녹음/녹화에 대한 원래 채팅 메시지를 삭제하면 사용자가 녹음/녹화에 액세스할 수 없게 됩니다. 다음과 같은 두 가지 시나리오가 있습니다.

- **사용자가 채팅 메시지를 수동으로 삭제합니다** - 이 시나리오에서는 원본 메시지가 사라지면 사용자는 더 이상 녹음/녹화에 액세스할 수 없으며 더 이상 다운로드할 수 없습니다. 그러나 녹음/녹화 자체는 Microsoft의 내부 시스템 내에서 원래 21일을 초과하지 않는 기간 동안 계속 유지될 수 있습니다.

- **채팅 메시지 녹음/녹화가 채팅 보존 정책에 의해 삭제됩니다** - 임시 저장소 녹음/녹화는 채팅 보존 정책과 직접적인 관련이 있습니다. 따라서 Teams 임시 저장소에 있는 녹음/녹화는 삭제되기 전에 기본적으로 21일 동안 유지되지만, 21일 전에 채팅 메시지가 삭제되면 채팅 메시지 보존 정책으로 인해 해당 녹음/녹화도 삭제됩니다. 이 경우 녹음/녹화를 복구할 방법이 없습니다.

### <a name="planning-for-storage"></a>저장소 계획

1시간 녹음/녹화 크기는 400MB입니다. 녹음/녹화된 파일에 대한 필요한 용량을 알고 있어야 하며 비즈니스용 OneDrive 및 SharePoint Online에서 충분한 저장소를 사용할 수 있는지 확인합니다.  구독에 포함된 기본 저장소 및 추가 저장소를 구입하는 방법을 이해하려면 [비즈니스용 OneDrive의 기본 저장 공간 설정](/onedrive/set-default-storage-space) 및 [SharePoint Online 사이트 저장소 제한 관리](/sharepoint/manage-site-collection-storage-limits)를 참조하세요.

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Teams 모임 녹음/녹화 자동 만료: 

> [!IMPORTANT]
>
> 이 문서에서 설명하는 자동 만료 기능은 아직 출시되지 않았습니다. 구현 날짜에 대한 자세한 내용은 [로드맵(기능 ID: 84580)](https://www.microsoft.com/microsoft-365/roadmap?searchterms=82057&filters=&searchterms=84580)을 참조하세요.
> 
> 당사는 이 기능이 미래에 어떻게 작동하는지에 대한 정보를 제공하고 있으므로 이러한 변경을 계획하고 사용자는 사전에 Teams 정책 설정을 수정할 수 있습니다.
>
> Teams에서 기본 만료 설정을 미리 변경하는 CMD는 아직 설정할 수 없습니다.  설정을 수정할 수 있는 경우 업데이트된 메시지 센터 게시물을 게시합니다.
>
>

관리자 및 최종 사용자를 위한 자주 묻는 질문(FAQ)을 참조하여 Teams 모임 녹화/녹음의 자동 만료 작동 방식, 지금 수행할 수 있는 작업 및 기능이 시작된 후 수행할 수 있는 작업에 대한 인사이트를 수집하세요.
  
## <a name="frequently-asked-questions"></a>자주 묻는 질문

**변경 사항은 무엇인가요?**
  
새로 만든 모든 Teams 모임 녹화(TMR)에 대한 기본 60일 만료 설정을 도입합니다. 이는 기본적으로 이 기능을 활성화한 후 작성된 모든 TMR이 작성 날짜로부터 60일 후에 삭제됨을 의미합니다. 관리자가 모임 녹화가 기본값보다 빠르거나 늦게 만료되기를 원하는 경우 만료 설정을 수정할 수 있습니다. OneDrive 및 SharePoint 시스템은 모든 모임 녹화에 설정된 만료 날짜를 모니터링하고 만료 날짜에 자동으로 휴지통으로 이동합니다.

**이는 누구에게 영향을 미치나요?**
  
OneDrive 또는 SharePoint에서 Teams 모임 녹화(비채널, 채널 또는 임시 모임)를 저장하는 모든 사용자입니다.

**이 기능을 사용해야 하는 이유는 무엇인가요?**
  
이 기능을 사용하여 Teams 모임 녹음/녹화에서 사용하는 OneDrive 또는 SharePoint 저장소를 제한해야 합니다(참고: 일반적으로 시간당 약 400MB의 녹음을 사용합니다).
  
**이 변경사항을 도입하는 이유는 무엇인가요?**
  
고객은 Teams 모임 녹음/녹화에서 생성된 저장소 낮은 우선 순위 메일을 줄이기 위해 더 많은 제어를 원한다는 압도적인 피드백을 제공했으며, 이 중 99%는 평균적으로 60일 후에 다시 시청하지 않습니다.
  
**이 기능이 기본적으로 켜져 있는 이유는 무엇인가요?**
  
우리는 거의 모든 고객이 60일 후에 다시 시청하지 않을 것 같은 녹화물을 제거함으로써 테넌트에 대한 저장소 부하 감소의 이점을 누릴 것이라고 믿습니다. 기본적으로 모든 고객에게 가능한 한 깨끗한 경험을 제공하는 것이 우리의 목표입니다.
  
**데이터를 액세스하거나 다운로드해도 자동으로 삭제되나요?**
  
파일에 액세스해도 만료 날짜는 변경되지 않습니다.
  
**목록에 만료 날짜가 열로 표시되나요?**

기록에 대한 보기 액세스 권한이 있는 사용자는 파일이 만료되기 14일 전에 OneDrive 또는 SharePoint 폴더의 파일 옆에 빨간색 아이콘이 표시됩니다. 현재 만료 날짜가 있는 목록에 열을 추가할 수 있는 방법은 없습니다.
  
**만료 날짜는 어떻게 계산되나요?**
  
만료 날짜는 모임 녹화가 생성된 날짜에 관리자가 Teams 설정에 설정한 기본일 수를 더한 값으로 계산됩니다.
  
**데이터 A의 만료일은 30일, 데이터 B의 만료일은 60일 등 각 TMR의 만료일을 변경할 수 있나요?**

예, 만료일은 파일별로 설정됩니다. 사용자는 OneDrive 또는 SharePoint의 선택한 파일의 세부 정보 창에서 만료일을 수정할 수 있습니다.

**관리자는 만료 날짜를 어떻게 변경할 수 있나요?**
  
관리자는 기능이 릴리스되기 전에 PowerShell 또는 Teams 관리 센터에서 기본 만료 설정을 변경할 수 있습니다. **설정을 수정할 수 없습니다**. 설정을 수정할 수 있는 경우 업데이트된 메시지 센터 게시물을 게시합니다. 기능이 시작되면 관리자는 Teams 관리 센터에서 이 설정을 변경할 수 있습니다. 만기 설정을 변경하면 그 시점부터 새로 작성된 TMR에만 영향을 미칩니다. 해당 날짜 이전에 녹음/녹화된 내용에는 영향을 미치지 않습니다. 

만료 날짜 값은 다음과 같이 설정할 수 있습니다.
  
- 값은 1에서 9,999까지 사용할 수 있습니다.
- TMR이 만료되지 않도록 설정하려면 값이 -1일 수도 있습니다. 
 
관리자는 이 기능이 출시되기 전에 OneDrive 또는 SharePoint에 이미 업로드된 기존 TMR의 만료 날짜를 변경할 수 없습니다. 이는 TMR을 소유한 사용자의 의도를 보호합니다.
  
**관리자가 TMR이 만료되지 않도록 설정할 수 있나요?**
  
 예, 관리자는 TMR이 만료되지 않도록 설정할 수 있습니다.
  
**녹음/녹화를 재생하면 만료 날짜가 변경되나요?**

아니요, 재생은 만료 날짜에 영향을 주지 않습니다.
  
**TMR을 다운로드하고 다시 업로드하는 경우 만료 날짜는 어떻게 되나요?**

만료 날짜는 사용자의 SKU에 관계없이 다시 업로드할 때 지워집니다.
  
**TMR을 복사하거나 다른 위치 또는 사이트로 이동하면 어떻게 되나요?**

날짜는 이동된 TMR 파일에 대해서만 보존됩니다. 복사된 파일에는 다시 업로드된 TMR과 마찬가지로 만료 날짜가 없습니다.
  

**관리자 정책의 제어 범위는 얼마인가요?**
  
모임와 통화 모두 동일한 `CsTeamsMeetingPolicy` 설정인 `MeetingRecordingExpirationDays`에 의해 제어됩니다. 
  
**최종 사용자가 특정 TMR 파일의 만료 날짜를 수정하려면 어떻게 해야 하나요?**
  
TMR에 대한 편집 및 삭제 권한이 있는 사람은 누구나 OneDrive 또는 SharePoint의 파일 세부 정보 창에서 만료 날짜를 수정할 수 있습니다.

사용자는 만료일을 14일, 30일 또는 60일로 연기하거나 미래의 특정 날짜를 선택하거나 파일이 만료되지 않도록 선택할 수 있습니다.
  
**관리자가 엄격한 보안 및 규정 준수를 위해 이 기능을 사용해야 하나요?**
  
아니요, 최종 사용자가 자신이 제어하는 ​​모든 녹음의 만료 날짜를 수정할 수 있으므로 관리자는 법적 보호를 위해 이 기능에 의존해서는 안 됩니다.
  
**이 기능으로 파일 보존이 시행되나요?**
  
아니요, 이 기능 또는 해당 설정으로 인해 파일이 보존되지 않습니다. 삭제 권한이 있는 사용자가 만기 설정이 있는 TMR을 삭제하려고 하면 해당 사용자의 삭제 조치가 실행됩니다.

**보안 및 규정 준수(S+C) 센터에서 설정한 보관 및/또는 삭제 정책이 TMR 만료 설정보다 우선 적용되나요?**
  
예, S+C 센터에서 설정한 모든 정책이 우선 적용됩니다. 예를 들면 다음과 같습니다.
  
- 사이트의 모든 파일을 100일 동안 보존해야 하는 정책이 있고 TMR의 만료 설정이 30일인 경우 녹음 파일은 전체 100일 동안 보존됩니다.  
- 모든 TMR이 5일 후에 삭제된다는 삭제 정책이 있고 녹음 파일의 만료 설정이 30일인 경우 해당 파일은 5일 후에 삭제됩니다.

**TMR이 '만료'되면 어떻게 되나요?**
  
만료 날짜에 TMR이 OneDrive 또는 SharePoint 휴지통으로 이동되고 만료 날짜 필드가 지워집니다. 시스템에 의한 이 작업은 사용자가 파일을 삭제한 것과 정확히 동일합니다. 휴지통 수명 주기는 이후에 일반 경로를 따릅니다. 사용자가 휴지통에서 TMR을 복구하면 최종 사용자가 파일에 새 만료 날짜를 설정하지 않는 한 만료 날짜가 지워진 이후로 이 기능에 의해 TMR이 다시 삭제되지 않습니다.
  
**파일 만료에 대한 알림은 어떻게 받나요?**
  
보기 액세스 권한이 있는 모든 사람은 Teams 채팅 창의 녹화 치클릿에서 만료 날짜에 대한 알림을 볼 수 있습니다.
  
보기 액세스 권한이 있는 모든 사용자에게 파일이 만료되기 14일 전에 OneDrive 또는 SharePoint 폴더의 파일 옆에 빨간색 아이콘이 표시됩니다.
  
파일 소유자는 TMR이 만료되면 이메일 알림을 받게 되며 원하는 경우 TMR을 복구하기 위해 휴지통으로 이동됩니다.
  
**이 기능에 필요한 SKU는 무엇인가요?**
  
모든 SKU에서 기본적으로 이 기능을 지원합니다. A1 사용자는 기본적으로 30일의 만료 기간이 설정됩니다.
  
**파일 만료가 감사된 이벤트이고 내 감사 로그에서 확인할 수 있나요?**
  
예, 파일 만료는 감사 로그에 시스템 삭제 이벤트로 표시됩니다.
  
**관리자가 TMR의 수명 주기를 완전히 제어하도록 하고 최종 사용자에게 만료 날짜를 무시할 수 있는 기능을 제공하지 않으려면 어떻게 해야 하나요?**
  
E5 규정 준수 SKU의 일부로 제공되는 S+C 보관 및/또는 삭제 정책을 사용하는 것이 좋습니다. 이 제품은 복잡한 정책 및 SLA 중심의 행정적 법적 문제를 해결하기 위한 것입니다.

이 기능은 Cold TMR에서 생성된 저장소 낮은 우선 순위 메일을 줄이기 위한 간단한 메커니즘으로만 의미됩니다.
  
**파일은 언제 삭제되나요?**
  
파일은 만료 날짜로부터 5일 이내에 삭제되지만 엄격히 보장되지는 않습니다.
  
**이 기능이 출시된 후 기본 스트림에서 마이그레이션된 향후 TMR에도 자동 만료가 적용되나요?**
  
아니오, 마이그레이션된 TMR에는 그에 대해 설정된 만기 날짜가 함께 제공되지 않습니다. 대신 관리자가 보유하려는 TMR만 마이그레이션하도록 권장합니다. 자세한 내용은 마이그레이션 문서에서 제공됩니다.
  
## <a name="manage-meeting-recordings"></a>모임 녹음/녹화 관리

모임 녹음/녹화는 비즈니스용 OneDrive 및 SharePoint Online에 비디오 파일로 저장되며 해당 플랫폼에서 사용할 수 있는 관리 및 거버넌스 옵션을 따릅니다. 자세한 내용은 [SharePoint Online 거버넌스 개요](/sharepoint/governance-overview), [엔터프라이즈용 비즈니스용 OneDrive 가이드](/onedrive/plan-onedrive-enterprise) 또는 [중소기업용 비즈니스용 OneDrive 가이드](/onedrive/one-drive-quickstart-small-business)를 참조하세요.

비 채널 모임의 경우, 녹음/녹화는 레코더의 비즈니스용 OneDrive 저장되므로 직원이 퇴사한 후 소유권 및 보존에 대한 처리는 일반적인 [비즈니스용 OneDrive 및 SharePoint Online 프로세스](/onedrive/retention-and-deletion#the-onedrive-deletion-process)를 따릅니다.

## <a name="closed-captions-for-recordings"></a>녹음/녹화를 위한 선택 자막

Teams 모임 녹음/녹화에 대한 선택 자막은 사용자가 녹음/녹화 시 필사 기능을 켠 경우에만 재생 중에 사용할 수 있습니다. 관리자는 사용자가 필사 기능을 사용하여 모임을 녹음/녹화할 수 있도록 [정책을 통해 녹음/녹화 필사를 켜야](#turn-on-or-turn-off-recording-transcription) 합니다.

캡션은 모든 기능을 갖춘 뷰어를 위한 포괄적인 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 모임 기록의 캡션을 숨길 수 있습니다. 단, 모임 스크립트를 삭제하지 않으면 Teams에서 계속 사용할 수 있습니다.

오늘 녹화 비디오 파일의 선택 자막은 Teams 모임 대본에 연결됩니다. 이 링크는 대부분의 경우 파일의 수명 동안 유지되지만, 비디오 파일이 동일한 비즈니스용 OneDrive 또는 SharePoint Online 사이트 내에서 복사되면 끊어질 수 있으며, 이로 인해 복사된 비디오 파일에서 캡션을 사용할 수 없게 됩니다.

Teams의 대본과 녹음/녹화 간의 링크에 대한 향후 변경 사항은 여기와 메시지 센터 알림에서 명확히 설명됩니다. 나중에 변경하면 60일이 안 된 녹음/녹화 파일에 모임의 대본이 캡션으로 표시됩니다.

> [!NOTE]
> GCC에서는 모임 기록을 아직 사용할 수 없습니다.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>모임 녹음/녹화에 대한 eDiscovery 및 규정 준수

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

## <a name="meeting-recording-diagnostic-tools"></a>모임 레코딩 진단 도구
  ### <a name="user-cannot-record-meetings"></a>사용자가 모임을 녹음/녹화할 수 없음

관리자인 경우 다음 진단 도구를 사용하여 사용자가 Teams에서 모임을 녹음/녹화하도록 올바르게 구성되어 있는지 확인할 수 있습니다.

1. 아래의 **테스트 실행** 을 선택하면 Microsoft 365 관리 센터에서 진단이 채워집니다. 

   > [!div class="nextstepaction"]
   > [실행 테스트: 모임 레코딩](https://aka.ms/MeetingRecordingDiag)

2. 진단 실행 창에서 **사용자 이름 또는 이메일** 필드에 모임을 녹음/녹화할 수 없는 사용자의 이메일을 입력한 다음 **테스트 실행** 을 선택합니다.

3. 테스트는 테넌트 또는 정책 구성을 처리하는 최상의 다음 단계를 반환하여 사용자가 Teams에서 모임을 녹음/녹화하도록 올바르게 구성되어 있는지 확인합니다.
  
  ### <a name="meeting-record-is-missing"></a>모임 레코드가 없습니다.

관리자인 경우 다음 진단 도구를 사용하여 모임 녹음/녹화가 성공적으로 완료되었으며 모임 ID 및 녹음/녹화 시작 시간에 따라 Stream 또는 OneDrive에 업로드되었는지 확인할 수 있습니다.

1. 아래의 **테스트 실행** 을 선택하면 Microsoft 365 관리 센터에서 진단이 채워집니다. 

   > [!div class="nextstepaction"]
   > [실행 테스트: 모임 레코딩 누락](https://aka.ms/MissingRecordingDiag)

2. 진단 실행 창에서 **녹음/녹화된 모임 URL** 필드(일반적으로 모임 초대에 있음)에 URL을 입력하고 **모임이 언제 녹음/녹화되었습니까?에도 모임 날짜를 입력합니다. ** 필드를 선택한 다음 **테스트 실행** 을 선택합니다.

3. 테스트는 모임 녹음/녹화가 성공적으로 완료되었으며 Stream 또는 OneDrive에 업로드되었는지 확인합니다.

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
