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
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814467"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="de72f-103">Microsoft 팀 PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="de72f-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="de72f-104">이 문서에서는 [PowerShellGet](/powershell/scripting/gallery/installing-psget)을 사용 하 여 Microsoft 팀 PowerShell 모듈을 설치 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="de72f-105">이러한 지침은 [Azure 클라우드 셸](/azure/cloud-shell/overview), Linux, Macos, Windows 플랫폼에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="de72f-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de72f-106">Requirements</span></span>

<span data-ttu-id="de72f-107">모든 플랫폼에서 팀 PowerShell에는 PowerShell 5.1 이상을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="de72f-108">운영 체제에 사용할 수 있는 [최신 버전의 PowerShell](/powershell/scripting/install/installing-powershell) 을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="de72f-109">PowerShell 7 및 팀 PowerShell에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="de72f-110">최상의 환경을 위해서는 PowerShell 5.1를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="de72f-111">팀 PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="de72f-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="de72f-112">최상의 환경을 위해서는 일반 가용성 (GA) 또는 공개 미리 보기 모듈을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="de72f-113">공동 작업을 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-113">They're not intended to work together.</span></span>


<span data-ttu-id="de72f-114">**PowerShellGet** cmdlet을 사용 하 여 팀 PowerShell 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="de72f-115">시스템의 모든 사용자에 대해 모듈을 설치 하려면 관리자 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="de72f-116">Windows에서 **관리자 권한으로 실행** 을 사용 하 여 PowerShell 세션을 시작 하거나 `sudo` Macos 또는 Linux의 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="de72f-117">기본적으로 PowerShell 갤러리 (PSGallery)는 **PowerShellGet**에 대해 신뢰할 수 있는 리포지토리로 구성 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="de72f-118">처음으로 PSGallery를 사용 하는 경우 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="de72f-119">설치를 계속 하려면 **yes** 또는 **yes에** 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="de72f-120">팀 PowerShell 공용 미리 보기 설치</span><span class="sxs-lookup"><span data-stu-id="de72f-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="de72f-121">팀 PowerShell의 공용 Preview 버전을 사용 하는 경우 먼저 비즈니스용 Skype Online Connector를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="de72f-122">시스템의 모든 사용자에 대해 팀 PowerShell 공용 미리 보기 모듈을 설치 하려면 관리자 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="de72f-123">Windows에서 **관리자 권한으로 실행** 을 사용 하 여 PowerShell 세션을 시작 하거나 `sudo` Macos 또는 Linux의 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="de72f-124">PowerShell 5.1를 사용 중인 경우에는 **PowerShellGet** 모듈을 미리 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="de72f-125">**PowerShellGet**을 업데이트 한 후에는 관리자 권한 PowerShell 세션을 닫았다가 다시 열어 최신 **PowerShellGet** 이 로드 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="de72f-126">팀 PowerShell 공개 미리 보기를 설치 하려면 아래에서 PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="de72f-127">[Powershell 갤러리](https://www.powershellgallery.com/packages/MicrosoftTeams) 또는 powershell에서 최신 preview 버전을 찾을 수 있습니다 ("Find-Module MicrosoftTeams-allowprerelease" 실행).</span><span class="sxs-lookup"><span data-stu-id="de72f-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="de72f-128">비즈니스용 Skype Online 커넥터 설치</span><span class="sxs-lookup"><span data-stu-id="de72f-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="de72f-129">비즈니스용 Skype Online 커넥터는 현재 최신 팀 PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="de72f-130">최신 [팀 PowerShell 공용 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용 하 고 있는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="de72f-131">서명하세요</span><span class="sxs-lookup"><span data-stu-id="de72f-131">Sign in</span></span>

<span data-ttu-id="de72f-132">팀 PowerShell 작업을 시작 하려면 Azure 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="de72f-133">최신 [팀 PowerShell 공용 preview 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용 하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="de72f-134">팀 업데이트 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de72f-134">Update Teams PowerShell</span></span>

<span data-ttu-id="de72f-135">팀 PowerShell을 업데이트 하려면 새 관리자 권한 PowerShell 명령 프롬프트를 열고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="de72f-136">팀 PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈 업데이트는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="de72f-137">PowerShell을 닫고 새 관리자 권한 PowerShell 세션을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="de72f-138">팀 제거 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de72f-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="de72f-139">팀 PowerShell을 제거 하려면 새 관리자 권한 PowerShell 명령 프롬프트를 열고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="de72f-140">팀 PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈을 제거 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="de72f-141">PowerShell을 닫고 새 관리자 권한 PowerShell 세션을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de72f-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="de72f-142">Next Steps</span></span>

<span data-ttu-id="de72f-143">이제 팀 PowerShell을 사용 하 여 팀을 관리할 준비가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="de72f-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="de72f-144">시작 하려면 [팀 PowerShell을 사용 하 여 팀 관리](teams-powershell-managing-teams.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de72f-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="de72f-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="de72f-145">Related topics</span></span>

[<span data-ttu-id="de72f-146">팀을 사용 하 여 팀 관리 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de72f-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="de72f-147">팀 PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="de72f-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="de72f-148">Microsoft 팀 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="de72f-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="de72f-149">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="de72f-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
