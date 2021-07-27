---
title: 모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint Online 사용
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 Stream에서 비즈니스용 OneDrive 및 SharePoint 모임 녹음/녹화 저장소로 전환하는 방법을 알아보세요.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506327"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint Online 사용

> [!Note]
> Microsoft Stream에서 모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 Microsoft SharePoint Online로의 변경은 단계별로 접근합니다.

|<div style="width:290px">날짜&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |이벤트&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020년 10월 5일<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 모임 정책을 사용하도록 설정하고 Microsoft Stream(클래식) 대신 비즈니스용 OneDrive 및 SharePoint Online에 모임 녹음/녹화를 저장합니다.|
|2021년 1월 7일부터 배포 중<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|조직의 Teams 모임 정책을 수정하고 명시적으로 **Stream** 으로로 설정하여 이 변경을 지연하지 않는 한 모든 새로운 Teams 모임 녹음/녹화는 비즈니스용 OneDrive 및 SharePoint Online에 저장됩니다. 정책 보고를 Stream으로 보는 것만으로는 충분하지 않습니다. 정책 값을 **Stream** 으로 명시적으로 설정해야 합니다.|
|2021년 1월 11일부터 배포 중<br> *(완료)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC 전용**<br> GCC 고객은 10월 5일부터 옵트아웃할 수 있지만 옵트인할 수 없습니다. 이 기능은 옵트아웃하지 않는 한 2021년 1월 11일부터 모든 GCC 고객에게 배포됩니다.<br>  <br>2021년 1월 11일부터 GCC 고객을 위한 모든 새로운 Teams 모임 녹음/녹화는 조직의 Teams 모임 정책을 수정하고 명시적으로 **Stream** 으로 설정하여 이 변경을 지연하지 않는 한 비즈니스용 OneDrive 및 SharePoint Online에 저장됩니다. <br><br>선택 해제했지만 이 기능을 켤 준비가 된 경우 Teams 모임 정책을 **비즈니스용 OneDrive** 로 명시적으로 설정하면 됩니다. |
|2021년 3월 1일부터 배포 중<br> *(완료)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 및 DoD만 해당**<br> 이제 고객은 Microsoft Teams에서 처음으로 클라우드 모임 녹음/녹화를 활성화할 수 있습니다. 이러한 녹음은 기본적으로 OneDrive 및 SharePoint Online에 저장되고 재생됩니다. |
|2021년 7월 7일부터 배포 중<br> *(완료)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(Enterprise, Education 및 GCC)**<br> OneDrive 및 SharePoint Online에 기록되고 모임 중에 실시간으로 기록된 Teams 모임의 경우 이제 Microsoft Search에서 검색하여 대화 내용을 기반으로 모임 녹음/녹화 파일을 찾을 수 있습니다. |
|2021년 8월 16일부터 점진적으로 배포 중&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**모든 고객(Enterprise, Education 및 GCC)**<br>Microsoft Stream(클래식)에 새 모임 녹음/녹화를 저장할 수 없습니다. 모든 고객은 Teams 모임 정책을 Stream으로 변경한 경우에도 비즈니스용 OneDrive 및 SharePoint Online에 모임 녹음/녹화가 자동으로 저장됩니다.<br><br> 고객이 조직의 변경 사항을 더 잘 제어할 수 있도록 변경 사항이 발생할 때까지 기다리기보다 편안할 때마다 옵트인하는 것이 좋습니다. |

Microsoft Teams는 모임의 녹음/녹화를 저장하는 새로운 방법이 있습니다. 기존 Microsoft Stream에서 [새 Stream](/stream/streamnew/new-stream)으로 전환하는 첫 번째 단계로, 이 방법은 Microsoft 비즈니스용 OneDrive 및 SharePoint Online에서의 녹음/녹화를 Microsoft 365에 저장하고 많은 이점을 제공합니다.

플랫폼으로서의 Stream(클래식)은 가까운 시일 내에 더 이상 사용되지 않습니다. 현재 Stream(클래식)에 있는 비디오는 향후 마이그레이션 도구를 사용하여 OneDrive 및 SharePoint Online으로 이동할 때까지 그대로 유지됩니다. 향후 계획에 대한 자세한 내용은 [Stream Classic 마이그레이션](/stream/streamnew/classic-migration)을 확인하세요.

> [!NOTE]
> Teams 모임 녹음/녹화가 OneDrive/SharePoint Online에 성공적으로 업로드되지 않으면 녹음/녹화가 대신 일시적으로 AMS(Azure Media Services)에 저장됩니다. AMS에 저장한 후에는 기록을 OneDrive/SharePoint Online 또는 Stream에 자동으로 업로드하기 위해 재시도하지 않습니다.

AMS에 저장된 모임녹음/녹화는 21일 동안 사용 가능하며 자동 삭제됩니다. 사용자는 사본을 보관해야 하는 경우 AMS에서 비디오를 다운로드할 수 있습니다.

녹음을 저장하기 위해 비즈니스용 OneDrive 및 SharePoint Online을 사용하면 다음과 같은 이점이 있습니다.

- Teams 모임 녹음(TMR)에 대한 보존 정책(S+C E5 자동 보존 레이블)
- 비즈니스용 OneDrive 및 SharePoint Online 정보 거버넌스의 이점
- 권한 설정 및 공유 용이
- 명시적 공유만 있는 게스트(외부 사용자)와 녹음/녹화 공유
- 액세스 흐름 요청
- 비즈니스용 OneDrive 및 SharePoint Online 공유 링크 제공
- 모임 녹음/녹화를 더 빠르게 사용할 수 있습니다.
- 모임에 녹음된 기본 스크립트 검색
- **로컬화** 테넌트 지원
- 다중 지역 지원 – 녹음/녹화는 해당 사용자의 특정 지역에 저장됩니다.
- BYOK(Bring Your Own Key) 지원

[오늘 사용할 수 있는 기능과 향후 예상되는 기능](/stream/streamnew/features-new-version-stream)의 전체 목록을 참조하세요.

자세한 내용은 "Microsoft Teams 모임 녹음/녹화의 새로운 기능"을 시청하세요.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>비즈니스용 OneDrive 및 SharePoint Online 모임 녹음/녹화 옵션 설정

모임 녹음/녹화 옵션은 Teams 정책 수준의 설정입니다. 다음 예는 글로벌 정책을 설정하는 방법을 보여줍니다. 사용자에게 할당한 정책에 대해 모임 녹음/녹화 옵션을 설정했는지 확인하세요.

> [!Note]
> Teams 모임 정책 변경 사항이 전파되는 데 시간이 걸립니다. 몇 시간을 설정한 후 다시 확인한 다음 로그아웃했다가 Teams Desktop 앱에 다시 로그인하거나 컴퓨터를 다시 시작하세요.

1. Teams PowerShell PowerShell을 설치합니다.

   > [!NOTE]
   > 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다. [PowerShell로 비즈니스용 Skype Online 관리](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)를 참조하세요.

2. PowerShell을 관리자로 시작합니다.

3. [Teams PowerShell 모듈](./teams-powershell-install.md)을 설치합니다.

4. MicrosoftTeams 모듈을 가져오고 Teams 관리자로 로그인합니다.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 사용하여 Stream 저장소에서 비즈니스용 OneDrive 및 SharePoint Online으로 전환하도록 Teams 모임 정책을 설정합니다.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 일부 사용자가 이끌이별 또는 사용자별 정책을 할당한 경우 비즈니스용 OneDrive 및 SharePoint Online에도 모임 녹음/녹화를 저장하도록 하려면 이 정책에서 이 설정을 설정해야 합니다. 자세한 내용은 [Teams에서 모임 정책 관리](meeting-policies-in-teams.md)를 참조하세요.

## <a name="learn-more"></a>자세한 정보

Teams 클라우드 모임 녹음/녹화에 대해 자세히 알아보려면 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요. 해당 문서에서는 녹음/녹화 설정, 관리, 거버넌스, 권한 및 스토리지에 대해 자세히 알아볼 수 있습니다.
