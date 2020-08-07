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
ms.openlocfilehash: f13acc1a401a6753b335c17fe0cd8a7984849216
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582115"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="8f07d-103">Microsoft 팀 문제 해결에서 로그 파일 사용</span><span class="sxs-lookup"><span data-stu-id="8f07d-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="8f07d-104">Microsoft 팀의 문제 해결을 지원 하기 위해 사용할 수 있는 세 가지 유형의 로그 파일이 클라이언트에서 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="8f07d-105">디버그 로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-105">Debug logs</span></span>

-   <span data-ttu-id="8f07d-106">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-106">Media logs</span></span>

-   <span data-ttu-id="8f07d-107">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-107">Desktop logs</span></span>

<span data-ttu-id="8f07d-108">Microsoft 지원으로 지원 요청을 만들 때 지원 엔지니어에 게 디버그 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="8f07d-109">지원 요청을 만들기 전에 이러한 로그에 로그인 하면 Microsoft에서 문제 해결을 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="8f07d-110">Microsoft에서 요청 하는 경우에만 미디어 또는 데스크톱 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="8f07d-111">다음 표에서는 다양 한 클라이언트 및 관련 로그에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="8f07d-112">로그 파일은 클라이언트 및 운영 체제와 관련 된 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="8f07d-113">클라이언트</span><span class="sxs-lookup"><span data-stu-id="8f07d-113">Client</span></span> |<span data-ttu-id="8f07d-114">디버깅이</span><span class="sxs-lookup"><span data-stu-id="8f07d-114">Debug</span></span>|<span data-ttu-id="8f07d-115">데스크톱이</span><span class="sxs-lookup"><span data-stu-id="8f07d-115">Desktop</span></span>|<span data-ttu-id="8f07d-116">미디어</span><span class="sxs-lookup"><span data-stu-id="8f07d-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="8f07d-117">웹</span><span class="sxs-lookup"><span data-stu-id="8f07d-117">Web</span></span>    |<span data-ttu-id="8f07d-118">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-118">X</span></span>         |-         |-         |
|<span data-ttu-id="8f07d-119">Windows</span><span class="sxs-lookup"><span data-stu-id="8f07d-119">Windows</span></span>     |<span data-ttu-id="8f07d-120">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-120">X</span></span>         |<span data-ttu-id="8f07d-121">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-121">X</span></span>         |<span data-ttu-id="8f07d-122">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-122">X</span></span>         |
|<span data-ttu-id="8f07d-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="8f07d-123">Mac OSX</span></span>     |<span data-ttu-id="8f07d-124">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-124">X</span></span>         |<span data-ttu-id="8f07d-125">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-125">X</span></span>         |<span data-ttu-id="8f07d-126">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-126">X</span></span>         |
|<span data-ttu-id="8f07d-127">Linux</span><span class="sxs-lookup"><span data-stu-id="8f07d-127">Linux</span></span>     |<span data-ttu-id="8f07d-128">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-128">X</span></span>         |<span data-ttu-id="8f07d-129">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-129">X</span></span>         |<span data-ttu-id="8f07d-130">X</span><span class="sxs-lookup"><span data-stu-id="8f07d-130">X</span></span>         |
|<span data-ttu-id="8f07d-131">iOS</span><span class="sxs-lookup"><span data-stu-id="8f07d-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="8f07d-132">Android</span><span class="sxs-lookup"><span data-stu-id="8f07d-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="8f07d-133">지원 되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f07d-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="8f07d-134">디버그 로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="8f07d-135">가장 일반적인 로그가 며 모든 Microsoft 지원 사례에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="8f07d-136">디버그 로그는 브라우저 기반 클라이언트를 비롯 하 여 Windows 및 Mac 데스크톱 클라이언트에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="8f07d-137">로그는 텍스트 기반 이며 아래쪽에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="8f07d-138">모든 텍스트 기반 편집기를 사용 하 여 읽을 수 있으며, 클라이언트에 로그인 할 때 새 로그가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="8f07d-139">디버그 로그에는 다음과 같은 데이터 흐름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="8f07d-140">로그인</span><span class="sxs-lookup"><span data-stu-id="8f07d-140">Login</span></span>

-   <span data-ttu-id="8f07d-141">중앙 계층 서비스에 대 한 연결 요청</span><span class="sxs-lookup"><span data-stu-id="8f07d-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="8f07d-142">통화/대화</span><span class="sxs-lookup"><span data-stu-id="8f07d-142">Call/conversation</span></span>

<span data-ttu-id="8f07d-143">디버그 로그는 다음 OS 관련 메서드를 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="8f07d-144">창을</span><span class="sxs-lookup"><span data-stu-id="8f07d-144">Windows:</span></span>

      <span data-ttu-id="8f07d-145">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="8f07d-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="8f07d-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="8f07d-146">Mac OSX:</span></span>

      <span data-ttu-id="8f07d-147">바로 가기 키: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="8f07d-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="8f07d-148">Linux</span><span class="sxs-lookup"><span data-stu-id="8f07d-148">Linux:</span></span>

      <span data-ttu-id="8f07d-149">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="8f07d-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="8f07d-150">디버그 로그는 다음 폴더에 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="8f07d-151">Windows:% userprofile% \\ 다운로드</span><span class="sxs-lookup"><span data-stu-id="8f07d-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="8f07d-152">Mac OSX: 다운로드</span><span class="sxs-lookup"><span data-stu-id="8f07d-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="8f07d-153">Linux: ~/다운로드</span><span class="sxs-lookup"><span data-stu-id="8f07d-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="8f07d-154">브라우저: 디버그 로그를 기본 저장 위치에 저장 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="8f07d-155">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="8f07d-156">미디어 로그에는 오디오, 비디오, 화면 공유에 대 한 진단 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="8f07d-157">요청 시에만 지원 서비스 케이스에 필요 하며 Microsoft만 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="8f07d-158">다음 표에서는 로그 위치에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="8f07d-159">클라이언트</span><span class="sxs-lookup"><span data-stu-id="8f07d-159">Client</span></span> |<span data-ttu-id="8f07d-160">위치</span><span class="sxs-lookup"><span data-stu-id="8f07d-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="8f07d-161">Windows</span><span class="sxs-lookup"><span data-stu-id="8f07d-161">Windows</span></span>     |<span data-ttu-id="8f07d-162">%appdata%\Microsoft\Teams\media-stack \\ \* 블로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="8f07d-163">%appdata%\Microsoft\Teams\skylib \\ \* 블로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="8f07d-164">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="8f07d-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="8f07d-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="8f07d-165">Mac OSX</span></span>     |<span data-ttu-id="8f07d-166">~/Library/Application Support/Microsoft/팀/media-stack/\* 블로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="8f07d-167">~/Library/Application Support/Microsoft/팀/skylib/\* 블로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="8f07d-168">Linux</span><span class="sxs-lookup"><span data-stu-id="8f07d-168">Linux</span></span>       |<span data-ttu-id="8f07d-169">~/.config/Microsoft/Microsoft 팀/media-stack/\*-블로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="8f07d-170">~/.config/Microsoft/Microsoft 팀/skylib/\*-블로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="8f07d-171">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="8f07d-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="8f07d-172">데스크톱 로그 (부트스트래퍼 로그 라고도 함)는 데스크톱 클라이언트와 브라우저 간에 발생 하는 로그 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="8f07d-173">이 로그는 미디어 로그와 마찬가지로, Microsoft에서 요청 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="8f07d-174">로그는 텍스트 기반 이며, 텍스트 기반 편집기를 사용 하 여 하향식 형식으로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="8f07d-175">창을</span><span class="sxs-lookup"><span data-stu-id="8f07d-175">Windows:</span></span>

1.  <span data-ttu-id="8f07d-176">시스템 트레이에서 **Microsoft 팀** 아이콘을 마우스 오른쪽 단추로 클릭 하 고 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="8f07d-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="8f07d-177">Mac OsX:</span></span>

1.  <span data-ttu-id="8f07d-178">**도움말** 풀 다운 메뉴에서 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="8f07d-179">Linux</span><span class="sxs-lookup"><span data-stu-id="8f07d-179">Linux:</span></span>

1.  <span data-ttu-id="8f07d-180">시스템 트레이에서 **Microsoft 팀** 아이콘을 클릭 하 고 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f07d-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="8f07d-181">클라이언트</span><span class="sxs-lookup"><span data-stu-id="8f07d-181">Client</span></span> |<span data-ttu-id="8f07d-182">위치</span><span class="sxs-lookup"><span data-stu-id="8f07d-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="8f07d-183">Windows</span><span class="sxs-lookup"><span data-stu-id="8f07d-183">Windows</span></span>     |<span data-ttu-id="8f07d-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="8f07d-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="8f07d-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="8f07d-185">Mac OSX</span></span>     |<span data-ttu-id="8f07d-186">~/Library/Application 지원/Microsoft/팀/logs.txt</span><span class="sxs-lookup"><span data-stu-id="8f07d-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="8f07d-187">Linux</span><span class="sxs-lookup"><span data-stu-id="8f07d-187">Linux</span></span>       |<span data-ttu-id="8f07d-188">~/.config/Microsoft/Microsoft 팀/logs.txt</span><span class="sxs-lookup"><span data-stu-id="8f07d-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="8f07d-189">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8f07d-189">Related topics</span></span>

[<span data-ttu-id="8f07d-190">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8f07d-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

