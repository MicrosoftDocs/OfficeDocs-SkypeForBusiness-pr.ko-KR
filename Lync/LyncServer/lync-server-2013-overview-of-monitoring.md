---
title: 'Lync Server 2013: 모니터링 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="5933f-102">Lync Server 2013의 모니터링 개요</span><span class="sxs-lookup"><span data-stu-id="5933f-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5933f-103">_**마지막으로 수정한 주제:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="5933f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="5933f-104">Microsoft Lync Server 2013에서는 모니터링을 사용 하 여 사용자가 관여 하는 통신 세션에 대 한 사용 정보 및 경력 (체감 품질) 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="5933f-105">세션은 다음에 대 한 사용자의 연결을 다루는 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="5933f-106">회의</span><span class="sxs-lookup"><span data-stu-id="5933f-106">Conference</span></span>

  - <span data-ttu-id="5933f-107">회의 모달 (예: 오디오/비디오 또는 응용 프로그램 공유)</span><span class="sxs-lookup"><span data-stu-id="5933f-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="5933f-108">인스턴트 메시지 또는 음성 통화와 같은 피어 투 피어 대화를 통해 다른 사용자</span><span class="sxs-lookup"><span data-stu-id="5933f-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5933f-109">Lync Server 2013는 각각의 세션에 대 한 정보를 추적 합니다. 세션에서 사용 된 끝점 세션이 마지막으로 얼마나 오래 되었나요? 세션의 인식 된 품질 .</span><span class="sxs-lookup"><span data-stu-id="5933f-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="5933f-110">그러나 Lync Server는 실제 통화 자체를 기록 하 고 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="5933f-111">여기에는 메신저 대화도 포함 됩니다. Lync Server는 메신저 대화 세션에 대 한 정보를 기록 하지만, 세션 중에 전송 된 각 인스턴트 메시지의 기록은 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="5933f-112">Lync Server에서 수집한 통화 정보 정보는 다음을 포함 하 여 다양 한 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="5933f-113">**Roi (투자 수익률)를 반환**합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="5933f-114">관리자는 서버 모니터링에서 수집한 사용량 데이터를 이전 전화 통신 시스템에 대해 수집 된 유사한 데이터로 비교 하 여 비용을 절약 하 고 Lync Server의 배포를 정당화 하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="5933f-115">**장치 인벤터리 관리**.</span><span class="sxs-lookup"><span data-stu-id="5933f-115">**Device Inventory Management**.</span></span> <span data-ttu-id="5933f-116">자산 관리 정보를 통해 관리자는 대체 해야 하는 오래 된 디바이스를 확인할 수 있을 뿐만 아니라 사용 되지 않는 비싼 디바이스를 식별 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="5933f-117">지원 센터.</span><span class="sxs-lookup"><span data-stu-id="5933f-117">Help Desk.</span></span> <span data-ttu-id="5933f-118">데이터 문제 해결을 통해 지원 엔지니어가 사용자의 호출이 실패 한 이유를 확인 하 고 서버 또는 클라이언트측 로그를 수집할 필요 없이이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="5933f-119">이 정보는 Microsoft Lync 2013 및 Lync Server 2013에 대 한 심층적인 기술 지식이 없는 지원 담당자가 쉽게 액세스 하 고 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="5933f-120">**시스템 문제 해결**</span><span class="sxs-lookup"><span data-stu-id="5933f-120">**System Troubleshooting**.</span></span> <span data-ttu-id="5933f-121">관리자가 최종 사용자가 회의에 참가 하거나 통화를 설정 하거나 인스턴트 메시지를 보내는 등의 기본 작업을 수행 하지 못하도록 하는 주요 문제를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-121">Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="5933f-122">모니터링 서버는이 기본 통화 정보 외에도 SIP 끝점 (예: Lync 2013)을 사용 하 여 서버에서 다른 방법으로 액세스할 수 없는 문제 해결 정보를 제공 하는 메커니즘도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="5933f-123">**품질에 영향을 주는 미디어 메트릭입니다**.</span><span class="sxs-lookup"><span data-stu-id="5933f-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="5933f-124">이러한 메트릭은 통화 자체의 실제 전송을 처리 합니다. 즉, 네트워크를 통해 통화 여행로 여행 로그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="5933f-125">이러한 메트릭 (패킷 손실, 지터, 라운드트립 시간 등)에는 끝점을 남겨진 시점부터 다른 사용자의 끝점에 도달 하는 시간까지 호출에 발생 한 정보에 대 한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="5933f-126">**최종 사용자에 게 보고 된 문제**</span><span class="sxs-lookup"><span data-stu-id="5933f-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="5933f-127">이러한 메트릭에는 사용자가 마이크에서 너무 멀리 떨어져 있거나, 너무 작게 말하고, 네트워크에 연결 되어 있지 않거나, 컴퓨터에 있는 다른 프로그램을 사용 하기 때문에 성능이 저하 되는 경우를 위해 Lync 2013에서 발생 하는 좋지 않은 품질 알림이 포함 됩니다. 사용 가능한 리소스 소모</span><span class="sxs-lookup"><span data-stu-id="5933f-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="5933f-128">**환경 정보**.</span><span class="sxs-lookup"><span data-stu-id="5933f-128">**Environment Information**.</span></span> <span data-ttu-id="5933f-129">이러한 메트릭 정보에는 사용 중인 마이크와 스피커 유형, 사용자가 VPN 연결을 통해 연결 되었는지 여부, 무선 연결 상태에 있는지 등의 통화 품질 요소가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-129">These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="5933f-130">각 호출이 끝날 때 SIP 호환 끝점은이 정보를 호출을 촉진 하는 프런트 엔드 서버로 자동으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="5933f-131">끝점을 사용 하 여 해당 정보를 전송 하는 데는 아무런 작업도 수행할 필요가 없습니다. 이 동작은 SIP 프로토콜에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="5933f-132">그러나 정보를 수집 하 고 저장 하려는 경우 모니터링을 설치 하 고 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="5933f-133">모니터링을 설치 하 고 사용 하도록 설정한 경우 프런트 엔드 서버에서 실행 되는 에이전트가 호출 정보를 수집 하 고 한 쌍의 SQL Server 데이터베이스에 릴레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="5933f-134">모니터링을 설치 하 고 구성 하는 프로세스는 Lync Server 2013에서 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="5933f-135">이전 버전의 소프트웨어에서는 모니터링 서버로 사용 하기 위해 별도의 컴퓨터를 별도로 설정 하는 별도의 모니터링 서버 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="5933f-136">그러나 Lync Server 2013에서는 모니터링 서버 역할이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="5933f-137">대신, 모니터링 서비스 ("통합 데이터 수집 에이전트" 형식)가 모든 프런트 엔드 서버에 collocated 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="5933f-138">최소 두 가지 주요 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-138">This has at least two major benefits.</span></span> <span data-ttu-id="5933f-139">모니터링 서비스의 콜론 위치:</span><span class="sxs-lookup"><span data-stu-id="5933f-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="5933f-140">Lync Server 2013을 구현할 때 필요한 서버 역할 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="5933f-141">모니터링 서버 역할을 감소 하면 모니터링을 위해 전용 서버를 유지 관리할 필요가 없어지므로 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="5933f-142">Lync Server 2013 설정 및 관리의 복잡도를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="5933f-143">각 프런트 엔드 서버에서 모니터링 서비스를 collocating 모니터링 서버 역할을 더 이상 설치, 구성, 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5933f-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="5933f-144">자세한 내용은 Lync server 2013 2013 배포 가이드의 [Lync server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5933f-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

