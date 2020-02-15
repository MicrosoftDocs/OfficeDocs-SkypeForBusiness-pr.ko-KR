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
ms.openlocfilehash: dfa0d3ed6b83d610ee4d92c76487f2dbfb50f89e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="24751-102">Lync Server 2013의 모니터링 개요</span><span class="sxs-lookup"><span data-stu-id="24751-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24751-103">_**마지막으로 수정 된 항목:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="24751-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="24751-104">Microsoft Lync Server 2013에서는 모니터링을 사용 하 여 사용자가 관련 된 통신 세션에 대 한 사용 현황 정보 및 경력 (QoE) 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="24751-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="24751-105">세션은 다음 항목들에 대한 사용자의 연결을 포함하는 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="24751-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="24751-106">전화</span><span class="sxs-lookup"><span data-stu-id="24751-106">Conference</span></span>

  - <span data-ttu-id="24751-107">회의 형식(오디오/비디오 또는 응용 프로그램 공유)</span><span class="sxs-lookup"><span data-stu-id="24751-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="24751-108">인스턴트 메시징 또는 음성 통화와 같은 피어 투 피어 대화를 통한 다른 사용자</span><span class="sxs-lookup"><span data-stu-id="24751-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24751-109">Lync Server 2013에서는 각 세션에 대 한 정보를 추적 합니다. 세션에서 사용 된 끝점 세션이 마지막으로 완료 된 시간 세션의 인식 된 품질은 무엇 이며, 합니다.</span><span class="sxs-lookup"><span data-stu-id="24751-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="24751-110">그러나 Lync Server는 실제 통화를 기록 하 고 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="24751-111">여기에는 인스턴트 메시징 세션도 포함 됩니다. Lync Server에서는 인스턴트 메시징 세션에 대 한 정보를 기록 하지만, 세션 중에 전송 된 각 인스턴트 메시지에 대 한 레코드는 유지 관리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="24751-112">Lync Server에서 수집한 통화 정보 정보는 다음과 같은 다양 한 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="24751-113">**ROI(투자 수익률)**.</span><span class="sxs-lookup"><span data-stu-id="24751-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="24751-114">관리자는 모니터링 서버에서 수집한 사용 현황 데이터와 이전 전화 통신 시스템에 대해 수집 된 유사한 데이터를 비교 하 여 비용 절감을 표시 하 고 Lync Server 배포를 정당화 하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="24751-p104">**장치 인벤토리 관리**. 자산 관리 정보를 통해 관리자는 현재 사용 중인 장치 중에서 교체가 필요한 오래된 장치를 식별하고 전혀 사용되지 않는 값비싼 장치를 식별할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="24751-p104">**Device Inventory Management**. Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="24751-117">지원 센터</span><span class="sxs-lookup"><span data-stu-id="24751-117">Help Desk.</span></span> <span data-ttu-id="24751-118">문제 해결 데이터를 통해 지원 엔지니어는 사용자의 통화가 실패한 이유를 확인하고 서버 또는 클라이언트 쪽 로그를 수집할 필요 없이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="24751-119">이 정보는 Microsoft Lync 2013 및 Lync Server 2013에 대 한 심층적 기술 지식이 없는 지원 담당자가 쉽게 액세스 하 고 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="24751-p106">**시스템 문제 해결**. 관리자가 회의 참가, 통화 설정 또는 인스턴트 메시지 전송과 같은 최종 사용자의 기본 작업을 수행하지 못하도록 방지하는 중요 문제를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="24751-122">모니터링 서버는 이러한 기본 통화 정보 외에도 SIP 2013 등의 기능을 사용 하 여 서버에서 다른 사람에 게 액세스 하지 못하는 문제 해결 정보를 제공할 수 있는 메커니즘도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="24751-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="24751-p107">**품질에 영향을 주는 미디어 메트릭**. 이러한 메트릭은 통화 자체의 실제 전송을 다룹니다. 즉, 네트워크 내에서 통화가 이동될 때 일종의 이동 로그를 제공합니다. 이러한 메트릭(패킷 손실, 지터 및 왕복 시간 등 포함)은 사용자의 끝점을 떠난 시간부터 다른 사용자의 끝점에 도달한 시간 사이에 통화에 발생한 작업들에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24751-p107">**Media Metrics that Impact Quality**. These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network. These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="24751-126">**최종 사용자에게 보고되는 문제**.</span><span class="sxs-lookup"><span data-stu-id="24751-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="24751-127">이러한 메트릭에는 Lync 2013이 최종 사용자에 게 너무 멀리 있거나 너무 작게 말하고, 네트워크에 연결 되지 않았거나, 컴퓨터에 있는 다른 프로그램에 문제가 발생 하 여 품질이 좋지 않은 경우의 잘못 된 품질 알림이 포함 됩니다. 사용 가능한 리소스 소비</span><span class="sxs-lookup"><span data-stu-id="24751-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="24751-p109">**환경 정보**. 사용 중인 마이크 및 스피커 유형, 사용자가 VPN 연결을 통해 연결되었는지 여부 및 사용자가 무선 연결을 사용 중인지 여부와 같은 메트릭 세부 통화 품질 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="24751-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="24751-p110">각 통화 종료 시 SIP 호환 끝점은 이 정보를 통화를 지원한 프런트 엔드 서버에 자동으로 전송합니다. 끝점이 이 정보를 전송하도록 하기 위해 특별히 조치를 취할 필요는 없습니다. 이 동작은 SIP 프로토콜에 내장되어 있습니다. 하지만 해당 정보를 수집하고 저장하려면 모니터링을 설치하고 사용하도록 설정해야 합니다. 모니터링을 설치하고 사용하도록 설정할 경우 프런트 엔드 서버에서 실행 중인 에이전트에 의해 통화 정보가 수집되고 SQL Server 데이터베이스 쌍에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="24751-p110">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call. You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol. However, if you want to collect and store that information, then you need to install and enable monitoring. If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="24751-134">모니터링을 설치 하 고 구성 하는 프로세스는 Lync Server 2013에서 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="24751-135">이전 버전의 소프트웨어에서는 모니터링을 위해 별도의 모니터링 서버 역할이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="24751-136">그러나 Lync Server 2013에서는 모니터링 서버 역할이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="24751-137">하지만 nm-server-w15-long에서는 모니터링 서버 역할이 제거되었고 모니터링 서비스("통합 데이터 컬렉션 에이전트"의 형식으로)가 모든 프런트 엔드 서버에 함께 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="24751-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="24751-138">이러한 방식은 두 가지 주요 장점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24751-138">This has at least two major benefits.</span></span> <span data-ttu-id="24751-139">모니터링 서비스를 함께 배치하여 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="24751-140">Lync Server 2013를 구현할 때 필요한 서버 역할의 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="24751-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="24751-141">모니터링 서버 역할이 없어져서 모니터링에 대한 전용 서버를 유지 관리할 필요가 없으므로 비용을 줄이는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24751-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="24751-142">Lync Server 2013 설치 및 관리의 복잡성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="24751-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="24751-143">각 프런트 엔드 서버에 모니터링 서비스를 함께 배치함으로써 더 이상 모니터링 서버 역할을 설치, 구성 및 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24751-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="24751-144">자세한 내용은 Lync server 2013 2013 배포 가이드의 [Lync server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="24751-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

