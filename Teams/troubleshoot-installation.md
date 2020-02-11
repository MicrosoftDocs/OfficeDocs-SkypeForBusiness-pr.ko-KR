---
title: Windows에서 Microsoft 팀 설치 및 업데이트 문제 해결
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Windows에서 팀 데스크톱 클라이언트 앱의 설치 및 업데이트 문제를 해결 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 5c6ee4da7e4bb78463cb262cb382e3a090529bb5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888847"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="39f38-103">Windows에서 Microsoft 팀 설치 및 업데이트 문제 해결</span><span class="sxs-lookup"><span data-stu-id="39f38-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="39f38-104">이 문서에서는 Windows에서 실행 되는 팀 데스크톱 클라이언트 앱의 설치 및 업데이트 문제를 진단 하 고 해결 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="39f38-105">팀이 성공적으로 업데이트 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="39f38-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="39f38-106">팀 업데이트가 성공적으로 설치 되었는지 확인 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="39f38-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="39f38-107">팀에서 프로필 사진을 선택한 다음**버전** **정보** > 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="39f38-108">같은 메뉴에서 **업데이트 확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="39f38-109">앱의 맨 위에 있는 배너가 팀의 "새로 고침"이 필요한 지 여부를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="39f38-110">이 프로세스는 새 버전의 팀을 다운로드할 수 있으므로 약 1 분에 링크를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="39f38-111">또한 배너를 통해 최신 버전을 이미 실행 하 고 있는지 알 수 있습니다 (이 경우 업데이트는 필요 없음).</span><span class="sxs-lookup"><span data-stu-id="39f38-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="39f38-112">배너의 새로 고침 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="39f38-113">팀이 다시 시작 될 때까지 기다린 다음 1 단계를 반복 하 여 앱이 업데이트 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="39f38-114">실패 메시지가 표시 되거나 버전 번호가 4 단계와 동일한 경우 업데이트 프로세스가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="39f38-115">설치 및 업데이트 문제 해결</span><span class="sxs-lookup"><span data-stu-id="39f38-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="39f38-116">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="39f38-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="39f38-117">팀이 설치 되 면 팀 설치 관리자 가%LocalAppData%\SquirrelTemp\SquirrelSetup.log.에 이벤트 순서를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="39f38-118">가장 먼저 찾을 사항은 오류 메시지 이거나 로그 끝에 있는 호출 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="39f38-119">로그 시작 부분에 있는 호출 스택은 설치 문제가 없음을 의미 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="39f38-120">설치 성공 (다른 컴퓨터에도 해당)에서 로그를 로그와 비교 하 여 예상 되는 결과를 확인 하는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="39f38-121">SquirrelSetup에서 원인을 표시 하지 않거나 문제 해결을 위해 추가 정보가 필요한 경우 [응용 프로그램 및 시스템 로그 수집 및 분석](#collect-and-analyze-application-and-system-logs)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39f38-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="39f38-122">업데이트 문제 해결</span><span class="sxs-lookup"><span data-stu-id="39f38-122">Troubleshoot update issues</span></span>

<span data-ttu-id="39f38-123">팀이 성공적으로 설치 되 면 로그 위치가%LocalAppData%\SquirrelTemp 에서%AppData%\Microsoft\Teams.로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %AppData%\Microsoft\Teams.</span></span> <span data-ttu-id="39f38-124">이 위치에는 SquirrelSetup 및 .log의 두 가지 로그 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="39f38-125">이 위치의 SquirrelSetup 파일은 팀 앱을 서비스 하는 실행 파일인 update.exe로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="39f38-126">Store.exe 파일은 팀 앱 (특히 팀)에서 중요 한 응용 프로그램 이벤트를 기록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="39f38-127">오류 정보를 포함 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-127">It will likely contain failure information.</span></span>

<span data-ttu-id="39f38-128">이러한 로그 파일에는 PII (개인 식별 정보)가 포함 되어 있으므로 Microsoft에 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="39f38-129">팀은 업데이트 프로세스 (정책에 따라 다름)를 자동으로 시작 하거나 사용자의 프로필 사진으로 이동해 업데이트를 **확인**하 여 수동으로 업데이트를 확인할 수 있습니다 >.</span><span class="sxs-lookup"><span data-stu-id="39f38-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="39f38-130">두 메서드 모두 다음 순서 대로 이벤트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="39f38-131">**업데이트를 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-131">**Check for updates**.</span></span> <span data-ttu-id="39f38-132">팀은 웹 요청을 만들고 현재 앱 버전과 배포 링 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="39f38-133">이 단계의 목표는 다운로드 링크를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="39f38-134">이 단계에서 오류가 로그. t e x에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="39f38-135">**업데이트를 다운로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-135">**Download update**.</span></span> <span data-ttu-id="39f38-136">팀은 1 단계에서 얻은 다운로드 링크를 사용 하 여 업데이트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="39f38-137">다운로드가 완료 되 면 팀이 Update.exe를 호출 하 여 다운로드를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="39f38-138">다운로드 오류도 로그 .txt에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="39f38-139">**업데이트를 준비**합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-139">**Stage the update**.</span></span> <span data-ttu-id="39f38-140">다운로드 된 콘텐츠는 Update.exe에 의해 수행 되는 중간 폴더%LocalAppData%\Microsoft\Teams\stage)에 확인 되 고 압축을 풀었습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="39f38-141">이 단계의 오류는 SquirrelTemp에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="39f38-142">**업데이트를 설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-142">**Install the update**.</span></span> <span data-ttu-id="39f38-143">팀을 시작 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="39f38-144">사용자가 로그인 하면 시스템에서 자동으로 팀을 시작 하거나 바로 가기를 통해 팀을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="39f38-145">이 단계에서는 Update.exe가 준비 폴더의 현재 상태를 확인 하 고, 콘텐츠를 다시 확인 하 고, 파일 작업을 수행 하 여 앱의 단계를 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="39f38-146">%LocalAppData%\Microsoft\Teams\current의 이전 응용 프로그램 폴더 는%LocalAppData%\Microsoft\Teams\previous에 백업 되 고 스테이지 폴더의 이름은 "current"로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="39f38-147">이 단계의 오류는 SquirrelTemp에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="39f38-148">SquirrelTemp 또는 .log에 충분 한 정보가 포함 되어 있지 않은 경우에도 문제 해결을 위한 자세한 정보가 필요 하며,이에 대 한 자세한 내용은 [응용 프로그램 및 시스템 로그 수집 및 분석](#collect-and-analyze-application-and-system-logs)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39f38-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="39f38-149">응용 프로그램 및 시스템 로그 수집 및 분석</span><span class="sxs-lookup"><span data-stu-id="39f38-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="39f38-150">이 섹션에서는 응용 프로그램 및 시스템 로그를 수집 하 고 분석 하 여 문제 해결에 대 한 자세한 정보를 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="39f38-151">Sysinternals 도구를 사용 하 여 이러한 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="39f38-152">자세히 알아보려면 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39f38-152">To learn more, see [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="39f38-153">로그 수집</span><span class="sxs-lookup"><span data-stu-id="39f38-153">Collect logs</span></span>

1. <span data-ttu-id="39f38-154">[Sysinternals 도구](https://download.sysinternals.com/files/SysinternalsSuite.zip)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="39f38-155">로컬 드라이브 의% TEMP% 폴더에 zip 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="39f38-156">관리자 권한 명령 프롬프트를 열고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="39f38-157">TEMP 폴더로 이동 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-157">Run the following to go to your TEMP folder:</span></span>

        ```console
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="39f38-158">설정 및 응용 프로그램 로그를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-158">Copy the setup and application logs.</span></span> <span data-ttu-id="39f38-159">실패 시점에 따라 일부 로그는 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="39f38-160">다음을 실행 하 여 열린 핸들을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-160">Run the following to capture the open handles.</span></span>

        ```console
        handle > handles.txt
        ```

    4. <span data-ttu-id="39f38-161">다음을 실행 하 여 열린 Dll을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-161">Run the following to capture the opened DLLs.</span></span>

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="39f38-162">실행 중인 드라이버를 캡처하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-162">Run the following to capture the drivers that are running.</span></span>

        ```console
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="39f38-163">다음을 실행 하 여 팀 폴더의 Acl (액세스 제어 목록)을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="39f38-164">로그 분석 (고급 사용자 용)</span><span class="sxs-lookup"><span data-stu-id="39f38-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="39f38-165">업데이트에 실패 하면 예기치 않은 앱 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="39f38-166">예를 들어 사용자가 팀을 종료 하거나 오래 된 버전의 팀을 사용 하거나 팀을 시작할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="39f38-167">업데이트 중에 문제가 발생 하는 경우 원인을 찾기 위한 첫 번째 위치는 SquirrelTemp입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="39f38-168">다음은 가장 일반적으로 사용 되는 여러 가지 유형의 업데이트 실패와 로그를 사용 하 여 분석 하 고 문제를 해결 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="39f38-169">팀을 종료할 수 없음</span><span class="sxs-lookup"><span data-stu-id="39f38-169">Unable to exit Teams</span></span>

<span data-ttu-id="39f38-170">팀에서 새 버전으로 자신을 업데이트 해야 하는 것으로 판단 하는 경우 새로운 앱을 다운로드 하 고 진행 한 다음 컴퓨터가 유휴 상태일 때 다시 시작 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="39f38-171">이 프로세스 중에 발생 하는 일반적인 문제는 다른 프로세스나 파일 시스템 드라이버가 팀 .exe 프로세스를 잠그고이로 인해 excel.exe가 종료 되지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="39f38-172">결과적으로, 팀 앱을 새로 다운로드 및 준비 된 앱으로 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="39f38-173">문제 해결 팁:</span><span class="sxs-lookup"><span data-stu-id="39f38-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="39f38-174">발생 한 문제를 확인 하려면 작업 표시줄에서 팀을 마우스 오른쪽 단추로 클릭 하 고 **종료**를 클릭 하 여 팀을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="39f38-175">그런 다음 Windows에서 작업 관리자를 열어 팀 인스턴스가 계속 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="39f38-176">이 문제가 있는 컴퓨터에 있지 않은 경우이 문제가 발생 하는 컴퓨터에서 수집 된 SquirrelTemp를 검사 하 여 "프로그램: 로그에서 프로세스를 종료할 수 없습니다" 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="39f38-177">At.exe를 종료 하지 못하도록 막는 기능을 확인 하려면 Dll (.txt) 및 핸들 .txt 로그를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39f38-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="39f38-178">팀에서 종료 하지 못하도록 하는 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="39f38-179">팀 종료를 방지할 수 있는 또 다른 원인으로는 커널 모드 파일 시스템 필터 드라이버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="39f38-180">SysInternals 도구, [Procdump](https://docs.microsoft.com/sysinternals/downloads/procdump)를 사용 하 여 커널 모드 프로세스 덤프를 수집 합니다 ```procdump -mk <pid>```(여기서 <pid> 작업 관리자에서 가져온 프로세스 ID).</span><span class="sxs-lookup"><span data-stu-id="39f38-180">Use the SysInternals tool, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="39f38-181">Driverquery 로그 파일을 검사 하 여 팀에 방해할 수 있는 활성 필터 드라이버를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="39f38-182">이 상태에서 복구 하려면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="39f38-183">파일 사용 권한</span><span class="sxs-lookup"><span data-stu-id="39f38-183">File permissions</span></span>

<span data-ttu-id="39f38-184">팀은 설치 및 업데이트 프로세스 전체에서 사용자의 프로필에 많은 하위 폴더 및 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="39f38-185">앱과 업데이트는 비관리자 수준의 사용자로 실행 되므로 다음 폴더에 대 한 읽기 및 쓰기 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="39f38-186">폴더</span><span class="sxs-lookup"><span data-stu-id="39f38-186">Folder</span></span>  |<span data-ttu-id="39f38-187">에서 사용 됨</span><span class="sxs-lookup"><span data-stu-id="39f38-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="39f38-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="39f38-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="39f38-189">설치 단계 중의 팀 설치 관리자 (예: Teams_Windows_x64)</span><span class="sxs-lookup"><span data-stu-id="39f38-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="39f38-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="39f38-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="39f38-191">업데이트 프로세스 중에 앱 패키지를 추출 하 고 스테이지 하는 팀 업데이트 업데이트 (update.exe)</span><span class="sxs-lookup"><span data-stu-id="39f38-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="39f38-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="39f38-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="39f38-193">팀 앱 (팀)-설정, 앱 상태 및 (미리 준비 됨) 다운로드 된 업데이트 패키지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="39f38-194">파일에 쓸 수 없기 때문에 팀의 액세스가 거부 되는 경우 다른 소프트웨어 응용 프로그램이 간섭 하거나 보안 설명자 항목이 폴더에 대 한 쓰기 권한을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="39f38-195">문제 해결 팁:</span><span class="sxs-lookup"><span data-stu-id="39f38-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="39f38-196">SquirrelTemp 또는 .log에서 "액세스 거부" 증명 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="39f38-197">이 파일을 확인 하 여 실패 한 파일에 쓰려는 시도가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="39f38-198">Icacls을 열고 관리자가 아닌 사용자가 쓰기 작업을 차단 하는 ACE (유효 액세스 제어 항목)를 찾습니다. 일반적으로이는 DACL 항목 중 하나에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="39f38-199">자세한 내용은 [icacls 설명서](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39f38-199">For more information, see the [icacls documentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="39f38-200">파일이 손상 됨</span><span class="sxs-lookup"><span data-stu-id="39f38-200">File corrupted</span></span>

<span data-ttu-id="39f38-201">일부 경우에는 암호화 소프트웨어 에서%LocalAppData%\Microsoft\Teams 폴더의 파일을 변경할 수 있으며,이 경우 팀이 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="39f38-202">이 문제는 앱이 업데이트 되지 않는 경우에도 언제 든 지 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="39f38-203">불행 하 게도 파일이 손상 되 면이 상태에서 복구 하는 유일한 방법은 팀을 제거 하 고 다시 설치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="39f38-204">이러한 단계 중 하나를 사용 하 여 문제의 근본 원인을 확인할 수 없는 경우 [프로세스 모니터](https://docs.microsoft.com/sysinternals/downloads/procmon) 세션을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="39f38-205">프로세스 모니터는 레지스트리와 파일 시스템에 대 한 액세스를 기록 하는 Sysinternals 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="39f38-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39f38-206">관련 항목</span><span class="sxs-lookup"><span data-stu-id="39f38-206">Related topics</span></span>

- [<span data-ttu-id="39f38-207">Teams용 클라이언트 가져오기</span><span class="sxs-lookup"><span data-stu-id="39f38-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="39f38-208">Teams 클라이언트 업데이트</span><span class="sxs-lookup"><span data-stu-id="39f38-208">Teams client updates</span></span>](teams-client-update.md)