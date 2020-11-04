---
title: Microsoft Teams에서 메모리를 사용하는 방법
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft 팀 시스템 메모리 사용량 및 데스크톱 응용 프로그램과 웹 응용 프로그램 간에 메모리 사용이 동일한 이유를 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878722"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="43d77-103">Microsoft Teams에서 메모리를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="43d77-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="43d77-104">일부 Microsoft 팀 사용자는 팀에서 메모리를 사용 하는 방법에 대 한 질문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="43d77-105">이 문서에서는 팀에서 메모리를 사용 하는 방법과 팀 데스크톱 응용 프로그램 (앱)과 팀 웹 앱이 동일한 컴퓨터의 다른 앱과 작업을 최적화 하는 데 메모리가 충분 하지 않은 이유를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="43d77-106">팀은 최신 웹 기술을 사용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="43d77-107">이를 위해 팀 데스크톱 클라이언트는 Chromium를 사용 하 여 렌더링 하는 전자로 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="43d77-108">이는 Edge 및 Chrome을 비롯 하 여 오늘날 가장 인기 있는 브라우저의 렌더링 엔진의 수와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="43d77-109">팀의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="43d77-109">How Teams works</span></span>

<span data-ttu-id="43d77-110">전자를 사용 하는 팀은 더 빠른 개발을 위해 다양 한 운영 체제 (Windows, Mac 및 Linux)에서 팀 버전 간의 패리티가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="43d77-111">이 패리티는 전자와 Chromium 모든 버전에서 유사한 코드 베이스를 유지 하기 때문에 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="43d77-112">이 아키텍처의 또 다른 장점은 팀 web app과 데스크톱 버전 사이에 비슷한 메모리 사용 프로필을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="43d77-113">웹 앱과 데스크톱 버전 모두 브라우저에서 사용 하는 것과 비슷한 방식으로 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="43d77-114">전자 메일에 대 한 자세한 내용은 [해당 웹 사이트](https://electronjs.org/)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="43d77-115">자세한 내용은 [Chrome 메모리의](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) [메모리 사용](https://www.chromium.org/developers/memory-usage-backgrounder) 및 키 개념 Chromium을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43d77-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="43d77-116">다음 이미지는 Windows 용 팀 데스크톱 앱 및 팀 웹 앱 (이 예제에서는 Google Chrome에서 실행 됨)의 병렬 메모리 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![데스크톱 앱 및 웹 앱에 대 한 팀 메모리 사용](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="43d77-118">팀의 메모리 사용</span><span class="sxs-lookup"><span data-stu-id="43d77-118">Memory usage in Teams</span></span>

<span data-ttu-id="43d77-119">시스템 메모리가 제공 되는 경우 팀의 *예상* 동작을 이해 하 고 실제로 문제가 있는 시스템 메모리 문제의 증상을 파악 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="43d77-120">팀의 메모리 사용량 예상</span><span class="sxs-lookup"><span data-stu-id="43d77-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="43d77-121">팀 데스크톱 앱 또는 팀 웹 앱을 실행 하 고 있는지 여부 Chromium는 사용 가능한 시스템 메모리의 양을 감지 하 고 해당 메모리를 충분히 활용 하 여 렌더링 환경을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="43d77-122">다른 앱 또는 서비스에 시스템 메모리가 필요한 경우 Chromium는 해당 프로세스에 메모리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="43d77-123">현재 실행 중인 모든 작업에 영향을 주지 않고 팀 성과를 최적화 하기 위해 팀 메모리 사용량을 지속적으로 Chromium 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="43d77-124">이런 방법으로, 비슷한 Chromium 작업은 사용 가능한 시스템 메모리의 양에 따라 다양 한 양의 메모리를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="43d77-125">다음 그래프는 각각 서로 다른 메모리 용량을 사용 하는 4 개의 개별 시스템에서 메모리 사용량을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="43d77-126">각 시스템은 유사한 작업을 처리 합니다 (동일한 앱을 열고 실행 중).</span><span class="sxs-lookup"><span data-stu-id="43d77-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![여러 시스템 간의 팀 메모리 사용](media/teams-memory-usage.png)

<span data-ttu-id="43d77-128">컴퓨터에 메모리가 더 있으면 팀에서 해당 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="43d77-129">메모리가 부족 한 시스템에서 팀은 덜 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="43d77-130">시스템 메모리 문제 증상</span><span class="sxs-lookup"><span data-stu-id="43d77-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="43d77-131">컴퓨터에 다음 중 하나 이상의 증상이 표시 되는 경우 심각한 시스템 메모리 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="43d77-132">대용량 응용 프로그램을 여러 개 동시에 실행 하는 경우에는 고위 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="43d77-133">시스템 성능이 느려지거나 응용 프로그램이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="43d77-134">모든 앱에서 90% 이상의 전체 시스템 메모리 사용량을 지속적으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="43d77-135">이 메모리 사용량을 통해 팀은 다른 앱과 작업 부하에 메모리를 다시 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="43d77-136">90%의 지속적인 메모리 사용은 팀에 메모리가 시스템에 다시 제공 되지 않고 문제가 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="43d77-137">다음 이미지는 시스템 메모리 사용량이 비정상적으로 높을 때 작업 관리자의 보기의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43d77-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![작업 관리자의 팀 메모리 배정 현황 보기](media/teams-memory-high-mem-process-list.png)

![작업 관리자의 팀 메모리 사용 그래프](media/teams-memory-high-mem-process-list2.png)
