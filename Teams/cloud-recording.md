---
title: Teams 클라우드 모임 녹음/녹화
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
- highpri
ms.reviewer: nakulm
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Teams 모임 및 그룹 통화를 녹음하여 오디오, 비디오 및 화면 공유 활동을 캡처하는 Teams 내 클라우드 음성 기능을 배치하기 위한 실제 지침입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 281a8997e3020b229ce8b34919177c1f6f2318c9
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2022
ms.locfileid: "68965750"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화

Microsoft Teams에서 사용자는 Teams 모임 및 그룹 통화를 녹음/녹화하여 오디오, 비디오 및 화면 공유 활동을 캡처할 수 있습니다. 사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검토할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 제공됩니다. 녹음/녹화는 클라우드에서 발생하고 OneDrive와 SharePoint에 저장되므로 조직 전체에서 안전하게 공유할 수 있습니다.

모임이 기록되면 자동으로 다음이 수행됩니다.

- OneDrive 또는 SharePoint에 업로드됨
- 모임에 초대된 사용자에게 사용 권한이 부여됨
- 모임에 대한 채팅에 연결됨
- Teams 일정에서 모임에 대한 녹음/녹화 및 기록 탭에 표시됨
- Microsoft 365 전반에 다양한 파일 목록(나와 공유됨, office.com, 권장, 최근에 사용한 항목 등)이 추가됨
- Microsoft 365 Search에 대해 인덱싱됨

관련: [Teams 모임 녹음/녹화 최종 사용자 문서](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> 모임 녹음/녹화에 Microsoft Stream(클래식) 대신 OneDrive 및 SharePoint를 사용하는 변경 내용은 2021년 8월에 자동으로 적용됩니다. 자세한 내용은 [모임 녹음/녹화에 OneDrive와 SharePoint 또는 Stream 사용](tmr-meeting-recording-change.md)을 참조하세요.

> [!NOTE]
> Teams 모임의 역할 사용 및 사용자 역할 변경 방법에 대한 자세한 내용은 [Teams 모임의 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)을 참조하세요. 실시간 이벤트 기록 옵션은 [Teams의 실시간 이벤트 기록 정책](teams-live-events/live-events-recording-policies.md)을 참조하세요.

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화 필수 구성 요소

Teams 사용자의 모임을 녹음/녹화하려면 테넌트의 OneDrive와 SharePoint를 사용하도록 설정해야 합니다. 또한 모임 이끌이 및 녹음/녹화를 시작하는 사용자 모두는 다음과 같은 필수 조건을 충족해야 합니다.

- 비 채널 모임 녹음/녹화를 저장할 수 있도록 사용자에게 충분한 OneDrive 저장 공간이 있어야 합니다.

- 모임 녹음/녹화를 저장할 수 있도록 Teams 채널에 충분한 SharePoint 저장 공간이 있어야 합니다.

- 사용자가 모임 및 그룹 통화를 녹음/녹화하기 위해 `CsTeamsMeetingPolicy -AllowCloudRecording` 설정을 true로 설정했습니다.

- 사용자가 1:1 통화를 기록하기 위해 `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` 설정을 true로 설정했습니다.

- 사용자가 모임에서 익명, 게스트 또는 페더레이션 사용자가 아닙니다.

- 사용자 모임에 대한 기록을 사용 가능으로 설정하려면, 할당된 Teams 모임 정책에 `-AllowTranscription` 설정이 true로 설정되어 있어야 합니다.

- 채널 구성원이 녹음/녹화를 편집하거나 다운로드할 수 없도록 채널 모임 녹음/녹화를 저장하려면 `CSTeamsMeetingPolicy -ChannelRecordingDownload` 설정을 차단으로 설정해야 합니다.

> [!IMPORTANT]
>
> 사용자가 녹음/녹화만 기록하고 다운로드하도록 설정하려면 OneDrive 또는 SharePoint를 사용하도록 설정할 필요가 없습니다. 이렇게 하면 녹음/녹화를 OneDrive나 SharePoint에 저장하는 대신 삭제하기 전까지 21일이라는 제한된 시간 동안 임시 Teams 저장소에 저장합니다. 관리자가 현재 제어, 관리 또는 삭제할 수 있는 것은 아닙니다.
>
> [임시 모임 녹음/녹화 저장소가 작동하는 방식에 대한 자세한 내용](#temp-storage)은 아래를 참조하세요.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>조직의 사용자를 위해 Teams 클라우드 모임 녹음/녹화 설정

이 섹션에서는 [Teams 모임 정책](policy-assignment-overview.md)을 통해 Teams 모임 녹음/녹화를 설정하고 계획하는 방법을 설명합니다.

### <a name="turn-on-or-turn-off-cloud-recording"></a>클라우드 녹음/녹화 설정 또는 해제

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자 모임을 녹음/녹화할 수 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **클라우드 녹음/녹화** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오의 모임 정책 설정](meetings-policies-recording-and-transcription.md#cloud-recording)을 참조하세요.

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
> [!NOTE]
> Teams 정책 기반 규정 준수 녹음/녹화를 사용하도록 설정된 외부 테넌트에서 Teams 사용자가 테넌트에서 모임 또는 통화에 참가하는 경우 테넌트에서 설정된 클라우드 기반 녹음/해제와 관계없이 규정 준수를 위해 해당 모임/통화가 다른 테넌트에서 기록됩니다. 다른 테넌트에서 사용자가 녹음/녹화를 캡처하지 않아야 하는 경우 테넌트에서 모임의 일부인 발표자는 모임에서 사용자를 제거하는 것이 좋습니다. Teams의 정책 기반 규정 준수 기록에 대한 자세한 내용은 [& 모임을 호출하기 위한 Teams 정책 기반 녹음/녹화 소개를 참조하세요](teams-recording-policy.md).

### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>채널 모임 녹음/녹화의 다운로드 차단 또는 허용

이 설정은 채널 모임이 채널의 "녹음/녹화" 폴더 또는 "녹음/녹화\보기 전용" 폴더에 저장되는지 여부를 제어합니다. 설정은 채널 모임에 대한 레코드를 선택하는 사용자의 정책에 적용됩니다.

이 설정의 두 값은 다음과 같습니다.

- **허용**(기본값) - 채널의 "녹음/ 녹화" 폴더에 채널 모임 녹음/녹화를 저장합니다. 녹음/녹화 파일에 대한 사용 권한은 채널 SharePoint 사용 권한을 기반으로 합니다. 이는 채널에 대해 업로드된 다른 파일과 동일합니다.

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

이 설정은 모임 녹음/녹화 재생 중에 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 녹음/녹화를 시작한 사람은 이러한 기능이 레코딩에서 작동하려면 이 설정을 켜야 합니다.
  
이 설정을 켜면 모임 기록에서 **검색**, **참조** 및 **대본** 을 사용하는 모임 기록과 함께 저장된 대본의 사본이 생성됩니다.

> [!NOTE]
> 녹음/녹화된 모임에 대한 기록은 현재 영어(미국), 영어(캐나다), 영어(인도), 영어(영국), 영어(오스트레일리아), 영어(뉴질랜드), 아랍어(아랍에미리트), 아랍어(사우디아라비아), 중국어(간체, 중국) 중국어(번체, 중국), 중국어(번체, 홍콩 특별 행정구), 중국어(번체, 대만), 체코어(체코), 덴마크어(덴마크), 네덜란드어(벨기에), 네덜란드어(네덜란드), 프랑스어(캐나다), 프랑스어(프랑스), 핀란드어(핀란드), 독일어(독일), 그리스어(그리스), 히브리어(이스라엘), 힌디어(인도), 헝가리어(헝가리), 이탈리아어(이탈리아), 일본어(일본), 한국어(한국), 노르웨이어(노르웨이), 폴란드어(폴란드), 포르투갈어(브라질), 포르투갈어(포르투갈), 루마니아어(루마니아), 러시아어(러시아), 슬로바키아어(슬로바키아), 스페인어(멕시코), 스페인어(스페인), 스웨덴어(스웨덴), 태국어(태국), 터키어(터키), 우크라이나어(베트남), 베트남어(베트남)으로만 지원됩니다. OneDrive와 SharePoint 클라우드 저장소에 모임 녹음/녹화와 함께 저장됩니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 녹음/녹화 개시자에게 모임 녹음/녹화를 기록할 수 있는 선택권이 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **기록 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오의 모임 정책 설정](meetings-policies-recording-and-transcription.md#transcription)을 참조하세요.

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

|시나리오|단계 |
|---|---|
|모임 녹음/녹화를 시작할 때 회사의 모든 사용자가 기록할 수 있게 하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = True가 있는지 확인합니다. <li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. </ol>|
|대부분의 사용자가 모임 녹음/녹화를 기록할 수 있게하고 기록을 허용하지 않는 특정 사용자를 선택적으로 해제하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = True가 있는지 확인합니다. <li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. <li>다른 모든 사용자에게 AllowTranscription = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|녹음/녹화에 대한 기록을 100% 사용하지 않도록 설정하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = False가 있는지 확인합니다. <li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|대부분의 사용자에게 기록을 사용하지 않도록 설정하고 선택적으로 특정 사용자에게 기록을 사용하도록 설정하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인합니다. <li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. <li>다른 모든 사용자에게 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|

### <a name="terms-of-use-acceptance"></a>사용 약관 동의

조직에서 모임을 녹음/녹화하기 전에 사용자가 동의하도록 하는 모임 녹음/녹화 정책이 있는 경우, [Azure Active Directory 사용 약관](/azure/active-directory/conditional-access/terms-of-use) 기능을 사용하세요. 이 기능을 사용하면 Microsoft Teams에 액세스하기 전에 조직의 사용자 정책에 동의할 수 있습니다. 이 기능은 녹음/녹화 단추를 클릭하는 것과 관련이 없지만 Teams나 기타 Microsoft 365 앱을 전체적으로 사용하는 것과 관련이 있습니다. Teams나 Microsoft 365 사용에 대한 전반적인 이용 약관에 회의 기록 정보를 추가하는 것이 좋습니다.

### <a name="set-a-custom-privacy-policy-url"></a>사용자 지정 개인 정보 보호 정책 URL 설정

관리자는 조직에 대한 사용자 지정 링크를 사용하여 Teams 녹음 및 전사 개인 정보 보호 정책 URL을 업데이트할 수 있습니다. 다음 단계에 따라 [Azure AD 관리 센터](https://aad.portal.azure.com)에서 이 작업을 수행할 수 있습니다.

1. Azure AD 관리 센터에 로그인합니다.
1. **Azure Active Directory** > **속성** 으로 이동합니다.
1. 개인 정보 취급 방침 링크로 **개인정보처리방침 URL** 필드를 업데이트합니다.

> [!NOTE]
> 조직에 대해 이 필드를 이미 업데이트한 경우 변경할 필요가 없습니다.

개인 정보 취급 방침 URL을 추가하면 기본 Teams 모임 녹음/녹화 및 전사 개인정보처리방침이 조직에서 제공한 새 URL로 바뀝니다.

> [!NOTE]
> 조직에서 호스팅하는 Teams 모임에 참가하는 익명, 게스트 및 페더레이션 사용자에게는 여전히 기본 Teams 모임 녹음/녹화 및 전사 개인 정보 보호 정책이 적용됩니다.

## <a name="permissions-and-storage"></a>사용 권한 및 저장소

모임 녹음/녹화는 OneDrive와 SharePoint 클라우드 저장소에 저장됩니다. 위치 및 사용 권한은 모임 유형과 모임에서 사용자의 역할에 따라 달라집니다. 녹화에 적용되는 기본 사용 권한은 아래에 나열되어 있습니다. 비디오 녹화 파일에 대한 전체 편집 권한이 있는 사용자는 사용 권한을 변경하고 필요에 따라 나중에 다른 사용자와 공유할 수 있습니다.

### <a name="non-channel-meetings"></a>비 채널 모임

- 녹음/녹화는 녹음/녹화를 클릭한 사용자의 OneDrive에 있는 **녹음/녹화** 폴더에 저장됩니다. 

  예: *레코더의 OneDrive*/**녹음/녹화**

- 외부 참가자를 제외하고 모임에 초대된 사용자에게는 다운로드는 할 수 없는 보기 전용 액세스 권한이 있는 녹음/녹화 파일에 대한 사용 권한이 자동으로 부여됩니다.

- 모임 소유자와 레코드를 클릭한 사람은 사용 권한을 변경하고 다른 사용자와 공유할 수 있는 모든 편집 권한을 얻습니다.

### <a name="channel-meetings"></a>채널 모임

`Set-CsTeamsMeetingPolicy -ChannelRecordingDownload`이(가) 허용(기본값)으로 설정된 경우:

- 녹음/녹화는 **녹음/녹화** 폴더의 Teams 사이트 설명서 라이브러리에 저장됩니다.

  예: *Teams 이름 - 채널 이름*/**문서**/**녹음/녹화**

- 레코드를 클릭한 멤버에게 녹음/녹화에 대한 편집 권한이 있습니다.

- 다른 모든 구성원의 권한은 채널 SharePoint 권한을 기반으로 합니다.

`Set-CsTeamsMeetingPolicy -ChannelRecordingDownload`이(가) 차단으로 설정된 경우:

- 녹음/녹화는 **녹음/녹화/보기 전용** 폴더의 Teams 사이트 설명서 라이브러리에 저장됩니다. 

  예: *Teams 이름 - 채널 이름*/**문서/녹음/보기 전용**

- 채널 소유자는 이 폴더의 녹음/녹화에 대한 전체 편집 및 다운로드 권한을 갖습니다.

- 채널 멤버는 다운로드할 수 없는 보기 전용 액세스 권한을 갖게 됩니다.

특정 모임 유형에 대한 자세한 내용은 다음 표를 참조하세요.

| 모임 유형  | 누가 레코드를 클릭했나요?| 녹음은 어디에 있나요? | 액세스 가능한 사용자 R/W, R 또는 공유  |
|-------------|-----------------------|------------------------|------------------------|
|내부 파티와의 1:1 통화             |발신자                 |발신자의 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다. <br /><br />수신자(동일한 테넌트에 있는 경우)는 읽기 전용 액세스 권한이 있습니다. 공유 액세스 권한이 없습니다. <br /><br /> 수신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|내부 파티와의 1:1 통화             |수신자                 |수신자의 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다. <br /><br />호출자(동일한 테넌트에 있으며 읽기 전용 액세스 권한이 있는 경우) 공유 액세스 권한이 없습니다. <br /><br />발신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
|외부 통화로 1:1 통화             |발신자                 |발신자의 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다.<br /> <br />수신자에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|외부 통화로 1:1 통화             |수신자                 |수신자의 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다.<br /><br />발신자에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
|그룹 통화                                 |통화의 모든 구성원 |녹음/녹화의 OneDrive 계정을 클릭한 그룹 구성원  |레코드를 클릭한 구성원은 모든 권한이 있습니다. <br /><br /> 동일한 테넌트에 있는 다른 멤버는 읽기 권한을 갖습니다. <br /><br /> 다른 테넌트에 있는 다른 그룹 구성원은 이 그룹에 대한 권한이 없습니다.|
|임시/예약된 모임                    |이끌이              |모임 이끌이의 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 가집니다. <br /><br /> 모임의 다른 모든 구성원은 다운로드할 수 없는 읽기 권한이 있습니다.|
|임시/예약된 모임                    |다른 모임 구성원   |레코드를 클릭한 모임 구성원                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. <br /><br />이끌이는 편집 권한이 있으며 공유할 수 있습니다.<br /><br /> 다른 모든 모임 구성원은 다운로드할 수 없는 읽기 권한이 있습니다.|
|외부 참가자와 임시/예약된 모임|이끌이              |모임 이끌이의 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 가집니다.<br /> <br /> 이끌이와 동일한 테넌트에 있는 모임의 다른 모든 구성원은 다운로드할 수 없는 읽기 권한을 갖습니다. <br /><br /> 다른 모든 외부 구성원은 액세스 권한이 없으며, 이끌이는 해당 구성원과 공유해야 합니다.|
|외부 참가자와 임시/예약된 모임|다른 모임 구성원   |레코드를 클릭한 구성원                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. 이끌이는 편집 권한이 있으며 공유할 수 있습니다. <br /><br /> 이끌이와 동일한 테넌트에 있는 모임의 다른 모든 구성원은 다운로드할 수 없는 읽기 권한을 갖습니다. <br /><br />다른 모든 외부 구성원은 액세스 권한이 없으며, 이끌이는 해당 구성원과 공유해야 합니다.|
|채널 모임                            |채널 구성원         |해당 채널에 대한 Teams의 SharePoint 위치                   |Set-CsTeamsMeetingPolicy -ChannelRecordingDownload가 허용(기본값)으로 설정된 경우, 레코드를 클릭한 구성원은 녹음/녹화에 대한 편집 권한을 가집니다. 다른 모든 구성원의 권한은 채널 SharePoint 권한을 기반으로 합니다.<Br><Br>Set-CsTeamsMeetingPolicy -ChannelRecordingDownload가 차단으로 설정된 경우, 채널 소유자는 녹음/녹화에 대한 모든 권한이 있지만 채널 멤버는 다운로드할 수 없는 읽기 권한을 갖습니다.|

<a name="temp-storage"></a>

### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>OneDrive와 SharePoint에 업로드할 수 없는 경우 임시 저장소

모임 녹음/녹화를 OneDrive와 SharePoint에 업로드할 수 없는 경우, 삭제되기 전에 21일 동안 Teams에서 일시적으로 다운로드할 수 있습니다. 이는 이 시점에서 관리자가 삭제하는 기능을 포함하도록 제어하거나 관리할 수 있는 것이 아닙니다.

모임 녹음/녹화는 다음과 같은 이유로 이 임시 저장소에 저장될 수 있습니다.

- 비 채널 모임에서 녹음/녹화 중인 사용자에게 OneDrive가 없거나 OneDrive가 저장소 할당량에 도달한 경우
- 채널 모임에서 SharePoint 사이트가 저장소 할당량에 도달했거나 사이트가 아직 프로비전되지 않은 경우
- 특정 OneDrive와 SharePoint 정책을 사용하도록 설정하면 특정 IP 범위 등에 없는 경우 사용자가 파일을 업로드하지 못하도록 제한할 수 있습니다.

이에 대한 녹음/녹화 보존은 임시 스토리지이며 채팅 메시지 자체의 영향을 받습니다. 따라서 녹음/녹화에 대한 원래 채팅 메시지를 삭제하면 사용자가 녹음/녹화에 액세스할 수 없게 됩니다. 다음과 같은 두 가지 시나리오가 있습니다.

- **사용자가 채팅 메시지를 수동으로 삭제합니다** - 이 시나리오에서는 원본 메시지가 사라지면 사용자는 더 이상 녹음/녹화에 액세스할 수 없으며 더 이상 다운로드할 수 없습니다. 그러나 녹음/녹화 자체는 Microsoft의 내부 시스템 내에서 원래 21일을 초과하지 않는 기간 동안 계속 유지될 수 있습니다.

- **채팅 메시지 녹음/녹화가 채팅 보존 정책에 의해 삭제됩니다** - 임시 저장소 녹음/녹화는 채팅 보존 정책과 직접적인 관련이 있습니다. 따라서 Teams 임시 저장소에 있는 녹음/녹화는 삭제되기 전에 기본적으로 21일 동안 유지되지만, 21일 전에 채팅 메시지가 삭제되면 채팅 메시지 보존 정책으로 인해 해당 녹음/녹화도 삭제됩니다. 이 경우 녹음/녹화를 복구할 방법이 없습니다.

### <a name="planning-for-storage"></a>저장소 계획

1시간 녹음/녹화 크기는 400MB입니다. 녹음/녹화된 파일에 필요한 용량을 이해하고 OneDrive와 SharePoint에 사용 가능한 저장소가 충분한지 확인합니다.  구독에 포함된 기본 저장소 및 추가 저장소를 구입하는 방법을 이해하려면 [OneDrive의 기본 저장 공간 설정](/onedrive/set-default-storage-space) 및 [SharePoint 사이트 저장소 제한 관리](/sharepoint/manage-site-collection-storage-limits)를 읽어 보세요.
  
## <a name="manage-meeting-recordings"></a>모임 녹음/녹화 관리

모임 녹음/녹화는 OneDrive와 SharePoint에 비디오 파일로 저장되며 해당 플랫폼에서 사용할 수 있는 관리 및 거버넌스 옵션을 따릅니다. 자세한 내용은 [SharePoint 거버넌스 개요](/sharepoint/governance-overview)를 참조하세요.

비 채널 모임의 경우 녹음/녹화는 레코더의 OneDrive에 저장되므로 직원이 퇴사한 후 소유권 및 보존을 처리하는 작업은 일반적인 [OneDrive와 SharePoint 프로세스](/onedrive/retention-and-deletion#the-onedrive-deletion-process)를 따릅니다.

모임 녹음/녹화의 기본 만료 시간은 120일입니다. 모임이 자동으로 만료되는 설정을 해제하거나 기본 만료 시간을 변경할 수 있습니다. [모임 녹음/녹화가 자동으로 만료되는 방법에](meetings-policies-recording-and-transcription.md#meetings-automatically-expire) 대해 자세히 알아봅니다.

## <a name="closed-captions-for-recordings"></a>녹음/녹화를 위한 선택 자막

Teams 모임 녹음/녹화에 대한 선택 자막은 사용자가 녹음/녹화 시 필사 기능을 켠 경우에만 재생 중에 사용할 수 있습니다. 관리자는 사용자가 필사 기능을 사용하여 모임을 녹음/녹화할 수 있도록 [정책을 통해 녹음/녹화 필사를 켜야](#turn-on-or-turn-off-recording-transcription) 합니다.

Captions help create inclusive content for viewers of all abilities. As an owner, you can hide captions on the meeting recording, although the meeting transcript will still be available on Teams unless you delete it there.

오늘 녹화 비디오 파일의 선택 자막은 Teams 모임 대본에 연결됩니다. 이 연결은 대부분 파일의 수명 동안 유지되지만 동일한 OneDrive 또는 SharePoint 사이트 내에서 비디오 파일을 복사하면 끊어질 수 있으며, 이 경우 복사된 비디오 파일에서 자막을 사용할 수 없게 됩니다.

Teams의 대본과 녹음/녹화 간의 링크에 대한 향후 변경 사항은 여기와 메시지 센터 알림에서 명확히 설명됩니다. 나중에 변경하면 60일이 안 된 녹음/녹화 파일에 모임의 대본이 캡션으로 표시됩니다.

> [!NOTE]
> GCC에서는 모임 기록을 아직 사용할 수 없습니다.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>모임 녹음/녹화에 대한 eDiscovery 및 규정 준수

### <a name="ediscovery"></a>eDiscovery

모임 녹음/녹화는 OneDrive와 SharePoint에 저장되며, 이는 Microsoft 365와 Office 365 D 계층을 준수합니다. 모임 또는 통화 녹음/녹화에 관심이 있는 규정 준수 관리자에 대한 e-Discovery 요청을 지원하기 위해, Microsoft Teams의 준수 콘텐츠 검색 기능에서는 녹음/녹화 완료 메시지를 제공합니다. 준수 관리자는 준수 콘텐츠 검색 미리 보기에서 항목의 제목 줄에서 “녹음/녹화” 키워드를 찾을 수 있으며 조직에서 모임 및 통화 녹음/녹화를 검색할 수 있습니다.

또한 eDiscovery를 통해 SharePoint 및 OneDrive에서 파일을 검색하여 모임 녹음/녹화 비디오 파일을 찾을 수도 있습니다.

eDiscovery에 대한 자세한 내용은 [Microsoft 365용 eDiscovery 솔루션](/microsoft-365/compliance/ediscovery) 문서를 참조하세요.

### <a name="retention-policies"></a>보존 정책

ProgID 속성을 통해 Teams 모임 녹음/녹화 비디오 파일만 대상으로 지정하도록 자동 보존 레이블을 적용할 수 있습니다. 자세한 내용은 [Teams 모임 녹음/녹화에 대한 보존 레이블을 자동으로 적용하는 방법](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings)을 참조하세요.

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Microsoft Purview DLP(데이터 손실 방지) 정책

ProgID 속성별로 모임 녹음/녹화 파일에 DLP 정책을 적용할 수도 있습니다. SharePoint와 OneDrive 파일에 대한 DLP 규칙에서 조건을 다음으로 설정합니다.

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

2. 진단 실행 창에서 **기록된 모임의 URL** (일반적으로 모임 초대에 있음)의 URL과 모임이 **기록된** 시기 필드에 모임 날짜를 입력한 다음 **, 테스트 실행을** 선택합니다.

3. 테스트는 모임 녹음/녹화가 성공적으로 완료되었으며 Stream 또는 OneDrive에 업로드되었는지 확인합니다.

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
