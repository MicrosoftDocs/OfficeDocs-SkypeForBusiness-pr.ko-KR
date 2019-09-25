---
title: StaffHub PowerShell 모듈 설치
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub PowerShell 모듈의 시험판 버전을 설치 하 고 연결 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142037"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="059da-103">Microsoft StaffHub PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="059da-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="059da-104">2019 년 10 월 1 일에 유효 합니다. Microsoft StaffHub는 곧 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059da-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="059da-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059da-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="059da-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059da-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="059da-107">StaffHub는 2019 년 10 월 1 일에 모든 사용자의 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059da-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="059da-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="059da-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="059da-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="059da-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="059da-110">이 문서의 단계를 사용 하 여 Microsoft StaffHub PowerShell 모듈의 시험판 버전을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="059da-111">[StaffHub 팀을 팀으로 이동](move-staffhub-teams-to-shifts-in-teams.md)하려면이이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="059da-112">Microsoft StaffHub PowerShell 모듈의 시험판 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="059da-113">Windows PowerShell 3.0 이상을 관리자로 엽니다. 이렇게 하려면 **시작**을 클릭 하 고 **windows powershell**을 입력 한 다음 **windows powershell**을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="059da-114">최신 버전의 Windows PowerShell을 얻으려면 [Windows Powershell 설치](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="059da-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="059da-115">다음을 실행 하 여 StaffHub PowerShell 모듈의 시험판 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="059da-116">다음과 같은 경고 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059da-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="059da-117">를 `Y`입력 하 고을 `Enter`클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="059da-118">Windows PowerShell을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="059da-119">Microsoft StaffHub PowerShell 모듈에 연결</span><span class="sxs-lookup"><span data-stu-id="059da-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="059da-120">다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="059da-121">메시지가 표시 되 면 전역 관리자로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="059da-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="059da-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="059da-122">Related topics</span></span>

- [<span data-ttu-id="059da-123">Microsoft StaffHub PowerShell 참조</span><span class="sxs-lookup"><span data-stu-id="059da-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="059da-124">팀에서 Microsoft StaffHub 팀을 교대으로 옮기기</span><span class="sxs-lookup"><span data-stu-id="059da-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
