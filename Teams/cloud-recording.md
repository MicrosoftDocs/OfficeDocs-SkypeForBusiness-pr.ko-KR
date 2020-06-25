---
title: Teams 클라우드 모임 녹음/녹화
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: 팀에서 클라우드 음성 기능을 배포 하 여 오디오, 비디오, 화면 공유 활동을 캡처하는 팀 모임 및 그룹 통화를 기록 하는 실용적인 지침입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97fa736a1f2277dbd9da2305b75bf16b26d34e73
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874415"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화

Microsoft Teams에서 사용자는 Teams 모임 및 그룹 통화를 녹음/녹화하여 오디오, 비디오 및 화면 공유 활동을 캡처할 수 있습니다. 사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검색할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 있습니다. 녹음/녹화는 클라우드에서 이루어지며 [Microsoft Stream](https://docs.microsoft.com/stream/)에 저장되므로 사용자는 조직 전체에서 녹음/녹화를 안전하게 공유할 수 있습니다.

관련: [Teams 모임 녹음/녹화 최종 사용자 문서](https://aka.ms/recordmeeting)

> [!NOTE]
> 팀 모임에서 역할을 사용 하는 방법과 사용자의 역할을 변경 하는 방법에 대 한 자세한 내용은 [팀 모임에서 역할](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조 하세요.

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화 필수 구성 요소

팀 사용자의 모임이 기록 되도록 하려면 테 넌 트에 대해 Microsoft Stream을 사용 하도록 설정 해야 합니다. 또한 다음과 같이 모임 이끌이 및 녹음/녹화를 시작하는 사용자 모두에게 필요한 필수 구성 요소가 있습니다.

- 사용자는 Office 365 E1, E3, E5, A1, A3, A5, M365 Business, Business Premium 또는 Business Essentials을 사용할 수 있습니다.
- 사용자에게 Microsoft Stream<sup>1</sup>에 대한 라이선스가 필요합니다. 
- 사용자에게 Microsoft Stream 업로드 비디오 권한이 있습니다.
- 관리자가 설정한 경우 사용자는 회사 지침을 동의합니다.
- 사용자는 Microsoft Stream의 저장 공간이 충분하여 녹음/녹화를 저장할 수 있습니다.
- 사용자에게 TeamsMeetingPolicy-AllowCloudRecording 설정이 True로 설정되어 있습니다.
- 사용자는 모임에서 익명, 게스트 또는 페더레이션 사용자가 아닙니다.
- 사용자의 모임에 대 한 기록을 사용 하도록 설정 하려면, 자신에 게 할당 된 팀 모임 정책에 대해-AllowTranscription 설정을 true로 설정 해야 합니다.

<sup>1</sup> 사용자에 게 Microsoft Stream에 대 한 모임 업로드/다운로드를 위한 라이선스가 필요 하지는 않지만 모임을 녹음/녹화할 수 있는 라이선스는 없습니다. Microsoft Temas 모임을 녹음/녹화하는 것에서 사용자를 차단하려면 AllowCloudRecording이 False로 설정된 TeamsMeetingPolicy를 부여해야 합니다.

> [!IMPORTANT] 
> 사용자가 녹음/녹화 및 녹음/녹화의 다운로드만 하도록 하려면 사용자에게 Microsoft Stream 라이선스를 할당할 필요가 없습니다. 이는 녹화가 Microsoft Stream에 저장 되지 않지만, 삭제 되기 21 일 제한을 초과 하 여 Azure Media Services (AMS)에 저장 되는 것을 의미 합니다. 이는 이 시점에 관리자가 삭제하는 기능을 포함하여 컨트롤하거나 관리할 수 있는 사항이 아닙니다.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>조직의 사용자를 위해 Teams 클라우드 모임 녹음/녹화 설정

해당 섹션에서는 Tema 모임 녹음/녹화를 설정하고 계획하는 방법을 설명합니다.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>조직의 사용자에 대해 Microsoft Stream 설정

Microsoft Stream은 적격 Microsoft 365 및 Office 365 구독의 일부로 또는 독립 실행형 서비스로 사용할 수 있습니다.  자세한 내용은 [Stream 라이선싱 개요](https://docs.microsoft.com/stream/license-overview)를 참조하세요.  Microsoft Stream이 이제 Microsoft 365 비즈니스, Microsoft 365 Business Standard 및 Microsoft 365 Business Basic에 포함 되어 있습니다.

Microsoft [365 또는 Office 365에서](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) 사용자가 microsoft Stream에 액세스할 수 있도록 라이선스를 할당 하는 방법에 대해 자세히 알아보세요. [Microsoft stream에 대 한 등록 차단](https://docs.microsoft.com/stream/disable-user-organization)에서 정의한 대로 microsoft stream이 사용자에 대해 차단 되지 않았는지 확인 합니다.

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>사용자가 Microsoft Stream에서 비디오 업로드 권한이 있는지 확인

기본적으로 Stream이 사용 가능하고 라이선스가 사용자에게 할당되면 회사의 모든 사용자가 Stream에서 콘텐츠를 만들 수 있습니다. Microsoft Stream 관리자는 Stream에서 [콘텐츠를 만들기 위해 직원을 제한](https://docs.microsoft.com/stream/restrict-uploaders)할 수 있습니다. 이 제한된 목록에 있는 사용자는 모임을 녹음/녹화할 수 없습니다.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>직원에게 Microsoft Stream의 회사 지침에 대한 동의를 공지하세요.

Microsoft Stream 관리자가 [회사 지침 정책을 설정](https://docs.microsoft.com/stream/company-policy-and-consent)했고 직원들이 콘텐츠를 저장하기 전에 이 정책을 수락해야 하는 경우 사용자는 Microsoft Teams에서 녹음/녹화를 하기 전에 작업을 수행해야 합니다. 조직에서 녹음/녹화 기능을 배포하기 전에 사용자가 정책에 동의했는지 확인합니다.

### <a name="turn-on-or-turn-off-cloud-recording"></a>클라우드 녹음/녹화 설정 또는 해제

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자 모임을 녹음/녹화할 수 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **클라우드 녹음/녹화 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [Teams에서 모임 정책 관리](meeting-policies-in-teams.md#allow-cloud-recording)를 참조하세요.

PowerShell을 사용하여 TeamsMeetingPolicy에서 AllowCloudRecording 설정을 구성할 수 있습니다. 자세한 내용은 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)를 참조하세요.

모임 이끌이 및 녹음/녹화 개시자 모두에게 모임을 녹음/녹화하는 데 필요한 녹음/녹화 권한이 있어야 합니다. 사용자에 게 사용자 지정 정책을 할당 하지 않은 경우 사용자는 기본적으로 허용 되는 AllowCloudRecording을 사용 하는 전역 정책을 가져옵니다.

> [!NOTE]
> 팀 역할을 사용 하 여 모임 기록 권한이 있는 사용자를 구성 하는 방법에 대 한 자세한 내용은 [팀 모임에서 역할](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조 하세요.

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
|      대부분의 사용자에 대해 녹화를 해제 하 고 녹화할 수 있는 특정 사용자를 선택적으로 사용 하도록 설정 하 고 싶습니다.       | <ol><li>Global CsTeamsMeetingPolicy에 AllowCloudRecording = False인지 확인<li>대부분의 사용자에게 Global CsTeamsMeetingPolicy 또는 AllowCloudRecording = False인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다.<li>다른 모든 사용자에게 AllowCloudRecording = True인 CsTeamsMeetingPolicy 정책 중 하나를 부여했습니다. <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>모임 녹음/녹화가 저장된 위치

모임 녹음/녹화는 Microsoft Stream 클라우드 저장소에 저장됩니다. 모임을 녹화 하면 Microsoft Stream이 영구적으로 보존 됩니다 (또는 녹음/녹화할 때까지 삭제 될 때까지). 녹화가 업로드 되지 않는 경우에는 20 일 동안 다운로드할 수 있는 팀 클라우드 저장소에 저장 됩니다. Microsoft Stream이 데이터가 저장된 국내 데이터 보존 지역에서 제공되지 않는 경우 Teams 데이터가 국내에 저장된 고객을 위해 모임 녹음/녹화 기능이 현재 설정되어 있습니다.

Microsoft Stream 데이터가 저장된 지역을 찾으려면 Microsoft Stream에서 오른쪽 상단 모서리의 **?** 를 클릭하고 **Microsoft Stream 정보**를 클릭한 다음 **사용자 데이터 저장 위치**를 클릭합니다.  Microsoft Stream이 데이터를 저장하는 지역에 대한 자세한 내용은 [Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)를 참조하세요.

Microsoft 365 또는 Office 365의 서비스에서 데이터가 저장 되는 위치에 대 한 자세한 내용은 [데이터](https://products.office.com/where-is-your-data-located?rtc=1) 위치

### <a name="turn-on-or-turn-off-recording-transcription"></a>녹음/녹화 기록 설정 또는 해제

이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다. 이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다. 녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다.

기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 녹음/녹화 개시자에게 모임 녹음/녹화를 기록할 수 있는 선택권이 있는지 여부를 제어하는 Teams 모임 정책을 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 모임 정책의 **기록 허용** 설정을 설정하거나 해제합니다. 자세한 내용은 [Teams에서 모임 정책 관리](meeting-policies-in-teams.md#allow-transcription)를 참조하세요.

PowerShell을 사용하여 TeamsMeetingPolicy에서 AllowTranscription 설정을 구성할 수 있습니다. 자세한 내용은 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)를 참조하세요.

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

1시간 녹음/녹화 크기는 400MB입니다. 녹음/녹화된 파일에 대한 필요한 용량을 알고 있어야 하며 Microsoft Stream에서 충분한 저장소를 사용할 수 있는지 확인합니다.  [Microsoft Stream 라이선스 개요](https://docs.microsoft.com/stream/license-overview) 를 읽고 구독에 포함 된 기본 저장소와 추가 저장소를 구입 하는 방법에 대해 알아보세요.

## <a name="manage-meeting-recordings"></a>모임 녹음/녹화 관리

모임 녹음/녹화는 테넌트 소유의 콘텐츠로 간주됩니다. 녹음/녹화 담당자가 회사를 떠나면 관리자가 Microsoft Stream에서 관리 모드로 녹음/녹화 비디오 URL을 열 수 있습니다. 관리자가 녹음/녹화를 삭제하거나 녹음/녹화 메타 데이터를 업데이트하거나 녹음/녹화 비디오의 사용 권한을 변경할 수 있습니다. [Stream의 관리자 기능](https://docs.microsoft.com/stream/manage-content-permissions)에 대해 자세히 알아봅니다.

> [!NOTE]
> 녹음/녹화 및 사용자 액세스 관리에 대한 자세한 내용은 [Microsoft Stream에서 사용자 데이터 관리](https://docs.microsoft.com/stream/managing-user-data) 및 [Microsoft Stream에서 사용 권한 및 개인 정보 보호](https://docs.microsoft.com/stream/portal-permissions)를 참조하세요.

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>모임 녹음/녹화에 대한 규정 준수 및 eDiscovery

모임 기록은 microsoft Stream에 저장 되며, Microsoft 365 및 Office 365 계층-C 규격입니다. Microsoft Stream의 모임 또는 통화 녹음/녹화에 관심이 있는 준수 관리자에 대한 eDiscovery 요청을 지원하기 위해 녹음/녹화 완료 메시지를 Microsoft Teams의 준수 콘텐츠 검색 기능에서 사용할 수 있습니다. 준수 관리자는 준수 콘텐츠 검색 미리 보기에서 항목의 제목 줄에서 “녹음/녹화” 키워드를 찾을 수 있으며 조직에서 모임 및 통화 녹음/녹화를 검색할 수 있습니다. 모든 녹음/녹화를 확인하기 위한 필수 구성 요소는 관리자 액세스로 Microsoft Stream에서 설정해야 한다는 것입니다. [Stream에서 관리자 권한 할당](https://docs.microsoft.com/stream/assign-administrator-user-role)에 대해 자세히 알아봅니다.

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
