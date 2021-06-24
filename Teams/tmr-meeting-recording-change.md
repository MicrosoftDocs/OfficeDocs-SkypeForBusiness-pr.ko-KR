---
title: 모임 비즈니스용 OneDrive SharePoint 및 SharePoint 사용
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Stream에서 비즈니스용 OneDrive 및 SharePoint 녹화 저장소로 전환하는 방법을 Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4824e24eb1e648d2ffc2d52fbdc1fa8593bbe9d9
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096302"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>모임 비즈니스용 OneDrive SharePoint 또는 Stream을 사용하여

> [!Note]
> Microsoft Stream을 사용하여 모임 비즈니스용 OneDrive Microsoft SharePoint 변경은 단계적 접근 방식입니다.

|<div style="width:290px">날짜&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |이벤트&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020년 10월 5일<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 모임 Teams Microsoft Stream(클래식) 대신 모임 비즈니스용 OneDrive SharePoint 저장하도록 설정|
|2021년 1월 7일 시작<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|조직의 Teams 모임 정책을 수정하고 명시적으로 stream으로 비즈니스용 OneDrive SharePoint Teams 변경을 지연하지 않는 한 모든 새 모임 녹음/녹화가 저장됩니다.  Stream으로 정책 보고를 보는 것만으로는 충분하지 않습니다. 정책 값을 Stream으로 명시적으로 **설정해야 합니다.**|
|2021년 1월 11일 시작<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC 전용**<br> GCC 고객이 10월 5일을 시작으로 옵트아웃할 수 있는 동안 옵트인할 수 없습니다. 이 기능은 옵트아웃하지 않은 GCC 2021년 1월 11일부터 모든 고객에게 롤아웃됩니다.<br>  <br>2021년 1월 11일 Teams 고객에 대한 모든 새 모임 GCC 조직의 모임 정책을 수정하고 명시적으로 Stream으로 비즈니스용 OneDrive SharePoint 변경을 지연하지 않는 한 모든 새 비즈니스용 OneDrive SharePoint Teams 저장됩니다. <br><br>옵트아웃했지만 이 기능을 설정할 준비가 된 경우 를 으로 명시적으로 Teams 모임 정책을 **비즈니스용 OneDrive.** |
|2021년 3월 1일 시작<br> *(완료)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 및 DoD만**<br> 이제 고객은 클라우드 모임 녹화를 처음으로 Microsoft Teams 수 있습니다. 이러한 녹음은 기본적으로 OneDrive 및 SharePoint 저장됩니다. |
|2021년 8월 16일을 시작으로 증분 롤아웃 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(Enterprise, 교육 및 GCC)**<br>Microsoft Stream(클래식)에 새 모임 녹음/녹화를 저장할 수 없습니다. 모든 고객은 모임 정책을 Stream으로 변경한 경우에도 비즈니스용 OneDrive SharePoint Teams 저장됩니다.<br><br> 고객이 조직의 변경을 더 잘 제어하기 위해 변경이 일어날 때까지 기다리지 않고 변경에 대해 잘 아는 경우 옵트인하는 것이 좋습니다. |

Microsoft Teams 기록을 저장하는 새로운 방법이 있습니다. 클래식 Microsoft Stream에서 새 Stream으로 전환하는 첫 번째 단계로 [이](/stream/streamnew/new-stream)메서드는 비즈니스용 Microsoft OneDrive 기록을 저장하고 SharePoint Microsoft 365 제공합니다.

> [!NOTE]
> 모임 Teams/OneDrive/SharePoint 성공적으로 업로드하지 못하면 녹화가 AMS(Azure Media Services)에 일시적으로 저장됩니다. AMS에 저장되고 나면 기록을 OneDrive/SharePoint 다시 시도하지 않습니다.

AMS에 저장된 모임 녹화는 자동으로 삭제되기 전에 21일 동안 사용할 수 있습니다. 사용자가 복사를 유지해야 하는 경우 AMS에서 비디오를 다운로드할 수 있습니다.

기록을 저장하는 데 비즈니스용 OneDrive SharePoint 이점은 다음과 같습니다.

- TMR(Teams)에 대한 보존 정책(S+C E5 자동 재시도 레이블)
- 정보 비즈니스용 OneDrive SharePoint 이점
- 사용 권한 및 공유를 쉽게 설정할 수 있습니다.
- 명시적 공유만 사용하여 게스트(외부 사용자)와 녹화 공유
- 액세스 흐름 요청
- 공유 비즈니스용 OneDrive SharePoint 공유 링크 제공
- 모임 녹화를 더 빠르게 사용할 수 있습니다.
- **로컬 테넌트** 지원으로 이동
- 다중 지역 지원 – 기록은 해당 사용자에 특정 지역에 저장됩니다.
- BYOK(사용자만의 키) 지원 가져오기

현재 사용 가능한 기능의 전체 목록과 시간이 지날 때 [예상할 수 있는 기능을 참조하세요.](https://docs.microsoft.com/stream/streamnew/features-new-version-stream) 

자세한 내용은 "모임 Microsoft Teams 새로운 정보"를 시청하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>모임 및 비즈니스용 OneDrive 녹화 옵션을 SharePoint

모임 기록 옵션은 정책 수준에 Teams 설정입니다. 다음 예제에서는 전역 정책을 설정하는 방법을 보여줍니다. 사용자에게 할당한 정책 또는 정책에 대해 모임 기록 옵션을 설정해야 합니다.

> [!Note]
> Teams 정책 변경 내용이 전파되는 데 시간이 걸릴 수 있습니다. 설정한 후 몇 시간 후에 다시 확인한 다음, 데스크톱 앱에 Teams 다시 로그인하거나 컴퓨터를 다시 시작합니다.

1. PowerShell Teams 설치합니다.

   > [!NOTE]
   > 비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다. 최신 PowerShell 공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다. [PowerShell을 비즈니스용 Skype 온라인 관리 를 참조하세요.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)

2. 관리자로 PowerShell을 실행합니다.

3. [PowerShell Teams 설치합니다.](./teams-powershell-install.md)

4. MicrosoftTeams 모듈을 가져오고 관리자로 Teams 합니다.


   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 사용하여 Stream storage에서 Teams 모임 정책을 설정하여 Stream storage에서 비즈니스용 OneDrive 및 SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 일부 사용자가 이끌이 또는 사용자당 정책을 할당한 경우 모임 녹음/녹화를 이 정책에 저장하려면 이 정책을 비즈니스용 OneDrive SharePoint. 자세한 내용은 에서 모임 정책 [관리를 Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Stream을 비즈니스용 OneDrive SharePoint 선택 해제

정책이 **Stream으로** 설정되어 있는 경우에도 설정되지 않을 수 있습니다. 일반적으로 정책이 설정되지 않은 경우 기본 설정은 **Stream 입니다.** 그러나 이 새 변경을 사용하여 SharePoint 또는 비즈니스용 OneDrive 옵트아웃하려는 경우 Stream이 기본값인지  확인하도록 정책을 **Stream으로** 다시 설정해야 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>권한 또는 역할 기반 액세스

> [!Note]
> 모임 녹음/녹화를 공유할 때 받는 사람이 로그인한 Teams 것이 좋습니다. 파일 **또는** 폴더 공유에 설명된 SharePoint (조직) [옵션을 선택합니다.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) 외부 공유는 대용량 파일 또는 많은 수의 파일을 배포하도록 설계되지 않습니다. 사기 및 악용 시나리오를 방지하기 위해 많은 양의 데이터를 외부 사용자에게 공유할 때 문제가 있을 수 있습니다.

|모임 유형                               | Who 클릭?| 기록 토지는 어디에 있나요?                               |Who 액세스 권한이 있나요? R/W, R 또는 공유                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|내부 파티를 통해 1:1 통화             |발신자                 |발신자 비즈니스용 OneDrive 계정                        |발신자 는 소유자이며 전체 권한을 습니다. <br /><br />호출자(동일한 테넌트의 경우)는 읽기 전용 액세스 권한이 있습니다. 공유 액세스 없음. <br /><br /> 호출자(다른 테넌트의 경우)에는 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|내부 파티를 통해 1:1 통화             |호출자                 |발신자 계정의 비즈니스용 OneDrive 계정                        |발신인은 소유자이며 전체 권한을 습니다. <br /><br />호출자(동일한 테넌트에 읽기 전용 액세스 권한이 있는 경우). 공유 액세스 없음. <br /><br />호출자(다른 테넌트의 경우)에는 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|외부 호출을 통해 1:1 통화             |발신자                 |발신자 비즈니스용 OneDrive 계정                        |발신자 는 소유자이며 전체 권한을 습니다.<br /> <br />호출자에 대한 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|외부 호출을 통해 1:1 통화             |호출자                 |발신자 계정의 비즈니스용 OneDrive 계정                        |발신인은 소유자이며 전체 권한을 습니다.<br /><br />호출자에 대한 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|그룹 호출                                 |호출의 모든 구성원 |레코드의 계정에서 비즈니스용 OneDrive 그룹 구성원  |레코드를 클릭한 멤버는 전체 권한을 습니다. <br /><br /> 동일한 테넌트의 다른 구성원은 읽기 권한을 습니다. <br /><br /> 다른 테넌트의 다른 그룹 구성원은 권한은 없습니다.|
|Adhoc/Scheduled meeting                    |이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 기록에 대한 모든 권한을 습니다. <br /><br /> 모임의 다른 모든 구성원은 읽기 액세스 권한이 있습니다.|
|Adhoc/Scheduled meeting                    |다른 모임 구성원   |레코드를 클릭한 모임 구성원                                  |레코드를 클릭한 멤버는 기록에 대한 모든 권한을 습니다. <br /><br />이끌이는 편집 권한을 가지며 공유할 수 있습니다.<br /><br /> 다른 모든 모임 구성원은 읽기 액세스 권한이 있습니다.|
|외부 사용자와의 Adhoc/예약된 모임|이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 기록에 대한 모든 권한을 습니다.<br /> <br /> 이끌이와 동일한 테넌트의 모임의 다른 모든 구성원은 읽기 액세스 권한을 습니다. <br /><br /> 다른 모든 외부 구성원은 액세스할 수 없습니다. 이끌이는 해당 구성원과 공유해야 합니다.|
|외부 사용자와의 Adhoc/예약된 모임|다른 모임 구성원   |레코드를 클릭한 멤버                                  |레코드를 클릭한 멤버는 기록에 대한 모든 권한을 습니다. 이끌이는 편집 권한을 가지며 공유할 수 있습니다. <br /><br /> 이끌이와 동일한 테넌트의 모임의 다른 모든 구성원은 읽기 액세스 권한을 습니다. <br /><br />다른 모든 외부 구성원은 액세스할 수 없습니다. 이끌이는 해당 구성원과 공유해야 합니다.|
|채널 모임                            |채널 멤버         |Teams SharePoint 위치                   |레코드를 클릭한 멤버는 기록에 대한 편집 권한을 습니다. <br /> <br />다른 모든 구성원의 사용 권한은 채널 SharePoint 기반입니다.|

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**모임 녹음/녹화는 어디에 저장하나요?**

- 비채널 모임의 경우 녹음/녹화는 모임  녹화를 시작한 사용자에 속한 비즈니스용 OneDrive 최상위 수준에 있는 기록이라는 폴더에 저장됩니다. 예제:

  <i>레코더의 비즈니스용 OneDrive</i> / **녹음/녹화**

- 채널 모임의 경우 기록은 기록 이라는 폴더에 Teams 사이트 설명서 라이브러리에 **저장됩니다.** 예제:

  <i>Teams 이름 - 채널 이름</i> / **문서** / **녹음/녹화**

**스트림 파일(예: 기록)이 SharePoint/OneDrive 어디로 이동하는지 어떻게 결정하나요? 관리자가 위치를 변경할 수 있나요?**

기본적으로 모든 기록 파일은 레코드 를 선택한 OneDrive 계정으로 **이동됩니다.** 채널 모임의 경우 기록은 항상 채널의 SharePoint 사이트로 이동됩니다. 관리자는 기록이 저장되는 위치를 변경할 수 없습니다.

**이전 직원의 녹음은 어떻게 처리하나요?**

비디오는 다른 파일과 비즈니스용 OneDrive SharePoint 마찬가지로 직원 퇴직 후 소유권 및 보존을 처리하는 것이 일반적인 비즈니스용 OneDrive SharePoint [합니다.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Who 녹화를 볼 수 있는 권한이 있나요?**

- 비채널 모임의 경우 외부 사용자를 제외한 모든 모임 초대자는 자동으로 개인적으로 공유되는 링크를 얻습니다. 외부 사용자는 모임 이끌이 또는 모임 녹화를 시작한 사람이 공유 목록에 명시적으로 추가해야 합니다.

- 채널 모임의 경우 채널의 소유자 및 구성원 목록에서 사용 권한이 상속됩니다.

> [!NOTE]
> 기록이 저장을 완료하면 전자 메일이 전송되지 않지만 녹화가 완료되면 모임 채팅에 기록이 표시됩니다. 이는 이전에 Stream에서보다 훨씬 빠르게 진행됩니다.

**캡션을 어떻게 관리할 수 있나요?**

모임 Teams 녹음/녹화에 대한 자막은 사용자가 기록할 때 전사가 켜져 있는 경우만 재생 중에 사용할 수 있습니다. 관리자는 [사용자가]( https://docs.microsoft.com/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) 전사로 모임을 녹음할 수 있도록 정책을 통해 기록 기록을 켜야 합니다.

캡션은 모든 능력의 시청자를 위한 포괄적 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 모임 기록에서 캡션을 숨길 수 있습니다. 모임 기록은 삭제하지 않는 한 Teams 계속 사용할 수 있습니다. 

모임이 기록된 Teams 60일 동안 모임 녹화에 대해 자막이 지원됩니다.

모임 녹화가 원래 위치에서 이동되거나 복사된 Teams 경우 자막이 완전히 지원되지 비즈니스용 OneDrive SharePoint.

> [!NOTE]
> 영어 전용 자막이 있습니다(모임 전사는 아직 사용할 수 GCC.

**저장소 할당량에 어떤 영향을 주나요?**

Teams 녹음 파일은 비즈니스용 OneDrive SharePoint 해당 서비스에 대한 할당량에 포함됩니다. 할당 [SharePoint](/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 비즈니스용 OneDrive [을 참조합니다.](/onedrive/set-default-storage-space)

Stream과 비교하여 [](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 비즈니스용 OneDrive 스토리지를 더 많이 사용할 수 있으며, 스토리지를 사용하면 SharePoint.

**모임 녹화를 Teams 수 있나요?**

비디오는 파일에 액세스하는 비즈니스용 OneDrive SharePoint 비디오 플레이어에서 재생됩니다.

**Stream에 추가를 더 이상 사용할 계획이면 기존 비디오는 현재와 얼마나 오래 유지하나요?**

플랫폼으로 스트림은 가까운 미래에 사용되지 않습니다. 현재 Stream에 있는 비디오는 마이그레이션을 시작할 때까지 계속 유지됩니다. 마이그레이션 시 해당 비디오도 비즈니스용 OneDrive 또는 SharePoint 됩니다. 자세한 [내용은 스트림 클래식 마이그레이션을](/stream/streamnew/classic-migration) 참조하세요.

**모임 녹화에 보존 레이블을 적용하는 Microsoft Teams 어떻게 해야 하나요?**

보존 [레이블을 자동으로 적용하는 방법을 참조합니다.](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**내 사용자에게 정책을 할당하는 Microsoft Teams 우선 순위는 어떻게 하나요?**

우선 [순위가 어떤 정책인가요?](./assign-policies.md#which-policy-takes-precedence)를 참조하세요.

**사용자가 저장 또는 비즈니스용 OneDrive 또는 SharePoint 할당량이 가득 차면 기록은 어디로 이동하나요?**

기록은 임시 저장소 위치에 21일 동안 보관됩니다. 이 기간 동안 이끌이는 녹화를 다운로드해야 합니다. 21일 이내에 다운로드하지 않은 경우 기록이 삭제됩니다.
