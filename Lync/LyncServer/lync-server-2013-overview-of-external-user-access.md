---
title: 'Lync Server 2013: 외부 사용자 액세스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1007dfb330aaa21dbac269f606102c51712c9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0c988-102">Lync Server 2013의 외부 사용자 액세스 개요</span><span class="sxs-lookup"><span data-stu-id="0c988-102">Overview of external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c988-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0c988-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0c988-104">이 문서에서는 *외부 사용자* 라는 용어를 사용 하 여 lync Server 2013 및 lync 2013 사용자와 통신 하는 대규모 사용자를 방화벽 외부에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-104">In this documentation, we use the term *external user* to define a large category of users who communicate with your Lync Server 2013 and Lync 2013 users from outside the firewall.</span></span> <span data-ttu-id="0c988-105">Lync Server 2013를 내부 사용자와 통신 하도록 권한을 부여할 수 있는 외부 사용자 (즉, 방화벽 내에서 Lync Server에 로그인 하는 사용자)에는 다음이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-105">External users that you can authorize to communicate Lync Server 2013 with internal users (that is, users who sign in to Lync Server from inside the firewall) can include the following:</span></span>

  - <span data-ttu-id="0c988-106">\*\*\*\*   방화벽 외부에서 Lync Server에 로그인 하는 조직의 사용자 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="0c988-106">**Remote users**   Users of your organization who sign in to Lync Server from outside the firewall.</span></span>

  - <span data-ttu-id="0c988-107">\*\*\*\*   Lync server 2010, lync server 2013 또는 Office Communications Server 2007 R2와 같이 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="0c988-107">**Federated users**   Users who have an account with a trusted customer or partner organization, such as Lync Server 2010, Lync Server 2013 or Office Communications Server 2007 R2.</span></span> <span data-ttu-id="0c988-108">페더레이션 사용자는 프런트 엔드 서버 또는 풀의 Edge 서버와 XMPP 게이트웨이에서 XMPP 프록시를 사용 하 여 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP)을 통해 정의 된 파트너 조직의 구성원 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-108">Federated users can also be members of defined partner organizations using extensible messaging and presence protocol (XMPP) by way of the XMPP proxy on the Edge Server and XMPP gateway on the Front End Server or pool.</span></span> <span data-ttu-id="0c988-109">페더레이션 이라고 하는 정의 된 신뢰 관계는 Active Directory 도메인 서비스 트러스트 관계에 관련 되거나 종속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-109">A defined trust relationship, called a federation, is not related to or dependent upon an Active Directory Domain Services trust relationship.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c988-110">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="0c988-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="0c988-111">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-111">has been announced.</span></span> <span data-ttu-id="0c988-112">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c988-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="0c988-113">**공용 인스턴트 메시징 연결 사용자**   가 공용 인스턴트 메시징 연결 서비스를 통해 설정 하는 대화 상대 (Windows Live, Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="0c988-113">**Public Instant Messaging Connectivity users**   Contacts that your users establish through public instant messaging connectivity services (Windows Live, Yahoo\!</span></span> <span data-ttu-id="0c988-114">및 AOL).</span><span class="sxs-lookup"><span data-stu-id="0c988-114">and AOL).</span></span>

  - <span data-ttu-id="0c988-115">**Lync 모바일 클라이언트**   를 실행 하는 스마트 휴대폰 이나 태블릿을 사용 하는 조직의 구성원 인 사용자는 내부 배포에 로그인 하 여 다른 사용자 클래스와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-115">**Mobile users**   Users that are members of your organization that use a smart phone or tablet running a Lync Mobile client sign in to your internal deployment and are able to communicate with the other classes of users.</span></span> <span data-ttu-id="0c988-116">모바일 사용자는 리버스 프록시를 통해 게시 된 이동성 서비스를 사용 하 여 내부 배포에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-116">The mobile user uses mobility services that are published through the reverse proxy to access the internal deployment.</span></span> <span data-ttu-id="0c988-117">Lync Mobile에서 사용할 수 있는 기능 및 기능에 대 한 자세한 내용은 모바일 클라이언트 비교 표 [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c988-117">For details on features and capabilities available to Lync Mobile , see the Mobile Client Comparison Tables at [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777).</span></span>

  - <span data-ttu-id="0c988-118">**익명 사용자**   조직의 Active Directory 도메인 서비스 또는 지원 되는 페더레이션 도메인에 사용자 계정이 없지만 온-프레미스 회의에 원격으로 참가할 수 있는 초대를 받은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-118">**Anonymous users**   Users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but who have received invitations to participate remotely in an on-premises conference.</span></span>

<span data-ttu-id="0c988-119">Edge 배포는 다음 유형의 통신에 대해 외부 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-119">Your edge deployment provides external access for the following types of communication:</span></span>

  - <span data-ttu-id="0c988-120">**Im 및 현재 상태**   승인 외부 사용자는 메신저 대화 및 회의에 참가할 수 있으며, 다른 사람의 현재 상태에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-120">**IM and presence**   Authorized external users can participate in IM conversations and conferences, and they can get information about one another’s presence status.</span></span> <span data-ttu-id="0c988-121">공용 IM 서비스 공급자의 사용자는 조직의 개별 Lync Server 사용자와의 메신저 대화에 참여할 수 있으며,이에 대 한 현재 상태 정보에는 관여 하지 않지만 Lync Server를 사용 하 여 IM 단체 회의에 참여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-121">Users of public IM service providers can participate in IM conversations with individual Lync Server users in your organization and access presence information, but they cannot participate in IM multiparty conferences using Lync Server.</span></span> <span data-ttu-id="0c988-122">이는 절대적으로 피어 투 피어 통신입니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-122">It is strictly peer-to-peer communication.</span></span> <span data-ttu-id="0c988-123">공용 IM 서비스 공급자의 사용자는 파일 전송을 지원 하지 않으며 피어 투 피어 통신의 오디오/비디오는 Windows Messenger 2011 사용자에 게 지원 되지만 다른 공용 IM 서비스 공급자 사용자에 게는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-123">File transfer is not supported for users of public IM service providers, and audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not other users of public IM service providers.</span></span>
    
    <span data-ttu-id="0c988-124">SIP와 XMPP 프로토콜이 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-124">Both SIP and XMPP protocols are supported.</span></span> <span data-ttu-id="0c988-125">XMPP에 대 한 서비스를 제공 하려면 [Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시지에 대 한 계획](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c988-125">To provide services for XMPP, see [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="0c988-126">**웹 회의**   승인 외부 사용자는 Lync Server 배포에 호스트 되는 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-126">**Web conferencing**   Authorized external users can participate in conferences that are hosted on your Lync Server deployment.</span></span> <span data-ttu-id="0c988-127">원격 사용자, 페더레이션 사용자, 익명 사용자는 웹 회의에 참여 하도록 설정할 수 있지만, 공용 IM 사용자는 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-127">Remote users, federated users, and anonymous users can be enabled for participation in web conferencing, but public IM users cannot participate in conferences.</span></span> <span data-ttu-id="0c988-128">선택 하는 옵션에 따라 웹 회의를 사용 하도록 설정 된 사용자는 데스크톱 및 응용 프로그램 공유에 참여할 수 있으며 모임 이끌이 또는 발표자 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-128">Depending on the options that you select, web conferencing-enabled users can participate in desktop and application sharing and can act as meeting organizers or presenters.</span></span>

  - <span data-ttu-id="0c988-129">**A/V 회의**   에서 승인 된 외부 사용자는 Lync Server 배포에서 호스트 하는 오디오 및 비디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-129">**A/V conferencing**   Authorized external users can participate in audio and video conferences that your Lync Server deployment hosts.</span></span> <span data-ttu-id="0c988-130">피어 투 피어 통신의 오디오/비디오는 Windows Messenger 2011 사용자에 게 지원 되지만 다른 공용 IM 서비스 공급자의 사용자에 게는 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-130">Audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not for other users of public IM service providers.</span></span>

<span data-ttu-id="0c988-131">통신을 제어 하기 위해 조직 내부와 외부의 사용자 간의 통신 방법을 정의 하는 하나 이상의 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-131">In order to control communications, you can configure one or more policies that define how users inside and outside your organization communicate with each other.</span></span> <span data-ttu-id="0c988-132">개별 내부 사용자 또는 특정 유형의 외부 사용자에 대 한 정책을 적용 하 고 외부 사용자와의 통신을 제어 하도록 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-132">You can also configure settings and apply policies for individual internal users or for specific types of external users to control communications with external users.</span></span>

<span data-ttu-id="0c988-133">외부 액세스를 제공 하는 데 사용 되는 Lync Server 2013 역할:</span><span class="sxs-lookup"><span data-stu-id="0c988-133">Lync Server 2013 roles that are used to provide external access:</span></span>

<span data-ttu-id="0c988-134">**Edge 서버**   edge 서버는 IM 및 현재 상태, 회의, 오디오/비디오, 기타 미디어 (예: 파일 전송) 서비스에 대 한 외부 액세스를 허용 하는 서비스를 실행 하는 서버 또는 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-134">**Edge Server**   The Edge Server is a server or a pool of servers that run the services that allow external access to IM and presence, conferencing, audio/video, and other media (for example, file transfer) services.</span></span> <span data-ttu-id="0c988-135">필요에 따라 다른 Lync Server 또는 Office Communications Server 2007 R2 배포 및 기타 XMPP 배포와 페더레이션 하도록 Edge 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-135">Optionally, you can configure the Edge Server to federate with other Lync Server or Office Communications Server 2007 R2 deployments, and other XMPP deployments.</span></span> <span data-ttu-id="0c988-136">선택적 공용 IM 연결 기능은 Edge 서버를 통해 설정 및 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-136">The optional public IM connectivity feature is enabled and configured through the Edge Server.</span></span>

<span data-ttu-id="0c988-137">**디렉터**   디렉터는 사용자 요청을 미리 인증 하 고 사용자의 홈 프런트 엔드 서버 또는 프런트 엔드 풀에 대 한 요청을 라우팅하는 데 사용 되는 Lync server 2013 디렉터 역할을 실행 하는 선택적 서버 또는 서버 풀입니다 (사용자 계정에는 홈이 지정 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="0c988-137">**Director**   The Director is an optional server or server pool running the Lync Server 2013 Director role that pre-authenticates user requests and routes requests to the users’ home Front End Server or Front End pool, but does not home any user accounts.</span></span>

<span data-ttu-id="0c988-138">**리버스 프록시**   역방향 프록시는 내부 네트워크에서 사용할 수 있는 리소스를 게시 하 고 게시 된 리소스에서 클라이언트에 대 한 정보를 검색 하는 특수 서버에 대 한 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-138">**Reverse Proxy**   A reverse proxy is a general term for specialized servers that publish resources available on the internal network and retrieve information for clients from the published resource.</span></span> <span data-ttu-id="0c988-139">Lync Server 2013는 리버스 프록시를 사용 하 여 회의 모임, 회의 참가 위치, 주소록, 메일 그룹 확장, 모임 콘텐츠 다운로드, 장치 업데이트, 이동성 서비스 등의 다양 한 기능을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-139">Lync Server 2013 uses the reverse proxy to publish a number of features, such as conferencing meetings, conference join locations, the address book, distribution list expansion, downloading meeting content, device updates, Mobility services, and more.</span></span> <span data-ttu-id="0c988-140">필요한 리소스 위치를 게시 하기 위한 요구 사항을 충족 시킬 수 있는 모든 역방향 프록시를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-140">Any reverse proxy that can meet the requirements for publishing the necessary resource locations can be used.</span></span> <span data-ttu-id="0c988-141">Microsoft Forefront (위협 관리 게이트웨이) 2010는 필요한 게시 규칙을 설명 하기 위해 예제로 사용 되지만 Forefront TMG 2010는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 is used as an example for the purposes of illustrating the publishing rules necessary, but Forefront TMG 2010 is not required.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c988-142">Lync 서버 2013는 IPv4 및 IPv6을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-142">Lync Server 2013 supports both IPv4 and IPv6.</span></span> <span data-ttu-id="0c988-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012 및 windows Server 2012 R2는 IPv4와 IPv6을 동시에 사용할 수 있는 이중 스택을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012, and Windows Server 2012 R2 use a dual stack that can use both IPv4 and IPv6 concurrently.</span></span> <span data-ttu-id="0c988-144">IPv4에서 IPv6으로 이동 하는 배포의 전환 특성 때문에이는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-144">This is important because of the transitional nature of a deployment moving from IPv4 to IPv6.</span></span> <span data-ttu-id="0c988-145">IPv4는 배포의 다른 영역에서 IPv6을 사용할 수 있는 일부 영역에서 지원 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-145">IPv4 can be supported in some areas, where in other areas of the deployment, IPv6 can be used.</span></span> <span data-ttu-id="0c988-146">이는 인터넷 및 내부 배포에 관련 된 경우 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-146">This is especially important where the Internet and internal deployments are concerned.</span></span> <span data-ttu-id="0c988-147">외부 클라이언트는 이동성, 모임, 주소록 다운로드 등의 서비스를 사용 하기 위해 리버스 프록시를 통해 통신 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-147">External clients must communicate through the reverse proxy to use services such as mobility, meetings, address book download, and others.</span></span> <span data-ttu-id="0c988-148">현재 배포 된 운영 체제 버전에 관계 없이 Forefront Threat Management 게이트웨이 2010 및 인터넷 보안 및 가속 서버 2006이 IPv6 주소 지정을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-148">Currently, Forefront Threat Management Gateway 2010 and Internet Security and Acceleration Server 2006 do not support IPv6 addressing, regardless of the operating system version that they are deployed on.</span></span> <span data-ttu-id="0c988-149">IPv6 및 IPv4를 외부 클라이언트와 관련 하 여 사용 하는 것과 관련 하 여 적절 하 게 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c988-149">You must plan accordingly in relation to your use of IPv6 and IPv4 as they relate to external clients.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

