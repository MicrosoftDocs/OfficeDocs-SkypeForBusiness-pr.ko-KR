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
ms.openlocfilehash: e5c23c362d9d425c163a46dde93c6daa3c593a92
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617780"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화

Microsoft Teams에서 사용자는 Teams 모임 및 그룹 통화를 녹음/녹화하여 오디오, 비디오 및 화면 공유 활동을 캡처할 수 있습니다. 사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검색할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 있습니다. 녹음/녹화는 클라우드에서 이루어지며 [Microsoft Stream](/stream/)에 저장되므로 사용자는 조직 전체에서 녹음/녹화를 안전하게 공유할 수 있습니다.

관련: [Teams 모임 녹음/녹화 최종 사용자 문서](https://aka.ms/recordmeeting)

>[!Note]
> Microsoft Stream에서 모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint로의 변경은 단계별로 접근합니다. 각 작업 단계의 자세한 정보는 [모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용](tmr-meeting-recording-change.md)을 참조하세요.

> [!NOTE]
> Teams 모임의 역할 사용 및 사용자 역할 변경 방법에 대한 자세한 내용은 [Teams 모임의 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조하세요. 실시간 이벤트 기록 옵션은 [Teams의 실시간 이벤트 기록 정책](teams-live-events/live-events-recording-policies.md)을 참조하세요.

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화 필수 구성 요소

Teams 사용자 모임을 녹음/녹화하려면 Microsoft Stream이 테넌트에 대해 활성화되어 있어야 합니다. 또한 다음과 같이 모임 이끌이 및 녹음/녹화를 시작하는 사용자 모두에게 필요한 필수 구성 요소가 있습니다.

- 사용자는 Office 365 E1, E3, E5, A1, A3, A5, Microsoft 365 Business Premium, Business Standard 또는 Business Basic <sup>1</sup>을 가지고 있습니다.
- 관리자가 설정한 경우 사용자는 회사 지침을 동의합니다.
- 사용자는 Microsoft Stream의 저장 공간이 충분하여 녹음/녹화를 저장할 수 있습니다.
- 사용자는 CsTeamsMeetingPolicy - AllowCloudRecording 설정을 true로 설정하여 모임 및 그룹 통화를 기록합니다.
- 사용자는 CsTeamsCallingPolicy - AllowCloudRecordingForCalls 설정을 true로 설정하여 1:1 통화를 기록합니다.
- 사용자는 모임에서 익명, 게스트 또는 페더레이션 사용자가 아닙니다.
- 사용자 모임에 대한 기록을 사용 가능으로 설정하려면, 할당된 Teams 모임 정책에 AllowTranscription 설정이 true로 설정되어 있어야 합니다.

<sup>1</sup> 2020년 8월 20일자로 모임 기록 파일에 대한 접근은 A1 사용자의 경우 21일 후에 만료됩니다. 자세한 내용은 [Microsoft Teams 모임 녹음/녹화를 스트림에 업로드](/stream/portal-upload-teams-meeting-recording)를 참조하세요.

> [!IMPORTANT] 
>
> 사용자가 녹음/녹화 및 녹음/녹화의 다운로드만 하도록 하려면 사용자에게 Microsoft Stream 라이선스를 할당할 필요가 없습니다. 이 경우 녹음/녹화는 Microsoft Stream에 저장되지는 않지만, 삭제되기까지 21일의 제한이 있는 Teams AMS(Azure Media Services)에 저장됩니다. 이는 이 시점에 관리자가 삭제하는 기능을 포함하여 컨트롤하거나 관리할 수 있는 사항이 아닙니다.
>
> 또한 AMS에 있는 녹음/녹화의 경우 녹음/녹화 보존은 채팅 메시지 자체의 영향을 받습니다. 따라서 원래 AMS 녹음/녹화 채팅 메시지를 삭제하면 사용자가 녹음/녹화에 액세스할 수 없게 됩니다. 다음과 같은 두 가지 시나리오가 있습니다.
> 
> - 사용자가 채팅 메시지를 수동으로 삭제
> 
>   이 시나리오에서는 원본 메시지가 사라지면 사용자는 더 이상 녹음/녹화에 액세스할 수 없으며 더 이상 다운로드할 수 없습니다. 그러나 녹음/녹화 자체는 Microsoft의 내부 시스템 내에서 원래 21일을 초과하지 않는 기간 동안 계속 유지될 수 있습니다.
> 
> - 채팅 보존 정책에 의해 채팅 메시지 녹음/녹화가 삭제됩니다.
> 
>   AMS 녹음/녹화는 채팅 보존 정책과 직접 연결됩니다. 따라서 AMS에 대한 녹음/녹화는 삭제되기 전에 기본적으로 21일 동안 유지되지만, 채팅 메시지 보존 정책으로 인해 21일 전에 채팅 메시지가 삭제되면 해당 녹음/녹화도 삭제됩니다. 이 경우 녹음/녹화를 복구할 방법이 없습니다.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>조직의 사용자를 위해 Teams 클라우드 모임 녹음/녹화 설정

해당 섹션에서는 Tema 모임 녹음/녹화를 설정하고 계획하는 방법을 설명합니다.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>조직의 사용자에 대한 Microsoft Stream 사용

Microsoft Stream은 적격 Microsoft 365 및 Office 365 구독 또는 독립 실행형 서비스의 일부로 사용할 수 있습니다.  자세한 내용은 [Stream 라이선싱 개요](/stream/license-overview)를 참조하세요.  Microsoft Stream은 현재 Microsoft 365 Business, Microsoft 365 Business Standard 및 Microsoft 365 Business Basic에 포함되어 있습니다.

사용자가 Microsoft Stream에 액세스할 수 있도록 [Microsoft 365 또는 Office 365에서 사용자에게 라이선스를 할당](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)하는 방법에 대해 자세히 알아보세요. Microsoft Stream에 대한 등록 차단에 정의된 대로 [Microsoft Stream이 사용자에 대해 차단되지 않았는지](/stream/disable-user-organization) 확인합니다.

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>사용자가 Microsoft Stream에서 비디오 업로드 권한을 보유하고 있는지 확인

기본적으로 Stream이 사용 가능하고 라이선스가 사용자에게 할당되면 회사의 모든 사용자가 Stream에서 콘텐츠를 만들 수 있습니다. Microsoft Stream 관리자는 Stream에서 [콘텐츠를 만들기 위해 직원을 제한](https://docs.microsoft.com/stream/restrict-uploaders)할 수 있습니다. 이 제한된 목록에 있는 사용자는 여전히 모임을 기록할 수 있지만, 사용자의 녹음/녹화는 Stream으로 전송되지 않습니다. 대신 이 녹음/녹화 파일은 AMS에 21일 동안 임시로 저장됩니다. 이 기간 동안 녹음/녹화는 해당 21일 후에 삭제되기 전에 다운로드해야 합니다.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>직원에게 Microsoft Stream의 회사 지침에 대한 동의를 공지하세요.

Microsoft Stream 관리자가 [회사 지침 정책을 설정](/stream/company-policy-and-consent)했고 직원들이 콘텐츠를 저장하기 전에 이 정책을 수락해야 하는 경우 사용자는 Microsoft Teams에서 녹음/녹화를 하기 전에 작업을 수행해야 합니다. 조직에서 녹음/녹화 기능을 배포하기 전에 사용자가 정책에 동의했는지 확인합니다.

### <a name="turn-on-or-turn-off-cloud-recording"></a>클라우드 녹음/녹화 설정 또는 해제

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자 모임을 녹음/녹화할 수 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **클라우드 녹음/녹화 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오 정책 설정 모임](meeting-policies-audio-and-video.md#allow-cloud-recording)을 참조하세요.

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
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```

</br>
</br>


|                                                                 시나리오                                                                 |                                                                                                                                                                         단계                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    회사의 모든 사용자가 모임을 녹음/녹화할 수 있게 하려고 합니다.                                    |                                                                     <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = True인지 확인<li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. </ol>                                                                     |
| 대부분의 사용자가 모임을 녹음/녹화할 수 있게하고 녹음/녹화를 허용하지 않는 특정 사용자를 선택적으로 해제하려고 합니다. |        <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = True인지 확인<li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다.<li>다른 모든 사용자에게 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다.</ol>         |
|                                                   녹음/녹화를 100% 사용하지 않도록 설정하려고 합니다.                                                   |                                                                <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인<li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다.                                                                 |
|      대부분의 사용자에게 녹음/녹화를 사용하지 않도록 설정하고 선택적으로 특정 사용자에게 녹음/녹화를 사용하도록 설정하려고 합니다.       | <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인<li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다.<li>다른 모든 사용자에게 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |

#### <a name="where-your-meeting-recordings-are-stored"></a>모임 녹음/녹화가 저장된 위치

모임 녹음/녹화는 Microsoft Stream 클라우드 저장소에 저장됩니다. Microsoft Stream이 데이터가 저장된 국내 데이터 보존 지역에서 제공되지 않는 경우 Teams 데이터가 국내에 저장된 고객을 위해 모임 녹음/녹화 기능이 현재 설정되어 있습니다. Microsoft Stream이 국내 데이터 보존 지역에서 제공되지 않는 경우 데이터가 국내에 저장된 고객을 위해 모임 녹음/녹화 기능이 향후 설정될 수 있습니다. 이 작업은 Microsoft Stream의 가장 가까운 지리적 영역에 녹화를 저장할 수 있도록 허용함으로써 수행할 수 있습니다. 

Teams 데이터가 국내에 저장되어 있고 모임 녹음/녹화를 국내에 저장하기를 선호하는 경우 기능을 해제하고 Microsoft Stream이 국내 데이터 보존 지역에 배포된 이후 설정하는 것이 좋습니다. 조직의 모든 사용자에 대해 기능을 해제하려면 Microsoft Teams 관리 센터에서 전역 Teams 모임 정책에서 **클라우드 녹음/녹화 허용** 설정을 해제합니다. 그러나 Microsoft Stream의 가장 가까운 지리적 영역에 녹음/녹화를 저장할 수 있도록 하려면 이 변경이 발생하기 전에 **클라우드 녹음/녹화 허용** 과 **외부 지역 녹음/녹화 저장 허용** 을 모두 켜야 합니다.

전역 정책에서 지역 내 녹음/녹화를 활성화하려면 다음 cmdlet을 사용하세요.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```

다음은 해당 변경 내용이 적용될 때 모임 녹음/녹화를 설정하는 경우의 결과에 대한 요약입니다.

|모임 녹음/녹화를 설정하는 경우...|모임 녹음/녹화는 저장됩니다... |
|---|---|
|Microsoft Stream이 국내 데이터 보존 지역에서 제공되기 이전 |가장 가까운 Microsoft Stream 지역|
|Microsoft Stream이 국내 데이터 보존 지역에서 제공된 이후 |사용자의 국내 데이터 보존 지역|

모임 녹음/녹화를 아직 설정하지 않은 신규 및 기존 테넌트의 경우 Microsoft Stream이 국내 데이터 보존 지역에서 제공된 이후 새 녹음/녹화는 국내에 저장됩니다. 그러나 Microsoft Stream이 국내 데이터 보존 지역에 제공되기 이전에 모임 녹음/녹화를 사용하는 모든 테넌트는 Microsoft Stream이 국내 데이터 보존 지역에 제공된 이후에도 기존 및 새 녹음/녹화에 대한 Microsoft Stream 저장소를 계속 사용할 수 있습니다.

Microsoft Stream 데이터가 저장된 지역을 찾으려면 Microsoft Stream에서 오른쪽 상단 모서리의 **?** 를 클릭하고 **Microsoft Stream 정보** 를 클릭한 다음 **사용자 데이터 저장 위치** 를 클릭합니다.  Microsoft Stream이 데이터를 저장하는 지역에 대한 자세한 내용은 [Microsoft Stream FAQ](/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)를 참조하세요.

Microsoft 365 또는 Office 365의 서비스에서 데이터가 저장되는 위치에 대한 자세한 내용은 [사용자 데이터 위치](https://products.office.com/where-is-your-data-located?rtc=1)를 참조하세요.

### <a name="turn-on-or-turn-off-recording-transcription"></a>녹음/녹화 기록 설정 또는 해제

이 설정은 모임 녹음/녹화 재생 중에 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 이 옵션을 해제하면 모임 녹음/녹화를 재생하는 동안 **검색** 및 **CC** 옵션을 사용할 수 없습니다. 녹음/녹화를 시작한 사용자는 녹음/녹화에 전사도 포함되도록 이 설정을 설정해야 합니다.

> [!NOTE]
> 녹음/녹화된 모임에 대한 문서 작성은 현재 Teams 언어를 영어로 설정한 사용자와 모임에서 영어가 사용되는 경우에만 지원됩니다. 모임 녹음/녹화와 함께 Microsoft Stream 클라우드 저장소에 저장됩니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 녹음/녹화 개시자에게 모임 녹음/녹화를 기록할 수 있는 선택권이 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **기록 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [오디오 및 비디오 정책 설정 모임](meeting-policies-audio-and-video.md#allow-transcription)을 참조하세요.

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
|모임 녹음/녹화를 시작할 때 회사의 모든 사용자가 기록할 수 있게 하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = True인지 확인 <li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. </ol>|
|대부분의 사용자가 모임 녹음/녹화를 기록할 수 있게하고 기록을 허용하지 않는 특정 사용자를 선택적으로 해제하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = True인지 확인 <li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = True인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. <li>다른 모든 사용자에게 AllowTranscription = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|녹음/녹화에 대한 기록을 100% 사용하지 않도록 설정하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowTranscription = False인지 확인 <li>모든 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowTranscription = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|대부분의 사용자에게 기록을 사용하지 않도록 설정하고 선택적으로 특정 사용자에게 기록을 사용하도록 설정하려고 합니다. |<ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인 <li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. <li>다른 모든 사용자에게 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. </ol>|
|||

### <a name="planning-for-storage"></a>저장소 계획

1시간 녹음/녹화 크기는 400MB입니다. 녹음/녹화된 파일에 대한 필요한 용량을 알고 있어야 하며 Microsoft Stream에서 충분한 저장소를 사용할 수 있는지 확인합니다.  구독에 포함된 기본 저장소 및 추가 저장소를 구입하는 방법을 이해하려면 [Microsoft Stream 라이선싱 개요](/stream/license-overview)를 참조하세요.

## <a name="manage-meeting-recordings"></a>모임 녹음/녹화 관리

모임 녹음/녹화는 테넌트 소유의 콘텐츠로 간주됩니다. 녹음/녹화 담당자가 회사를 떠나면 관리자가 Microsoft Stream에서 관리 모드로 녹음/녹화 비디오 URL을 열 수 있습니다. 관리자가 녹음/녹화를 삭제하거나 녹음/녹화 메타 데이터를 업데이트하거나 녹음/녹화 비디오의 사용 권한을 변경할 수 있습니다. [Stream의 관리자 기능](/stream/manage-content-permissions)에 대해 자세히 알아봅니다.

> [!NOTE]
> 녹음/녹화 및 사용자 액세스 관리에 대한 자세한 내용은 [Microsoft Stream에서 사용자 데이터 관리](/stream/managing-user-data) 및 [Microsoft Stream에서 사용 권한 및 개인 정보 보호](/stream/portal-permissions)를 참조하세요.

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>모임 녹음/녹화에 대한 규정 준수 및 eDiscovery

모임 녹음/녹화는 Microsoft 365 및 Office 365 계층 C 규격인 Microsoft Stream에 저장됩니다. Microsoft Stream의 모임 또는 통화 녹음/녹화에 관심이 있는 준수 관리자에 대한 eDiscovery 요청을 지원하기 위해 녹음/녹화 완료 메시지를 Microsoft Teams의 준수 콘텐츠 검색 기능에서 사용할 수 있습니다. 준수 관리자는 준수 콘텐츠 검색 미리 보기에서 항목의 제목 줄에서 “녹음/녹화” 키워드를 찾을 수 있으며 조직에서 모임 및 통화 녹음/녹화를 검색할 수 있습니다. 모든 녹음/녹화를 확인하기 위한 필수 구성 요소는 관리자 액세스로 Microsoft Stream에서 설정해야 한다는 것입니다. [Stream에서 관리자 권한 할당](/stream/assign-administrator-user-role)에 대해 자세히 알아봅니다.

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)