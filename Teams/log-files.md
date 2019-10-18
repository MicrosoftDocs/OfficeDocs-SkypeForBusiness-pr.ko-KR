---
title: Microsoft 팀 문제 해결에서 로그 파일 사용
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft 팀에서 생성 하는 디버그, 미디어, 데스크톱 로그, 찾을 수 있는 위치, 문제 해결에 도움이 되는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba40d1d3694666f8fd0b4612ffe53c49808f7297
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570671"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="9858c-103">Microsoft 팀 문제 해결에서 로그 파일 사용</span><span class="sxs-lookup"><span data-stu-id="9858c-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="9858c-104">Microsoft 팀의 문제 해결을 지원 하기 위해 사용할 수 있는 세 가지 유형의 로그 파일이 클라이언트에서 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="9858c-105">디버그 로그</span><span class="sxs-lookup"><span data-stu-id="9858c-105">Debug logs</span></span>

-   <span data-ttu-id="9858c-106">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="9858c-106">Media logs</span></span>

-   <span data-ttu-id="9858c-107">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="9858c-107">Desktop logs</span></span>

<span data-ttu-id="9858c-108">Microsoft 지원으로 지원 요청을 만들 때 지원 엔지니어에 게 디버그 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="9858c-109">지원 요청을 만들기 전에 이러한 로그에 로그인 하면 Microsoft에서 문제 해결을 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="9858c-110">Microsoft에서 요청 하는 경우에만 미디어 또는 데스크톱 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="9858c-111">다음 표에서는 다양 한 클라이언트 및 관련 로그에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="9858c-112">로그 파일은 클라이언트 및 운영 체제와 관련 된 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="9858c-113">클라이언트측</span><span class="sxs-lookup"><span data-stu-id="9858c-113">Client</span></span> |<span data-ttu-id="9858c-114">디버깅이</span><span class="sxs-lookup"><span data-stu-id="9858c-114">Debug</span></span>|<span data-ttu-id="9858c-115">데스크톱이</span><span class="sxs-lookup"><span data-stu-id="9858c-115">Desktop</span></span>|<span data-ttu-id="9858c-116">미디어</span><span class="sxs-lookup"><span data-stu-id="9858c-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="9858c-117">웹</span><span class="sxs-lookup"><span data-stu-id="9858c-117">Web</span></span>    |<span data-ttu-id="9858c-118">축</span><span class="sxs-lookup"><span data-stu-id="9858c-118">X</span></span>         |-         |-         |
|<span data-ttu-id="9858c-119">창을</span><span class="sxs-lookup"><span data-stu-id="9858c-119">Windows</span></span>     |<span data-ttu-id="9858c-120">축</span><span class="sxs-lookup"><span data-stu-id="9858c-120">X</span></span>         |<span data-ttu-id="9858c-121">축</span><span class="sxs-lookup"><span data-stu-id="9858c-121">X</span></span>         |<span data-ttu-id="9858c-122">축</span><span class="sxs-lookup"><span data-stu-id="9858c-122">X</span></span>         |
|<span data-ttu-id="9858c-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9858c-123">Mac OSX</span></span>     |<span data-ttu-id="9858c-124">축</span><span class="sxs-lookup"><span data-stu-id="9858c-124">X</span></span>         |<span data-ttu-id="9858c-125">축</span><span class="sxs-lookup"><span data-stu-id="9858c-125">X</span></span>         |<span data-ttu-id="9858c-126">축</span><span class="sxs-lookup"><span data-stu-id="9858c-126">X</span></span>         |
|<span data-ttu-id="9858c-127">Io</span><span class="sxs-lookup"><span data-stu-id="9858c-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="9858c-128">Android</span><span class="sxs-lookup"><span data-stu-id="9858c-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="9858c-129">지원 되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9858c-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="9858c-130">디버그 로그</span><span class="sxs-lookup"><span data-stu-id="9858c-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="9858c-131">가장 일반적인 로그가 며 모든 Microsoft 지원 사례에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="9858c-132">디버그 로그는 브라우저 기반 클라이언트를 비롯 하 여 Windows 및 Mac 데스크톱 클라이언트에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="9858c-133">로그는 텍스트 기반 이며 아래쪽에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="9858c-134">모든 텍스트 기반 편집기를 사용 하 여 읽을 수 있으며, 클라이언트에 로그인 할 때 새 로그가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="9858c-135">디버그 로그에는 다음과 같은 데이터 흐름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="9858c-136">로그인</span><span class="sxs-lookup"><span data-stu-id="9858c-136">Login</span></span>

-   <span data-ttu-id="9858c-137">중앙 계층 서비스에 대 한 연결 요청</span><span class="sxs-lookup"><span data-stu-id="9858c-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="9858c-138">통화/대화</span><span class="sxs-lookup"><span data-stu-id="9858c-138">Call/conversation</span></span>

<span data-ttu-id="9858c-139">디버그 로그는 다음 OS 관련 메서드를 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="9858c-140">창을</span><span class="sxs-lookup"><span data-stu-id="9858c-140">Windows:</span></span>

      <span data-ttu-id="9858c-141">바로 가기 키: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="9858c-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="9858c-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="9858c-142">Mac OSX:</span></span>

      <span data-ttu-id="9858c-143">바로 가기 키: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="9858c-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="9858c-144">디버그 로그는 다음 폴더에 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="9858c-145">Windows:% userprofile%\\다운로드</span><span class="sxs-lookup"><span data-stu-id="9858c-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="9858c-146">Mac OSX: 다운로드</span><span class="sxs-lookup"><span data-stu-id="9858c-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="9858c-147">브라우저: 디버그 로그를 기본 저장 위치에 저장 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="9858c-148">미디어 로그</span><span class="sxs-lookup"><span data-stu-id="9858c-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="9858c-149">미디어 로그에는 오디오, 비디오, 화면 공유에 대 한 진단 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-149">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="9858c-150">요청 시에만 지원 서비스 케이스에 필요 하며 Microsoft만 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-150">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="9858c-151">다음 표에서는 로그 위치에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-151">The following table outlines the log location.</span></span>


|<span data-ttu-id="9858c-152">클라이언트측</span><span class="sxs-lookup"><span data-stu-id="9858c-152">Client</span></span> |<span data-ttu-id="9858c-153">위치</span><span class="sxs-lookup"><span data-stu-id="9858c-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="9858c-154">창을</span><span class="sxs-lookup"><span data-stu-id="9858c-154">Windows</span></span>     |<span data-ttu-id="9858c-155">%appdata%\Microsoft\Teams\media-stack\\* 블로그</span><span class="sxs-lookup"><span data-stu-id="9858c-155">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="9858c-156">%appdata%\Microsoft\Teams\skylib\\* 블로그</span><span class="sxs-lookup"><span data-stu-id="9858c-156">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="9858c-157">%appdata%\Microsoft\Teams\media-stack\\* .etl</span><span class="sxs-lookup"><span data-stu-id="9858c-157">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="9858c-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9858c-158">Mac OSX</span></span>     |<span data-ttu-id="9858c-159">~/Library/Application Support/Microsoft/팀/media-stack/\* 블로그</span><span class="sxs-lookup"><span data-stu-id="9858c-159">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="9858c-160">~/Library/Application Support/Microsoft/팀/skylib/\* 블로그</span><span class="sxs-lookup"><span data-stu-id="9858c-160">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="9858c-161">데스크톱 로그</span><span class="sxs-lookup"><span data-stu-id="9858c-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="9858c-162">데스크톱 로그 (부트스트래퍼 로그 라고도 함)는 데스크톱 클라이언트와 브라우저 간에 발생 하는 로그 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-162">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="9858c-163">이 로그는 미디어 로그와 마찬가지로, Microsoft에서 요청 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-163">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="9858c-164">로그는 텍스트 기반 이며, 텍스트 기반 편집기를 사용 하 여 하향식 형식으로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-164">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="9858c-165">창을</span><span class="sxs-lookup"><span data-stu-id="9858c-165">Windows:</span></span>

1.  <span data-ttu-id="9858c-166">응용 프로그램 트레이에서 **Microsoft 팀 아이콘** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="9858c-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="9858c-167">Mac OsX:</span></span>

1.  <span data-ttu-id="9858c-168">**도움말** 풀 다운 메뉴에서 **로그 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9858c-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="9858c-169">클라이언트측</span><span class="sxs-lookup"><span data-stu-id="9858c-169">Client</span></span> |<span data-ttu-id="9858c-170">위치</span><span class="sxs-lookup"><span data-stu-id="9858c-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="9858c-171">창을</span><span class="sxs-lookup"><span data-stu-id="9858c-171">Windows</span></span>     |<span data-ttu-id="9858c-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="9858c-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="9858c-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9858c-173">Mac OSX</span></span>     |<span data-ttu-id="9858c-174">~/Library/Application 지원/Microsoft/팀/로그. t e</span><span class="sxs-lookup"><span data-stu-id="9858c-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
