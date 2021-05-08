---
title: 로그 파일을 사용하여 문제 해결 Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 디버그, 미디어 및 데스크톱 로그를 Microsoft Teams 찾을 수 있는 위치 및 문제 해결에 도움이 되는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264878"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="f3cd8-103">로그 파일을 사용하여 문제 해결 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3cd8-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="f3cd8-104">클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있습니다. 이 파일에서 문제를 해결하는 데 도움이 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="f3cd8-105">로그 디버그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-105">Debug logs</span></span>

-   <span data-ttu-id="f3cd8-106">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-106">Media logs</span></span>

-   <span data-ttu-id="f3cd8-107">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-107">Desktop logs</span></span>

<span data-ttu-id="f3cd8-108">Microsoft Support를 사용하여 지원 요청을 만들 때 지원 엔지니어는 디버그 로그를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="f3cd8-109">지원 요청을 만들기 전에 디버그 로그를 진행하면 Microsoft에서 문제 해결을 신속하게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="f3cd8-110">**미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="f3cd8-111">이 문서에서 **디버그** 로그는 문제 해결에 사용되는 로그를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="f3cd8-112">그러나 이러한 로그에 대해 생성된 파일에는 이름에 진단 **로그이라는** 용어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="f3cd8-113">다음 표에서는 다양한 클라이언트 및 해당 관련 로그를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="f3cd8-114">로그 파일은 클라이언트 및 운영 체제에 특정 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="f3cd8-115">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f3cd8-115">Client</span></span> |<span data-ttu-id="f3cd8-116">디버그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-116">Debug</span></span>|<span data-ttu-id="f3cd8-117">데스크톱</span><span class="sxs-lookup"><span data-stu-id="f3cd8-117">Desktop</span></span>|<span data-ttu-id="f3cd8-118">미디어</span><span class="sxs-lookup"><span data-stu-id="f3cd8-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="f3cd8-119">웹</span><span class="sxs-lookup"><span data-stu-id="f3cd8-119">Web</span></span>    |<span data-ttu-id="f3cd8-120">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-120">X</span></span>         |-         |-         |
|<span data-ttu-id="f3cd8-121">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cd8-121">Windows</span></span>     |<span data-ttu-id="f3cd8-122">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-122">X</span></span>         |<span data-ttu-id="f3cd8-123">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-123">X</span></span>         |<span data-ttu-id="f3cd8-124">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-124">X</span></span>         |
|<span data-ttu-id="f3cd8-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f3cd8-125">Mac OSX</span></span>     |<span data-ttu-id="f3cd8-126">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-126">X</span></span>         |<span data-ttu-id="f3cd8-127">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-127">X</span></span>         |<span data-ttu-id="f3cd8-128">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-128">X</span></span>         |
|<span data-ttu-id="f3cd8-129">Linux</span><span class="sxs-lookup"><span data-stu-id="f3cd8-129">Linux</span></span>     |<span data-ttu-id="f3cd8-130">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-130">X</span></span>         |<span data-ttu-id="f3cd8-131">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-131">X</span></span>         |<span data-ttu-id="f3cd8-132">X</span><span class="sxs-lookup"><span data-stu-id="f3cd8-132">X</span></span>         |
|<span data-ttu-id="f3cd8-133">iOS</span><span class="sxs-lookup"><span data-stu-id="f3cd8-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="f3cd8-134">Android</span><span class="sxs-lookup"><span data-stu-id="f3cd8-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="f3cd8-135">지원되는 운영 체제 및 브라우저의 전체 목록은 에 대한 클라이언트 [Microsoft Teams.](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="f3cd8-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="f3cd8-136">로그 디버그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="f3cd8-137">이러한 로그는 가장 일반적인 로그로 모든 Microsoft 지원 사례에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="f3cd8-138">디버그 로그는 브라우저 기반 Windows 및 Mac 데스크톱 클라이언트에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="f3cd8-139">로그는 텍스트 기반이 며 아래쪽에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="f3cd8-140">텍스트 기반 편집기를 사용하여 읽을 수 있으며, 클라이언트에 로그인할 때 새 로그가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="f3cd8-141">디버그 로그에는 다음 데이터 흐름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="f3cd8-142">로그인</span><span class="sxs-lookup"><span data-stu-id="f3cd8-142">Login</span></span>

-   <span data-ttu-id="f3cd8-143">중간 계층 서비스에 대한 연결 요청</span><span class="sxs-lookup"><span data-stu-id="f3cd8-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="f3cd8-144">통화/대화</span><span class="sxs-lookup"><span data-stu-id="f3cd8-144">Call/conversation</span></span>

<span data-ttu-id="f3cd8-145">디버그 로그는 다음 OS별 메서드를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="f3cd8-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="f3cd8-146">Windows:</span></span>

      <span data-ttu-id="f3cd8-147">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f3cd8-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="f3cd8-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="f3cd8-148">Mac OSX:</span></span>

      <span data-ttu-id="f3cd8-149">바로 가기 키: 옵션 + 명령 + Shift+1</span><span class="sxs-lookup"><span data-stu-id="f3cd8-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="f3cd8-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="f3cd8-150">Linux:</span></span>

      <span data-ttu-id="f3cd8-151">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f3cd8-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="f3cd8-152">디버그 로그는 다음 폴더에 자동으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="f3cd8-153">Windows: %userprofile% \\ 다운로드</span><span class="sxs-lookup"><span data-stu-id="f3cd8-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="f3cd8-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="f3cd8-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="f3cd8-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="f3cd8-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="f3cd8-156">브라우저: 디버그 로그를 기본 저장 위치로 저장하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="f3cd8-157">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-157">Media logs</span></span>
---------------------------

<span data-ttu-id="f3cd8-158">미디어 로그에는 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="f3cd8-159">호출 관련 문제에 연결된 지원 사례에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="f3cd8-160">미디어 로깅이 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-160">Media logging is turned off by default.</span></span> <span data-ttu-id="f3cd8-161">모임에 대한 진단 데이터를 Teams 클라이언트에서 옵션을 설정해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="f3cd8-162">일반 **설정** 으로 이동하여 모임 진단에 로깅 사용(Teams 다시 시작 필요) 확인란을 선택하고, Teams 다시 시작하고  >  문제를 재현합니다. </span><span class="sxs-lookup"><span data-stu-id="f3cd8-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="f3cd8-163">다음 표에서는 미디어 로그 위치를 간략하게 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="f3cd8-164">Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 커버하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="f3cd8-165">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f3cd8-165">Client</span></span> |<span data-ttu-id="f3cd8-166">위치</span><span class="sxs-lookup"><span data-stu-id="f3cd8-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f3cd8-167">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cd8-167">Windows</span></span>     |<span data-ttu-id="f3cd8-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="f3cd8-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="f3cd8-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="f3cd8-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="f3cd8-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f3cd8-171">Mac OSX</span></span>     |<span data-ttu-id="f3cd8-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="f3cd8-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="f3cd8-174">Linux</span><span class="sxs-lookup"><span data-stu-id="f3cd8-174">Linux</span></span>       |<span data-ttu-id="f3cd8-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="f3cd8-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="f3cd8-177">생성되는 로그 파일 목록과 포함된 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="f3cd8-178">로그 파일 이름</span><span class="sxs-lookup"><span data-stu-id="f3cd8-178">Log file name</span></span>  |<span data-ttu-id="f3cd8-179">설명</span><span class="sxs-lookup"><span data-stu-id="f3cd8-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f3cd8-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="f3cd8-181">미디어 스택과 관련된 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-181">Contains information related to the media stack.</span></span> <span data-ttu-id="f3cd8-182">여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 전송 및 수신된 프레임 수, 카메라 및 VBSS(비디오 기반 화면 공유) 세션 상태가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="f3cd8-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="f3cd8-184">제어가 제공된 타임스탬프 및 마우스 포인터 정보와 같은 원격 제어 작업과 관련된 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="f3cd8-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="f3cd8-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="f3cd8-186">미디어 스택 추적 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="f3cd8-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="f3cd8-188">렌더링 품질을 포함하여 미디어 에이전트와 관련된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="f3cd8-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="f3cd8-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="f3cd8-190">ts-calling API에서 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="f3cd8-191">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="f3cd8-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="f3cd8-192">부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="f3cd8-193">미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="f3cd8-194">로그는 텍스트 기반이 며, 하락 형식의 텍스트 기반 편집기를 사용하여 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="f3cd8-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="f3cd8-195">Windows:</span></span>

 - <span data-ttu-id="f3cd8-196">시스템 **트레이에서** Microsoft Teams 아이콘을 마우스 오른쪽 단추로 클릭하고 로그를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3cd8-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="f3cd8-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="f3cd8-197">Mac OsX:</span></span>

 - <span data-ttu-id="f3cd8-198">도움말 **풀다운 메뉴에서** 로그를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="f3cd8-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="f3cd8-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="f3cd8-199">Linux:</span></span>

 - <span data-ttu-id="f3cd8-200">시스템 **트레이에서** Microsoft Teams 아이콘을 클릭하고 로그를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3cd8-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="f3cd8-201">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f3cd8-201">Client</span></span> |<span data-ttu-id="f3cd8-202">위치</span><span class="sxs-lookup"><span data-stu-id="f3cd8-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f3cd8-203">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cd8-203">Windows</span></span>     |<span data-ttu-id="f3cd8-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="f3cd8-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="f3cd8-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f3cd8-205">Mac OSX</span></span>     |<span data-ttu-id="f3cd8-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="f3cd8-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="f3cd8-207">Linux</span><span class="sxs-lookup"><span data-stu-id="f3cd8-207">Linux</span></span>       |<span data-ttu-id="f3cd8-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="f3cd8-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="f3cd8-209">브라우저 추적</span><span class="sxs-lookup"><span data-stu-id="f3cd8-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="f3cd8-210">일부 오류 범주의 경우 Microsoft 지원에서 브라우저 추적을 수집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="f3cd8-211">이 정보는 오류 발생 시 클라이언트의 Teams 중요한 세부 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="f3cd8-212">브라우저 추적을 시작하기 전에 로그인되어 있는지 Teams.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="f3cd8-213">추적에 중요한 로그인 정보가 포함되지 않습니다. 추적을 시작하기 전에 이 작업을 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="f3cd8-214">로그인한 후 브라우저에 적합한 다음 링크 중 하나를 선택하고 제공된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="f3cd8-215">Chrome & Edge(Chromium)</span><span class="sxs-lookup"><span data-stu-id="f3cd8-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="f3cd8-216">Edge</span><span class="sxs-lookup"><span data-stu-id="f3cd8-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="f3cd8-217">Safari</span><span class="sxs-lookup"><span data-stu-id="f3cd8-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="f3cd8-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="f3cd8-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="f3cd8-219">이 단계에서 Azure Portal에 대한 모든 참조를 Teams 클라이언트로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="f3cd8-220">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f3cd8-220">Related topics</span></span>

[<span data-ttu-id="f3cd8-221">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f3cd8-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
