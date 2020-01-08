---
title: 'Lync Server 2013: 외부 사용자 액세스 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d3b6f-102">Lync Server 2013의 외부 사용자 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="d3b6f-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3b6f-103">_**마지막으로 수정한 주제:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="d3b6f-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="d3b6f-104">대부분의 조직의 통신에는 내부 네트워크 내에 있지 않은 서비스 및 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="d3b6f-105">이러한 서비스 및 사용자에 게는 일시적으로 또는 영구적으로 오프 사이트, 고객 또는 파트너 조직의 직원, 공공 메신저 대화 서비스를 사용 하는 사용자, 초대 받은 잠재 고객, 파트너, 익명 사용자 등이 포함 됩니다. 모임 및 프레젠테이션으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="d3b6f-106">이 문서에서는 이러한 사람들을 통틀어 *외부 사용자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="d3b6f-107">Microsoft Lync Server 2013를 사용 하는 경우 조직의 사용자는 메신저 대화 및 현재 상태를 사용 하 여 외부 사용자와 통신할 수 있으며, 오프 사이트의 직원 및 기타 유형의 외부 사용자와 함께 오디오/비디오 (A/V) 회의 및 웹 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="d3b6f-108">모바일 장치 및 엔터프라이즈 음성을 통해 외부 액세스를 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="d3b6f-109">조직의 구성원이 아닌 외부 사용자는 Lync Server 2013 모임에 참가 하 여 익명 참석자를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="d3b6f-110">조직의 방화벽을 통해 통신을 지원 하려면 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)에 Lync Server 2013 Edge 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="d3b6f-111">Edge 서버는 방화벽 외부의 사용자가 내부 Lync Server 2013 배포에 연결 될 수 있는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="d3b6f-112">또한 방화벽 내에서 시작 된 외부 사용자와의 통신을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="d3b6f-113">요구 사항에 따라 하나 이상의 위치에 하나 이상의 Edge 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="d3b6f-114">이 섹션에서는 Lync Server 2013에서 외부 사용자 액세스 시나리오에 대해 설명 하 고, edge 및 리버스 프록시 토폴로지를 계획 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3b6f-115">엔터프라이즈 음성 및 외부 사용자 액세스를 지원 하기 위해 Edge 서버가 필요 하지만이 섹션에서는 IM, 현재 상태, A/V 회의, 페더레이션, 웹 회의, Lync Mobile에 대 한 지원을 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="d3b6f-116">Enterprise Voice 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013의 Enterprise Voice 계획</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3b6f-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3b6f-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d3b6f-117">In This Section</span></span>

  - [<span data-ttu-id="d3b6f-118">에지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항</span><span class="sxs-lookup"><span data-stu-id="d3b6f-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="d3b6f-119">Lync Server 2013의 외부 사용자 액세스 구성 요소에 대한 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3b6f-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="d3b6f-120">Lync Server 2013의 외부 사용자 액세스 개요</span><span class="sxs-lookup"><span data-stu-id="d3b6f-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="d3b6f-121">Lync Server 2013의 자동 검색 이해</span><span class="sxs-lookup"><span data-stu-id="d3b6f-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="d3b6f-122">Lync Server 2013에서 토폴로지 선택</span><span class="sxs-lookup"><span data-stu-id="d3b6f-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="d3b6f-123">Lync Server 2013의 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d3b6f-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="d3b6f-124">Lync Server 2013에 대한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="d3b6f-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="d3b6f-125">Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="d3b6f-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="d3b6f-126">Lync Server 2013의 에지 서버 인증서 계획</span><span class="sxs-lookup"><span data-stu-id="d3b6f-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="d3b6f-127">Lync Server 2013의 외부 사용자 액세스에 대한 시나리오</span><span class="sxs-lookup"><span data-stu-id="d3b6f-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

