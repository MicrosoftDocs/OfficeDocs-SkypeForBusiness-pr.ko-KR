---
title: Google Workspace에 대한 Microsoft Teams 모임 추가 기능 설정
ms.author: mabond
author: mkbond007
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Google 작업 영역에 대한 Microsoft Teams 모임 추가 기능을 설정하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd6897b770215af75862438996a365acd463c96
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706645"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google Workspace에 대한 Microsoft Teams 모임 추가 기능 설정

Microsoft Teams 모임 추가 기능을 사용하면 Google 일정 사용자가 Google Workspace에서 직접 Microsoft Teams 모임을 예약하고 참가할 수 있습니다. 사용자는 비디오 및 오디오 회의, 화면 공유, 모임 채팅, 디지털 화이트보드 등을 포함한 Teams 모임 기능에 액세스할 수 있습니다. 회사, 학교 및 생활 전반에 걸쳐 더 많은 작업을 수행할 수 있도록 연결하고 체계적으로 유지합니다.

테넌트 사용자가 앱에 액세스하려면 먼저 Teams 관리자가 Google 작업 영역에 대한 Microsoft Teams 모임 추가 기능을 사용하도록 설정해야 합니다.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Azure Portal Google Workspace에 대한 Microsoft Teams 모임 추가 기능을 사용하거나 사용하지 않도록 설정합니다.

테넌트 관리자는 Azure Portal 사용하여 조직의 관리자 계정에서 Google Workspace에 대한 Microsoft Teams 모임 추가 기능을 사용하거나 사용하지 않도록 설정할 수 있습니다.

추가 기능은 기본적으로 사용하도록 설정되어 있습니다.

1. Azure Portal 로그인합니다.

2. **엔터프라이즈 애플리케이션****모든 애플리케이션** > 을 선택합니다.

3. **Google 작업 영역에 대한 Microsoft Teams 모임 추가** 기능을 검색합니다.

   ![모든 애플리케이션을 표시하는 Azure Portal.](media/aad-add-google-workspace.png)

4. **예를** 선택합니다.

   ![google 작업 영역 속성을 보여 주는 Azure Portal.](media/google-workspace-properties.png)

5. (선택 사항) 추가 기능을 사용하지 않도록 설정하려면 4단계에서 **예** 대신 **아니요** 를 선택합니다.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>PowerShell을 사용하여 Google 작업 영역에 대한 Microsoft Teams 모임 추가 기능 사용 안 함

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

자세한 내용은 [Azure PowerShell 사용하여 Azure 서비스 주체 만들기를](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0) 참조하세요.

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Google Workspace에 대한 Microsoft Teams 모임 추가 기능 삭제

지침은 Google [작업 영역 Marketplace 앱 삭제](https://support.google.com/a/answer/6216211?hl=en) 에 대한 Google 설명서를 참조하세요.

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>PowerShell을 사용하여 Google 작업 영역에 대한 Microsoft Teams 모임 추가 기능 만들기

Microsoft Teams 모임 추가 기능이 테넌트에 없는 경우 PowerShell을 사용하여 만들 수 있습니다. 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
