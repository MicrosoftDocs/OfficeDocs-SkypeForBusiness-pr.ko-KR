---
title: 'Lync Server 2013: 응답 그룹에서 사용하는 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="e82f2-102">Lync Server 2013의 응답 그룹에서 사용하는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e82f2-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e82f2-103">_**마지막으로 수정한 주제:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e82f2-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e82f2-104">엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 자동으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e82f2-105">이 섹션에서는 응답 그룹 응용 프로그램을 지 원하는 구성 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="e82f2-106">응답 그룹 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e82f2-106">Response Group Components</span></span>

<span data-ttu-id="e82f2-107">다음 Microsoft Lync Server 2013 구성 요소는 응답 그룹 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="e82f2-108">**응용 프로그램 서비스**   응용 프로그램 서비스는 응답 그룹과 같은 통합 커뮤니케이션 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="e82f2-109">응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="e82f2-110">**응답 그룹 애플리케이션**   응답 그룹 응용 프로그램은 응용 프로그램 서비스에 의해 호스팅되는 통합 커뮤니케이션 응용 프로그램 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="e82f2-111">응답 그룹을 배포할 때 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="e82f2-112">응답 그룹 응용 프로그램은 에이전트 그룹에 대 한 수신 전화를 라우팅하고 큐에 대기 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="e82f2-113">**언어 팩**   텍스트 음성 변환 및 음성 인식을 지원 하려면 언어 팩이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="e82f2-114">이러한 음성 기술은 메시지 (예: 환영 메시지 및 기타 프롬프트)와 IVR (대화형 음성 응답) 질문과 대답을 구성할 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="e82f2-115">기본적으로 Lync Server 2013을 배포할 때 지원 되는 26 개 언어 팩이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e82f2-116">**오디오 파일**   오디오 파일은 메시지 및 대기 중인 음악에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="e82f2-117">**파일 저장소**   응답 그룹은 파일 저장소를 사용 하 여 오디오 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="e82f2-118">여러 응답 그룹 풀이 동일한 파일 저장소 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="e82f2-119">**응답 그룹 구성 도구**   응답 그룹 구성 도구는 응답 그룹을 만들고 구성 하는 데 사용 되는 웹 기반 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="e82f2-120">응답 그룹 구성 도구는 웹 서비스를 설치할 때 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="e82f2-121">**Microsoft lync server 2013 제어판**   Lync server 제어판을 사용 하 여 응답 그룹의 에이전트 그룹과 큐를 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="e82f2-122">**Lync server 관리 셸**   lync server management shell cmdlet을 사용 하 여 모든 응답 그룹 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="e82f2-123">**Microsoft lync 2013**   정식 에이전트 (그룹에 대 한 호출을 수락 하기 전에 그룹에 로그인 해야 하는 상담원) Lync 2013를 사용 하 여 그룹에 로그인 하거나 로그 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="e82f2-124">공식 에이전트에 대 한 에이전트 그룹이 구성 되어 있는 경우, 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Internet Explorer를 열고 그룹 로그인 및 로그 아웃을 위한 웹 페이지 콘솔을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="e82f2-125">**웹 서비스**   웹 서비스는 응답 그룹 구성 도구, 에이전트의 로그인 및 로그 아웃 콘솔, Lync Server 제어판 및 응답 그룹 클라이언트 웹 서비스에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="e82f2-126">**응답 그룹 클라이언트 웹 서비스**   응답 그룹 응용 프로그램은 타사 응용 프로그램에서 에이전트, 에이전트 그룹 구성원, 에이전트 로그인 상태, 그룹에 대 한 통화 상태, 익명 통화를 지 원하는 그룹에 대 한 정보를 검색 하는 데 사용할 수 있는 클라이언트 웹 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="e82f2-127">Lync 2013 및 Lync 2010 수행자는 응답 그룹 클라이언트 웹 서비스를 사용 하 여 에이전트가 익명으로 전화를 걸 때 사용할 수 있는 응답 그룹 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="e82f2-128">웹 서비스를 설치 하는 경우 클라이언트 웹 서비스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82f2-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

