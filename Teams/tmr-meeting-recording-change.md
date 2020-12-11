---
title: 모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 사용
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 Stream에서 비즈니스용 OneDrive 및 SharePoint 모임 녹음/녹화 저장소로 전환하는 방법을 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea07079a94e2f76f8833e0854fd0161b4ff9ec09
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620713"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용

> [!Note]
> 모임 녹음/녹화를 위해 Microsoft Stream을 비즈니스용 OneDrive로, Microsoft SharePoint를 사용하는 변경은 단계적 접근 방식입니다.

|<div style="width:290px">날짜&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |이벤트&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020년 10월 5일 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 모임 정책을 사용하여 Microsoft Stream(클래식) 대신 비즈니스용 OneDrive 및 SharePoint에 모임 녹음/녹화를 저장할 수 있습니다.|
|2021년 1월 7일 출시 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|조직의 Teams 모임 정책을 수정하고 명시적으로 Stream으로 설정하여 변경을 지연하지 않는 한 모든 새 Teams 모임 기록은 비즈니스용 OneDrive 및 SharePoint에 **저장됩니다.** 정책 보고를 스트림으로 보는 것만으로는 충분하지 않습니다. 정책 값을 Stream으로 명시적으로 설정해야 **합니다.**|
|2021년 1월 11일 출시 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC만 해당**<br> GCC 고객은 10월 5일을 시작으로 옵트아웃할 수 있는 반면, 옵트인할 수 없습니다. 이 기능은 옵트아웃하지 않는 한 2021년 1월 11일을 시작하는 모든 GCC 고객에게 롤아웃됩니다.<br>  <br>2021년 1월 11일부터 조직의 Teams 모임 정책을 수정하고 명시적으로 스트림으로 설정하여 이 변경을 지연하지 않는 한 GCC 고객을 위한 모든 새 Teams 모임 녹음/녹화가 비즈니스용 OneDrive 및 SharePoint에 저장됩니다. <br><br>옵트아웃했지만 이 기능을 설정할 준비가 된 경우 Teams 모임 정책을 비즈니스용 **OneDrive로** 명시적으로 설정하여 설정할 수 있습니다. |
|2021년 3월 1일 출시 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Enterprise & GCC 고객**<br>**Microsoft Stream(클래식)에** 새 모임 녹음/녹화를 저장할 수 없습니다. Teams 모임 정책을 Stream으로 변경한 경우에도 모든 고객은 자동으로 비즈니스용 OneDrive 및 SharePoint에 모임 녹음/녹화를 저장합니다.<br><br> 고객이 릴리스 타이밍을 제어할 수 있도록 이 날짜 전에 이 기능을 롤아웃하는 것이 좋습니다. |
|2021년 7월 7일 출시 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**교육 고객**<br>**Microsoft Stream(클래식)에** 새 모임 녹음/녹화를 저장할 수 없습니다. Teams 모임 정책을 Stream으로 변경한 경우에도 모든 고객은 자동으로 비즈니스용 OneDrive 및 SharePoint에 모임 녹음/녹화를 저장합니다.<br><br> 고객이 릴리스 타이밍을 제어할 수 있도록 이 날짜 전에 이 기능을 롤아웃하는 것이 좋습니다. 교육 고객에게 진행 중 학기 완료 기능을 제공하기 위해 이 일정을 업데이트했습니다. |

> [!Note]
> 엔터프라이즈 및 교육 고객이 조직의 변경을 보다 잘 제어하기 위해 변경이 발생하기를 기다리지 않고 변경에 대해 잘 아는 경우 옵트인하는 것이 좋습니다.

Microsoft Teams에는 모임 녹음/녹화를 저장하는 새로운 방법이 있습니다. 클래식 Microsoft Stream에서 새 스트림으로 전환하는 첫 번째 단계로 [이](https://docs.microsoft.com/stream/streamnew/new-stream)메서드는 Microsoft 365의 비즈니스용 Microsoft OneDrive 및 SharePoint에 기록을 저장하고 다양한 이점을 제공합니다.

기록을 저장하기 위해 비즈니스용 OneDrive 및 SharePoint를 사용할 경우의 이점은 다음과 같습니다.

- Teams 모임 기록(TMR)에 대한 보존 정책(S+C E5 자동 재시도 레이블)
- 비즈니스용 OneDrive 및 SharePoint 정보 거버넌스 이점
- 사용 권한 및 공유를 쉽게 설정할 수 있습니다.
- 명시적 공유만 사용하여 게스트(외부 사용자)와 기록 공유
- 액세스 흐름 요청
- 비즈니스용 OneDrive 및 SharePoint 공유 링크 제공
- 할당량 증가
- 모임 녹음/녹화를 더 빠르게 사용할 수 있습니다.
- **로컬 테넌트** 지원으로 이동
- 다중 지역 지원 – 기록은 해당 사용자에 특정 지역에 저장됩니다.
- BYOK(Bring Your Own Key) 지원
- 향상된 대본 품질 및 화자 기여

고려해야 할 몇 가지 제한 사항이 있습니다.

- 영어 전용 자막과 대본이 있습니다.
- 대본 또는 해당 콘텐츠를 검색할 수 없습니다.
- 대본을 편집할 수 없지만 캡션을 해제/해제할 수 있습니다.
- 기록을 공유하는 사용자와 제어할 수 있지만 공유 액세스 권한이 있는 사람이 기록을 다운로드하지 못하게 차단할 수 없습니다.
- 녹음/녹화가 완료되면 전자 메일을 받을 수 없지만, 녹음/녹화가 완료되면 모임 채팅에 기록이 표시됩니다. 이 경우 이전에 Stream에서보다 훨씬 빠르게 진행됩니다.

자세한 내용은 "모임 녹음/녹화"를 시청하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>비즈니스용 OneDrive 및 SharePoint에 대한 모임 기록 옵션 설정

모임 녹음/녹화 옵션은 Teams 정책 수준에서 설정됩니다. 다음 예제에서는 전역 정책을 설정하는 방법을 보여줍니다. 사용자에게 할당한 정책 또는 정책에 대한 모임 기록 옵션을 설정해야 합니다.

> [!Note]
> Teams 모임 정책 변경 내용이 전파하는 데 시간이 걸릴 수 있습니다. 설정한 후 몇 시간 후에 다시 확인한 다음, 로그인하고 다시 로그인합니다.

1. 비즈니스용 Skype Online PowerShell을 설치합니다.
**참고:** 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다. [PowerShell을 사용하여 비즈니스용 Skype Online 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. 비즈니스용 [Skype Online PowerShell을 다운로드합니다.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. 프롬프트에 따라 설치합니다.

    c. 컴퓨터를 다시 시작합니다.

2. 관리자로 PowerShell 시작

3. SkypeOnline 커넥터를 가져오고 Teams 관리자로 로그인합니다.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. [Set-CsTeamsMeetingPolicy를](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 사용하여 Stream Storage에서 비즈니스용 OneDrive 및 SharePoint로 전환할 Teams 모임 정책을 설정할 수 있습니다.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 일부 사용자가 이끌이 또는 사용자당 정책을 할당한 경우 모임 녹음/녹화를 비즈니스용 OneDrive 및 SharePoint에 저장하려면 이 정책에서 이 설정을 설정해야 합니다. 자세한 내용은 [Teams에서 모임 정책 관리를 참조하세요.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>비즈니스용 OneDrive 및 SharePoint에서 스트림을 계속 사용 옵트아웃

정책이 Stream으로 설정되어 있는 경우에도 설정되지 않을 수 있습니다. 일반적으로 정책이 설정되지 않은 경우 기본 설정은 **Stream입니다.** 그러나 이 새로운 변경으로 SharePoint 또는 비즈니스용 OneDrive 사용을 옵트아웃하려는 경우 Stream으로 정책을 다시 설정하여 **Stream이** 기본값이 되도록 해야 합니다. 

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>권한 또는 역할 기반 액세스

> [!Note]
> Teams 모임 녹음/녹화를 공유할 때 받는 사람이 로그인한 사용자인 것이 좋습니다. SharePoint **파일 또는** 폴더에 설명된 파일 공유 시 사용자(조직) 옵션을 [선택합니다.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) 외부 공유는 대용량 파일 또는 많은 수의 파일을 배포하도록 설계되지 않습니다. 사기 및 남용 시나리오를 방지하기 위해 외부 사용자에게 많은 양의 데이터를 공유할 때 문제가 있을 수 있습니다.

|모임 유형                               | 레코드를 클릭한 사람| 녹음은 어디에 있나요?                               |액세스 권한이 있는 사용자 R/W, R 또는 공유                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|내부 당사자와 1:1 통화             |호출자                 |발신자 비즈니스용 OneDrive 계정                        |호출자(caller)는 소유자로, 모든 권한을 가졌다. <br /><br />호출자(동일한 테넌트에 있는 경우)에게 읽기 전용 액세스 권한이 있습니다. 공유 액세스 권한이 없습니다. <br /><br /> 다른 테넌트에 있는 경우 호출자(다른 테넌트)는 액세스할 수 없습니다. 발신자는 발신자에게 공유해야 합니다.|
|내부 당사자와 1:1 통화             |발신자                 |발신자 비즈니스용 OneDrive 계정                        |발신인은 소유자로, 모든 권한을 가졌다. <br /><br />호출자(동일한 테넌트에 읽기 전용 액세스 권한이 있는 경우). 공유 액세스 권한이 없습니다. <br /><br />호출자(다른 테넌트의 경우)는 액세스할 수 없습니다. 발신자는 발신자에게 공유해야 합니다.|
|외부 통화를 통해 1:1 통화             |호출자                 |발신자 비즈니스용 OneDrive 계정                        |호출자(caller)는 소유자로, 모든 권한을 가졌다.<br /> <br />발신자에는 액세스할 수 없습니다. 호출자는 발신자와 공유해야 합니다.|
|외부 통화를 통해 1:1 통화             |발신자                 |발신자 비즈니스용 OneDrive 계정                        |발신인은 소유자로, 모든 권한을 가졌다.<br /><br />호출자에 액세스할 수 없습니다. 발신자는 발신자에게 공유해야 합니다.|
|그룹 통화                                 |통화의 모든 멤버 |레코드의 비즈니스용 OneDrive 계정을 클릭한 구성원  |레코드를 클릭한 멤버에게는 모든 권한이 있습니다. <br /><br /> 동일한 테넌트의 다른 멤버는 읽기 권한을 습니다. <br /><br /> 다른 테넌트의 다른 멤버는 권한을 가지지 않습니다.|
|회의/예약된 모임                    |이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 습니다. <br /><br /> 모임의 다른 모든 구성원은 읽기 권한이 있습니다.|
|회의/예약된 모임                    |다른 모임 구성원   |레코드를 클릭한 멤버                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. <br /><br />이끌이는 편집 권한을 가지며 공유할 수 있습니다.<br /><br /> 다른 모든 멤버는 읽기 권한이 있습니다.|
|외부 사용자와의 예정된 모임|이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 습니다.<br /> <br /> 이끌이와 동일한 테넌트의 모임의 다른 모든 구성원은 읽기 권한이 있습니다. <br /><br /> 다른 모든 외부 구성원은 액세스할 수 없습니다. 이끌이는 외부 구성원과 공유해야 합니다.|
|외부 사용자와의 예정된 모임|다른 모임 구성원   |레코드를 클릭한 멤버                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. 이끌이는 편집 권한을 가지며 공유할 수 있습니다. <br /><br /> 이끌이와 동일한 테넌트의 모임의 다른 모든 구성원은 읽기 권한이 있습니다. <br /><br />다른 모든 외부 구성원은 액세스할 수 없습니다. 이끌이는 외부 구성원과 공유해야 합니다.|
|채널 모임                            |채널 멤버         |해당 채널에 대한 Teams의 SharePoint 위치                   |레코드를 클릭한 구성원에게는 기록에 대한 편집 권한도 있습니다. <br /> <br />다른 모든 구성원의 권한은 채널 SharePoint 사용 권한을 기반으로 합니다.|

## <a name="frequently-asked-questions"></a>자주하는 질문

**모임 녹음/녹화는 어디에 저장될까요?**

- 비 채널 모임의 경우 기록은 모임 녹음/녹화를 시작한 사람이 속한 비즈니스용 OneDrive의 최상위 수준에 있는 기록이라는 폴더에 저장됩니다.  예:

  <i>레코더의 비즈니스용 OneDrive</i> / **녹음/녹화**

- 채널 모임의 경우 기록은 기록이라는 폴더의 Teams 사이트 설명서 **라이브러리에 저장됩니다.** 예:

  <i>Teams 이름 - 채널 이름</i> / **문서** / **녹음/녹화**

**퇴직한 직원의 녹음/녹화는 어떻게 처리하나요?**

비디오는 비즈니스용 OneDrive 및 SharePoint의 다른 파일과 같기 때문에 직원 퇴사 후 소유권 및 보존을 처리하면 일반적인 비즈니스용 [OneDrive]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)및 SharePoint 프로세스를 따르게 됩니다.

**모임 녹화를 볼 수 있는 권한이 있는 사용자**

- 비 채널 모임의 경우 외부 사용자를 제외한 모든 모임 초대를 통해 개인적으로 공유되는 링크가 자동으로 표시됩니다. 외부 사용자는 모임 이끌이 또는 모임 녹음/녹화를 시작한 사람이 공유 목록에 명시적으로 추가해야 합니다.

- 채널 모임의 경우 사용 권한은 채널의 소유자 및 구성원 목록에서 상속됩니다.

**대본은 어떻게 관리할 수 있나요?**

이 미리 보기에 옵트인하는 고객은 비즈니스용 OneDrive 및 SharePoint로 마이그레이션된 Teams 모임 녹음/녹화에서 선택 자막을 사용할 수 없습니다.영어 자막부터 Q4 CY2020의 모임 녹화에 캡션을 추가하기 위해 작업 중입니다.

선택 자막은 Teams 클라우드 녹음/녹화에 설명된 기록을 허용하도록 옵트인한 고객을 위해 Teams 모임 녹음/녹화에서 사용할 [수 있습니다.](cloud-recording.md)

캡션은 모든 장애가 있는 시청자를 위한 포괄 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 Teams에서 캡션을 삭제하지 않는 한 Teams에서 캡션을 계속 사용할 수 있는 경우 캡션을 숨길 수 있습니다. 모임 [녹화를 켜거나 끄는 방법을 참조합니다.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

모임이 녹화된 후 60일 동안 Teams 모임 녹화에 대해 자막이 지원됩니다.

Teams 모임 녹음/녹화를 비즈니스용 OneDrive 또는 SharePoint의 원래 위치에서 이동하거나 복사한 경우 선택 자막이 완전히 지원되지 않습니다.

**저장소 할당량에 어떤 영향을 주나요?**

Teams 모임 녹화 파일은 비즈니스용 OneDrive 및 SharePoint에 있으며 해당 서비스의 할당량에 포함됩니다. [SharePoint 할당량 및](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 비즈니스용 [OneDrive 할당량 참조](https://docs.microsoft.com/onedrive/set-default-storage-space)

Stream과 비교하여 비즈니스용 [OneDrive를](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 통해 더 많은 저장소를 얻을 수 있으며 SharePoint를 사용하면 더 많은 저장소를 사용할 수 있습니다.

**Teams 모임 녹음/녹화를 재생하는 방법**

파일에 액세스하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생됩니다.

**Stream에 추가를 더 이상 사용할 계획이 없는 경우 기존 비디오는 현재와 얼마나 오래 유지하나요?**

플랫폼으로 스트림은 가까운 미래에 사용되지 않습니다. 현재 Stream에 있는 비디오는 마이그레이션을 시작할 때까지 여기에 유지됩니다. 마이그레이션 시 해당 비디오는 비즈니스용 OneDrive 또는 SharePoint로도 마이그레이션됩니다. 자세한 [내용은 Stream 클래식 마이그레이션을](https://docs.microsoft.com/stream/streamnew/classic-migration) 참조하세요.

**보존 레이블을 적용하는 방법**

보존 [레이블을 자동으로 적용하는 방법을 참조합니다.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Microsoft Teams에서 내 사용자에게 정책을 할당하고 어떤 정책이 우선적으로 적용하나요?**

어떤 [정책이 우선하는지 봐야 하나요?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).
