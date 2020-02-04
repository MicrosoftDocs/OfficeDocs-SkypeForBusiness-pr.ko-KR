---
title: 'Lync Server 2013: 원격 통화 제어에 대한 배포 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="9ddc6-102">Lync Server 2013의 원격 통화 제어에 대한 배포 작업</span><span class="sxs-lookup"><span data-stu-id="9ddc6-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ddc6-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="9ddc6-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="9ddc6-104">이 항목에서는 Lync Server 환경에서 사용자에 대 한 원격 통화 제어를 사용 하도록 설정 하기 위해 수행 해야 하는 배포 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ddc6-105">Microsoft Office Communicator 2007 R2에서 이전에 원격 통화 제어에 대해 사용 하도록 설정 된 사용자를 마이그레이션하는 경우에는이 항목에서 설명 하는 원격 통화 제어 배포 작업을 시작 하기 전에 추가 배포 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="9ddc6-106">Lync Server로 마이그레이션 프로세스를 진행 하는 동안에는 Office Communications Server 2007 R2 관리 도구를 사용 하 여 신뢰할 수 있는 응용 프로그램 항목 (이전에는 <EM>권한이 있는 호스트 항목</EM>이라고 함)을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="9ddc6-107">권한이 부여 된 호스트를 제거 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013에서 레거시 권한 있는 호스트 제거 (선택 사항)</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="9ddc6-108">1 단계: SIP/CSTA 게이트웨이를 설치 하 고 구성 하 여 PBX와 통신</span><span class="sxs-lookup"><span data-stu-id="9ddc6-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="9ddc6-109">사용자에 게 원격 통화 제어 기능을 제공 하려면 해당 환경에서 Lync 서버와 기존 개인 분기 교환 (PBX)에 연결할 수 있는 SIP/CSTA 게이트웨이를 하나 이상 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="9ddc6-110">SIP/CSTA 게이트웨이는 SIP와 컴퓨터에서 지 원하는 텔레커뮤니케이션 응용 프로그램 (CSTA) 간의 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="9ddc6-111">게이트웨이를 여러 개 설치 하 든 둘 중 하나를 설치할지에 관계 없이 각 사용자는 하나의 게이트웨이 또는 PBX를 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="9ddc6-112">기존 PBX에 SIP/CSTA 인터페이스가 없으면 독점 PBX 공급자별 신호 프로토콜에 대 한 지원을 포함 하 여 PBX를 지원할 수 있는 SIP/CSTA 게이트웨이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="9ddc6-113">기능에 대 한 자세한 내용은 각 공급 업체를 직접 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="9ddc6-114">원격 통화 제어를 위해 Lync Server와 통합할 수 있는 SIP/CSTA 게이트웨이를 배포할 준비가 되 면 다음 정보에 대해 게이트웨이에 필요한 구문에 대 한 게이트웨이 공급 업체나 공급 업체의 게이트웨이 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="9ddc6-115">게이트웨이의 회선 서버 URI</span><span class="sxs-lookup"><span data-stu-id="9ddc6-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="9ddc6-116">게이트웨이에 할당 되는 사용자의 회선 URI</span><span class="sxs-lookup"><span data-stu-id="9ddc6-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="9ddc6-117">앞의 설정이 사용자 구성 중에 필요 하며, 게이트웨이에 올바르게 라우팅하고 연결 하는 데 필요한 대로 게이트웨이가 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="9ddc6-118">의 Microsoft 통합 커뮤니케이션에서 상호 운용성 프로그램 웹 사이트를 통해 공급 업체를 [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="9ddc6-119">2 단계: CSTA 요청을 SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 구성</span><span class="sxs-lookup"><span data-stu-id="9ddc6-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="9ddc6-120">원격 통화 제어 요청을 라우팅할 배포의 모든 SIP/CSTA 게이트웨이의 대상 주소 (서버 URI)에 대 한 고정 경로를 Lync Server 풀에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="9ddc6-121">또한 각 대상 주소에 해당 하는 신뢰할 수 있는 응용 프로그램 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="9ddc6-122">게이트웨이를 신뢰할 수 있는 응용 프로그램으로 지정 하면 타사에서 개발 하는 경우에도 Lync Server 환경의 일부로 실행할 신뢰할 수 있는 상태가 지정 되 고 제품의 기본 제공 부분이 아닌 서비스 이므로 *외부 서비스로* 참조 되는 항목을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="9ddc6-123">마지막으로 Lync Server가 TLS (전송 계층 보안) 연결 대신 TCP (전송 제어 프로토콜) 연결을 사용 하 여 SIP/CSTA 게이트웨이에 연결 하는 경우 토폴로지 작성기를 사용 하 여 게이트웨이 IP 주소도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="9ddc6-124">고정 경로를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성을](lync-server-2013-configure-a-static-route-for-remote-call-control.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="9ddc6-125">신뢰할 수 있는 응용 프로그램 항목을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대해 신뢰할 수 있는 응용 프로그램 항목 구성을](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)참조 하세요</span><span class="sxs-lookup"><span data-stu-id="9ddc6-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="9ddc6-126">토폴로지 작성기에서 SIP/CSTA 게이트웨이 IP 주소를 정의 하는 방법에 대 한 자세한 내용은 [Lync 서버 2013에서 sip/CSTA 게이트웨이 ip 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="9ddc6-127">3 단계: 원격 통화 제어를 위해 Lync 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="9ddc6-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="9ddc6-128">Lync Server에 대해 사용자를 설정한 후에는 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 원격 통화 제어에 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="9ddc6-129">이 배포 단계에서는 각 사용자에 게 회선 서버 URI와 줄 URI를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="9ddc6-130">줄 서버 URI는 사용자에 게 할당할 SIP/CSTA 게이트웨이의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="9ddc6-131">줄 URI는 사용자에 게 할당 된 고유 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="9ddc6-132">원격 통화 제어를 위해 사용자를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 lync 사용자를 위한 원격 통화 제어 사용](lync-server-2013-enable-lync-users-for-remote-call-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="9ddc6-133">4 단계: Lync Server 전화 번호 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="9ddc6-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="9ddc6-134">원격 통화 제어 시나리오에서 Lync Server는 전화 번호 정규화 규칙을 사용 하 여 수신 하는 전화 번호를 SIP/CSTA 게이트웨이에서 E-164 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="9ddc6-135">전화 번호는 특정 원격 통화 제어 기능이 제대로 작동 하려면이 표준화 된 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="9ddc6-136">원격 통화 제어는 주소록 서비스 전화 번호 정규화에 대해 구성 하는 것과 동일한 전화 번호 정규화 규칙을 사용 하 여 Enterprise Voice에 사용 되는 전화 번호 정규화 규칙과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="9ddc6-137">원격 통화 제어에서 전화 번호 정규화 규칙을 사용 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어 및 전화 번호 정규화](lync-server-2013-remote-call-control-and-phone-number-normalization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="9ddc6-138">주소록 서비스에 대 한 전화 번호 정규화 규칙에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 주소록 서비스 관리](lync-server-2013-administering-the-address-book-service.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddc6-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

