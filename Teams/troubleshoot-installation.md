---
title: Windows에서 Microsoft Teams 설치 및 업데이트 문제 해결
author: cichur
ms.author: v-cichur
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
localization_priority: Priority
search.appverid: MET150
description: Windows에서 Teams 데스크톱 클라이언트 앱의 설치 및 문제를 해결하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 6235bd6336940d7d36a7de526eaaf1fbb93f5323
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768375"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="caec8-103">Windows에서 Microsoft Teams 설치 및 업데이트 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caec8-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="caec8-104">이 자료에서는 Windows에서 실행 중인 Teams 데스크톱 클라이언트 앱의 설치 및 문제를 진단하고 해결하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="caec8-105">Teams가 제대로 업데이트되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="caec8-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="caec8-106">다음 단계에 따라 Teams 업데이트가 설치되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="caec8-107">Teams에서 프로필 그림을 선택한 다음  > **버전** 에 대한 **정보** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="caec8-108">같은 메뉴에서 **업데이트 확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="caec8-109">앱 상단에 있는 배너가 Teams에 "새로 고침"이 필요함을 나타낼 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="caec8-110">이 프로세스는 새 버전의 Teams를 다운로드하므로 링크가 약 1분 후에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="caec8-111">또한 최신 버전을 이미 실행 중인지 여부를 배너를 통해 알 수 있으며, 이 경우 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="caec8-112">배너에서 [새로 고침] 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="caec8-113">Teams가 다시 시작될 때까지 기다렸다가 1단계를 반복하여 앱이 업데이트되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="caec8-114">오류 메시지가 표시되거나 버전 번호가 4단계와 같으면 업데이트 프로세스가 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="caec8-115">설치 및 업데이트 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caec8-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="caec8-116">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caec8-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="caec8-117">Teams가 설치된 경우 Teams 설치 관리자는 이벤트 순서를 %LocalAppData%\SquirrelTemp\SquirrelSetup.log에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="caec8-118">가장 먼저 찾아야 할 것은 로그의 끝 근처에 있는 오류 메시지 또는 호출 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="caec8-119">로그의 시작 부분에 있는 호출 스택은 설치 문제가 존재함을 의미하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="caec8-120">다른 컴퓨터에서도 성공적인 설치에서 얻은 로그와 로그를 비교하여 예상한 내용을 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="caec8-121">SquirelSetup.log에서 원인을 표시하지 않거나 문제를 해결하는 데 필요한 추가 정보가 필요한 경우 [응용 프로그램 및 시스템 로그 수집 및 분석을 참조하세요](#collect-and-analyze-application-and-system-logs).</span><span class="sxs-lookup"><span data-stu-id="caec8-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="caec8-122">업데이트 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caec8-122">Troubleshoot update issues</span></span>

<span data-ttu-id="caec8-123">Teams가 성공적으로 설치되면 로그 위치가 %LocalAppData%\SquirrelTemp to %LocalAppData%\Microsoft\Teams로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %LocalAppData%\Microsoft\Teams.</span></span> <span data-ttu-id="caec8-124">이 위치에는 SquirrelSetup.log 및 logs.txt라는 두 로그 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="caec8-125">이 위치의 SquirrelSetup.log 파일은 Teams 앱을 서비스하는 실행 파일인 Update.exe에 의해 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="caec8-126">Logs.txt 파일은 Teams 앱(특히 Teams.exe)에서 중요한 응용 프로그램 이벤트를 기록하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="caec8-127">오류 정보는 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-127">It will likely contain failure information.</span></span>

<span data-ttu-id="caec8-128">이러한 로그 파일에는 PII(개인 식별 가능 정보)가 포함되어 있으므로 Microsoft로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="caec8-129">Teams는 정책에 따라 자동으로 업데이트 프로세스를 시작하거나 사용자가 프로파일 그림 > **업데이트 확인** 으로 이동하여 업데이트를 수동으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="caec8-130">두 방법 모두 다음 이벤트 순서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="caec8-131">**업데이트 확인**.</span><span class="sxs-lookup"><span data-stu-id="caec8-131">**Check for updates**.</span></span> <span data-ttu-id="caec8-132">Teams는 웹 요청을 하고 현재 앱 버전 및 배포 링 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="caec8-133">이 단계의 목표는 다운로드 링크를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="caec8-134">이 단계에서 오류가 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="caec8-135">**업데이트를 다운로드합니다**.</span><span class="sxs-lookup"><span data-stu-id="caec8-135">**Download update**.</span></span> <span data-ttu-id="caec8-136">Teams는 1단계에서 얻은 다운로드 링크를 사용하여 업데이트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="caec8-137">다운로드가 완료되면 Teams는 Update.exe를 호출하여 다운로드를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="caec8-138">또한 다운로드 오류가 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="caec8-139">**업데이트를 준비합니다**.</span><span class="sxs-lookup"><span data-stu-id="caec8-139">**Stage the update**.</span></span> <span data-ttu-id="caec8-140">다운로드한 콘텐츠는 Update.exe에서 수행되는 중간 폴더 %LocalAppData%\Microsoft\Teams\stage)로 확인되고 압축이 풀립니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="caec8-141">이 단계의 실패는 SquirrelTemp.log에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="caec8-142">**업데이트를 설치합니다**.</span><span class="sxs-lookup"><span data-stu-id="caec8-142">**Install the update**.</span></span> <span data-ttu-id="caec8-143">Teams를 시작하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="caec8-144">사용자가 로그인하거나 바로 가기를 통해 Teams를 시작할 수있을 때 시스템이 자동으로 Teams를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="caec8-145">이 단계에서 Update.exe는 준비 폴더가 있는지 확인하고 콘텐츠를 다시 확인한 다음 파일 작업을 수행하여 앱의 스테이지를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="caec8-146">%LocalAppData%\Microsoft\Teams\current의 이전 응용 프로그램 폴더는 %LocalAppData%\Microsoft\Teams\previous에 백업되고 스테이지 폴더의 이름은 "current"로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="caec8-147">이 단계의 실패는 SquirrelTemp.log에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="caec8-148">SquirrelTemp.log 또는 Logs.txt에 근본적인 원인을 판별하기에 충분한 정보가 없고 문제점을 해결하기 위해 추가 정보가 필요한 경우 [ 응용 프로그램 및 시스템 로그 수집 및 분석](#collect-and-analyze-application-and-system-logs)으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="caec8-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="caec8-149">응용 프로그램 및 시스템 로그 수집 및 분석</span><span class="sxs-lookup"><span data-stu-id="caec8-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="caec8-150">이 섹션에서는 응용 프로그램 및 시스템 로그를 수집 및 분석하여 문제를 해결하기 위한 보다 포괄적인 정보를 얻는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="caec8-151">Sysinternals 도구를 사용하여 이 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="caec8-152">자세한 내용은 [Windows Sysinternals](/sysinternals/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="caec8-152">To learn more, see [Windows Sysinternals](/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="caec8-153">로그 수집</span><span class="sxs-lookup"><span data-stu-id="caec8-153">Collect logs</span></span>

1. <span data-ttu-id="caec8-154">[Sysinternals 도구](https://download.sysinternals.com/files/SysinternalsSuite.zip)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="caec8-155">zip 파일을 로컬 드라이브의 %TEMP% 폴더로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="caec8-156">관리자 권한 명령 프롬프트를 열고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="caec8-157">다음을 실행하여 TEMP 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-157">Run the following to go to your TEMP folder:</span></span>

        ```console
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="caec8-158">설정 및 응용 프로그램 로그를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-158">Copy the setup and application logs.</span></span> <span data-ttu-id="caec8-159">실패 지점에 따라 이러한 로그 중 일부가 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="caec8-160">열린 핸들을 캡처하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-160">Run the following to capture the open handles.</span></span>

        ```console
        handle > handles.txt
        ```

    4. <span data-ttu-id="caec8-161">열린 DLL을 캡처하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-161">Run the following to capture the opened DLLs.</span></span>

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="caec8-162">다음을 실행하여 실행 중인 드라이버를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-162">Run the following to capture the drivers that are running.</span></span>

        ```console
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="caec8-163">Teams 폴더의 ACL(액세스 제어 목록)을 캡처하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="caec8-164">로그 분석(고급 사용자용)</span><span class="sxs-lookup"><span data-stu-id="caec8-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="caec8-165">업데이트에 실패하면 예측할 수 없는 앱 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="caec8-166">예를 들어, 사용자가 Teams를 종료할 수 없거나, 오래된 버전의 Teams를 보유하고 있거나, Teams를 시작할 수 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="caec8-167">업데이트 중에 문제가 발생하는 경우 원인을 찾을 수 있는 첫 번째 위치는 SquirrelTemp.log입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="caec8-168">다음은 가장 일반적인 업데이트 오류가 나열된 여러 가지 유형과 로그를 사용하여 해당 업데이트를 분석하고 해결하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="caec8-169">Teams를 종료할 수 없음</span><span class="sxs-lookup"><span data-stu-id="caec8-169">Unable to exit Teams</span></span>

<span data-ttu-id="caec8-170">Teams를 스스로 최신 버전으로 업데이트해야 한다고 판단함에 따라 새 앱을 다운로드하고 스테이징한 다음, 시스템이 유휴 상태일 때 다시 시작될 기회를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="caec8-171">이 프로세스 중에 발생하는 일반적인 문제는 다른 프로세스 또는 파일 시스템 드라이버가 Teams.exe 프로세스를 잠가 Teams.exe가 종료되지 않는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="caec8-172">결과적으로 Teams 앱은 새로 다운로드하여 준비된 앱으로 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="caec8-173">문제 해결 팁:</span><span class="sxs-lookup"><span data-stu-id="caec8-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="caec8-174">겪고 있는 문제가 이에 해당되는지 확인하려면, Teams를 종료합니다(작업 표시 줄에서 Teams를 마우스 오른쪽 단추로 클릭한 후 **종료** 를 클릭합니다).</span><span class="sxs-lookup"><span data-stu-id="caec8-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="caec8-175">그런 다음 Windows에서 [작업 관리자]를 열어 Teams 인스턴스가 아직 실행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="caec8-176">이 문제가 있는 컴퓨터에 있지 않은 경우 이 문제가 발생한 컴퓨터에서 수집한 SquirrelTemp.log를 검사하고 "프로그램 : 로그에서 프로세스를 종료할 수 없음"항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="caec8-177">Teams.exe가 종료할 수 없는 원인을 확인하려면 Dlls.txt 및 Handles.txt 로그를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="caec8-178">이는 Teams를 종료할 수 없는 프로세스를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="caec8-179">Teams를 종료하지 못하게 할 수 있는 또 다른 원인은 커널 모드 파일 시스템 필터 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="caec8-180">SysInternals 도구 [ ProcDump ](/sysinternals/downloads/procdump)를 사용하여 ```procdump -mk <pid>```을 실행하여 커널 모드 프로세스 덤프를 수집합니다. 여기서 <pid>는 작업 관리자에서 얻은 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-180">Use the SysInternals tool, [ProcDump](/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="caec8-181">Driverquery.txt 로그 파일을 검사하여 Teams를 방해할 수 있는 활성 필터 드라이버를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="caec8-182">이 상태에서 복구하려면 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="caec8-183">파일 사용 권한</span><span class="sxs-lookup"><span data-stu-id="caec8-183">File permissions</span></span>

<span data-ttu-id="caec8-184">Teams는 설치 및 업데이트 프로세스 동안 사용자의 프로필에 여러 개의 하위 폴더와 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="caec8-185">앱과 업데이트 프로그램이 비사용 사용자로 실행되므로 다음 폴더에 대한 읽기 및 쓰기 권한이 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="caec8-186">폴더</span><span class="sxs-lookup"><span data-stu-id="caec8-186">Folder</span></span>  |<span data-ttu-id="caec8-187">사용자</span><span class="sxs-lookup"><span data-stu-id="caec8-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="caec8-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="caec8-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="caec8-189">설치 단계 중 Teams 설치 프로그램(예 : Teams_Windows_x64.exe)</span><span class="sxs-lookup"><span data-stu-id="caec8-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="caec8-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="caec8-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="caec8-191">업데이트 프로세스 중에 앱 패키지를 추출하고 준비하기 위한 Teams 업데이트 프로그램(Update.exe)</span><span class="sxs-lookup"><span data-stu-id="caec8-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="caec8-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="caec8-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="caec8-193">설정, 앱 상태 및 다운로드된(사전 준비된) 업데이트 패키지를 저장하는 Teams 앱(Teams.exe)</span><span class="sxs-lookup"><span data-stu-id="caec8-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="caec8-194">Teams에서 파일에 쓸 수 없어 액세스가 거부되는 경우 다른 소프트웨어 응용 프로그램이 간섭하거나 보안 설명자 항목이 폴더에 대한 쓰기 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="caec8-195">문제 해결 팁:</span><span class="sxs-lookup"><span data-stu-id="caec8-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="caec8-196">SquirrelTemp.log 또는 Logs.txt에서 "액세스 거부" 증거를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="caec8-197">이 파일을 확인하여, 파일에 쓰려고 시도했으나 실패한 기록이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="caec8-198">Icacls.txt를 열고 관리자가 아닌 사용자의 쓰기 작업을 차단하는 효과적인 ACE(액세스 제어 항목)를 찾습니다. 일반적으로 DACL 항목 중 하나에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="caec8-199">자세한 내용을 보려면 [icacls 설명서](/windows-server/administration/windows-commands/icacls)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="caec8-199">For more information, see the [icacls documentation](/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="caec8-200">파일이 손상됨</span><span class="sxs-lookup"><span data-stu-id="caec8-200">File corrupted</span></span>

<span data-ttu-id="caec8-201">경우에 따라 암호화 소프트웨어가 %LocalAppData%\Microsoft\Teams 폴더의 파일을 변경하여 Teams가 시작되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="caec8-202">앱이 업데이트되지 않은 경우에도 언제든지 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="caec8-203">안타깝게도 파일이 손상된 경우 이 상태에서 복구하는 유일한 방법은 Teams를 제거하고 다시 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="caec8-204">다음 단계 중 하나를 사용하여 문제의 근본 원인을 확인할 수 없는 경우 [프로세스 모니터링](/sysinternals/downloads/procmon) 세션을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="caec8-205">프로세스 모니터링은 레지스트리 및 파일 시스템에 대한 액세스를 기록하는 Sysinternals 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="caec8-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="caec8-206">관련 항목</span><span class="sxs-lookup"><span data-stu-id="caec8-206">Related topics</span></span>

- [<span data-ttu-id="caec8-207">Teams용 클라이언트 가져오기</span><span class="sxs-lookup"><span data-stu-id="caec8-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="caec8-208">Teams 클라이언트 업데이트</span><span class="sxs-lookup"><span data-stu-id="caec8-208">Teams client updates</span></span>](teams-client-update.md)
- [<span data-ttu-id="caec8-209">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="caec8-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
