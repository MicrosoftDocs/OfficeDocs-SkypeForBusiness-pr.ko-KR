---
title: 'Lync Server 2013: 프런트 엔드 서버 VoIP 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62261a4d4651e38941f5068b58636b82d0151965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500705"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="20a2b-102">Lync Server 2013의 프런트 엔드 서버 VoIP 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-102">Front End Server VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20a2b-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="20a2b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="20a2b-104">프런트 엔드 서버에 있는 VoIP 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="20a2b-105">변환 서비스</span><span class="sxs-lookup"><span data-stu-id="20a2b-105">Translation Service</span></span>

  - <span data-ttu-id="20a2b-106">인바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-106">Inbound Routing component</span></span>

  - <span data-ttu-id="20a2b-107">아웃바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-107">Outbound Routing component</span></span>

  - <span data-ttu-id="20a2b-108">Exchange UM 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="20a2b-109">Intercluster 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="20a2b-110">Lync Server 2013의 중재 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="20a2b-111">변환 서비스</span><span class="sxs-lookup"><span data-stu-id="20a2b-111">Translation Service</span></span>

<span data-ttu-id="20a2b-p101">변환 서비스는 관리자가 정의한 정규화 규칙에 따라 전화 건 번호를 E.164 형식 또는 다른 형식으로 변환하는 역할을 수행하는 서버 구성 요소입니다. 조직에서 사설 번호 시스템을 사용하거나 E.164 형식을 지원하지 않는 게이트웨이나 PBX를 사용할 경우에는 변환 서비스가 E.164 이외의 다른 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="20a2b-114">인바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-114">Inbound Routing Component</span></span>

<span data-ttu-id="20a2b-115">인바운드 라우팅 구성 요소는 Enterprise Voice 클라이언트에서 사용자가 지정한 기본 설정에 따라 수신 전화를 대규모로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="20a2b-116">또한 사용자가 구성한 경우 대리인 신호 울림 및 동시 신호 울림도 쉽게 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="20a2b-117">예를 들어 사용자는 응답하지 않는 전화를 착신 전환할지 알림을 위해 기록만 할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="20a2b-118">착신 전환 기능을 사용 하도록 설정 하면 사용자는 응답 하지 않은 통화를 다른 번호 또는 전화 응답을 제공 하도록 구성 된 Exchange UM 서버로 전달할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="20a2b-119">인바운드 라우팅 구성 요소는 모든 Standard Edition 서버 및 프런트 엔드 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="20a2b-120">아웃바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-120">Outbound Routing Component</span></span>

<span data-ttu-id="20a2b-121">아웃바운드 라우팅 구성 요소는 전화를 PBX 또는 PSTN 대상으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="20a2b-122">이 구성 요소는 사용자 음성 정책에 의해 정의된 통화 권한 부여 규칙을 발신자에게 적용하고 각 전화를 라우팅하는 데 사용할 최적의 PSTN 게이트웨이를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="20a2b-123">아웃 바운드 라우팅 구성 요소는 모든 Standard Edition 서버 및 프런트 엔드 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="20a2b-124">아웃바운드 라우팅 구성 요소에 사용되는 라우팅 논리는 대부분 네트워크 또는 전화 통신 관리자가 해당 조직의 요구 사항에 따라 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="20a2b-125">Exchange UM 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="20a2b-126">Exchange UM 라우팅 구성 요소는 lync Server와 Exchange UM (통합 메시징)을 실행 하는 서버 간의 라우팅을 처리 하 여 Lync Server를 통합 메시징 기능과 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="20a2b-127">Exchange um 서버를 사용할 수 없는 경우에도 PSTN을 통해 음성 메일을 다시 라우팅하는 것을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="20a2b-128">중앙 사이트에 대 한 복구 가능한 WAN 링크가 없는 분기 사이트에 Enterprise Voice users가 있는 경우 분기 사이트에서 배포 하는 Sba (survivable 분기 기기는 WAN 중단 시 분기 사용자에 게 음성 메일 지 속성 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="20a2b-129">WAN 연결을 사용할 수 없는 경우 SBA는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="20a2b-130">PSTN을 통해 응답하지 않은 전화를 중앙 사이트의 Exchange 통합 메시징 서버로 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="20a2b-131">PSTN을 통해 음성 메일 메시지를 검색하는 기능을 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="20a2b-132">부재 중 전화 알림을 큐에 넣은 다음 WAN 링크가 복원되면 Exchange UN 서버로 해당 알림을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="20a2b-133">음성 메일 경로를 다시 라우팅하도록 설정 하려면 Exchange 관리자가 메시지를 수락 하도록 Exchange UM 자동 전화 교환 (AA)을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="20a2b-134">이러한 기능에 대 한 자세한 내용은 [Lync server 2013의 Exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 및 [lync Server 2013의 Enterprise Voice 복구 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20a2b-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="20a2b-135">Intercluster 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-135">Intercluster Routing Component</span></span>

<span data-ttu-id="20a2b-p105">Intercluster 라우팅 구성 요소는 통화를 수신자의 기본 등록자 풀로 라우팅합니다. 이렇게 할 수 없는 경우 이 구성 요소는 통화를 수신자의 백업 등록자 풀로 라우팅합니다. IP 네트워크를 통해 수신자의 기본 및 백업 등록자 풀에 연결할 수 없으면 Intercluster 라우팅 구성 요소는 PSTN을 통해 통화를 사용자 전화 번호로 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="20a2b-139">VoIP에 필요한 기타 프런트 엔드 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20a2b-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="20a2b-140">VoIP에 필수적인 지원을 제공 하지만 자체 VoIP 구성 요소가 아니라 프런트 엔드 서버 또는 디렉터에 있는 기타 구성 요소에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="20a2b-141">**사용자 서비스.**</span><span class="sxs-lookup"><span data-stu-id="20a2b-141">**User Services.**</span></span> <span data-ttu-id="20a2b-142">각 수신 전화의 대상 전화 번호에 대해 역방향 번호 조회를 수행하고 대상 사용자의 SIP URI에 해당 번호를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="20a2b-143">이 정보를 사용하여 인바운드 라우팅 구성 요소가 사용자의 등록된 SIP 끝점으로 전화를 분산시킵니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="20a2b-144">사용자 서비스는 모든 프런트 엔드 서버 및 디렉터의 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="20a2b-145">**User Replicator.**</span><span class="sxs-lookup"><span data-stu-id="20a2b-145">**User Replicator.**</span></span> <span data-ttu-id="20a2b-146">Active Directory 도메인 서비스에서 사용자 전화 번호를 추출 하 여 사용자 서비스 및 주소록 서버에서 사용할 수 있는 RTC 데이터베이스의 테이블에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="20a2b-147">사용자 복제기는 모든 프런트 엔드 서버의 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="20a2b-148">**주소록 서버.**</span><span class="sxs-lookup"><span data-stu-id="20a2b-148">**Address Book Server.**</span></span> <span data-ttu-id="20a2b-149">Active Directory 도메인 서비스의 전체 주소 목록 정보를 Lync Server 클라이언트에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="20a2b-150">또한 RTC 데이터베이스에서 사용자 및 연락처 정보를 검색 하 고, 정보를 주소록 파일에 쓴 다음 Lync 클라이언트에서 다운로드 한 공유 폴더에 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="20a2b-151">주소록 서버는 주소록 웹 쿼리 서비스에서 Microsoft Lync 2010 Mobile의 사용자 검색 쿼리에 응답 하기 위해 사용 하는 RTCAb 데이터베이스에 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="20a2b-152">선택적으로 Lync에서 사용자 연락처를 프로 비전 하기 위해 RTC 데이터베이스에 기록 되는 엔터프라이즈 사용자 전화 번호를 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="20a2b-153">주소록 서비스는 모든 프런트 엔드 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="20a2b-154">주소록 웹 쿼리 서비스는 각 프런트 엔드 서버의 웹 서비스와 함께 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a2b-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

