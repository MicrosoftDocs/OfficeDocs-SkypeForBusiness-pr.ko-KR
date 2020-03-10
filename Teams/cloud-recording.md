---
title: Teams 클라우드 모임 녹음/녹화
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 팀에서 클라우드 음성 기능을 배포 하기 위한 실용적인 지침입니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 678e17ed92c0f269e134ac6c23dce29169c0d36d
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583005"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 클라우드 모임 녹음/녹화

> [!IMPORTANT]
> 앞으로는 Microsoft Stream을 국내 데이터 영주권 지역에서 사용할 수 없는 경우에도 팀 데이터가 국가 내에 저장 되어 있는 고객에 대해 팀 모임 기록 기능이 설정 되는 **구성을 변경** 하 게 됩니다. 이 변경 사항이 적용 되 면 모임 기록은 기본적으로 가장 가까운 Microsoft 스트림 영역에 저장 됩니다. 팀 데이터가 국가 내에 저장 되어 있는 경우 모임 녹음/녹화를 국가 내에 저장 하는 경우에는 Microsoft Stream이 국가 내 지역에 배포 된 후 모임 녹음/녹화를 해제 하는 것이 좋습니다. 자세한 내용은 [모임 녹음/녹화 저장 위치](#where-your-meeting-recordings-are-stored)를 참조 하세요.

Microsoft 팀에서 사용자는 팀 모임 및 그룹 통화를 녹음/녹화 하 여 오디오, 비디오, 화면 공유 활동을 캡처할 수 있습니다. 사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검색할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 있습니다. 녹음/녹화는 클라우드에서 수행 되며 [Microsoft Stream](https://docs.microsoft.com/stream/)에 저장 되므로 사용자가 조직에서 안전 하 게 공유할 수 있습니다.

관련: [팀 모임 녹음/녹화 최종 사용자 문서](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>팀 클라우드 모임 녹음/녹화 선행 조건

팀 사용자의 모임이 기록 되도록 하려면 테 넌 트에 대해 Microsoft Stream을 사용 하도록 설정 해야 합니다. 또한 모임 이끌이와 녹음/녹화를 시작 하는 사용자에 게 다음 필수 구성 요소가 필요 합니다.

- 사용자에 게 Office 365 E1, E3, E5, A1, A3, A5, M365 Business, Business Premium 또는 Business Essentials가 있습니다.
- 사용자에 게 Microsoft Stream<sup>1</sup> 에 대 한 라이선스가 있어야 합니다. 
- 사용자에 게 Microsoft Stream 비디오 업로드 권한이 있음
- 관리자가 설정한 경우 사용자가 회사 지침을 였음을
- 사용자가 Microsoft Stream에 저장소를 저장할 충분 한 공간이 있습니다.
- 사용자의 TeamsMeetingPolicy-AllowCloudRecording 설정이 true로 설정 되어 있습니다.
- 사용자가 모임에서 익명, 게스트 또는 페더레이션 사용자가 아닙니다.

> [!NOTE]
> 또한 녹음/녹화를 시작 하는 사용자가 자동으로 녹음/녹화를 녹음 여부를 선택할 수 있도록 하려면 사용자의 TeamsMeetingPolicy-AllowTranscription 설정을 true로 설정 해야 합니다.

<sup>1</sup> 사용자에 게 Microsoft Stream에 대 한 모임을 업로드/다운로드할 수 있는 권한이 필요 하지만 모임을 녹음/녹화할 수 있는 라이선스가 필요 하지는 않습니다. 사용자가 Microsoft 팀 모임을 기록 하지 못하도록 차단 하려면 AllowCloudRecording이 $False로 설정 된 TeamsMeetingPolicy를 부여 해야 합니다.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>조직의 사용자를 위한 팀 클라우드 모임 녹음/녹화 설정

이 섹션에서는 팀 회의 기록을 위해 설정 하 고 계획 하는 방법을 설명 합니다.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>조직의 사용자에 대해 Microsoft Stream 사용

Microsoft 스트림은 적격 Office 365 구독의 일부로 또는 독립 실행형 서비스로 사용할 수 있습니다.  자세한 내용은 [스트림 라이선스 개요](https://docs.microsoft.com/stream/license-overview) 를 참조 하세요.  Microsoft Stream이 이제 Microsoft 365 Business, Office 365 Business Premium 및 Office 365 비즈니스 Essentials에 포함 되어 있습니다.

사용자가 Microsoft Stream에 액세스할 수 있도록 [Office 365에서 사용자에 게 라이선스를 할당할](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) 수 있는 방법에 대해 자세히 알아보세요. [이 문서](https://docs.microsoft.com/stream/disable-user-organization)에 정의 된 대로 Microsoft Stream이 사용자에 대해 차단 되지 않았는지 확인 합니다.

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>사용자가 Microsoft Stream에서 비디오 업로드 권한을가지고 있는지 확인

기본적으로 회사의 모든 사용자는 스트림을 사용 하도록 설정 하 고 사용자에 게 라이선스가 할당 되 면 Stream에서 콘텐츠를 만들 수 있습니다. Microsoft Stream 관리자는 스트림에서 [콘텐츠를 만들기 위해 직원을 제한할](https://docs.microsoft.com/stream/restrict-uploaders) 수 있습니다. 이 제한 된 목록에 있는 사용자는 모임을 녹화할 수 없습니다.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Microsoft Stream에서 회사의 지침에 동의 하도록 직원에 게 알림

Microsoft Stream administrator가 [회사 지침 정책을 설정](https://docs.microsoft.com/stream/company-policy-and-consent) 하 고 직원 들이 콘텐츠를 저장 하기 전에이 정책을 수락 해야 하는 경우 microsoft 팀에서 기록 하기 전에 사용자가 작업을 수행 해야 합니다. 조직에서 기록 기능을 배포 하기 전에 사용자가 정책에 였음을 있는지 확인 합니다.

### <a name="turn-on-or-turn-off-cloud-recording"></a>구름 기록 설정 또는 해제

Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 팀 모임 정책을 설정 하 여 사용자의 모임을 녹화할 수 있는지 여부를 제어할 수 있습니다.

Microsoft 팀 관리 센터에서 모임 정책에 대 한 **클라우드 기록 허용** 설정을 사용 하거나 사용 하지 않도록 설정 합니다. 자세히 알아보려면 [팀에서 모임 정책 관리](meeting-policies-in-teams.md#allow-cloud-recording)를 참조 하세요.

PowerShell을 사용 하 여 TeamsMeetingPolicy에서 AllowCloudRecording/녹화 설정을 구성 합니다. 자세히 알아보려면 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.

모임 이끌이와 녹음 개시자 모두 모임에 녹음/녹화를 위한 기록 권한이 있어야 합니다. 사용자에 게 사용자 지정 정책을 할당 하지 않은 경우 사용자는 기본적으로 사용 하지 않도록 설정 된 AllowCloudRecording/전역 정책을 가져옵니다.

사용자가 전역 정책으로 돌아가려면 다음 cmdlet을 사용 하 여 사용자에 대 한 특정 정책 할당을 제거 합니다.

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

전역 정책에서 AllowCloudRecording의 값을 변경 하려면 다음 cmdlet을 사용 합니다.

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 시나리오                                                                 |                                                                                                                                                                         방법은                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    내 회사의 모든 사용자가 모임을 녹음/녹화할 수 있도록 하 고 싶습니다.                                    |                                                                     <ol><li>전역 CsTeamsMeetingPolicy에 AllowCloudRecording/녹화 확인 = True<li>모든 사용자에 게 전역 CsTeamsMeetingPolicy 또는 AllowCloudRecording = True 인 CsTeamsMeetingPolicy 정책 중 하나가 있습니다. </ol>                                                                     |
| 대부분의 사용자가 모임을 녹화할 수 있고 녹화할 수 없는 특정 사용자는 선택적으로 사용 하지 않도록 설정 하 고 싶습니다. |        <ol><li>GlobalCsTeamsMeetingPolicy에 AllowCloudRecording이 있는지 확인 합니다. = True<li>대부분의 사용자는 전역 CsTeamsMeetingPolicy 또는 AllowCloudRecording = True 인 CsTeamsMeetingPolicy 정책 중 하나를 보유 하 고 있습니다.<li>다른 모든 사용자에 게 AllowCloudRecording을 사용 하는 CsTeamsMeetingPolicy 정책 중 하나를 승인 했습니다 = False</ol>         |
|                                                   100% 사용 하지 않도록 기록 하 고 싶습니다.                                                   |                                                                <ol><li>전역 CsTeamsMeetingPolicy에 AllowCloudRecording 확인 = False<li>모든 사용자에 게 전역 CsTeamsMeetingPolicy 또는 AllowCloudRecording을 사용 하는 CsTeamsMeetingPolicy 정책 중 하나가 부여 되었습니다. = False                                                                 |
|      대부분의 사용자에 대해 기록을 사용할 수 없도록 설정 하 고 녹화할 수 있는 특정 사용자를 선택적으로 사용 하도록 설정 하 고 싶습니다.       | <ol><li>전역 CsTeamsMeetingPolicy에 AllowCloudRecording 확인 = False<li>대부분의 사용자에 게 전역 CsTeamsMeetingPolicy 또는 AllowCloudRecording을 사용 하는 CsTeamsMeetingPolicy 정책 중 하나가 부여 되었습니다. = False<li>다른 모든 사용자에 게 AllowCloudRecording = True 인 CsTeamsMeetingPolicy 정책 중 하나가 부여 되었습니다. <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>모임 녹음/녹화 저장 위치

모임 녹음/녹화는 Microsoft Stream 클라우드 저장소에 저장 됩니다. 현재, 데이터를 저장 하는 국내 데이터 영주권 지역에서 Microsoft Stream을 사용할 수 없는 경우 팀 데이터가 국가 내에 저장 되어 있는 고객에 대해 모임 기록 기능이 꺼집니다. 미래에는 Microsoft Stream을 국내 데이터 영주권 지역에서 사용할 수 없는 경우에도 데이터가 국가 내에 저장 되어 있는 고객에 게 모임 기록 기능이 설정 됩니다.

이 변경 사항이 적용 되 면 모임 녹음/녹화는 기본적으로 Microsoft Stream의 가장 가까운 지역에 저장 됩니다. 팀 데이터가 국가 내에 저장 되어 있는 경우 모임 녹음/국가를 국내으로 저장 하는 경우에는 해당 기능을 해제 한 후 Microsoft Stream이 국가 내 데이터 영주권 지역에 배포 된 후에 설정 하는 것이 좋습니다. 조직의 모든 사용자에 대 한 기능을 해제 하려면 Microsoft 팀 관리 센터에서 전역 팀 모임 정책에서 **클라우드 기록 허용** 설정을 해제 합니다.

다음은이 변경 사항이 적용 될 때 모임 녹음/녹화를 켤 때 발생 하는 상황에 대 한 요약입니다.

|모임 녹음/녹화를 사용 하는 경우 |모임 녹음/녹화는 저장 됩니다.  |
|---------|---------|
|Microsoft Stream을 국가별 데이터 영주권 지역에서 사용 하기 전에    |가장 가까운 Microsoft 스트림 영역         |
|Microsoft Stream을 국가별 데이터 영주권 지역에서 사용할 수 있는 경우    | 국가별 데이터 영주권 지역        |

모임 녹음/녹화를 아직 설정 하지 않은 새 및 기존 테 넌 트의 경우 Microsoft Stream을 국가별 데이터 영주권 지역에서 사용할 수 있게 되 면 새 녹화가 국가 내에 저장 됩니다. 그러나 Microsoft Stream을 국가별 데이터 영주권 지역에서 사용할 수 있도록 설정 하는 테 넌 트는 Microsoft Stream을 다음에 사용할 수 있는 경우에도 기존 및 새 녹화에 대 한 Microsoft 스트림 저장소를 계속 사용 하 게 됩니다. 국내 데이터 영주권 지역입니다.

Microsoft stream 데이터가 저장 된 영역을 찾으려면 Microsoft Stream에서 **을 클릭 합니다** . 오른쪽 위 모서리에서 **Microsoft Stream 정보**를 클릭 한 다음 **데이터를 저장**합니다 .를 클릭 합니다.  Microsoft Stream에서 데이터를 저장 하는 영역에 대 한 자세한 내용은 [Microsoft STREAM FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)를 참조 하세요.

Office 365의 서비스에서 데이터가 저장 되는 위치에 대 한 자세한 내용은 [데이터](https://products.office.com/where-is-your-data-located?rtc=1) 위치

### <a name="turn-on-or-turn-off-recording-transcription"></a>녹음/녹화 기록 설정 또는 해제

사용자가 팀 회의를 기록할 때 모임이 기록 된 후 자동으로 성적을 생성할지 여부를 확인할 수 있습니다. 모임 이끌이 및 녹음/녹화 개시자에 대 한 기록 기능을 사용 하지 않도록 설정한 경우 녹음 개시자가 모임 녹음/녹화를 녹음 수 있는 선택 항목을 받지 않습니다.

Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 팀 모임 정책을 설정 하 여 기록 개시자가 모임 녹음/녹화를 녹음 선택 하도록 할지 여부를 제어할 수 있습니다.

Microsoft 팀 관리 센터에서 모임 정책에 대해 내용 **허용** 설정을 사용 하거나 사용 하지 않도록 설정 합니다. 자세히 알아보려면 [팀에서 모임 정책 관리](meeting-policies-in-teams.md#allow-transcription)를 참조 하세요.

PowerShell을 사용 하 여 TeamsMeetingPolicy에서 AllowTranscription 설정을 구성 합니다. 자세히 알아보려면 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 및 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.

사용자에 게 사용자 지정 정책을 할당 하지 않은 경우 사용자는 기본적으로 사용 하지 않도록 설정 된 AllowTranscription를 갖는 전역 정책을 가져옵니다.

사용자가 전역 정책으로 돌아가려면 다음 cmdlet을 사용 하 여 사용자에 대 한 특정 정책 할당을 제거 합니다.

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

전역 정책에서 AllowCloudRecording의 값을 변경 하려면 다음 cmdlet을 사용 합니다.

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|시나리오|방법은 |
|---|---|
|내 회사의 모든 사용자가 모임 녹음/녹화를 시작할 때 녹음 수 있도록 하 고 싶습니다. |<ol><li>전역 CsTeamsMeetingPolicy에 AllowTranscription이 있는지 확인 = True <li>모든 사용자에 게 전역 csTeamsMeetingPolicy 또는 AllowTranscription가 True 인 경우의 정책 중 하나가 있습니다. </ol>|
|대부분의 사용자가 모임 녹음/녹화를 녹음 수 있으며, 녹음 허용 되지 않는 특정 사용자는 선택적으로 사용 하지 않도록 설정 하려고 합니다. |<ol><li>전역 CsTeamsMeetingPolicy에 AllowTranscription이 있는지 확인 = True <li>대부분의 사용자는 전역 CsTeamsMeetingPolicy를 보유 하 고 있으며, CsTeamsMeetingPolicy 정책 중 하나에 AllowTranscription가 True 인 경우 <li>다른 모든 사용자에 게 AllowTranscription를 사용 하는 정책 중 하나를 승인 했습니다 = False </ol>|
|녹화 기록을 100% 사용 안 함으로 설정 합니다. |<ol><li>전역 CsTeamsMeetingPolicy에 AllowTranscription이 있는지 확인 = False <li>모든 사용자에 게 전역 CsTeamsMeetingPolicy 나 허용 된 CsTeamsMeetingPolicy 정책 중 하나에 AllowTranscription = False가 부여 되었습니다. </ol>|
|대부분의 사용자에 대해 기록을 사용 하지 않도록 설정 하 고 녹음를 허용 하는 특정 사용자를 선택적으로 사용 하도록 설정 합니다. |<ol><li>전역 CsTeamsMeetingPolicy에 AllowCloudRecording 확인 = False <li>대부분의 사용자에 게 전역 CsTeamsMeetingPolicy 또는 AllowCloudRecording을 사용 하는 CsTeamsMeetingPolicy 정책 중 하나가 부여 되었습니다. = False <li>다른 모든 사용자에 게 AllowCloudRecording = True 인 CsTeamsMeetingPolicy 정책 중 하나가 부여 되었습니다. </ol>|
|||

### <a name="planning-for-storage"></a>저장소 계획

1 시간 녹화의 크기는 400 MB입니다. 기록 된 파일에 필요한 용량을 이해 하 고 Microsoft Stream에서 충분 한 저장소를 사용할 수 있는지 확인 합니다.  구독에 포함 된 기본 저장소와 추가 저장소를 구입 하는 방법에 대해 설명 하는 [이 문서](https://docs.microsoft.com/stream/license-overview) 를 읽어 보세요.

## <a name="manage-meeting-recordings"></a>모임 녹음/녹화 관리

모임 기록은 테 넌 트 소유 콘텐츠로 간주 됩니다. 기록의 소유자가 회사에서 나간 경우 관리자는 Microsoft Stream의 관리 모드에서 녹화 비디오 URL을 열 수 있습니다. 관리자가 녹음/녹화를 삭제 하거나, 녹음/녹화 메타 데이터를 업데이트 하거나, 녹음 비디오의 사용 권한을 변경할 수 있습니다. [스트림의 관리 기능](https://docs.microsoft.com/stream/manage-content-permissions)에 대해 자세히 알아보세요.

> [!NOTE]
> 녹음/녹화 및 사용자 액세스 관리에 대 한 자세한 내용은 microsoft stream의 [사용자 데이터 관리](https://docs.microsoft.com/stream/managing-user-data) 및 [Microsoft Stream의 사용 권한 및 개인 정보](https://docs.microsoft.com/stream/portal-permissions) 를 참조 하세요.


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>모임 녹음/녹화에 대 한 준수 및 eDiscovery

모임 기록은 Office 365 계층-C 규격 인 Microsoft Stream에 저장 됩니다. Microsoft Stream 용 모임 또는 녹음/녹화에 관심이 있는 규정 준수 관리자에 대 한 전자 검색 요청을 지원 하기 위해 Microsoft 팀의 콘텐츠 준수 검색 기능에서 기록 완료 메시지를 사용할 수 있습니다. 준수 관리자는 준수 콘텐츠 검색 미리 보기에서 항목의 제목 줄에 있는 "기록" 키워드를 찾아 조직의 모임 및 통화 기록을 검색할 수 있습니다. 모든 녹화가 표시 되는 필수 구성 요소는 관리자 액세스 권한으로 Microsoft Stream에 설정 해야 한다는 것입니다. [Stream에서 관리자 권한을 할당](https://docs.microsoft.com/stream/assign-administrator-user-role)하는 방법에 대해 자세히 알아보세요.

## <a name="related-topics"></a>관련 항목

- [팀 PowerShell 개요](teams-powershell-overview.md)
