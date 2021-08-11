---
title: 2013에서 라이브 구성 요소 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 2016에서 라이브 구성 요소를 관리하는 Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305020"
---
# <a name="manage-live-components-in-teams"></a>2013에서 라이브 구성 요소 Teams

채팅의 Teams 구성 요소는 함께 생각하고, 만들고, 결정을 내리는 새로운 방법을 제공합니다. 테이블, 작업 목록 또는 단락과 같은 구성 요소를 보내 채팅의 모든 사람이 인라인으로 편집하고 변경 내용을 볼 수 있습니다. 즉, 모임 수를 줄이면서 긴 채팅 스레드의 필요성을 최소화하면서 팀에서 아이디어와 피드백을 수집할 수 있습니다.

**작업을 함께 더 빠르게 수행하세요.** 어젠더를 크라우드 소스로 작성하거나, 그룹의 작업 항목을 추적하거나, 메모를 총체적으로 작성합니다. 이러한 시나리오는 라이브 구성 요소를 사용하여 몇 가지 시나리오에 불과합니다.

**구성 요소를 공유합니다.** 이 릴리스에서는 라이브 구성 요소를 다른 공유 Teams 수 있습니다. 받는 사람은 어디서든 편집할 수 있으며, 변경된 위치와 상관없이 즉시 업데이트를 볼 수 있습니다. 이후 릴리스에서 라이브 구성 요소는 모든 Teams 및 채널, Outlook 및 모든 Microsoft 365 지원됩니다.

**채팅에서 시작하고 거기에서 빌드합니다.** 채팅에서 만든 모든 구성 Teams 자동으로 파일로 OneDrive. 따라서 채팅에서 공동 작업을 시작한 다음 나중에 파일로 이동하여 편집할 수 있는 더 큰 시각적 공간이 있으며 원하는 수만큼 구성 요소를 추가할 수 있습니다.

## <a name="clients-and-platforms"></a>클라이언트 및 플랫폼

Mac, Teams, iOS 및 Android의 Windows 앱에서 사용할 수 있습니다.

9월 초부터 라이브 구성 요소를 전 세계에 사용할 수 있습니다. 9월 말에는 Mod(정부 커뮤니티 클라우드 사용할 수 GCC.

## <a name="settings-management"></a>설정 관리

라이브 구성 요소는 Microsoft Fluid Framework 제품군에서 Microsoft 365 지원하며 SharePoint Teams 관리 센터가 아닌 SharePoint 제어합니다.

온라인 [PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) 모듈의 최신 버전이 SharePoint 테넌트 전체에서 모든 유동 환경을 활성화 또는 Office 365 필요합니다. Microsoft Fluid Framework 대상 릴리스 테넌트의 기본값은 **ON입니다.** 라이브 구성 요소는 공동 작업을 위해 설계되어 있기 때문에 테넌트가 다른 파일 형식에 대해 보기 전용으로 설정되어 있는 경우에도 구성 요소는 항상 다른 사용자가 편집 가능한 것으로 공유합니다. 자세한 **내용은** 설정 옆에 있는 자세한 정보 링크를 참조하세요.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>온라인 PowerShell cmdlet을 Fluid Framework 사용하도록 설정되어 SharePoint 확인

1. [커넥트 PowerShell을 SharePoint 합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 인수 없이 Fluid Framework cmdlet을 실행하여 Get-SPOTenant 활성화되어 있는지 확인합니다.

3. IsFluidEnabled 값이 **true인지 확인**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>온라인 Fluid Framework PowerShell cmdlet을 통해 SharePoint 설정 

1. [커넥트 PowerShell을 SharePoint 합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. -IsFluidEnabled cmdlet을 사용하여 Set-SPOTenant -IsFluidEnabled $true 
   
   변경을 테넌시 전체에 적용하는 데 짧은 시간이 걸릴 것입니다. 

이 기능은 데스크톱, Teams Windows, iOS, Android에서 사용할 수 있습니다. 사용하도록 설정하면 이러한 클라이언트에 대한 메시지 작성 환경의 라이브 구성 요소를 삽입하는 새로운 옵션이 표시됩니다.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>온라인 powerShell cmdlet을 Fluid Framework SharePoint 사용 안 하게

1. [커넥트 PowerShell을 SharePoint 합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. -IsFluidEnabled Set-SPOTenant cmdlet을 Set-SPOTenant 유동을 $false. 

   변경을 테넌시 전체에 적용하는 데 짧은 시간이 걸릴 것입니다. 

이 기능을 다시 사용하도록 설정해야 하는 경우 온라인 PowerShell cmdlet을 SharePoint 수 있습니다.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>알려진 제한

- 앱을 다시 시작한 후 테이블 또는 작업 목록을 Teams 구성 요소로 만드는 데 다소 시간이 걸릴 수 있습니다.

- @(@) 기호로 언급된 다른 채팅 구성원은 전자 메일 알림을 받게 됩니다. (Teams 작업 피드의 언급 알림은 곧 제공될 예정입니다.)

- Teams 검색 내에서 라이브 구성 요소를 검색하면 채팅 메시지 자체가 아니라 office.com 링크가 반환됩니다.

- 라이브 구성 요소는 페더래드 채팅에서 사용하지 않도록 설정되어 있으며 Azure B2B를 사용하는 게스트 계정과의 일반 채팅을 사용할 수 있습니다.

- Teams 다른 Microsoft 365 앱에서 구성 요소를 공유할 수 있는 반면, 받는 사람은 현재 대부분의 장소에서 링크를 얻게 됩니다. 인라인 편집은 향후 더 많은 환경을 계획할 예정입니다.

## <a name="storage-of-fluid-files"></a>Storage `.fluid` 파일 수

**저장 `.fluid` 방법**

이 문서에서 만든 Teams 구성 요소는 작성자의 웹 서버에 `.fluid` 저장된 파일로 비즈니스용 OneDrive. 파일을 비즈니스용 OneDrive 수 있는 것은 사용자가 모든 문서에서처럼 쉽게 라이브 구성 요소(파일)를 만들고 `.fluid` 검색하고 관리할 수 Office 의미입니다.

사용자는 Office.com에서 파일에서 콘텐츠를 `.fluid` 검색할 수 비즈니스용 OneDrive.
`.fluid` 파일은 eDiscovery, 감사, 보고 및 법적 보유와 같은 데이터 거버넌스 기능을 사용할 수 있습니다.

`.fluid`이제 파일이 Office.com 및 비즈니스용 OneDrive 및 권장 영역에 표시됩니다.
`.fluid`파일을 이전 버전으로 복원할 수 비즈니스용 OneDrive.

채팅 참가자는 라이브 구성 요소를 OneDrive 계정이 있어야 합니다. 유효한 OneDrive 계정이 없는 경우 채팅 참가자는 여전히 유효한 OneDrive 계정이 있는 다른 사용자가 만든 구성 요소에 대해 공동 작업을 할 수 있지만 직접 만들 수는 없습니다.

[파일을](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) OneDrive 사이트로 SharePoint 사이트로 이동하면 라이브 구성 요소가 Teams `.fluid` 로드되지 않습니다.

**파일 소유자가 퇴사하면 어떻게 하나요?**

OneDrive 보존 [정책은](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) 사용자가 만든 다른 콘텐츠와 같은 파일에 `.fluid` 적용됩니다.

**파일이 `.fluid` 공유되는 방식**

라이브 구성 요소는 채팅에 삽입하거나 Teams 채팅에서 다른 채팅으로 복사할 수 있습니다. 라이브 구성 요소는 채널에서 아직 지원되지 않습니다. 테넌트의 기존 사용 권한은 기본적으로 사용되지만 사용자가 보내기 전에 권한을 변경하여 모든 사용자가 액세스할 수 있도록 할 수 있습니다.

Office.com에서 Teams 채팅에서 구성 요소를 열면 다른 Office 문서에 대해 제공되는 공유 옵션과 비슷하게 창 맨 위에 공유 기능이 제공됩니다.

**파일이 손상되거나 손상되면 `.fluid` 어떻게 하나요?**

버전 기록을 사용하면 이전 버전의 파일을 검토하고 복사할 수 있습니다.

**어떤 앱이 파일을 열고 편집할 수 `.fluid` 있나요?**

`.fluid`파일은 Office.com과 같은 브라우저의 링크로만 열 수 있으며 채팅에서 라이브 구성 Teams 있습니다. 다운로드한 경우 먼저 온라인 또는 온라인에 다시 업로드하지 않고는 다시 비즈니스용 OneDrive SharePoint 없습니다.
