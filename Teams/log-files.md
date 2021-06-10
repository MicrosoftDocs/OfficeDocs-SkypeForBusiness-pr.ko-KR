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
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689696"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="b9dac-103">로그 파일을 사용하여 로그 파일을 모니터링하고 문제를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9dac-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="b9dac-104">클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있습니다. 이러한 로그 파일을 모니터링 및 문제 해결을 지원하기 위해 활용할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="b9dac-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="b9dac-105">로그 디버그</span><span class="sxs-lookup"><span data-stu-id="b9dac-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="b9dac-106">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="b9dac-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="b9dac-107">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="b9dac-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="b9dac-108">이 문서에서는 이러한 로그와 이 로그가 사용되는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="b9dac-109">특정 문제 해결에 대한 자세한 내용은 문제 [해결 Teams 참조하세요.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="b9dac-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="b9dac-110">지원에 문의하는 방법에 대한 자세한 내용은 지원 을 [참조하세요.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="b9dac-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="b9dac-111">Microsoft Support를 사용하여 지원 요청을 만들 때 지원 엔지니어는 디버그 로그를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="b9dac-112">지원 요청을 만들기 전에 디버그 로그를 진행하면 Microsoft에서 문제 해결을 신속하게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="b9dac-113">**미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="b9dac-114">이 문서에서 **디버그** 로그는 문제 해결에 사용되는 로그를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="b9dac-115">그러나 이러한 로그에 대해 생성된 파일에는 이름에 진단 **로그이라는** 용어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="b9dac-116">로깅 수집 및 사용</span><span class="sxs-lookup"><span data-stu-id="b9dac-116">Collect and enable logging</span></span>

<span data-ttu-id="b9dac-117">문제가 발생하는 즉시 로그를 수집하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="b9dac-118">몇 번의 클릭으로 로그를 함께 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="b9dac-119">Windows: 시스템 Teams 아이콘을 마우스 오른쪽 단추로 클릭하고 지원 파일 수집을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="b9dac-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="b9dac-120">Mac: 도움말 메뉴를 선택하고 지원 파일 **수집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9dac-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="b9dac-121">디버그, 데스크톱 및 미디어 로그는 MSTeams Diagnostics Log 이름이 있는 한 폴더에 <local data and time> 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="b9dac-122">Microsoft 지원에서 지원 요청을 열 때 이 폴더를 압축하고 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="b9dac-123">폴더에는 데스크톱, 모임(미디어), 디버그(웹)에 대한 폴더가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="b9dac-124">다음 바로 가기 키를 사용하여 파일을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="b9dac-125">Windows: Crtl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="b9dac-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="b9dac-126">Mac: 옵션 + 명령 + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="b9dac-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="b9dac-127">미디어 로깅이 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-127">Media logging is turned off by default.</span></span> <span data-ttu-id="b9dac-128">미디어 로깅을 사용하도록 설정하려면 사용자는 클라이언트에서 옵션을 설정해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="b9dac-129">일반 **설정** 으로 이동하고 모임 진단에 로깅 사용(다시 시작  >   **필요)을 Teams.**</span><span class="sxs-lookup"><span data-stu-id="b9dac-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="b9dac-130">로깅을 Teams 클라이언트를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="b9dac-131">미디어 로깅을 사용하도록 설정하면 오디오 및 비디오 문제를 조사하는 데 필요한 추가 파일이 모임 폴더에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="b9dac-132">미디어 로깅을 사용하도록 설정하지 않은 경우 사용할 수 있는 로그 수가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="b9dac-133">다음 표에서는 다양한 클라이언트 및 해당 관련 로그를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="b9dac-134">로그 파일은 클라이언트 및 운영 체제에 특정 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="b9dac-135">클라이언트</span><span class="sxs-lookup"><span data-stu-id="b9dac-135">Client</span></span> |<span data-ttu-id="b9dac-136">디버그</span><span class="sxs-lookup"><span data-stu-id="b9dac-136">Debug</span></span>|<span data-ttu-id="b9dac-137">데스크톱</span><span class="sxs-lookup"><span data-stu-id="b9dac-137">Desktop</span></span>|<span data-ttu-id="b9dac-138">미디어</span><span class="sxs-lookup"><span data-stu-id="b9dac-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="b9dac-139">웹</span><span class="sxs-lookup"><span data-stu-id="b9dac-139">Web</span></span>    |<span data-ttu-id="b9dac-140">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-140">X</span></span>         |-         |-         |
|<span data-ttu-id="b9dac-141">Windows</span><span class="sxs-lookup"><span data-stu-id="b9dac-141">Windows</span></span>     |<span data-ttu-id="b9dac-142">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-142">X</span></span>         |<span data-ttu-id="b9dac-143">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-143">X</span></span>         |<span data-ttu-id="b9dac-144">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-144">X</span></span>         |
|<span data-ttu-id="b9dac-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b9dac-145">Mac OSX</span></span>     |<span data-ttu-id="b9dac-146">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-146">X</span></span>         |<span data-ttu-id="b9dac-147">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-147">X</span></span>         |<span data-ttu-id="b9dac-148">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-148">X</span></span>         |
|<span data-ttu-id="b9dac-149">Linux</span><span class="sxs-lookup"><span data-stu-id="b9dac-149">Linux</span></span>     |<span data-ttu-id="b9dac-150">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-150">X</span></span>         |<span data-ttu-id="b9dac-151">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-151">X</span></span>         |<span data-ttu-id="b9dac-152">X</span><span class="sxs-lookup"><span data-stu-id="b9dac-152">X</span></span>         |
|<span data-ttu-id="b9dac-153">iOS</span><span class="sxs-lookup"><span data-stu-id="b9dac-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="b9dac-154">Android</span><span class="sxs-lookup"><span data-stu-id="b9dac-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="b9dac-155">지원되는 운영 체제 및 브라우저의 전체 목록은 에 대한 클라이언트 [Microsoft Teams.](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="b9dac-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="b9dac-156">로그 디버그</span><span class="sxs-lookup"><span data-stu-id="b9dac-156">Debug logs</span></span>

<span data-ttu-id="b9dac-157">로깅  및 Mac에 대한 수집 및 사용 Windows 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9dac-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="b9dac-158">디버그 로그는 브라우저 기반 Windows 및 Mac 데스크톱 클라이언트에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="b9dac-159">로그는 텍스트 기반으로 아래쪽에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="b9dac-160">텍스트 기반 편집기를 사용하여 읽을 수 있으며, 클라이언트에 로그인할 때 새 로그가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="b9dac-161">디버그 로그에는 다음 데이터 흐름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="b9dac-162">로그인</span><span class="sxs-lookup"><span data-stu-id="b9dac-162">Login</span></span>

-   <span data-ttu-id="b9dac-163">중간 계층 서비스에 대한 연결 요청</span><span class="sxs-lookup"><span data-stu-id="b9dac-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="b9dac-164">통화/대화</span><span class="sxs-lookup"><span data-stu-id="b9dac-164">Call/conversation</span></span>

<span data-ttu-id="b9dac-165">Linux에 대한 로그를 수집하려면 바로 가기: Ctrl + Alt + Shift + 1 파일은 ~/Downloads에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="b9dac-166">브라우저에 대한 로그 수집: 바로 가기 키: Crtl + Alt + Shift + 1 파일은 %userprofile%\Downloads에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="b9dac-167">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="b9dac-167">Media logs</span></span>

<span data-ttu-id="b9dac-168">로깅  및 Mac에 대한 수집 및 사용 Windows 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9dac-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="b9dac-169">미디어 로그에는 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="b9dac-170">호출 관련 문제에 연결된 지원 사례에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="b9dac-171">미디어 로깅이 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-171">Media logging is turned off by default.</span></span> <span data-ttu-id="b9dac-172">모임에 대한 진단 데이터를 Teams 클라이언트에서 옵션을 설정해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="b9dac-173">일반 **설정** 으로 이동하여 모임 진단에 로깅 사용(Teams 다시 시작 필요) 확인란을 선택하고, Teams 다시 시작하고  >  문제를 재현합니다. </span><span class="sxs-lookup"><span data-stu-id="b9dac-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="b9dac-174">Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 커버하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="b9dac-175">Linux에 대한 로그를 수집하려면 ~/.config/Microsoft/Microsoft Teams/media-stack/.blog 및 *~/.config/Microsoft/Microsoft Teams/skylib/.blog에서* 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="b9dac-176">생성되는 로그 파일 목록과 포함된 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="b9dac-177">로그 파일 이름</span><span class="sxs-lookup"><span data-stu-id="b9dac-177">Log file name</span></span>  |<span data-ttu-id="b9dac-178">설명</span><span class="sxs-lookup"><span data-stu-id="b9dac-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b9dac-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="b9dac-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="b9dac-180">미디어 스택과 관련된 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-180">Contains information related to the media stack.</span></span> <span data-ttu-id="b9dac-181">여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 전송 및 수신된 프레임 수, 카메라 및 VBSS(비디오 기반 화면 공유) 세션 상태가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="b9dac-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="b9dac-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="b9dac-183">제어가 제공된 타임스탬프 및 마우스 포인터 정보와 같은 원격 제어 작업과 관련된 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="b9dac-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="b9dac-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="b9dac-185">미디어 스택 추적 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="b9dac-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="b9dac-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="b9dac-187">렌더링 품질을 포함하여 미디어 에이전트와 관련된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="b9dac-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="b9dac-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="b9dac-189">ts-calling API에서 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="b9dac-190">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="b9dac-190">Desktop logs</span></span>

<span data-ttu-id="b9dac-191">로깅  및 Mac에 대한 수집 및 사용 Windows 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9dac-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="b9dac-192">부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="b9dac-193">미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="b9dac-194">로그는 텍스트 기반으로, 하락 형식의 텍스트 기반 편집기를 사용하여 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="b9dac-195">Linux에 대한 로그를 수집하려면 시스템 Microsoft Teams 아이콘을 클릭하고 로그를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9dac-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="b9dac-196">파일은 ~/.config/Microsoft/Microsoft Teams/logs.txt.</span><span class="sxs-lookup"><span data-stu-id="b9dac-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="b9dac-197">브라우저 추적</span><span class="sxs-lookup"><span data-stu-id="b9dac-197">Browser trace</span></span>

<span data-ttu-id="b9dac-198">일부 오류 범주의 경우 Microsoft 지원에서 브라우저 추적을 수집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="b9dac-199">이 정보는 오류 발생 시 클라이언트의 Teams 중요한 세부 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="b9dac-200">브라우저 추적을 시작하기 전에 로그인되어 있는지 Teams.</span><span class="sxs-lookup"><span data-stu-id="b9dac-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="b9dac-201">추적에 중요한 로그인 정보가 포함되지 않습니다. 추적을 시작하기 전에 이 작업을 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="b9dac-202">로그인한 후 브라우저에 적합한 다음 링크 중 하나를 선택하고 제공된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="b9dac-203">Chrome & Edge(Chromium)</span><span class="sxs-lookup"><span data-stu-id="b9dac-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="b9dac-204">Edge</span><span class="sxs-lookup"><span data-stu-id="b9dac-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="b9dac-205">Safari</span><span class="sxs-lookup"><span data-stu-id="b9dac-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="b9dac-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="b9dac-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="b9dac-207">이 단계에서 Azure Portal에 대한 모든 참조를 Teams 클라이언트로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="b9dac-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b9dac-208">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b9dac-208">Related topics</span></span>

[<span data-ttu-id="b9dac-209">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b9dac-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
