---
title: StaffHub PowerShell 모듈 설치
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub PowerShell 모듈을 설치 하 고 연결 하는 방법을 알아봅니다.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc7c97a3c8107de3c2515a8f112bbc1993e3d8f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184535"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bb15d-103">Microsoft StaffHub PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="bb15d-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb15d-104">2019 년 10 월 1 일에 유효 합니다. Microsoft StaffHub는 곧 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="bb15d-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="bb15d-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="bb15d-107">StaffHub는 2019 년 10 월 1 일에 모든 사용자의 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="bb15d-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="bb15d-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb15d-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="bb15d-110">이 문서의 단계를 사용 하 여 Microsoft StaffHub PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="bb15d-111">PowerShell을 사용 하 여 StaffHub를 관리 하 고 StaffHub 팀을 Microsoft 팀으로 이동 하려면이이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bb15d-112">Microsoft StaffHub PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="bb15d-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="bb15d-113">[StaffHub PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="bb15d-114">Windows PowerShell 3.0 이상을 관리자로 엽니다. 이렇게 하려면 **시작**을 클릭 하 고 **windows powershell**을 입력 한 다음 **windows powershell**을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="bb15d-115">최신 버전의 Windows PowerShell을 얻으려면 [Windows Powershell 설치](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb15d-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
3. <span data-ttu-id="bb15d-116">다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="bb15d-117">출력에서 폴더 경로를 확인 하 고 다음 단계로 이동 하기 전에 경로의 모든 폴더가 컴퓨터에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="bb15d-118">폴더가 없는 경우 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="bb15d-119">StaffHub PowerShell 모듈을 설치할 수 있도록 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. <span data-ttu-id="bb15d-120">다음을 실행 합니다. &lt;여기서&gt; path는 2 단계의 출력에서 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="bb15d-121">예를 들어 경로는 C:\Users\User1\Documents\WindowsPowerShell\Modules. 처럼 표시 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="bb15d-122">각 명령을 개별적으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-122">Be sure to run each command separately.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. <span data-ttu-id="bb15d-123">Windows PowerShell을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="bb15d-124">Windows PowerShell 3.0 이상을 전역 관리자로 연 후 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bb15d-125">Microsoft StaffHub PowerShell 모듈에 연결</span><span class="sxs-lookup"><span data-stu-id="bb15d-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="bb15d-126">다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-126">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="bb15d-127">메시지가 표시 되 면 전역 관리자로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb15d-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb15d-128">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bb15d-128">Related topics</span></span>

- [<span data-ttu-id="bb15d-129">Microsoft StaffHub PowerShell 참조</span><span class="sxs-lookup"><span data-stu-id="bb15d-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="bb15d-130">팀에서 Microsoft StaffHub 팀을 교대으로 옮기기</span><span class="sxs-lookup"><span data-stu-id="bb15d-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
