---
title: Microsoft 팀 PowerShell 설치
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell 컨트롤을 사용 하 여 Microsoft 팀을 관리 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944109"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="fbb6a-103">Microsoft 팀 PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="fbb6a-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="fbb6a-104">이 문서에서는 [PowerShellGet](/powershell/scripting/gallery/installing-psget)을 사용 하 여 Microsoft 팀 PowerShell 모듈을 설치 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="fbb6a-105">이러한 지침은 [Azure 클라우드 셸](/azure/cloud-shell/overview), Linux, Macos, Windows 플랫폼에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="fbb6a-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fbb6a-106">Requirements</span></span>

<span data-ttu-id="fbb6a-107">팀 PowerShell은 모든 플랫폼에서 PowerShell 6.2.4 이상에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-107">Teams PowerShell works with PowerShell 6.2.4 and later on all platforms.</span></span> <span data-ttu-id="fbb6a-108">Windows의 PowerShell 5.1 에서도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-108">It is also supported with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="fbb6a-109">운영 체제에 사용할 수 있는 [최신 버전의 PowerShell](/powershell/scripting/install/installing-powershell) 을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-109">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> <span data-ttu-id="fbb6a-110">PowerShell 6.2.4 이상에서 실행 되는 경우 팀 PowerShell에는 추가 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-110">Teams PowerShell has no additional requirements when run on PowerShell 6.2.4 and later.</span></span>

> [!WARNING]
> <span data-ttu-id="fbb6a-111">PowerShell 7 및 팀 PowerShell에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-111">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="fbb6a-112">최상의 환경을 위해서는 PowerShell 5.1를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-112">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="fbb6a-113">팀 PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="fbb6a-113">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="fbb6a-114">최상의 환경을 위해서는 일반 가용성 (GA) 또는 공개 미리 보기 모듈을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-114">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="fbb6a-115">공동 작업을 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-115">They're not intended to work together.</span></span>


<span data-ttu-id="fbb6a-116">**PowerShellGet** cmdlet을 사용 하 여 팀 PowerShell 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-116">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="fbb6a-117">시스템의 모든 사용자에 대해 모듈을 설치 하려면 관리자 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-117">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="fbb6a-118">Windows에서 **관리자 권한으로 실행** 을 사용 하 여 PowerShell 세션을 시작 하거나 `sudo` Macos 또는 Linux의 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-118">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="fbb6a-119">기본적으로 PowerShell 갤러리 (PSGallery)는 **PowerShellGet**에 대해 신뢰할 수 있는 리포지토리로 구성 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-119">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="fbb6a-120">처음으로 PSGallery를 사용 하는 경우 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-120">The first time you use the PSGallery, you'll see the following message:</span></span>

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="fbb6a-121">설치를 응답 `Yes` 하거나 `Yes to All` 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-121">Answer `Yes` or `Yes to All` to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="fbb6a-122">팀 PowerShell 공용 미리 보기 설치</span><span class="sxs-lookup"><span data-stu-id="fbb6a-122">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="fbb6a-123">팀 PowerShell의 공용 Preview 버전을 사용 하는 경우 먼저 비즈니스용 Skype Online Connector를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-123">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="fbb6a-124">시스템의 모든 사용자에 대해 팀 PowerShell 공용 미리 보기 모듈을 설치 하려면 관리자 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-124">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="fbb6a-125">Windows에서 **관리자 권한으로 실행** 을 사용 하 여 PowerShell 세션을 시작 하거나 `sudo` Macos 또는 Linux의 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-125">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="fbb6a-126">PowerShell 5.1를 사용 중인 경우에는 **PowerShellGet** 모듈을 미리 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-126">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="fbb6a-127">**PowerShellGet**을 업데이트 한 후에는 관리자 권한 PowerShell 세션을 닫았다가 다시 열어 최신 **PowerShellGet** 이 로드 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-127">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="fbb6a-128">팀 Powershell 공개 미리 보기를 설치 하려면 아래에서 PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-128">To install Teams Powershell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="fbb6a-129">비즈니스용 Skype Online 커넥터 설치</span><span class="sxs-lookup"><span data-stu-id="fbb6a-129">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="fbb6a-130">비즈니스용 Skype Online 커넥터는 현재 팀 PowerShell 공개 미리 보기의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-130">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="fbb6a-131">이 기능을 팀 PowerShell의 GA 릴리스에 겹쳐서 표시 하면 비즈니스용 Skype Online 커넥터를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-131">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="fbb6a-132">[비즈니스용 Skype PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드 하 여 설치한 후 PowerShell에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-132">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="fbb6a-133">서명하세요</span><span class="sxs-lookup"><span data-stu-id="fbb6a-133">Sign in</span></span>

<span data-ttu-id="fbb6a-134">팀 PowerShell 작업을 시작 하려면 Azure 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-134">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="fbb6a-135">최신 [팀 PowerShell 공용 preview 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용 하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-135">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="fbb6a-136">팀 업데이트 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbb6a-136">Update Teams PowerShell</span></span>

<span data-ttu-id="fbb6a-137">팀 PowerShell을 업데이트 하려면 새 관리자 권한 PowerShell 명령 프롬프트를 열고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="fbb6a-138">팀 PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈 업데이트는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="fbb6a-139">PowerShell을 닫고 새 관리자 권한 PowerShell 세션을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="fbb6a-140">팀 제거 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbb6a-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="fbb6a-141">팀 PowerShell을 제거 하려면 새 관리자 권한 PowerShell 명령 프롬프트를 열고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="fbb6a-142">팀 PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈을 제거 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="fbb6a-143">PowerShell을 닫고 새 관리자 권한 PowerShell 세션을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fbb6a-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fbb6a-144">Next Steps</span></span>

<span data-ttu-id="fbb6a-145">이제 팀 PowerShell을 사용 하 여 팀을 관리할 준비가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="fbb6a-146">시작 하려면 [팀 PowerShell을 사용 하 여 팀 관리](teams-powershell-managing-teams.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbb6a-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fbb6a-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fbb6a-147">Related topics</span></span>

[<span data-ttu-id="fbb6a-148">팀을 사용 하 여 팀 관리 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbb6a-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="fbb6a-149">팀 PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="fbb6a-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="fbb6a-150">Microsoft 팀 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="fbb6a-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="fbb6a-151">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="fbb6a-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
