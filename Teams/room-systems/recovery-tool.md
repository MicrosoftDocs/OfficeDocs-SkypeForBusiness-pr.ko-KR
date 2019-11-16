---
title: Microsoft 팀 대화방 복구 도구 사용
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다.
ms.openlocfilehash: bc35dc744dac5f04d537f023e790bc89c2c649d0
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675352"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="c5ea7-103">Microsoft 팀 대화방 복구 도구 사용</span><span class="sxs-lookup"><span data-stu-id="c5ea7-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="c5ea7-104">이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="c5ea7-105">Microsoft 팀 대화방 콘솔에 "시스템 구성 날짜가 만료 됨" 오류가 표시 되는 경우이 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="c5ea7-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="c5ea7-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="c5ea7-107">필요 조건</span><span class="sxs-lookup"><span data-stu-id="c5ea7-107">Prerequisites</span></span>

<span data-ttu-id="c5ea7-108">최신 [Microsoft 팀 대화방 설치 패키지](https://go.microsoft.com/fwlink/?linkid=851168) 를 다운로드 하 고 Microsoft 팀 회의실 장치에서 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유에 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="c5ea7-109">[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)를 설치 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="c5ea7-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="c5ea7-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="c5ea7-111">Windows 버전 확인</span><span class="sxs-lookup"><span data-stu-id="c5ea7-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="c5ea7-112">**Windows 설정> 설정** 으로 이동한 다음 Microsoft 팀 대화방 장치에서 관리자 로그인> 관리자 계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c5ea7-113">이 옵션은 로그인 화면으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="c5ea7-114">관리자 계정에 로그인 하 고, 기본 관리자 계정 `admin` 으로 암호를 입력 `sfb`합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="c5ea7-115">시작 메뉴를 클릭 하 고 검색 `winver.exe` 상자에 입력 한 다음 \* 결과에 대해 \**실행 명령을* 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="c5ea7-116">정보 창의 두 번째 행에 있는 ' 버전 ' 다음의 번호를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="c5ea7-117">표시 되는 버전이 1607 이거나 이전인 경우 복구 단계를 <a href="#Perform">수행</a> 하기 전에 <a href="#Windows-up">복구 하기 전에 Windows 업데이트</a> 단계 proceding를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="c5ea7-118">표시 된 버전이 1607 보다 크면 <a href="#Perform">복구 수행</a>단계만 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="c5ea7-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="c5ea7-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="c5ea7-120">복구 하기 전에 Windows 업데이트 (필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="c5ea7-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="c5ea7-121">계속 해 서 관리자 사용자로 로그인 한 상태에서 관리자 권한 Powershell 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="c5ea7-122">명령을 `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="c5ea7-123">Windows 업데이트를 실행 하 고 Windows 1709 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="c5ea7-124">1709에 대 한 업데이트가 완료 되 면 관리자 계정으로 다시 로그인 하 고 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="c5ea7-125">이 업데이트는 링크 또는 Windows Update를 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="c5ea7-126">선택적 단계로 Windows Update에서 사용할 수 있는 추가 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="c5ea7-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="c5ea7-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="c5ea7-128">복구 수행</span><span class="sxs-lookup"><span data-stu-id="c5ea7-128">Perform a recovery</span></span>

1. <span data-ttu-id="c5ea7-129">Microsoft 팀 대화방 장치에서 관리자 계정에 로그인 하 고 관리자 권한 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="c5ea7-130">Microsoft 팀 대화방 설치 패키지에서 추출한 파일에 포함 되어 있는 `RecoveryTool.ps1` 파일에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="c5ea7-131">이 키트는 필수 구성 요소를 준비할 때 사용 되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="c5ea7-132">Debug.exe 명령을 `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="c5ea7-133">스크립트 선택 옵션 `1:"Repair System"`에 따라 메시지가 표시 되는 경우</span><span class="sxs-lookup"><span data-stu-id="c5ea7-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="c5ea7-134">완료 되 면 Microsoft 팀 대화방 장치를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c5ea7-135">자동으로 다시 부팅 되 고 두 번 완전히 복구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ea7-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="c5ea7-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="c5ea7-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="c5ea7-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5ea7-137">See also</span></span>
 
[<span data-ttu-id="c5ea7-138">Microsoft 팀 대화방 도움말</span><span class="sxs-lookup"><span data-stu-id="c5ea7-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="c5ea7-139">Microsoft 팀 대화방 관리</span><span class="sxs-lookup"><span data-stu-id="c5ea7-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
