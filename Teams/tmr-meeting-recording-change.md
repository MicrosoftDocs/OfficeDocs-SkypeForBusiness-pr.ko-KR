---
title: 모임 녹화에 비즈니스용 OneDrive 및 SharePoint 사용
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 Stream에서 비즈니스용 OneDrive 및 SharePoint 모임 기록 저장소로 전환하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83688d6c4318aff9ef7a014a1792f52761145b4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111034"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>모임 녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용

> [!Note]
> 모임 녹화를 위해 Microsoft Stream을 비즈니스용 OneDrive로, Microsoft SharePoint를 사용하는 방식은 단계적 접근 방식입니다.

|<div style="width:290px">날짜&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |이벤트&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020년 10월 5일<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 모임 정책을 사용하여 Microsoft Stream(클래식) 대신 비즈니스용 OneDrive 및 SharePoint에 모임 녹음이 저장됩니다.|
|2021년 1월 7일 시작<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|조직의 Teams 모임 정책을 수정하고 명시적으로 Stream으로 설정하여 변경을 지연하지 않는 한 모든 새 Teams 모임 녹음은 비즈니스용 OneDrive 및 SharePoint에 **저장됩니다.** Stream으로 정책 보고를 보는 것만으로는 충분하지 않습니다. 정책 값을 Stream으로 명시적으로 **설정해야 합니다.**|
|2021년 1월 11일 시작<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC만 해당**<br> GCC 고객은 10월 5일부터 옵트아웃할 수 있는 반면, 옵트인할 수 없습니다. 이 기능은 옵트아웃하지 않는 한 2021년 1월 11일부터 모든 GCC 고객에게 롤아웃됩니다.<br>  <br>2021년 1월 11일부터 조직의 Teams 모임 정책을 수정하고 명시적으로 스트림으로 설정하지 않으면 GCC 고객에 대한 모든 새 Teams 모임 녹화가 비즈니스용 OneDrive 및 SharePoint에 저장됩니다. <br><br>옵트아웃했지만 이 기능을 사용할 준비가 된 경우 Teams 모임 정책을 비즈니스용 **OneDrive로** 명시적으로 설정하여 설정할 수 있습니다. |
|2021년 3월 1일 시작 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 및 DoD만**<br> 이제 고객은 Microsoft Teams에서 처음으로 클라우드 모임 녹화를 사용하도록 설정할 수 있습니다. 이러한 기록은 기본적으로 OneDrive 및 SharePoint에 저장되고 재생됩니다. |
|2021년 7월 7일을 시작으로 증분 롤아웃 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(엔터프라이즈, 교육 및 GCC)**<br>Microsoft Stream(클래식)에 새 모임 녹음/녹화를 저장할 수 없습니다. 모든 고객은 Teams 모임 정책을 Stream으로 변경한 경우에도 비즈니스용 OneDrive 및 SharePoint에 자동으로 모임 녹음이 저장됩니다.<br><br> 고객이 조직의 변경을 더 잘 제어하기 위해 변경이 일어날 때까지 기다리지 않고 변경에 대해 잘 아는 경우 옵트인하는 것이 좋습니다. |

Microsoft Teams에는 모임 기록을 저장하는 새로운 방법이 있습니다. 클래식 Microsoft Stream에서 새 [Stream으로](/stream/streamnew/new-stream)전환하는 첫 번째 단계로 이 메서드는 Microsoft 365의 비즈니스용 Microsoft OneDrive 및 SharePoint에 기록을 저장하고 많은 이점을 제공합니다.

기록을 저장하기 위해 비즈니스용 OneDrive 및 SharePoint를 사용하는 이점은 다음과 같습니다.

- TMR(Teams 모임 기록)에 대한 보존 정책(S+C E5 자동 재시도 레이블)
- 비즈니스용 OneDrive 및 SharePoint 정보 거버넌스의 이점
- 사용 권한 및 공유를 쉽게 설정할 수 있습니다.
- 명시적 공유만 사용하여 게스트(외부 사용자)와 녹화 공유
- 액세스 흐름 요청
- 비즈니스용 OneDrive 및 SharePoint 공유 링크 제공
- 모임 녹화를 더 빠르게 사용할 수 있습니다.
- **로컬 테넌트** 지원으로 이동
- 다중 지역 지원 – 기록은 해당 사용자에 특정 지역에 저장됩니다.
- BYOK(사용자만의 키) 지원 가져오기

자세한 내용은 "모임 기록"을 시청하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>비즈니스용 OneDrive 및 SharePoint에 대한 모임 녹화 옵션 설정

모임 기록 옵션은 Teams 정책 수준에서 설정됩니다. 다음 예제에서는 전역 정책을 설정하는 방법을 보여줍니다. 사용자에게 할당한 정책 또는 정책에 대해 모임 기록 옵션을 설정해야 합니다.

> [!Note]
> 팀 모임 정책 변경 내용이 전파하는 데 시간이 걸릴 수 있습니다. 설정한 후 몇 시간 후에 다시 확인한 다음, 로그인하고 다시 로그인합니다.

1. Teams PowerShell PowerShell을 설치합니다.

   > [!NOTE]
   > 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다. [PowerShell을 사용하여 비즈니스용 Skype Online 관리를 참조하세요.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)

1. 관리자로 PowerShell을 실행합니다.

2. [Teams PowerShell 모듈을 설치합니다.](./teams-powershell-install.md)

3. MicrosoftTeams 모듈을 가져오고 Teams 관리자로 로그인합니다.


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

4. [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 사용하여 Stream Storage에서 비즈니스용 OneDrive 및 SharePoint로 전환하는 Teams 모임 정책을 설정합니다.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 일부 사용자가 이끌이 또는 사용자당 정책을 할당한 경우 모임 기록을 비즈니스용 OneDrive 및 SharePoint에 저장하려면 이 정책에 이 설정을 설정해야 합니다. 자세한 내용은 Teams 에서 [모임 정책 관리를 참조하세요.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Stream을 계속 사용하기 위해 비즈니스용 OneDrive 및 SharePoint에서 옵트아웃

정책이 **Stream으로** 설정되어 있는 경우에도 설정되지 않을 수 있습니다. 일반적으로 정책이 설정되지 않은 경우 기본 설정은 **Stream 입니다.** 그러나 이 새로운 변경을 통해 SharePoint 또는 비즈니스용 OneDrive 사용을 옵트아웃하려는 경우  Stream이  기본값인지 확인하려면 정책을 Stream으로 다시 설정해야 합니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>권한 또는 역할 기반 액세스

> [!Note]
> Teams 모임 녹음/녹화를 공유할 때 받는 사람이 로그인된 사용자로 있어야 합니다. SharePoint 파일 또는 폴더에 설명된 파일 공유 시 **(조직)의** 사용자 [옵션을 선택합니다.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) 외부 공유는 대용량 파일 또는 많은 수의 파일을 배포하도록 설계되지 않습니다. 사기 및 악용 시나리오를 방지하기 위해 많은 양의 데이터를 외부 사용자에게 공유할 때 문제가 있을 수 있습니다.

|모임 유형                               | 레코드를 클릭한 사람| 기록 토지는 어디에 있나요?                               |액세스 권한이 있는 사용자 R/W, R 또는 공유                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|내부 파티를 통해 1:1 통화             |발신자                 |발신자 비즈니스용 OneDrive 계정                        |발신자 는 소유자이며 전체 권한을 습니다. <br /><br />호출자(동일한 테넌트의 경우)는 읽기 전용 액세스 권한이 있습니다. 공유 액세스 없음. <br /><br /> 호출자(다른 테넌트의 경우)에는 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|내부 파티를 통해 1:1 통화             |호출자                 |비즈니스용 Callee의 OneDrive 계정                        |발신인은 소유자이며 전체 권한을 습니다. <br /><br />호출자(동일한 테넌트에 읽기 전용 액세스 권한이 있는 경우). 공유 액세스 없음. <br /><br />호출자(다른 테넌트의 경우)에는 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|외부 호출을 통해 1:1 통화             |발신자                 |발신자 비즈니스용 OneDrive 계정                        |발신자 는 소유자이며 전체 권한을 습니다.<br /> <br />호출자에 대한 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|외부 호출을 통해 1:1 통화             |호출자                 |비즈니스용 Callee의 OneDrive 계정                        |발신인은 소유자이며 전체 권한을 습니다.<br /><br />호출자에 대한 액세스 권한이 없습니다. 호출자는 호출자에 공유해야 합니다.|
|그룹 호출                                 |호출의 모든 구성원 |레코드의 비즈니스용 OneDrive 계정을 클릭한 그룹 구성원  |레코드를 클릭한 멤버는 전체 권한을 습니다. <br /><br /> 동일한 테넌트의 다른 fr에는 읽기 권한이 있습니다. <br /><br /> 다른 테넌트의 다른 그룹 구성원은 권한은 없습니다.|
|Adhoc/Scheduled meeting                    |이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 기록에 대한 모든 권한을 습니다. <br /><br /> 모임의 다른 모든 구성원은 읽기 액세스 권한이 있습니다.|
|Adhoc/Scheduled meeting                    |다른 모임 구성원   |레코드를 클릭한 모임 구성원                                  |레코드를 클릭한 멤버는 기록에 대한 모든 권한을 습니다. <br /><br />이끌이는 편집 권한을 가지며 공유할 수 있습니다.<br /><br /> 다른 모든 모임 구성원은 읽기 액세스 권한이 있습니다.|
|외부 사용자와의 Adhoc/예약된 모임|이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 기록에 대한 모든 권한을 습니다.<br /> <br /> 이끌이와 동일한 테넌트의 모임의 다른 모든 구성원은 읽기 액세스 권한을 습니다. <br /><br /> 다른 모든 외부 구성원은 액세스할 수 없습니다. 이끌이는 해당 구성원과 공유해야 합니다.|
|외부 사용자와의 Adhoc/예약된 모임|다른 모임 구성원   |레코드를 클릭한 멤버                                  |레코드를 클릭한 멤버는 기록에 대한 모든 권한을 습니다. 이끌이는 편집 권한을 가지며 공유할 수 있습니다. <br /><br /> 이끌이와 동일한 테넌트의 모임의 다른 모든 구성원은 읽기 액세스 권한을 습니다. <br /><br />다른 모든 외부 구성원은 액세스할 수 없습니다. 이끌이는 해당 구성원과 공유해야 합니다.|
|채널 모임                            |채널 멤버         |해당 채널에 대한 Teams의 SharePoint 위치                   |레코드를 클릭한 멤버는 기록에 대한 편집 권한을 습니다. <br /> <br />다른 모든 구성원의 사용 권한은 채널 SharePoint 사용 권한을 기반으로 합니다.|

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**모임 녹음/녹화는 어디에 저장하나요?**

- 비채널 모임의 경우 기록은 모임 녹화를  시작한 사용자에 속하는 비즈니스용 OneDrive의 최상위 수준에 있는 기록이라는 폴더에 저장됩니다. 예제:

  <i>Recorder's OneDrive for Business</i> / **녹음/녹화**

- 채널 모임의 경우 기록은 기록이라는 폴더에 Teams 사이트 설명서 **라이브러리에 저장됩니다.** 예제:

  <i>팀 이름 - 채널 이름</i> / **문서** / **녹음/녹화**

**Stream 파일(예: 기록)이 SharePoint/OneDrive에 저장되는 경우 어디로 이동하는지 어떻게 결정하나요? 관리자가 위치를 변경할 수 있나요?**

기본적으로 모든 기록 파일은 레코드 를 선택한 사용자의 OneDrive 계정으로 **이동됩니다.** 채널 모임의 경우 기록은 항상 채널의 SharePoint 사이트로 이동됩니다. 관리자는 기록이 저장되는 위치를 변경할 수 없습니다.

**이전 직원의 녹음은 어떻게 처리하나요?**

비디오는 비즈니스용 OneDrive 및 SharePoint의 다른 파일과 같기 때문에 직원 퇴직 후 소유권 및 보존을 처리하면 비즈니스용 [일반 OneDrive]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)및 SharePoint 프로세스가 수행됩니다.

**모임 녹화를 볼 수 있는 권한이 있는 사용자**

- 비채널 모임의 경우 외부 사용자를 제외한 모든 모임 초대자는 자동으로 개인적으로 공유되는 링크를 얻습니다. 외부 사용자는 모임 이끌이 또는 모임 녹화를 시작한 사람이 공유 목록에 명시적으로 추가해야 합니다.

- 채널 모임의 경우 채널의 소유자 및 구성원 목록에서 사용 권한이 상속됩니다.

**캡션을 어떻게 관리할 수 있나요?**

Teams 모임 녹음/녹화에 대한 자막은 사용자가 녹화할 때 전사가 켜져 있는 경우 재생 중에만 사용할 수 있습니다. 관리자는 [사용자가]( https://docs.microsoft.com/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) 전사로 모임을 녹음할 수 있도록 정책을 통해 기록 기록을 켜야 합니다.

캡션은 모든 능력의 시청자를 위한 포괄적 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 모임 기록에서 캡션을 숨길 수 있습니다. 모임 기록은 삭제하지 않는 한 Teams에서 계속 사용할 수 있습니다. 

모임이 기록된 후 60일 동안 Teams 모임 녹화에 대해 자막이 지원됩니다.

Teams 모임 기록이 비즈니스용 OneDrive 또는 SharePoint의 원래 위치에서 이동되거나 복사된 경우 자막이 완전히 지원되지 않습니다.

**저장소 할당량에 어떤 영향을 주나요?**

Teams 모임 녹음 파일은 비즈니스용 OneDrive 및 SharePoint에 라이브로 제공하며 해당 서비스에 대한 할당량에 포함됩니다. [SharePoint 할당량](/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 [비즈니스용 OneDrive 할당량 을 참조합니다.](/onedrive/set-default-storage-space)

SharePoint를 사용하면 Stream과 비교하여 [비즈니스용 OneDrive로](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 더 많은 저장소를 얻을 수 있으며 SharePoint를 사용하면 더 많은 스토리지를 사용할 수 있습니다.

**Teams 모임 녹음/녹화를 어떻게 재생할 수 있나요?**

파일에 액세스하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생됩니다.

**Stream에 추가를 더 이상 사용할 계획이면 기존 비디오는 현재와 얼마나 오래 유지하나요?**

플랫폼으로 스트림은 가까운 미래에 사용되지 않습니다. 현재 Stream에 있는 비디오는 마이그레이션을 시작할 때까지 계속 유지됩니다. 마이그레이션 시 해당 비디오는 비즈니스용 OneDrive 또는 SharePoint로 마이그레이션됩니다. 자세한 [내용은 스트림 클래식 마이그레이션을](/stream/streamnew/classic-migration) 참조하세요.

**보존 레이블을 적용하는 방법**

보존 [레이블을 자동으로 적용하는 방법을 참조합니다.](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Microsoft Teams의 사용자에게 정책을 할당하고 우선 순위를 지정하는 정책은 무엇입니까?**

우선 [순위가 어떤 정책인가요?](./assign-policies.md#which-policy-takes-precedence)를 참조하세요.