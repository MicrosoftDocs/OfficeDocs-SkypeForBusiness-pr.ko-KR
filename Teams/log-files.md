---
title: 로그 파일을 사용하여 문제 해결 Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 디버그, 미디어 및 데스크톱 로그를 Microsoft Teams 찾을 수 있는 위치 및 모니터링 및 문제 해결에 도움이 되는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337745"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="00de8-103">로그 파일을 사용하여 로그 파일을 모니터링하고 문제를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00de8-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="00de8-104">클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있습니다. 이러한 로그 파일을 모니터링 및 문제 해결을 지원하기 위해 활용할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="00de8-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="00de8-105">로그 디버그</span><span class="sxs-lookup"><span data-stu-id="00de8-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="00de8-106">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="00de8-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="00de8-107">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="00de8-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="00de8-108">이 문서에서는 세 개의 로그와 이 로그가 사용되는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="00de8-109">특정 문제 해결에 대한 자세한 내용은 문제 [해결 Teams 참조하세요.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="00de8-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="00de8-110">지원에 문의하는 방법에 대한 자세한 내용은 지원 을 [참조하세요.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="00de8-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="00de8-111">Microsoft Support를 사용하여 지원 요청을 만들 때 지원 엔지니어는 디버그 로그를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="00de8-112">지원 요청을 만들기 전에 디버그 로그를 진행하면 Microsoft에서 문제 해결을 신속하게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="00de8-113">**미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="00de8-114">이 문서에서 **디버그** 로그는 문제 해결에 사용되는 로그를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="00de8-115">그러나 이러한 로그에 대해 생성된 파일에는 이름에 진단 **로그이라는** 용어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="00de8-116">다음 표에서는 다양한 클라이언트 및 해당 관련 로그를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="00de8-117">로그 파일은 클라이언트 및 운영 체제에 특정 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="00de8-118">클라이언트</span><span class="sxs-lookup"><span data-stu-id="00de8-118">Client</span></span> |<span data-ttu-id="00de8-119">디버그</span><span class="sxs-lookup"><span data-stu-id="00de8-119">Debug</span></span>|<span data-ttu-id="00de8-120">데스크톱</span><span class="sxs-lookup"><span data-stu-id="00de8-120">Desktop</span></span>|<span data-ttu-id="00de8-121">미디어</span><span class="sxs-lookup"><span data-stu-id="00de8-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="00de8-122">웹</span><span class="sxs-lookup"><span data-stu-id="00de8-122">Web</span></span>    |<span data-ttu-id="00de8-123">X</span><span class="sxs-lookup"><span data-stu-id="00de8-123">X</span></span>         |-         |-         |
|<span data-ttu-id="00de8-124">Windows</span><span class="sxs-lookup"><span data-stu-id="00de8-124">Windows</span></span>     |<span data-ttu-id="00de8-125">X</span><span class="sxs-lookup"><span data-stu-id="00de8-125">X</span></span>         |<span data-ttu-id="00de8-126">X</span><span class="sxs-lookup"><span data-stu-id="00de8-126">X</span></span>         |<span data-ttu-id="00de8-127">X</span><span class="sxs-lookup"><span data-stu-id="00de8-127">X</span></span>         |
|<span data-ttu-id="00de8-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="00de8-128">Mac OSX</span></span>     |<span data-ttu-id="00de8-129">X</span><span class="sxs-lookup"><span data-stu-id="00de8-129">X</span></span>         |<span data-ttu-id="00de8-130">X</span><span class="sxs-lookup"><span data-stu-id="00de8-130">X</span></span>         |<span data-ttu-id="00de8-131">X</span><span class="sxs-lookup"><span data-stu-id="00de8-131">X</span></span>         |
|<span data-ttu-id="00de8-132">Linux</span><span class="sxs-lookup"><span data-stu-id="00de8-132">Linux</span></span>     |<span data-ttu-id="00de8-133">X</span><span class="sxs-lookup"><span data-stu-id="00de8-133">X</span></span>         |<span data-ttu-id="00de8-134">X</span><span class="sxs-lookup"><span data-stu-id="00de8-134">X</span></span>         |<span data-ttu-id="00de8-135">X</span><span class="sxs-lookup"><span data-stu-id="00de8-135">X</span></span>         |
|<span data-ttu-id="00de8-136">iOS</span><span class="sxs-lookup"><span data-stu-id="00de8-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="00de8-137">Android</span><span class="sxs-lookup"><span data-stu-id="00de8-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="00de8-138">지원되는 운영 체제 및 브라우저의 전체 목록은 에 대한 클라이언트 [Microsoft Teams.](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="00de8-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="00de8-139">로그 디버그</span><span class="sxs-lookup"><span data-stu-id="00de8-139">Debug logs</span></span>

<span data-ttu-id="00de8-140">이러한 로그는 가장 일반적인 로그로 모든 Microsoft 지원 사례에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="00de8-141">디버그 로그는 브라우저 기반 Windows 및 Mac 데스크톱 클라이언트에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="00de8-142">로그는 텍스트 기반이 며 아래쪽에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="00de8-143">텍스트 기반 편집기를 사용하여 읽을 수 있으며, 클라이언트에 로그인할 때 새 로그가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="00de8-144">디버그 로그에는 다음 데이터 흐름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="00de8-145">로그인</span><span class="sxs-lookup"><span data-stu-id="00de8-145">Login</span></span>

-   <span data-ttu-id="00de8-146">중간 계층 서비스에 대한 연결 요청</span><span class="sxs-lookup"><span data-stu-id="00de8-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="00de8-147">통화/대화</span><span class="sxs-lookup"><span data-stu-id="00de8-147">Call/conversation</span></span>

<span data-ttu-id="00de8-148">디버그 로그는 다음 OS별 메서드를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="00de8-149">Windows:</span><span class="sxs-lookup"><span data-stu-id="00de8-149">Windows:</span></span>

      <span data-ttu-id="00de8-150">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="00de8-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="00de8-151">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="00de8-151">Mac OSX:</span></span>

      <span data-ttu-id="00de8-152">바로 가기 키: 옵션 + 명령 + Shift+1</span><span class="sxs-lookup"><span data-stu-id="00de8-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="00de8-153">Linux:</span><span class="sxs-lookup"><span data-stu-id="00de8-153">Linux:</span></span>

      <span data-ttu-id="00de8-154">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="00de8-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="00de8-155">디버그 로그는 다음 폴더에 자동으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="00de8-156">Windows: %userprofile% \\ 다운로드</span><span class="sxs-lookup"><span data-stu-id="00de8-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="00de8-157">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="00de8-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="00de8-158">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="00de8-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="00de8-159">브라우저: 디버그 로그를 기본 저장 위치로 저장하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="00de8-160">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="00de8-160">Media logs</span></span>

<span data-ttu-id="00de8-161">미디어 로그에는 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="00de8-162">호출 관련 문제에 연결된 지원 사례에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="00de8-163">미디어 로깅이 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-163">Media logging is turned off by default.</span></span> <span data-ttu-id="00de8-164">모임에 대한 진단 데이터를 Teams 클라이언트에서 옵션을 설정해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="00de8-165">일반 **설정** 으로 이동하여 모임 진단에 로깅 사용(Teams 다시 시작 필요) 확인란을 선택하고, Teams 다시 시작하고  >  문제를 재현합니다. </span><span class="sxs-lookup"><span data-stu-id="00de8-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="00de8-166">다음 표에서는 미디어 로그 위치를 간략하게 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="00de8-167">Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 커버하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="00de8-168">클라이언트</span><span class="sxs-lookup"><span data-stu-id="00de8-168">Client</span></span> |<span data-ttu-id="00de8-169">위치</span><span class="sxs-lookup"><span data-stu-id="00de8-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="00de8-170">Windows</span><span class="sxs-lookup"><span data-stu-id="00de8-170">Windows</span></span>     |<span data-ttu-id="00de8-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="00de8-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="00de8-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="00de8-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="00de8-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="00de8-174">Mac OSX</span></span>     |<span data-ttu-id="00de8-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="00de8-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="00de8-177">Linux</span><span class="sxs-lookup"><span data-stu-id="00de8-177">Linux</span></span>       |<span data-ttu-id="00de8-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="00de8-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="00de8-180">생성되는 로그 파일 목록과 포함된 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="00de8-181">로그 파일 이름</span><span class="sxs-lookup"><span data-stu-id="00de8-181">Log file name</span></span>  |<span data-ttu-id="00de8-182">설명</span><span class="sxs-lookup"><span data-stu-id="00de8-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="00de8-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="00de8-184">미디어 스택과 관련된 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-184">Contains information related to the media stack.</span></span> <span data-ttu-id="00de8-185">여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 전송 및 수신된 프레임 수, 카메라 및 VBSS(비디오 기반 화면 공유) 세션 상태가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="00de8-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="00de8-187">제어가 제공된 타임스탬프 및 마우스 포인터 정보와 같은 원격 제어 작업과 관련된 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="00de8-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="00de8-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="00de8-189">미디어 스택 추적 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="00de8-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="00de8-191">렌더링 품질을 포함하여 미디어 에이전트와 관련된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="00de8-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="00de8-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="00de8-193">ts-calling API에서 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="00de8-194">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="00de8-194">Desktop logs</span></span>

<span data-ttu-id="00de8-195">부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="00de8-196">미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="00de8-197">로그는 텍스트 기반이 며, 하락 형식의 텍스트 기반 편집기를 사용하여 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="00de8-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="00de8-198">Windows:</span></span>

 - <span data-ttu-id="00de8-199">시스템 **트레이에서** Microsoft Teams 아이콘을 마우스 오른쪽 단추로 클릭하고 로그를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="00de8-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="00de8-200">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="00de8-200">Mac OsX:</span></span>

 - <span data-ttu-id="00de8-201">도움말 **풀다운 메뉴에서** 로그를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="00de8-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="00de8-202">Linux:</span><span class="sxs-lookup"><span data-stu-id="00de8-202">Linux:</span></span>

 - <span data-ttu-id="00de8-203">시스템 **트레이에서** Microsoft Teams 아이콘을 클릭하고 로그를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="00de8-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="00de8-204">클라이언트</span><span class="sxs-lookup"><span data-stu-id="00de8-204">Client</span></span> |<span data-ttu-id="00de8-205">위치</span><span class="sxs-lookup"><span data-stu-id="00de8-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="00de8-206">Windows</span><span class="sxs-lookup"><span data-stu-id="00de8-206">Windows</span></span>     |<span data-ttu-id="00de8-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="00de8-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="00de8-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="00de8-208">Mac OSX</span></span>     |<span data-ttu-id="00de8-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="00de8-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="00de8-210">Linux</span><span class="sxs-lookup"><span data-stu-id="00de8-210">Linux</span></span>       |<span data-ttu-id="00de8-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="00de8-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="00de8-212">브라우저 추적</span><span class="sxs-lookup"><span data-stu-id="00de8-212">Browser trace</span></span>

<span data-ttu-id="00de8-213">일부 오류 범주의 경우 Microsoft 지원에서 브라우저 추적을 수집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="00de8-214">이 정보는 오류 발생 시 클라이언트의 Teams 중요한 세부 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="00de8-215">브라우저 추적을 시작하기 전에 로그인되어 있는지 Teams.</span><span class="sxs-lookup"><span data-stu-id="00de8-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="00de8-216">추적에 중요한 로그인 정보가 포함되지 않습니다. 추적을 시작하기 전에 이 작업을 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="00de8-217">로그인한 후 브라우저에 적합한 다음 링크 중 하나를 선택하고 제공된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="00de8-218">Chrome & Edge(Chromium)</span><span class="sxs-lookup"><span data-stu-id="00de8-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="00de8-219">Edge</span><span class="sxs-lookup"><span data-stu-id="00de8-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="00de8-220">Safari</span><span class="sxs-lookup"><span data-stu-id="00de8-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="00de8-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="00de8-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="00de8-222">이 단계에서 Azure Portal에 대한 모든 참조를 Teams 클라이언트로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="00de8-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="00de8-223">관련 항목</span><span class="sxs-lookup"><span data-stu-id="00de8-223">Related topics</span></span>

[<span data-ttu-id="00de8-224">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="00de8-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
