---
title: Microsoft Teams PowerShell 설치
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
description: Microsoft Teams를 관리하기 위해 PowerShell 컨트롤을 사용하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662023"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="4c989-103">Microsoft Teams PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="4c989-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="4c989-104">이 문서에서는 [PowerShellGet을](/powershell/scripting/gallery/installing-psget)사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="4c989-105">이러한 지침은 [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS 및 Windows 플랫폼에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4c989-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4c989-106">Requirements</span></span>

<span data-ttu-id="4c989-107">Teams PowerShell에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="4c989-108">운영 체제에 사용할 수 있는 [최신 버전의 PowerShell을](/powershell/scripting/install/installing-powershell) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="4c989-109">PowerShell 7 및 Teams PowerShell에는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="4c989-110">최상의 환경을 위해 PowerShell 5.1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="4c989-111">Teams PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="4c989-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="4c989-112">최상의 환경을 위해 GA(일반 공급) 또는 공개 미리 보기 모듈을 모두 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="4c989-113">함께 작업할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-113">They're not intended to work together.</span></span>


<span data-ttu-id="4c989-114">**PowerShellGet** cmdlet을 사용하여 Teams PowerShell 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="4c989-115">시스템에 모든 사용자에 대한 모듈을 설치하려면 상승된 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="4c989-116">Windows에서 관리자 권한으로 실행을 사용하여 PowerShell 세션을 **시작하거나** macOS 또는 Linux에서 명령을 `sudo` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="4c989-117">기본적으로 PSGallery(PowerShell 갤러리)는 **PowerShellGet에** 대한 신뢰할 수 있는 리포지토리로 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="4c989-118">PSGallery를 처음 사용하면 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="4c989-119">설치를 계속 진행하기 **위해 모두에 예** 또는 예로 응답합니다. </span><span class="sxs-lookup"><span data-stu-id="4c989-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="4c989-120">Teams PowerShell 공개 미리 보기 설치</span><span class="sxs-lookup"><span data-stu-id="4c989-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="4c989-121">공개 미리 보기 버전의 Teams PowerShell을 사용하는 경우 먼저 비즈니스용 Skype Online Connector를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="4c989-122">시스템의 모든 사용자에 대해 Teams PowerShell 공개 미리 보기 모듈을 설치하려면 상승된 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="4c989-123">Windows에서 관리자 권한으로 실행을 사용하여 PowerShell 세션을 **시작하거나** macOS 또는 Linux에서 명령을 `sudo` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="4c989-124">PowerShell 5.1을 사용하는 경우 **PowerShellGet** 모듈을 먼저 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="4c989-125">**PowerShellGet을** 업데이트한 후 상승된 PowerShell 세션을 닫았다가 다시 열고 최신 **PowerShellGet이** 로드되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="4c989-126">Teams PowerShell 공개 미리 보기를 설치하려면 아래 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="4c989-127">"Find-Module MicrosoftTeams -AllowPrerelease"를 실행하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 갤러리 또는 PowerShell에서 최신 미리 보기 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="4c989-128">비즈니스용 Skype Online Connector 설치</span><span class="sxs-lookup"><span data-stu-id="4c989-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="4c989-129">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="4c989-130">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="4c989-131">서명하세요</span><span class="sxs-lookup"><span data-stu-id="4c989-131">Sign in</span></span>

<span data-ttu-id="4c989-132">Teams PowerShell 작업을 시작하고 Azure 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="4c989-133">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 미리 보기 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="4c989-134">Teams PowerShell 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c989-134">Update Teams PowerShell</span></span>

<span data-ttu-id="4c989-135">Teams PowerShell을 업데이트하기 위해 상승된 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="4c989-136">Teams PowerShell을 PowerShell 세션으로 이미 가져온 경우 모듈 업데이트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="4c989-137">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="4c989-138">Teams PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="4c989-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="4c989-139">Teams PowerShell을 제거하기 위해 상승된 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="4c989-140">Teams PowerShell을 PowerShell 세션으로 이미 가져온 경우 모듈을 삭제하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="4c989-141">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c989-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4c989-142">Next Steps</span></span>

<span data-ttu-id="4c989-143">이제 Teams PowerShell을 사용하여 Teams를 관리할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="4c989-144">시작은 [Teams PowerShell을](teams-powershell-managing-teams.md) 통해 Teams 관리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4c989-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c989-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4c989-145">Related topics</span></span>

[<span data-ttu-id="4c989-146">Teams PowerShell을 통해 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="4c989-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="4c989-147">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="4c989-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="4c989-148">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="4c989-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="4c989-149">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="4c989-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
