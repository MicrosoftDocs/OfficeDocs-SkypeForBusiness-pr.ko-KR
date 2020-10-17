---
title: 'Lync Server 2013: 중앙 로깅 서비스 사용'
description: 'Lync Server 2013: 중앙 로깅 서비스를 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8b9edf839de889e9f0b01c10311f6b5c70ced8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548524"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="62b51-103">Lync Server 2013에서 중앙 로깅 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="62b51-103">Using the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62b51-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="62b51-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="62b51-105">중앙 로깅 서비스는 Lync Server 2013의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-105">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="62b51-106">이는 이전 릴리스에서 제공 된 **Ocslogger** 및 **Ocstracer** 도구에 대 한 향상 된 교체입니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-106">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="62b51-107">중앙 로깅 서비스를 사용 하 여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-107">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="62b51-108">단일 위치 및 명령을 사용해서 하나 이상의 컴퓨터 또는 풀에서 로그인을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-108">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="62b51-109">단일 위치 및 명령을 사용해서 하나 이상의 컴퓨터 또는 풀에서 로그인을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-109">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="62b51-p102">단일 위치 및 명령으로 하나 이상의 컴퓨터 및 풀에서 로그를 검색합니다. 모든 컴퓨터에서 캡처되고 저장된 전체 로그 집계를 반환하거나 특정 데이터만 캡처하도록 조정된 결과를 반환하도록 검색 명령을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="62b51-112">다음과 같이 로깅 세션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-112">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="62b51-113">**시나리오**를 정의하거나 기본 시나리오를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-113">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="62b51-114">중앙 로깅 서비스의 *시나리오* 는 범위 (전역 또는 사이트), 시나리오의 목적을 식별 하는 시나리오 이름 및 하나 이상의 공급자로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-114">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="62b51-115">한 컴퓨터에서 언제라도 두 개의 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-115">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="62b51-p104">기존 *공급자*를 사용하거나 새 공급자를 만듭니다. *공급자*는 로깅 세션이 수집하는 항목, 세부 정보 수준, 추적할 구성 요소 및 적용할 플래그를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="62b51-118">OCSLogger에 익숙한 경우 <EM>공급자</EM>는 <STRONG>구성 요소</STRONG>(예: S4, SIPStack), <STRONG>로깅 유형</STRONG>(예: WPP, EventLog 또는 IIS 로그 파일), <STRONG>추적 수준</STRONG>(예: 모두, 상세, 디버그) 및 <STRONG>플래그</STRONG>(예: TF_COMPONENT, TF_DIAG)를 나타내는 총체적 표현을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-118">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="62b51-119">이러한 항목은 공급자 (Windows PowerShell 변수)에서 정의 되 고 중앙화 된 로깅 서비스 명령으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-119">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="62b51-120">로그를 수집하려는 컴퓨터 및 풀을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-120">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="62b51-121">**사이트**(해당 사이트의 컴퓨터에서만 로깅 캡처 실행) 또는 **전역**(배포에 포함된 모든 컴퓨터에서 로깅 캡처 실행) 옵션 중에서 로깅 세션의 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-121">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="62b51-122">중앙 로깅 서비스는 매우 강력 하며, 문제 해결을 위해 거의 모든 요구 사항을 충족할 수 있습니다 (대규모 또는 소규모).</span><span class="sxs-lookup"><span data-stu-id="62b51-122">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="62b51-123">근본 원인 분석을 통해 성능 문제가 발생 하는 경우 중앙 로깅 서비스는 모든 관리자에 게 중요 한 도구가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-123">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="62b51-124">모든 예는 Lync Server 관리 셸을 사용 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-124">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="62b51-125">중앙 로깅 서비스에는 **CLSController.exe**라는 명령줄 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-125">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="62b51-126">도움말은 도구 자체를 통해 명령줄 도구로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-126">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="62b51-127">하지만 명령줄에서 실행할 수 있는 기능은 제한적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-127">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="62b51-128">Lync Server 관리 셸을 사용 하면 훨씬 더 크고 광범위 하 게 구성 가능한 기능 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-128">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="62b51-129">중앙 로깅 서비스를 사용 하는 경우에는 항상 Lync Server 관리 셸을 첫 번째 및 가장 방법으로 고려 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-129">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="62b51-130">이 섹션의 항목에서는 중앙 로깅 서비스를 사용 하는 방법과 다양 한 기능을 사용 하는 방법의 예를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="62b51-130">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62b51-131">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="62b51-131">In This Section</span></span>

  - [<span data-ttu-id="62b51-132">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="62b51-132">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="62b51-133">Lync Server 2013에서 중앙 로깅 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="62b51-133">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="62b51-134">Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해</span><span class="sxs-lookup"><span data-stu-id="62b51-134">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="62b51-135">중앙 로깅 서비스에 시작을 사용 하 여 Lync Server 2013에서 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="62b51-135">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="62b51-136">Lync Server 2013에서 중앙화 된 로깅 서비스에 대해 Stop 사용</span><span class="sxs-lookup"><span data-stu-id="62b51-136">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="62b51-137">Lync Server 2013의 중앙 로깅 서비스에서 만든 캡처 로그에 검색 사용</span><span class="sxs-lookup"><span data-stu-id="62b51-137">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="62b51-138">Lync Server 2013의 중앙 로깅 서비스에서 캡처 로그 읽기</span><span class="sxs-lookup"><span data-stu-id="62b51-138">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

