---
title: PowerShell Microsoft Teams 설치
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
description: PowerShell 컨트롤을 사용하여 데이터 관리에 Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768345"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="2f0f0-103">PowerShell Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="2f0f0-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="2f0f0-104">이 문서에서는 [PowerShellGet](/powershell/scripting/gallery/installing-psget)를 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="2f0f0-105">이러한 지침은 [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS 및 Windows 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f0f0-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f0f0-106">Requirements</span></span>

<span data-ttu-id="2f0f0-107">Teams PowerShell에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="2f0f0-108">운영 체제에 사용할 수 있는 [최신 버전의 PowerShell을](/powershell/scripting/install/installing-powershell) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="2f0f0-109">최상의 환경을 위해 PowerShell 5.1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="2f0f0-110">PowerShell Teams 설치</span><span class="sxs-lookup"><span data-stu-id="2f0f0-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="2f0f0-111">최상의 환경을 위해 GA(일반 가용성) 또는 공용 미리 보기 모듈을 모두 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="2f0f0-112">함께 작동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-112">They're not intended to work together.</span></span>


<span data-ttu-id="2f0f0-113">**PowerShellGet** cmdlet을 사용하여 PowerShell Teams 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="2f0f0-114">시스템에 있는 모든 사용자에 대해 모듈을 설치하려면 높은 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="2f0f0-115">macOS 또는 Linux에서  관리자 권한으로 실행을 Windows PowerShell 세션을 시작하거나 다음 명령을 `sudo` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="2f0f0-116">기본적으로 PSGallery(PowerShell 갤러리)는 **PowerShellGet의** 신뢰할 수 있는 리포지토리로 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="2f0f0-117">PSGallery를 처음 사용할 때 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="2f0f0-118">설치를 계속 진행하기 위해 **모두에** 예 또는 **예에** 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="2f0f0-119">서명하세요</span><span class="sxs-lookup"><span data-stu-id="2f0f0-119">Sign in</span></span>

<span data-ttu-id="2f0f0-120">PowerShell에서 Teams Azure 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="2f0f0-121">최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 릴리스를 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="2f0f0-122">MFA 및 최신 인증을 사용하여 로그인</span><span class="sxs-lookup"><span data-stu-id="2f0f0-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="2f0f0-123">계정에서 다단계 인증을 사용하는 경우 이 섹션의 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="2f0f0-124">PowerShell Teams 업데이트</span><span class="sxs-lookup"><span data-stu-id="2f0f0-124">Update Teams PowerShell</span></span>

<span data-ttu-id="2f0f0-125">PowerShell을 Teams 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="2f0f0-126">PowerShell을 Teams PowerShell 세션으로 이미 가져온 경우 모듈 업데이트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="2f0f0-127">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="2f0f0-128">PowerShell Teams 제거</span><span class="sxs-lookup"><span data-stu-id="2f0f0-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="2f0f0-129">PowerShell을 Teams 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="2f0f0-130">PowerShell을 Teams PowerShell 세션으로 이미 가져온 경우 모듈을 삭제하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="2f0f0-131">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="2f0f0-132">PowerShell Teams 미리 보기 설치</span><span class="sxs-lookup"><span data-stu-id="2f0f0-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="2f0f0-133">PowerShell의 공개 미리 보기 버전을 사용하는 Teams 먼저 온라인 커넥터를 비즈니스용 Skype 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="2f0f0-134">시스템의 모든 Teams PowerShell 공개 미리 보기 모듈을 설치하려면 높은 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="2f0f0-135">MacOS 또는 Linux에서  관리자 권한으로 실행을 Windows `sudo` PowerShell 세션을 시작하거나 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="2f0f0-136">PowerShell 5.1을 사용하는 경우 **PowerShellGet** 모듈을 먼저 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="2f0f0-137">**PowerShellGet를** 업데이트한 후 상승된 PowerShell 세션을 닫고 다시 열고 최신 **PowerShellGet가** 로드되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="2f0f0-138">PowerShell Teams 미리 보기를 설치하려면 아래 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="2f0f0-139">"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"를 실행하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 갤러리 또는 PowerShell에서 최신 미리 보기 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="2f0f0-140">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2f0f0-140">Next Steps</span></span>

<span data-ttu-id="2f0f0-141">이제 PowerShell을 사용하여 Teams 관리할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="2f0f0-142">PowerShell을 Teams [Teams PowerShell을 통해](teams-powershell-managing-teams.md) 데이터 관리 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f0-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f0f0-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2f0f0-143">Related topics</span></span>

[<span data-ttu-id="2f0f0-144">PowerShell을 Teams Teams 관리</span><span class="sxs-lookup"><span data-stu-id="2f0f0-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="2f0f0-145">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="2f0f0-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="2f0f0-146">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="2f0f0-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="2f0f0-147">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="2f0f0-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
