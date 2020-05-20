---
title: 시험판 버전의 팀 PowerShell 모듈 설치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: PowerShell 테스트 갤러리에서 팀 PowerShell 모듈의 시험판 버전을 설치 하려면 다음 단계를 따릅니다.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321771"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="3d2c5-103">시험판 버전의 팀 PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="3d2c5-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="3d2c5-104">이 문서에서는 [Powershell 테스트 갤러리](https://www.poshtestgallery.com/packages/MicrosoftTeams/)에서 팀 powershell 모듈의 최신 시험판 버전을 설치 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="3d2c5-105">팀 구성 기능을 관리 하는 cmdlet은 일반적으로 사용 가능한 모듈 버전에서 지원 되지 않고 시험판 버전 에서만 사용할 수 있는 시나리오에서 팀 PowerShell 모듈의 시험판 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="3d2c5-106">이 단계를 사용 하 여 PowerShell 테스트 갤러리에서 팀 PowerShell 모듈의 최신 시험판 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="3d2c5-107">PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 [공용 Powershell 갤러리](https://www.powershellgallery.com/packages/MicrosoftTeams/)의 모듈 버전과 나란히 설치 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="3d2c5-108">이 단계에 따라 먼저 공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하 고 PowerShell 테스트 갤러리에서 최신 버전의 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="3d2c5-109">모든 기존 PowerShell 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="3d2c5-110">Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="3d2c5-111">공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="3d2c5-112">모든 기존 PowerShell 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="3d2c5-113">Windows PowerShell 모듈을 다시 시작 하 고 다음을 실행 하 여 PowerShell 테스트 갤러리를 신뢰할 수 있는 원본으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="3d2c5-114">PowerShell 테스트 갤러리에서 최신 팀 PowerShell 모듈을 설치 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="3d2c5-115">다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="3d2c5-116">PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈로 업데이트</span><span class="sxs-lookup"><span data-stu-id="3d2c5-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="3d2c5-117">PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 이미 설치한 경우 다음 단계를 사용 하 여 최신 버전으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="3d2c5-118">모든 기존 PowerShell 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="3d2c5-119">Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="3d2c5-120">다음을 실행 하 여 PowerShell 테스트 갤러리에서 현재 설치 된 버전의 팀 PowerShell 모듈을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="3d2c5-121">다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2c5-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="3d2c5-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3d2c5-122">Related topics</span></span>

- [<span data-ttu-id="3d2c5-123">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="3d2c5-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
