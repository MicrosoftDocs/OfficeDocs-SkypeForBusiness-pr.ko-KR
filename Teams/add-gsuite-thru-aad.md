---
title: Google 용 Microsoft 팀 모임 추가 기능 설정 작업 영역
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
description: Google 용 Microsoft 팀 모임 추가 기능을 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387297"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="86727-103">Google 용 Microsoft 팀 모임 추가 기능 설정 작업 영역</span><span class="sxs-lookup"><span data-stu-id="86727-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="86727-104">Microsoft 팀 모임 추가 기능을 사용 하면 Google 일정 사용자가 Google Workspace에서 직접 Microsoft 팀 모임을 예약 하 고 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86727-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="86727-105">사용자는 비디오 및 오디오 회의, 화면 공유, 모임 채팅, 디지털 화이트 보드 등을 비롯 한 팀 모임 기능을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86727-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="86727-106">업무, 학교, 생활을 통해 더 많은 작업을 수행할 수 있도록 연결 및 구성을 유지 하세요.</span><span class="sxs-lookup"><span data-stu-id="86727-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="86727-107">테 넌 트 사용자가 앱에 액세스할 수 있으려면 먼저 팀 관리자가 Google 용 Microsoft 팀 모임 추가 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86727-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="86727-108">Azure 포털에서 Google 용 Microsoft 팀 모임 추가 기능 사용 또는 사용 안 함 작업</span><span class="sxs-lookup"><span data-stu-id="86727-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="86727-109">테 넌 트 관리자는 Azure 포털을 사용 하 여 조직의 관리자 계정에서 Google 용 Microsoft 팀 모임 추가 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86727-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="86727-110">추가 기능은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86727-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="86727-111">Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86727-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="86727-112">모든 응용 프로그램의 **엔터프라이즈 응용 프로그램**  >  **All applications** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86727-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="86727-113">**Google 용 Microsoft 팀 모임 추가 기능 검색 작업 영역**</span><span class="sxs-lookup"><span data-stu-id="86727-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![모든 응용 프로그램을 표시 하는 Azure 포털](media/aad-add-google-workspace.png)

4. <span data-ttu-id="86727-115">**예** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86727-115">Select **Yes**.</span></span>

   ![Google workspace 속성을 표시 하는 Azure 포털](media/google-workspace-properties.png)

5. <span data-ttu-id="86727-117">) 추가 기능을 사용 하지 않도록 설정 하려면 4 단계에서 **예** 대신 **아니요** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86727-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="86727-118">PowerShell을 사용 하 여 Google 용 Microsoft 팀 모임 추가 기능 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="86727-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="86727-119">자세한 내용은 [Azure PowerShell을 사용 하 여 azure 서비스 사용자 만들기](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86727-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="86727-120">Google 용 Microsoft 팀 모임 추가 기능 삭제 작업 영역</span><span class="sxs-lookup"><span data-stu-id="86727-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="86727-121">Google 설명서에서 [Google 작업 영역 마켓플레이스 앱 삭제](https://support.google.com/a/answer/6216211?hl=en) 에 대 한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86727-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
