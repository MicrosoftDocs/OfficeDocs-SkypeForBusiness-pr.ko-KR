---
title: Microsoft 팀 문제 해결에서 로그 파일 사용
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
description: Microsoft 팀에서 생성 하는 디버그, 미디어, 데스크톱 로그, 찾을 수 있는 위치, 문제 해결에 도움이 되는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650831"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="c2f60-103">Microsoft 팀 문제 해결에서 로그 파일 사용</span><span class="sxs-lookup"><span data-stu-id="c2f60-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="c2f60-104">Microsoft 팀의 문제 해결을 지원 하기 위해 사용할 수 있는 세 가지 유형의 로그 파일이 클라이언트에서 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="c2f60-105">디버그 로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-105">Debug logs</span></span>

-   <span data-ttu-id="c2f60-106">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-106">Media logs</span></span>

-   <span data-ttu-id="c2f60-107">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-107">Desktop logs</span></span>

<span data-ttu-id="c2f60-108">Microsoft 지원으로 지원 요청을 만들 때 지원 엔지니어에 게 디버그 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="c2f60-109">지원 요청을 만들기 전에 이러한 로그에 로그인 하면 Microsoft에서 문제 해결을 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="c2f60-110">Microsoft에서 요청 하는 경우에만 미디어 또는 데스크톱 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="c2f60-111">다음 표에서는 다양 한 클라이언트 및 관련 로그에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="c2f60-112">로그 파일은 클라이언트 및 운영 체제와 관련 된 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="c2f60-113">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c2f60-113">Client</span></span> |<span data-ttu-id="c2f60-114">디버깅이</span><span class="sxs-lookup"><span data-stu-id="c2f60-114">Debug</span></span>|<span data-ttu-id="c2f60-115">데스크톱이</span><span class="sxs-lookup"><span data-stu-id="c2f60-115">Desktop</span></span>|<span data-ttu-id="c2f60-116">미디어</span><span class="sxs-lookup"><span data-stu-id="c2f60-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="c2f60-117">웹</span><span class="sxs-lookup"><span data-stu-id="c2f60-117">Web</span></span>    |<span data-ttu-id="c2f60-118">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-118">X</span></span>         |-         |-         |
|<span data-ttu-id="c2f60-119">Windows</span><span class="sxs-lookup"><span data-stu-id="c2f60-119">Windows</span></span>     |<span data-ttu-id="c2f60-120">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-120">X</span></span>         |<span data-ttu-id="c2f60-121">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-121">X</span></span>         |<span data-ttu-id="c2f60-122">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-122">X</span></span>         |
|<span data-ttu-id="c2f60-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="c2f60-123">Mac OSX</span></span>     |<span data-ttu-id="c2f60-124">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-124">X</span></span>         |<span data-ttu-id="c2f60-125">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-125">X</span></span>         |<span data-ttu-id="c2f60-126">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-126">X</span></span>         |
|<span data-ttu-id="c2f60-127">Linux</span><span class="sxs-lookup"><span data-stu-id="c2f60-127">Linux</span></span>     |<span data-ttu-id="c2f60-128">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-128">X</span></span>         |<span data-ttu-id="c2f60-129">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-129">X</span></span>         |<span data-ttu-id="c2f60-130">X</span><span class="sxs-lookup"><span data-stu-id="c2f60-130">X</span></span>         |
|<span data-ttu-id="c2f60-131">iOS</span><span class="sxs-lookup"><span data-stu-id="c2f60-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="c2f60-132">Android</span><span class="sxs-lookup"><span data-stu-id="c2f60-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="c2f60-133">지원 되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2f60-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="c2f60-134">디버그 로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="c2f60-135">가장 일반적인 로그가 며 모든 Microsoft 지원 사례에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="c2f60-136">디버그 로그는 브라우저 기반 클라이언트를 비롯 하 여 Windows 및 Mac 데스크톱 클라이언트에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="c2f60-137">로그는 텍스트 기반 이며 아래쪽에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="c2f60-138">모든 텍스트 기반 편집기를 사용 하 여 읽을 수 있으며, 클라이언트에 로그인 할 때 새 로그가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="c2f60-139">디버그 로그에는 다음과 같은 데이터 흐름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="c2f60-140">로그인</span><span class="sxs-lookup"><span data-stu-id="c2f60-140">Login</span></span>

-   <span data-ttu-id="c2f60-141">중앙 계층 서비스에 대 한 연결 요청</span><span class="sxs-lookup"><span data-stu-id="c2f60-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="c2f60-142">통화/대화</span><span class="sxs-lookup"><span data-stu-id="c2f60-142">Call/conversation</span></span>

<span data-ttu-id="c2f60-143">디버그 로그는 다음 OS 관련 메서드를 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="c2f60-144">창을</span><span class="sxs-lookup"><span data-stu-id="c2f60-144">Windows:</span></span>

      <span data-ttu-id="c2f60-145">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="c2f60-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="c2f60-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="c2f60-146">Mac OSX:</span></span>

      <span data-ttu-id="c2f60-147">바로 가기 키: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="c2f60-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="c2f60-148">Linux</span><span class="sxs-lookup"><span data-stu-id="c2f60-148">Linux:</span></span>

      <span data-ttu-id="c2f60-149">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="c2f60-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="c2f60-150">디버그 로그는 다음 폴더에 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="c2f60-151">Windows:% userprofile% \\ 다운로드</span><span class="sxs-lookup"><span data-stu-id="c2f60-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="c2f60-152">Mac OSX: ~/다운로드</span><span class="sxs-lookup"><span data-stu-id="c2f60-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="c2f60-153">Linux: ~/다운로드</span><span class="sxs-lookup"><span data-stu-id="c2f60-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="c2f60-154">브라우저: 디버그 로그를 기본 저장 위치에 저장 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="c2f60-155">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-155">Media logs</span></span>
---------------------------

<span data-ttu-id="c2f60-156">미디어 로그에는 팀 모임에서 오디오, 비디오, 화면 공유에 대 한 진단 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="c2f60-157">통화 관련 문제에 연결 된 지원 사례에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="c2f60-158">미디어 로깅은 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-158">Media logging is turned off by default.</span></span> <span data-ttu-id="c2f60-159">팀 모임에 대 한 진단 데이터를 기록 하려면 사용자가 팀 클라이언트에서 옵션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="c2f60-160">**설정**  >  **일반**으로 이동 하 여 **모임 진단 로깅 사용 (팀 다시 시작 필요**) 확인란을 선택한 다음 팀을 다시 시작 하 고 문제를 재현해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c2f60-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="c2f60-161">다음 표에서는 미디어 로그 위치에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="c2f60-162">Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임 스탬프를 확인 하 여 문제를 재현할 때 로그가 시간 프레임을 포함 하는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2f60-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="c2f60-163">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c2f60-163">Client</span></span> |<span data-ttu-id="c2f60-164">위치</span><span class="sxs-lookup"><span data-stu-id="c2f60-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="c2f60-165">Windows</span><span class="sxs-lookup"><span data-stu-id="c2f60-165">Windows</span></span>     |<span data-ttu-id="c2f60-166">%appdata%\Microsoft\Teams\media-stack \\ \* 블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="c2f60-167">%appdata%\Microsoft\Teams\skylib \\ \* 블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="c2f60-168">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="c2f60-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="c2f60-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="c2f60-169">Mac OSX</span></span>     |<span data-ttu-id="c2f60-170">~/Library/Application Support/Microsoft/팀/media-stack/\* 블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="c2f60-171">~/Library/Application Support/Microsoft/팀/skylib/\* 블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="c2f60-172">Linux</span><span class="sxs-lookup"><span data-stu-id="c2f60-172">Linux</span></span>       |<span data-ttu-id="c2f60-173">~/.config/Microsoft/Microsoft 팀/media-stack/\*-블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="c2f60-174">~/.config/Microsoft/Microsoft 팀/skylib/\*-블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="c2f60-175">생성 되는 로그 파일과 해당 파일에 포함 된 정보 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="c2f60-176">로그 파일 이름</span><span class="sxs-lookup"><span data-stu-id="c2f60-176">Log file name</span></span>  |<span data-ttu-id="c2f60-177">설명</span><span class="sxs-lookup"><span data-stu-id="c2f60-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c2f60-178">팀. msrtc-0-s1039525249. 블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="c2f60-179">미디어 스택과 관련 된 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-179">Contains information related to the media stack.</span></span> <span data-ttu-id="c2f60-180">여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 보내고 받은 프레임 수, 카메라 및 비디오 기반 화면 공유 (VBSS) 세션 상태 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="c2f60-181">rtmcontrol-msrtc-0-2415069487. 블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="c2f60-182">컨트롤을 지정 하는 경우의 타임 스탬프 및 마우스 포인터 정보 등 원격 제어 작업과 관련 된 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="c2f60-183">Teams_MediaStackETW -2-U-xr-U .etl</span><span class="sxs-lookup"><span data-stu-id="c2f60-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="c2f60-184">미디어 스택 추적 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="c2f60-185">디버그-0-s2790420889</span><span class="sxs-lookup"><span data-stu-id="c2f60-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="c2f60-186">미디어 에이전트와 관련 된 정보 (렌더링 품질 포함)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="c2f60-187">tscalling-0-2061129496-블로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="c2f60-188">Ts 호출 API의 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="c2f60-189">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="c2f60-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="c2f60-190">데스크톱 로그 (부트스트래퍼 로그 라고도 함)는 데스크톱 클라이언트와 브라우저 간에 발생 하는 로그 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-190">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="c2f60-191">이 로그는 미디어 로그와 마찬가지로, Microsoft에서 요청 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-191">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="c2f60-192">로그는 텍스트 기반 이며, 텍스트 기반 편집기를 사용 하 여 하향식 형식으로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-192">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="c2f60-193">창을</span><span class="sxs-lookup"><span data-stu-id="c2f60-193">Windows:</span></span>

1.  <span data-ttu-id="c2f60-194">시스템 트레이에서 **Microsoft 팀** 아이콘을 마우스 오른쪽 단추로 클릭 하 고 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="c2f60-195">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="c2f60-195">Mac OsX:</span></span>

1.  <span data-ttu-id="c2f60-196">**도움말** 풀 다운 메뉴에서 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="c2f60-197">Linux</span><span class="sxs-lookup"><span data-stu-id="c2f60-197">Linux:</span></span>

1.  <span data-ttu-id="c2f60-198">시스템 트레이에서 **Microsoft 팀** 아이콘을 클릭 하 고 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f60-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="c2f60-199">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c2f60-199">Client</span></span> |<span data-ttu-id="c2f60-200">위치</span><span class="sxs-lookup"><span data-stu-id="c2f60-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="c2f60-201">Windows</span><span class="sxs-lookup"><span data-stu-id="c2f60-201">Windows</span></span>     |<span data-ttu-id="c2f60-202">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="c2f60-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="c2f60-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="c2f60-203">Mac OSX</span></span>     |<span data-ttu-id="c2f60-204">~/Library/Application 지원/Microsoft/팀/logs.txt</span><span class="sxs-lookup"><span data-stu-id="c2f60-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="c2f60-205">Linux</span><span class="sxs-lookup"><span data-stu-id="c2f60-205">Linux</span></span>       |<span data-ttu-id="c2f60-206">~/.config/Microsoft/Microsoft 팀/logs.txt</span><span class="sxs-lookup"><span data-stu-id="c2f60-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="c2f60-207">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c2f60-207">Related topics</span></span>

[<span data-ttu-id="c2f60-208">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c2f60-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
