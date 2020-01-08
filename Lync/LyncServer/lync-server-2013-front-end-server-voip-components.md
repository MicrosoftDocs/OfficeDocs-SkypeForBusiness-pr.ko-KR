---
title: 'Lync Server 2013: 프런트 엔드 서버 VoIP 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3558d230b1fb767f0e7844be3894b579149c3f6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="723c7-102">Lync Server 2013의 프런트 엔드 서버 VoIP 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="723c7-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="723c7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="723c7-104">프런트 엔드 서버에 있는 VoIP 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="723c7-105">번역 서비스</span><span class="sxs-lookup"><span data-stu-id="723c7-105">Translation Service</span></span>

  - <span data-ttu-id="723c7-106">인바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-106">Inbound Routing component</span></span>

  - <span data-ttu-id="723c7-107">아웃 바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-107">Outbound Routing component</span></span>

  - <span data-ttu-id="723c7-108">Exchange UM 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="723c7-109">Intercluster 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="723c7-110">Lync Server 2013의 중재 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="723c7-111">번역 서비스</span><span class="sxs-lookup"><span data-stu-id="723c7-111">Translation Service</span></span>

<span data-ttu-id="723c7-112">번역 서비스는 관리자가 정의한 정규화 규칙에 따라, 전화를 통해 번호를 E 164 형식 또는 다른 형식으로 번역 하는 역할을 하는 서버 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-112">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator.</span></span> <span data-ttu-id="723c7-113">조직에서 개인 번호 매기기 시스템을 사용 하거나 E. f 2를 지원 하지 않는 게이트웨이나 PBX를 사용 하는 경우 번역 서비스는 E가 아닌 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-113">The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="723c7-114">인바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-114">Inbound Routing Component</span></span>

<span data-ttu-id="723c7-115">인바운드 라우팅 구성 요소는 해당 엔터프라이즈 음성 클라이언트에서 사용자가 지정한 환경 설정에 따라 들어오는 전화를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="723c7-116">또한 사용자가 구성한 경우 대리인의 신호음 울림 및 동시 벨 울림이 용이해 집니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="723c7-117">예를 들어 사용자는 응답 하지 않은 통화가 전달 되는지, 아니면 간단히 알림만 로깅할지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="723c7-118">착신 통화 전환 기능을 사용 하는 경우 사용자는 응답 하지 않은 전화를 다른 번호로 전달할지 또는 통화 응답을 제공 하도록 구성 된 Exchange UM 서버로 보낼지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="723c7-119">인바운드 라우팅 구성 요소는 모든 스탠더드 버전 서버와 프런트 엔드 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="723c7-120">아웃 바운드 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-120">Outbound Routing Component</span></span>

<span data-ttu-id="723c7-121">아웃 바운드 라우팅 구성 요소는 PBX 또는 PSTN 대상으로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="723c7-122">이는 사용자의 음성 정책에 의해 정의 된 대로 통화 권한 부여 규칙을 호출자에 적용 하 고 각 호출을 라우팅하기 위한 최적의 PSTN 게이트웨이를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="723c7-123">아웃 바운드 라우팅 구성 요소는 모든 스탠더드 버전 서버와 프런트 엔드 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="723c7-124">아웃 바운드 라우팅 구성 요소에서 사용 하는 라우팅 논리는 조직의 요구 사항에 따라 네트워크 또는 전화 통신 관리자가 구성한 대규모 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="723c7-125">Exchange UM 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="723c7-126">Exchange UM 라우팅 구성 요소는 Lync Server와 UM (통합 메시징)를 실행 하는 서버 간 라우팅을 처리 하 여 Lync Server를 통합 메시징 기능과 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="723c7-127">Exchange um 라우팅 구성 요소는 또한 Exchange UM 서버를 사용할 수 없는 경우 PSTN을 통해 음성 메일을 다시 라우팅하도록 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="723c7-128">중앙 사이트에 대 한 탄성 WAN 링크가 없는 지점 사이트에서 엔터프라이즈 음성 사용자를 사용 하는 경우 지점 사이트에서 배포 하는 Survivable Branch 기기는 WAN을 중단 하는 동안 분기 사용자를 위해 음성 메일 survivability을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="723c7-129">WAN 링크를 사용할 수 없는 경우 Survivable Branch 기기는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="723c7-130">중앙 사이트의 Exchange 통합 메시징 서버에 대 한 PSTN을 통해 응답 하지 않은 통화를 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="723c7-131">사용자가 PSTN을 통해 음성 메일 메시지를 검색할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="723c7-132">부재 중 전화 알림을 큐에 대기 시키고 WAN 링크가 복원 되 면 Exchange UM 서버에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="723c7-133">음성 메일 전환 기능을 사용 하도록 설정 하려면 Exchange 관리자가 메시지를 수락 하도록 Exchange UM 자동 전화 교환 (AA)을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="723c7-134">이러한 기능에 대 한 자세한 내용은 [Lync server 2013의 Exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 및 [lync Server 2013의 Enterprise Voice 회복성](lync-server-2013-planning-for-enterprise-voice-resiliency.md)(영문)에서 각각에 대 한 계획을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="723c7-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="723c7-135">Intercluster 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-135">Intercluster Routing Component</span></span>

<span data-ttu-id="723c7-136">Intercluster routing component는 피호출자의 기본 등록자 풀로의 호출을 라우팅하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-136">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="723c7-137">이 기능을 사용할 수 없는 경우이 구성 요소는 호출을 피호출자의 백업 등록자 풀로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-137">If that is unavailable, the component routes the call to the callee’s backup Registrar pool.</span></span> <span data-ttu-id="723c7-138">호출 수신자의 기본 및 백업 등록자 풀에 IP 네트워크를 통해 연결할 수 없는 경우 Intercluster routing component는 PSTN을 통해 통화를 사용자의 전화 번호로 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-138">If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="723c7-139">VoIP에 필요한 다른 프런트 엔드 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="723c7-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="723c7-140">VoIP에 대 한 필수 지원을 제공 하는 프런트 엔드 서버 또는 디렉터에 있는 다른 구성 요소는 자신의 VoIP 구성 요소가 아니라 다음을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="723c7-141">**사용자 서비스.**</span><span class="sxs-lookup"><span data-stu-id="723c7-141">**User Services.**</span></span> <span data-ttu-id="723c7-142">들어오는 각 호출의 대상 전화 번호에 대 한 역방향 번호 조회를 수행 하 고 해당 번호와 대상 사용자의 SIP URI를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="723c7-143">인바운드 라우팅 구성 요소는이 정보를 사용 하 여 해당 사용자의 등록 된 SIP 끝점으로 통화를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="723c7-144">사용자 서비스는 모든 프런트 엔드 서버 및 디렉터의 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="723c7-145">**사용자 복제기.**</span><span class="sxs-lookup"><span data-stu-id="723c7-145">**User Replicator.**</span></span> <span data-ttu-id="723c7-146">Active Directory 도메인 서비스에서 사용자의 전화 번호를 추출 하 고이를 사용자 서비스 및 주소록 서버에서 사용할 수 있는 RTC 데이터베이스의 테이블에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="723c7-147">사용자 복제기는 모든 프런트 엔드 서버의 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="723c7-148">**주소록 서버.**</span><span class="sxs-lookup"><span data-stu-id="723c7-148">**Address Book Server.**</span></span> <span data-ttu-id="723c7-149">Active Directory 도메인 서비스에서 Lync Server 클라이언트에 대 한 전역 주소 목록 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="723c7-150">또한 RTC 데이터베이스에서 사용자 및 연락처 정보를 검색 하 고, 정보를 주소록 파일에 쓴 다음 Lync 클라이언트에서 해당 파일을 다운로드 한 공유 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="723c7-151">주소록 서버는 주소록 웹 쿼리 서비스에서 Microsoft Lync 2010 Mobile의 사용자 검색 쿼리에 응답 하는 데 사용 하는 RTCAb 데이터베이스에 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="723c7-152">Lync에서 사용자 연락처를 프로 비전 하기 위해 선택적으로 RTC 데이터베이스에 기록 되는 엔터프라이즈 사용자 전화 번호를 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="723c7-153">주소록 서비스는 모든 프런트 엔드 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="723c7-154">주소록 웹 쿼리 서비스는 기본적으로 각 프런트 엔드 서버의 웹 서비스와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="723c7-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

