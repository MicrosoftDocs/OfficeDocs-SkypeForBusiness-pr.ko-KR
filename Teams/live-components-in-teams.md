---
title: 라이브 구성 요소 관리 Teams
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
description: 라이브 구성 요소를 관리하는 방법을 Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd65370a000bac3d91ae8f3dbc07a121add62ec1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772739"
---
# <a name="manage-live-components-in-teams"></a>라이브 구성 요소 관리 Teams

채팅의 Teams 구성 요소는 함께 아이디어를 만들고, 만들고, 결정을 내릴 수 있는 새로운 방법을 제공합니다. 테이블, 작업 목록 또는 단락과 같은 구성 요소를 보내면 채팅의 모든 사람이 인라인을 편집하고 변경 내용을 볼 수 있습니다. 즉, 모임을 더 적게 개최하고 긴 채팅 스레드의 필요성을 최소화하면서 팀에서 아이디어와 피드백을 수집할 수 있습니다.

**작업을 함께 더 빠르게 수행할 수 있습니다.** 크라우드 소스 의제, 그룹의 작업 항목을 추적하거나, 총체적으로 메모를 작성합니다. 라이브 구성 요소를 사용하여 몇 가지 시나리오만 쉽게 만들 수 있습니다.

**구성 요소를 공유합니다.** 이 릴리스에서는 라이브 구성 요소를 다른 채팅으로 공유할 Teams 있습니다. 받는 사람은 어디에 있든 편집할 수 있으며 변경 내용에 상관없이 즉시 업데이트를 볼 수 있습니다. 이후 릴리스에서는 라이브 구성 요소가 모든 Teams 및 채널, Outlook 모든 애플리케이션에서 Microsoft 365 지원됩니다.

**채팅에서 시작하고 거기에서 빌드합니다.** 채팅에서 만드는 Teams 모든 구성 요소가 자동으로 OneDrive. 따라서 채팅에서 공동 작업을 시작한 다음 나중에 파일로 이동하여 편집할 수 있는 시각적 공간이 커지고 원하는만큼 구성 요소를 추가할 수 있습니다.

## <a name="clients-and-platforms"></a>클라이언트 및 플랫폼

Mac, Teams, Windows, iOS 및 Android에서 사용할 수 있습니다.

9월 초부터 라이브 구성 요소를 전 세계적으로 사용할 수 있습니다. 9월 하순에는 Mod(정부 커뮤니티 클라우드)에 GCC.

## <a name="settings-management"></a>설정 관리

라이브 구성 요소는 Microsoft Fluid Framework Microsoft 365 관리 센터가 아닌 SharePoint 온라인에서 제어되는 Teams 있습니다.

최신 버전의 온라인 [powerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) 모듈이 SharePoint 테넌트에서 모든 Fluid 환경을 사용하도록 설정하거나 사용하지 않도록 Office 365 필요합니다. Microsoft Fluid Framework 모든 대상 릴리스 테넌트에 **대해 ON으로** 기본값을 지정합니다. 라이브 구성 요소는 공동 작업을 위해 설계되어 있기 때문에 테넌트가 다른 파일 형식에 대한 보기 전용으로 기본값으로 설정되어 있는 경우에도 구성 요소는 항상 다른 사용자가 편집할 수 있는 것으로 공유됩니다. 자세한 **내용은** 설정 옆에 있는 자세한 정보 링크를 참조하세요.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>온라인 PowerShell cmdlet을 통해 Fluid Framework 활성화되어 SharePoint 확인

1. [커넥트 PowerShell을 SharePoint 합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 인수 없이 Fluid Framework cmdlet을 실행하여 Get-SPOTenant 활성화되어 있는지 확인합니다.

3. IsFluidEnabled의 값이 **true인지 확인**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>온라인 Fluid Framework PowerShell cmdlet을 통해 SharePoint 설정 

1. [커넥트 PowerShell을 SharePoint 합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   변경은 테넌트 전체에 적용하는 데 짧은 시간이 걸릴 것입니다. 

이 기능은 데스크톱, Teams Windows, iOS, Android에서 사용할 수 있습니다. 사용하도록 설정하면 이러한 클라이언트에 대한 메시지 작성 환경의 라이브 구성 요소를 삽입하기 위한 새 옵션이 표시됩니다.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>온라인 PowerShell cmdlet을 Fluid Framework 통해 SharePoint 사용 안 하세요.

1. [커넥트 PowerShell을 SharePoint 합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. -IsFluidEnabled Set-SPOTenant cmdlet Set-SPOTenant -IsFluidEnabled $false. 

   변경은 테넌트 전체에 적용하는 데 짧은 시간이 걸릴 것입니다. 

이 기능을 다시 사용하도록 설정해야 하는 경우 온라인 PowerShell cmdlet에서 SharePoint 수 있습니다.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>알려진 제한 사항

- 앱을 다시 시작한 후 테이블 또는 작업 Teams 첫 번째 구성 요소로 만드는 데 다소 시간이 걸릴 수 있습니다.

- 다른 채팅 구성원은 at(@) 기호로 언급될 때 전자 메일 알림을 받게 됩니다. (활동 피드의 Teams 알림은 곧 사용할 수 있습니다.)

- 검색 내에서 라이브 Teams 검색하면 채팅 메시지 자체가 아니라 office.com 구성 요소에 대한 링크가 반환됩니다.

- 라이브 구성 요소는 페더리된 채팅에서 비활성화되어 Azure B2B를 사용하여 게스트 계정과 일반 채팅에 사용할 수 있습니다.

- 여러 채널 및 기타 Teams 앱에서 구성 요소를 공유할 수 Microsoft 365 받는 사람은 현재 대부분의 장소에서 링크를 얻을 수 있습니다. 인라인 편집은 향후 더 많은 환경을 위해 계획됩니다.

## <a name="storage-of-fluid-files"></a>Storage `.fluid` 파일

**저장 `.fluid` 방법**

에서 만든 라이브 Teams 작성자의 문서에 `.fluid` 저장된 파일로 비즈니스용 OneDrive. 파일 형식의 비즈니스용 OneDrive 사용자가 모든 문서와 같은 라이브 구성 요소(파일)를 쉽게 만들고 `.fluid` 검색하고 관리할 Office 있습니다.

사용자는 Office.com에서 파일에서 콘텐츠를 `.fluid` 검색하고 비즈니스용 OneDrive.
`.fluid` 파일은 eDiscovery, 감사, 보고 및 법적 보류와 같은 데이터 거버넌스 기능과 함께 작동합니다.

`.fluid`이제 Office.com 및 비즈니스용 OneDrive(예: 최근 및 권장 영역)에 표시됩니다.
`.fluid`파일을 이전 버전으로 복원할 비즈니스용 OneDrive.

채팅 참가자는 라이브 구성 요소를 OneDrive 계정이 있어야 합니다. 유효한 OneDrive 계정이 없는 경우 채팅 참가자는 여전히 유효한 계정이 있는 다른 사용자가 만든 구성 요소에서 공동 작업할 OneDrive 수 있지만 자체 계정을 만들 수 없습니다.

[파일을](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) OneDrive 사이트로 SharePoint 라이브 구성 요소가 채팅에서 로드되지 Teams `.fluid` 됩니다.

**파일의 소유자가 회사를 떠날 경우 어떻게 하나요?**

[OneDrive](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) 보존 정책은 사용자가 만든 다른 콘텐츠와 같은 파일에 `.fluid` 적용됩니다.

**파일은 `.fluid` 어떻게 공유하나요?**

라이브 구성 요소는 채팅에 삽입하거나 Teams 채팅에서 다른 채팅으로 복사할 수 있습니다. (라이브 구성 요소는 채널에서 아직 지원되지 않습니다.) 테넌트의 기존 사용 권한은 기본적으로 제공되지만 사용자는 보내기 전에 권한을 변경하여 모든 사용자가 액세스할 수 있도록 할 수 있습니다.

Teams 채팅에서 구성 요소를 열면 Office 문서에 대해 제공되는 공유 옵션과 마찬가지로 창 맨 위에 공유 기능을 Office 있습니다.

**파일이 `.fluid` 손상되거나 손상된 경우 어떻게 하나요?**

버전 기록을 사용하면 이전 버전의 파일을 검토하고 복사할 수 있습니다.

**파일을 열고 편집할 수 있는 앱은 `.fluid` 무엇입니까?**

`.fluid`파일은 브라우저의 링크(예: Office.com)로 열 수 있으며, 채팅의 라이브 구성 요소로만 Teams 수 있습니다. 다운로드한 경우 온라인 또는 온라인에 다시 업로드하지 않고는 다시 비즈니스용 OneDrive SharePoint 수 없습니다.
