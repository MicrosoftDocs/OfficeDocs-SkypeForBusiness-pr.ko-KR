---
title: Google 작업 영역용 Microsoft Teams 모임 추가 기능 설정
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Google 작업 영역의 Microsoft Teams 모임 추가 기능을 설정하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120699"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="70e6c-103">Google 작업 영역용 Microsoft Teams 모임 추가 기능 설정</span><span class="sxs-lookup"><span data-stu-id="70e6c-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="70e6c-104">Microsoft Teams 모임 추가 기능을 사용하면 Google 일정 사용자가 Google 작업 영역에서 직접 Microsoft Teams 모임을 예약하고 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="70e6c-105">사용자는 비디오 및 오디오 회의, 화면 공유, 모임 채팅, 디지털 화이트보드 등을 포함한 Teams 모임 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="70e6c-106">업무, 학교 및 생활에서 더 많은 작업을 수행하기 위해 연결되고 체계적으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="70e6c-107">테넌트 사용자가 앱에 액세스할 수 있도록 하기 전에 Google 작업 영역용 Microsoft Teams 모임 추가 기능을 Teams 관리자가 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="70e6c-108">Azure Portal에서 Google 작업 영역의 Microsoft Teams 모임 추가 기능 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="70e6c-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="70e6c-109">테넌트 관리자는 Azure Portal을 사용하여 조직의 관리자 계정에서 Google 작업 영역의 Microsoft Teams 모임 추가 기능을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="70e6c-110">추가 기능을 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="70e6c-111">Azure Portal에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="70e6c-112">엔터프라이즈 **애플리케이션 모든**  >  **애플리케이션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70e6c-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="70e6c-113">Google **작업 영역의 Microsoft Teams 모임** 추가 기능을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![모든 애플리케이션을 보여주는 Azure Portal](media/aad-add-google-workspace.png)

4. <span data-ttu-id="70e6c-115">예 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70e6c-115">Select **Yes**.</span></span>

   ![Google 작업 영역 속성을 보여주는 Azure Portal](media/google-workspace-properties.png)

5. <span data-ttu-id="70e6c-117">(선택 사항) 추가 기능을 사용하지 않도록  설정하려면 4단계에서 예 대신 **아니요를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70e6c-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="70e6c-118">PowerShell을 사용하여 Google 작업 영역의 Microsoft Teams 모임 추가 기능 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="70e6c-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

<span data-ttu-id="70e6c-119">자세한 내용은 [Azure PowerShell을 사용하여 Azure 서비스 주체 만들기를 참조하세요.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)</span><span class="sxs-lookup"><span data-stu-id="70e6c-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="70e6c-120">Google 작업 영역의 Microsoft Teams 모임 추가 기능 삭제</span><span class="sxs-lookup"><span data-stu-id="70e6c-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="70e6c-121">지침은 Google 워크스페이스 Marketplace 앱을 [삭제하는 Google](https://support.google.com/a/answer/6216211?hl=en) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70e6c-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>