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
description: Microsoft Teams를 관리하는 데 PowerShell 컨트롤을 사용하는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6679cd22800307ec95ac242c190d6483411413a9
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586547"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="2197b-103">Microsoft Teams PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="2197b-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="2197b-104">이 문서에서는 [PowerShellGet](/powershell/scripting/gallery/installing-psget)를 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="2197b-105">이러한 지침은 [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS 및 Windows 플랫폼에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="2197b-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2197b-106">Requirements</span></span>

<span data-ttu-id="2197b-107">Teams PowerShell에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="2197b-108">운영 체제에 사용할 수 있는 [최신 버전의 PowerShell을](/powershell/scripting/install/installing-powershell) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="2197b-109">PowerShell 7 및 Teams PowerShell에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="2197b-110">최상의 환경을 위해 PowerShell 5.1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="2197b-111">Teams PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="2197b-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="2197b-112">최상의 환경을 위해 GA(일반 가용성) 또는 공용 미리 보기 모듈을 모두 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="2197b-113">함께 작동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-113">They're not intended to work together.</span></span>


<span data-ttu-id="2197b-114">**PowerShellGet** cmdlet을 사용하여 Teams PowerShell 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="2197b-115">시스템에 있는 모든 사용자에 대해 모듈을 설치하려면 높은 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="2197b-116">Windows에서 관리자 권한으로  실행을 사용하여 PowerShell 세션을 시작하거나 macOS 또는 Linux에서 명령을 `sudo` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="2197b-117">기본적으로 PSGallery(PowerShell 갤러리)는 **PowerShellGet의** 신뢰할 수 있는 리포지토리로 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="2197b-118">PSGallery를 처음 사용할 때 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="2197b-119">설치를 계속 진행하기 위해 **모두에** 예 또는 **예에** 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="2197b-120">서명하세요</span><span class="sxs-lookup"><span data-stu-id="2197b-120">Sign in</span></span>

<span data-ttu-id="2197b-121">Teams PowerShell 작업을 시작하고 Azure 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-121">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="2197b-122">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 미리 보기 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-122">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="2197b-123">MFA 및 최신 인증을 사용하여 로그인</span><span class="sxs-lookup"><span data-stu-id="2197b-123">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="2197b-124">계정에서 다단계 인증을 사용하는 경우 이 섹션의 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2197b-124">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="2197b-125">Teams PowerShell 업데이트</span><span class="sxs-lookup"><span data-stu-id="2197b-125">Update Teams PowerShell</span></span>

<span data-ttu-id="2197b-126">Teams PowerShell을 업데이트하기 위해 새 상승된 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-126">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="2197b-127">Teams PowerShell이 PowerShell 세션으로 이미 가져온 경우 모듈 업데이트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-127">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="2197b-128">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-128">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="2197b-129">Teams PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="2197b-129">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="2197b-130">Teams PowerShell을 제거하기 위해 상승된 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-130">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="2197b-131">Teams PowerShell이 PowerShell 세션으로 이미 가져온 경우 모듈을 삭제하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-131">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="2197b-132">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-132">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="2197b-133">Teams PowerShell 공개 미리 보기 설치</span><span class="sxs-lookup"><span data-stu-id="2197b-133">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="2197b-134">Teams PowerShell의 공개 미리 보기 버전을 사용하는 경우 먼저 비즈니스용 Skype Online 커넥터를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-134">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="2197b-135">시스템의 모든 사용자에 대해 Teams PowerShell 공개 미리 보기 모듈을 설치하려면 높은 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-135">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="2197b-136">Windows에서 관리자 권한으로  실행을 사용하여 PowerShell 세션을 시작하거나 macOS 또는 Linux에서 명령을 `sudo` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-136">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="2197b-137">PowerShell 5.1을 사용하는 경우 **PowerShellGet** 모듈을 먼저 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-137">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="2197b-138">**PowerShellGet를** 업데이트한 후 상승된 PowerShell 세션을 닫고 다시 열고 최신 **PowerShellGet가** 로드되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-138">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="2197b-139">Teams PowerShell 공개 미리 보기를 설치하려면 아래 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-139">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="2197b-140">"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"를 실행하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 갤러리 또는 PowerShell에서 최신 미리 보기 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-140">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="2197b-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2197b-141">Next Steps</span></span>

<span data-ttu-id="2197b-142">이제 Teams PowerShell을 사용하여 Teams를 관리할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-142">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="2197b-143">시작은 [Teams PowerShell을 통해 팀](teams-powershell-managing-teams.md) 관리 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2197b-143">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2197b-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2197b-144">Related topics</span></span>

[<span data-ttu-id="2197b-145">Teams PowerShell을 통해 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="2197b-145">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="2197b-146">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="2197b-146">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="2197b-147">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="2197b-147">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="2197b-148">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="2197b-148">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)