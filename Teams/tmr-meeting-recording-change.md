---
title: 모임 비즈니스용 OneDrive SharePoint 및 SharePoint 온라인 사용
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Stream에서 비즈니스용 OneDrive 및 SharePoint 온라인 모임 녹화 저장소로 전환하는 방법을 Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486138"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>모임 비즈니스용 OneDrive SharePoint 온라인 또는 스트림 사용

> [!Note]
> Microsoft Stream을 사용하여 모임 비즈니스용 OneDrive Microsoft Office SharePoint Online 단계적 접근 방식이 변경됩니다.

|<div style="width:290px">날짜&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |이벤트&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020년 10월 5일<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 모임 Teams Microsoft Stream(클래식) 대신 모임 비즈니스용 OneDrive SharePoint 저장하도록 설정|
|2021년 1월 7일 시작<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|조직의 Teams 모임 정책을 수정하고 명시적으로 스트림으로 비즈니스용 OneDrive SharePoint Teams 변경을 지연하지 않는 한 모든 새 모임 녹음/녹화가 온라인에 **저장됩니다.** Stream으로 정책 보고를 보는 것만으로는 충분하지 않습니다. 정책 값을 Stream으로 명시적으로 **설정해야 합니다.**|
|2021년 1월 11일 시작<br> *(완료)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC 전용**<br> GCC 고객이 10월 5일을 시작으로 옵트아웃할 수 있는 동안 옵트인할 수 없습니다. 이 기능은 옵트아웃하지 않은 GCC 2021년 1월 11일부터 모든 고객에게 롤아웃됩니다.<br>  <br>2021년 1월 11일 Teams 고객에 대한 모든 새 모임 GCC 조직의 모임 정책을 수정하고 명시적으로 스트림으로 비즈니스용 OneDrive SharePoint Teams 변경을 지연하지 않는 한 모든 새 비즈니스용 OneDrive 온라인에 저장됩니다. <br><br>옵트아웃했지만 이 기능을 설정할 준비가 된 경우 를 으로 명시적으로 Teams 모임 정책을 **비즈니스용 OneDrive.** |
|2021년 3월 1일 시작<br> *(완료)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 및 DoD만**<br> 이제 고객은 클라우드 모임 녹화를 처음으로 Microsoft Teams 수 있습니다. 이러한 녹음은 기본적으로 온라인 및 OneDrive SharePoint 저장되고 재생됩니다. |
|2021년 7월 7일 시작<br> *(완료)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(Enterprise, 교육 및 GCC)**<br> 온라인 Teams 녹화하고 OneDrive SharePoint 라이브로 기록된 모임의 경우 이제 Microsoft Search 검색하여 대본을 기반으로 모임 녹음 파일을 찾을 수 있습니다. |
|2021년 8월 16일을 시작으로 증분 롤아웃 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(Enterprise, 교육 및 GCC)**<br>Microsoft Stream(클래식)에 새 모임 녹음/녹화를 저장할 수 없습니다. 모든 고객은 모임 정책을 Stream으로 변경한 경우에도 비즈니스용 OneDrive SharePoint Teams 온라인에 자동으로 저장됩니다.<br><br> 고객이 조직의 변경을 더 잘 제어하기 위해 변경이 일어날 때까지 기다리지 않고 변경에 대해 잘 아는 경우 옵트인하는 것이 좋습니다. |

Microsoft Teams 기록을 저장하는 새로운 방법이 있습니다. 클래식 Microsoft Stream에서 새 Stream으로 전환하는 첫 번째 단계로 이 메서드는 비즈니스용 Microsoft OneDrive 온라인에 SharePoint 기록을 저장하고 많은 Microsoft 365 제공합니다. [](/stream/streamnew/new-stream)

플랫폼으로 스트림(클래식)은 가까운 미래에 사용되지 않습니다. 현재 Stream(클래식)에 있는 비디오는 이후 마이그레이션 도구를 사용하여 온라인에서 온라인으로 이동하는 데 사용할 OneDrive SharePoint 있습니다. 향후 [계획에](/stream/streamnew/classic-migration) 대한 자세한 내용은 Stream 클래식 마이그레이션을 참조하세요.

> [!NOTE]
> 모임 Teams 온라인에 OneDrive/SharePoint 성공적으로 업로드하지 못하면 녹화가 AMS(Azure Media Services)에 일시적으로 저장됩니다. AMS에 저장되고 나면 온라인 또는 Stream에 기록을 OneDrive/SharePoint 시도하지 않습니다.

AMS에 저장된 모임 녹화는 자동으로 삭제되기 전에 21일 동안 사용할 수 있습니다. 사용자가 복사를 유지해야 하는 경우 AMS에서 비디오를 다운로드할 수 있습니다.

기록을 저장하기 위해 비즈니스용 OneDrive SharePoint 온라인을 사용하는 이점은 다음과 같습니다.

- TMR(Teams)에 대한 보존 정책(S+C E5 자동 재시도 레이블)
- 온라인 정보 비즈니스용 OneDrive SharePoint 이점
- 사용 권한 및 공유를 쉽게 설정할 수 있습니다.
- 명시적 공유만 사용하여 게스트(외부 사용자)와 녹화 공유
- 액세스 흐름 요청
- 온라인 비즈니스용 OneDrive SharePoint 공유 링크 제공
- 모임 녹화를 더 빠르게 사용할 수 있습니다.
- 모임에 기록된 검색 기준 성적표
- **로컬 테넌트** 지원으로 이동
- 다중 지역 지원 – 기록은 해당 사용자에 특정 지역에 저장됩니다.
- BYOK(사용자만의 키) 지원 가져오기

현재 사용 가능한 기능의 전체 목록과 시간이 지날 때 [예상할 수 있는 기능을 참조하세요.](/stream/streamnew/features-new-version-stream)

자세한 내용은 "모임 Microsoft Teams 새로운 정보"를 시청하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>온라인 및 온라인에 대한 모임 비즈니스용 OneDrive SharePoint 설정

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

5. [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 사용하여 Stream storage에서 Teams 온라인으로 전환할 비즈니스용 OneDrive SharePoint 설정합니다.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 일부 사용자가 이끌이 또는 사용자당 정책을 할당한 경우 모임 기록을 온라인 및 온라인에 저장하려면 이 정책에 비즈니스용 OneDrive SharePoint 설정해야 합니다. 자세한 내용은 에서 모임 정책 [관리를 Teams.](meeting-policies-in-teams.md)

## <a name="learn-more"></a>자세히 알아보기

클라우드 모임 녹화에 대한 Teams 자세한 내용은 클라우드 모임 Teams [를 참조합니다.](cloud-recording.md) 이 문서에서는 설정, 관리, 거버넌스, 사용 권한 및 저장소 기록에 대해 자세히 알아보실 수 있습니다.
