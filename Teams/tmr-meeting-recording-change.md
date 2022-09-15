---
title: 모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 사용
ms.author: mabond
author: mkbond007
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 Stream에서 비즈니스용 OneDrive 및 SharePoint 모임 녹음/녹화 저장소로 전환하는 방법을 알아보세요.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c6dbcbe57694273d1e74a4d1a60a3df8cc8ace4
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706705"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용

> [!NOTE]
> 2021년 8월 30일부터 Teams 모임 녹음/녹화를 클래식 스트림에서 OneDrive 및 SharePoint(ODSP)로 저장하는 변경이 완료되었습니다. 이제 모든 기록이 ODSP에 저장됩니다. 이 변경은 RecordingStorageMode 정책을 재정의하고 PowerShell에서 설정을 수정해도 더 이상 영향을 주지 않습니다.

|날짜&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|이벤트&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020년 10월 5일<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 모임 정책이 비즈니스용 OneDrive 및 SharePoint에 저장되는 모임 녹음/녹화를 Microsoft Stream(클래식)|
|2021년 1월 7일부터 배포 중<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|조직의 Teams 모임 정책을 수정하고 명시적으로 **Stream** 으로 설정하여 이 변경을 지연하지 않는 한 모든 새 Teams 모임 녹음/녹화는 비즈니스용 OneDrive 및 SharePoint에 저장됩니다. 정책 보고를 Stream으로 보는 것만으로는 충분하지 않습니다. 정책 값을 **Stream** 으로 명시적으로 설정해야 합니다.|
|2021년 1월 11일부터 배포 중<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC 전용**<br> GCC 고객은 10월 5일부터 옵트아웃할 수 있지만 옵트인할 수 없습니다. 이 기능은 옵트아웃하지 않는 한 2021년 1월 11일부터 모든 GCC 고객에게 배포됩니다.<br>  <br>2021년 1월 11일부터 조직의 Teams 모임 정책을 수정하고 명시적으로 **Stream** 으로 설정하여 이 변경을 지연하지 않는 한 GCC 고객을 위한 모든 새 Teams 모임 녹음/녹화가 비즈니스용 OneDrive 및 SharePoint에 저장됩니다. <br><br>선택 해제했지만 이 기능을 켤 준비가 된 경우 Teams 모임 정책을 **비즈니스용 OneDrive** 로 명시적으로 설정하면 됩니다. |
|2021년 3월 1일부터 배포 중<br> *(완료)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 및 DoD만 해당**<br> 이제 고객은 Microsoft Teams에서 처음으로 클라우드 모임 녹음/녹화를 활성화할 수 있습니다. 이러한 녹음/녹화는 기본적으로 OneDrive 및 SharePoint에 저장되고 재생됩니다. |
|2021년 8월 16일부터 점진적으로 배포 중<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(Enterprise, Education 및 GCC)**<br>새 모임 녹음/녹화를 Microsoft Stream(클래식) 저장할 수 없습니다. 모든 고객은 Teams 모임 정책을 Stream으로 변경한 경우에도 비즈니스용 OneDrive 및 SharePoint에 모임 녹음/녹화를 자동으로 저장합니다.<br><br> 고객이 조직의 변경 사항을 더 잘 제어할 수 있도록 변경 사항이 발생할 때까지 기다리기보다 편안할 때마다 옵트인하는 것이 좋습니다. |

Microsoft Teams는 모임의 녹음/녹화를 저장하는 새로운 방법이 있습니다. 클래식 Microsoft Stream [새 Stream](/stream/streamnew/new-stream)으로 전환하는 첫 번째 단계로, 이 메서드는 Microsoft 365의 Microsoft 비즈니스용 OneDrive 및 SharePoint에 녹음/녹화를 저장하고 많은 이점을 제공합니다.

> [!NOTE]
> Teams 모임 녹음/녹화가 OneDrive/SharePoint에 성공적으로 업로드되지 않으면 "녹음/녹화가 예기치 않게 종료됨" 오류 메시지가 표시되고 녹음/녹화가 일시적으로 AMS(Azure Media Services)에 저장됩니다. AMS에 저장되면 녹음/녹화를 OneDrive/SharePoint 또는 Stream에 자동으로 업로드하려고 다시 시도하지 않습니다.

AMS에 저장된 모임녹음/녹화는 21일 동안 사용 가능하며 자동 삭제됩니다. 사용자는 사본을 보관해야 하는 경우 AMS에서 비디오를 다운로드할 수 있습니다.

비즈니스용 OneDrive 및 SharePoint를 사용하여 기록을 저장할 경우의 이점은 다음과 같습니다.

- Teams 모임 녹음(TMR)에 대한 보존 정책(S+C E5 자동 보존 레이블)
- 비즈니스용 OneDrive 및 SharePoint 정보 거버넌스의 이점
- 권한 설정 및 공유 용이
- 명시적 공유만 사용하여 게스트와 녹음/녹화 공유
- 액세스 흐름 요청
- 비즈니스용 OneDrive 및 SharePoint 공유 링크 제공
- 모임 녹음/녹화를 더 빠르게 사용할 수 있습니다.
- **로컬화** 테넌트 지원
- 다중 지역 지원 – 녹음/녹화는 해당 사용자의 특정 지역에 저장됩니다.
- BYOK(Bring Your Own Key) 지원

[오늘 사용할 수 있는 기능과 향후 예상되는 기능](/stream/streamnew/features-new-version-stream)의 전체 목록을 참조하세요.

자세한 내용은 "Microsoft Teams 모임 녹음/녹화의 새로운 기능"을 시청하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>비즈니스용 OneDrive 및 SharePoint에 대한 모임 녹음/녹화 옵션 설정

모임 녹음/녹화 옵션은 Teams 정책 수준의 설정입니다. 다음 예는 글로벌 정책을 설정하는 방법을 보여줍니다. 사용자에게 할당한 정책에 대해 모임 녹음/녹화 옵션을 설정했는지 확인하세요.

> [!NOTE]
> Teams 모임 정책 변경 내용을 전파하는 데 시간이 걸립니다. 몇 시간을 설정한 후 다시 확인한 다음 로그아웃했다가 Teams Desktop 앱에 다시 로그인하거나 컴퓨터를 다시 시작하세요.

1. Teams PowerShell을 설치합니다.

   > [!NOTE]
   > 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다. [PowerShell로 비즈니스용 Skype Online 관리](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)를 참조하세요.

2. PowerShell을 관리자로 시작합니다.

3. [Teams PowerShell 모듈](./teams-powershell-install.md)을 설치합니다.

4. MicrosoftTeams 모듈을 가져오고 Teams 관리자로 로그인합니다.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 사용하여 Stream 스토리지에서 비즈니스용 OneDrive 및 SharePoint로 전환하도록 Teams 모임 정책을 설정합니다.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!NOTE]
> 일부 사용자가 이끌이별 또는 사용자별 정책을 할당한 경우 모임 녹음/녹화를 비즈니스용 OneDrive 및 SharePoint에 저장하려는 경우 이 정책에 대해 이 설정을 설정해야 합니다. 자세한 내용은 [Teams에서 모임 정책 관리](meeting-policies-overview.md)를 참조하세요.

## <a name="permissions-or-role-based-access"></a>권한 또는 역할 기반 액세스

> [!NOTE]
> Teams 모임 녹음/녹화를 공유할 때 받는 사람이 로그인한 사용자여야 하는 것이 좋습니다. [SharePoint 파일 또는 폴더](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c)에 설명된 대로 파일을 공유할 때 **(조직에서)** 사람 옵션을 선택합니다. 외부 공유는 대용량 파일 또는 많은 수의 파일을 배포하도록 설계되지 않았습니다.

|모임 유형                               | 누가 레코드를 클릭했나요?| 녹음은 어디에 있나요?                               |액세스 가능한 사용자 R/W, R 또는 공유                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|내부 파티와의 1:1 통화             |발신자                 |발신자의 비즈니스용 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다. <br /><br />수신자(동일한 테넌트에 있는 경우)는 읽기 전용 액세스 권한이 있지만, 공유 액세스 권한은 없습니다. <br /><br /> 수신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|내부 파티와의 1:1 통화             |수신자                 |수신자의 비즈니스용 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다. <br /><br />호출자(동일한 테넌트에 있는 경우)는 읽기 전용 액세스 권한이 있지만, 공유 액세스 권한은 없습니다. <br /><br />발신자(다른 테넌트에 있는 경우)에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
|외부 통화로 1:1 통화             |발신자                 |발신자의 비즈니스용 OneDrive 계정                        |발신자는 소유자이며 전체 권한을 가집니다.<br /> <br />수신자에게 액세스 권한이 없습니다. 발신자는 이를 호출 수신자와 공유해야 합니다.|
|외부 통화로 1:1 통화             |수신자                 |수신자의 비즈니스용 OneDrive 계정                        |수신자는 소유자이며 모든 권한을 가집니다.<br /><br />발신자에게 액세스 권한이 없습니다. 수신자는 이를 발신자와 공유해야 합니다.|
|그룹 통화                                 |통화의 모든 구성원 |레코드의 비즈니스용 OneDrive 계정을 클릭한 그룹 구성원  |레코드를 클릭한 구성원은 모든 권한이 있습니다. <br /><br /> 동일한 테넌트에서 다른 그룹 구성원은 읽기 권한을 갖습니다. <br /><br /> 다른 테넌트에서 다른 그룹 구성원은 이 그룹에 대한 권한이 없습니다.|
|임시/예약된 모임                    |이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 가집니다. <br /><br /> 모임의 다른 모든 구성원은 읽기 권한이 있습니다.|
|임시/예약된 모임                    |다른 모임 구성원   |레코드를 클릭한 모임 구성원                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. <br /><br />이끌이는 편집 권한이 있으며 공유할 수 있습니다.<br /><br /> 다른 모든 모임 구성원은 읽기 권한이 있습니다.|
|외부 참가자와 임시/예약된 모임|이끌이              |이끌이의 비즈니스용 OneDrive 계정                     |이끌이는 녹음/녹화에 대한 모든 권한을 가집니다.<br /> <br /> 이끌이와 동일한 테넌트에서 모임의 다른 모든 구성원은 읽기 권한이 있습니다. <br /><br /> 다른 모든 외부 참가자는 액세스할 수 없으며 이끌이는 이를 공유해야 합니다.|
|외부 참가자와 임시/예약된 모임|다른 모임 구성원   |레코드를 클릭한 구성원                                  |레코드를 클릭한 멤버에게는 녹음/녹화에 대한 모든 권한이 있습니다. 이끌이는 편집 권한이 있으며 공유할 수 있습니다. <br /><br /> 이끌이와 동일한 테넌트에서 모임의 다른 모든 구성원은 읽기 권한이 있습니다. <br /><br />다른 모든 외부 참가자는 액세스할 수 없으며 이끌이는 이를 공유해야 합니다.|
|채널 모임                            |채널 구성원         |해당 채널의 Teams SharePoint 위치입니다. **참고**: SharePoint에 채널 모임 녹음/녹화 업로드는 IP 기반 제한에 대해 지원되지 않습니다. [Azure 조건부 액세스를](/azure/active-directory/conditional-access/overview) 사용하는 것이 좋습니다. |레코드를 클릭한 멤버는 녹음/녹화에 대한 편집 권한이 있습니다. <br /> <br />다른 모든 구성원의 권한은 채널 SharePoint 권한을 기반으로 합니다.|

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**모임 녹음/녹화는 어디에 저장되나요?**

- 비 채널 모임의 경우 녹음/녹화는 모임 녹음/녹화를 시작한 사람에게 속한 비즈니스용 OneDrive 최상위 수준인 **녹음/녹화** 폴더에 저장됩니다. 예제:

  *레코더의 비즈니스용 OneDrive*/**리코딩**

- 채널 모임의 경우 녹음/녹화는 Teams 사이트 설명서 라이브러리의 기록 폴더에 저장 **됩니다**. 예제:

  *Teams 이름 - 채널 이름*/ **문서**/ **녹음**

**Stream 파일(예: 녹음/녹화)이 SharePoint/OneDrive에 저장되는 경우 어디로 가는지 어떻게 결정하나요? 관리자가 어디로 가는지 변경할 수 있나요?**

기본적으로 모든 녹음 파일은 **레코드** 를 선택한 사용자의 OneDrive 계정으로 이동합니다. 채널 모임의 경우 녹음/녹화는 항상 채널의 SharePoint 사이트로 이동합니다. 관리자는 녹음/녹화가 저장되는 위치를 변경할 수 없습니다.

**이전 직원의 녹음/녹화를 처리할 어떻게 할까요? 있나요?**

비디오는 비즈니스용 OneDrive 및 SharePoint의 다른 파일과 같으므로 직원이 떠난 후 소유권 및 보존을 처리하는 것은 일반적인 [비즈니스용 OneDrive 및 SharePoint 프로세스를](/onedrive/retention-and-deletion) 따릅니다.

**모임 녹음/녹화를 볼 수 있는 권한이 있는 사람은 누구인가요?**

- 비 채널 모임의 경우 외부 참가자를 제외한 모든 모임 초대자는 자동으로 개인 공유 링크를 받습니다. 외부 참가자는 모임 이끌이 또는 모임 녹음/녹화를 시작한 사용자가 공유 목록에 명시적으로 추가해야 합니다.

- 채널 모임의 경우 사용 권한은 채널의 소유자 및 구성원 목록에서 상속됩니다.

> [!NOTE]
> 녹음/녹화 저장이 완료되면 전자 메일을 받지 못하지만 녹음/녹화가 완료되면 모임 채팅에 표시됩니다. 이는 이전에 Stream에서 했던 것보다 훨씬 더 빠르게 발생합니다.

**캡션을 관리하기 위해 어떻게 해야 하나요?**

Teams 모임 녹음/녹화에 대한 선택 자막은 사용자가 녹음/녹화 시 필사 기능을 켠 경우에만 재생 중에 사용할 수 있습니다. 관리자는 사용자가 [대화 내용 기록](meetings-policies-recording-and-transcription.md#transcription) 으로 모임을 녹음/녹화할 수 있도록 기록 기록을 켜야 합니다.

캡션은 모든 기능을 갖춘 뷰어를 위한 포괄적인 콘텐츠를 만드는 데 도움이 됩니다. 소유자는 모임 기록의 캡션을 숨길 수 있습니다. 단, 모임 스크립트를 삭제하지 않으면 Teams에서 계속 사용할 수 있습니다.

모임이 기록된 시점부터 60일 동안 Teams 모임 녹음/녹화에 대해 선택 자막이 지원됩니다.

Teams 모임 녹음/녹화가 비즈니스용 OneDrive 또는 SharePoint의 원래 위치에서 이동되거나 복사되는 경우 선택 자막이 완전히 지원되지 않습니다.

> [!NOTE]
> 영어 전용 선택 자막이 있습니다(GCC에서는 모임 필사를 아직 사용할 수 없음).

**스토리지 할당량에 어떤 영향을 주나요?**

Teams 모임 녹음/녹화 파일은 비즈니스용 OneDrive 및 SharePoint에 있으며 해당 서비스에 대한 할당량에 포함됩니다. [SharePoint 할당량](/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 [비즈니스용 OneDrive 할당량](/onedrive/set-default-storage-space)을 참조하세요.

Stream에 비해 [비즈니스용 OneDrive](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 더 많은 스토리지를 얻고 SharePoint를 사용하는 더 재미있는 스토리지를 얻을 수 있습니다.

**Teams 모임 녹음/녹화를 재생하려면 어떻게 해야 하나요?**

파일에 액세스하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생됩니다.

**Stream에 추가를 더하지 않으려는 경우 기존 비디오는 있는 그대로, 그리고 얼마나 오래 유지될까요?**

플랫폼으로서의 스트림은 가까운 장래에 더 이상 사용되지 않을 것입니다. 현재 Stream에 있는 비디오는 마이그레이션을 시작할 때까지 계속 유지됩니다. 마이그레이션 시 해당 비디오도 비즈니스용 OneDrive 또는 SharePoint로 마이그레이션됩니다. [자세한 내용은 마이그레이션 세부 정보를](/stream/streamnew/migration-details) 확인하세요.

**Microsoft Teams 모임 녹음/녹화에 보존 레이블을 적용할 어떻게 할까요? 있나요?**

[보존 레이블을 자동으로 적용하는 방법을](/microsoft-365/compliance/apply-retention-labels-automatically) 참조하세요.

**Microsoft Teams에서 사용자에게 정책을 할당할 어떻게 할까요? 있으며 어떤 정책이 우선적으로 적용되나요?**

[어떤 정책이 우선적으로 적용되는지](./policy-assignment-overview.md#which-policy-takes-precedence) 확인하세요.

**사용자에게 비즈니스용 OneDrive 또는 SharePoint가 없거나 스토리지 할당량이 가득 차면 녹음/녹화는 어디로 이동하나요?**

녹음은 21일 동안 보관될 임시 저장 위치에 배치됩니다. 이 시간 동안 이끌이는 녹음/녹화를 다운로드해야 합니다. 21일 이내에 다운로드하지 않으면 기록이 삭제됩니다.
