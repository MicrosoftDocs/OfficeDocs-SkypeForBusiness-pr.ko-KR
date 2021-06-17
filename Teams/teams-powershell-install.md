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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947569"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="ba77c-103">PowerShell Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="ba77c-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="ba77c-104">이 문서에서는 PowerShell 갤러리를 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="ba77c-105">모든 Microsoft Teams PowerShell 모듈은 모든 Windows 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="ba77c-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba77c-106">Requirements</span></span>

<span data-ttu-id="ba77c-107">Microsoft Teams PowerShell 모듈에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="ba77c-108">운영 체제에 사용할 수 있는 [최신 버전의 PowerShell을](/powershell/scripting/install/installing-powershell)   설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="ba77c-109">PowerShell 버전을 확인한 후 PowerShell 세션 내에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="ba77c-110">Install-Module cmdlet을 사용하여 PowerShell 모듈을 Microsoft Teams 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="ba77c-111">PowerShell 갤러리(PSGallery)가 **PowerShellGet의** 신뢰할 수 있는 리포지토리로 구성되지 않은 경우 PSGallery를 처음 사용할 때 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="ba77c-112">설치를 계속 진행하기 위해 **모두에** 예 또는 **예에** 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="ba77c-113">PowerShellGallery를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="ba77c-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="ba77c-114">Microsoft Teams PowerShell 모듈은 현재 PowerShell 5.1에서 사용할 수 Windows.</span><span class="sxs-lookup"><span data-stu-id="ba77c-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="ba77c-115">다음 단계를 수행하여 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="ba77c-116">[5.1 Windows PowerShell 업데이트합니다.](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ba77c-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="ba77c-117">버전 1607 이상에 Windows 10 PowerShell 5.1이 이미 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="ba77c-118">[4.7.2](/dotnet/framework/install) .NET Framework 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="ba77c-119">다음 명령을 실행하여 최신 PowerShellGet를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="ba77c-120">PowerShell Teams 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="ba77c-121">오프라인 설치</span><span class="sxs-lookup"><span data-stu-id="ba77c-121">Offline Installation</span></span> 

<span data-ttu-id="ba77c-122">일부 환경에서는 PowerShell 갤러리에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="ba77c-123">이러한 상황에서는 다음 수동 설치 [단계를 따르세요.](https://aka.ms/psgallery-manualdownload)</span><span class="sxs-lookup"><span data-stu-id="ba77c-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="ba77c-124">서명하세요</span><span class="sxs-lookup"><span data-stu-id="ba77c-124">Sign in</span></span>

<span data-ttu-id="ba77c-125">PowerShell 모듈을 Microsoft Teams Azure 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="ba77c-126">PowerShell Teams 업데이트</span><span class="sxs-lookup"><span data-stu-id="ba77c-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="ba77c-127">PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 동일한 방법을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="ba77c-128">예를 들어 처음 설치 모듈을 사용했다면 [Update-Module을](/powershell/module/powershellget/update-module) 사용하여 최신 버전을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="ba77c-129">PowerShell을 Teams PowerShell 세션으로 이미 가져온 경우 모듈 업데이트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="ba77c-130">PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="ba77c-131">PowerShell Teams 제거</span><span class="sxs-lookup"><span data-stu-id="ba77c-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="ba77c-132">PowerShell을 Microsoft Teams 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="ba77c-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ba77c-133">Next Steps</span></span> 

<span data-ttu-id="ba77c-134">이제 PowerShell을 사용하여 Microsoft Teams 관리할 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="ba77c-135">PowerShell을 Teams [Teams PowerShell을 통해](teams-powershell-managing-teams.md) 데이터 관리 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ba77c-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ba77c-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ba77c-136">Related topics</span></span>

[<span data-ttu-id="ba77c-137">PowerShell을 Teams Teams 관리</span><span class="sxs-lookup"><span data-stu-id="ba77c-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ba77c-138">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="ba77c-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ba77c-139">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="ba77c-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ba77c-140">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="ba77c-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
