---
title: 'Lync Server 2013: 원격 통화 제어에 대 한 배포 작업'
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
ms.openlocfilehash: bd2ac45e0f589ac155d2e0f51b0115036a97809e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499055"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="60d56-102">Lync Server 2013의 원격 통화 제어에 대 한 배포 작업</span><span class="sxs-lookup"><span data-stu-id="60d56-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60d56-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="60d56-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="60d56-104">이 항목에서는 Lync Server 환경에서 사용자에 대 한 원격 통화 제어를 사용 하도록 설정 하기 위해 수행 해야 하는 배포 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60d56-105">Microsoft Office Communicator 2007 r 2의 원격 통화 제어를 위해 이전에 사용 하도록 설정한 사용자를 마이그레이션하는 경우에는이 항목에서 설명 하는 원격 통화 제어 배포 작업을 수행 하기 전에 추가 배포 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="60d56-106">Lync Server로의 마이그레이션 프로세스 중에는 적절 한 Office Communications Server 2007 R2 관리 도구를 사용 하 여 신뢰할 수 있는 응용 프로그램 항목 (이전에는 <EM>권한이 부여 된 호스트 항목</EM>으로 알려진)을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="60d56-107">권한이 부여 된 호스트를 제거 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy 공인 host in a Lync Server 2013 (optional)</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="60d56-108">1단계: PBX와 통신할 SIP/CSTA 게이트웨이 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="60d56-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="60d56-109">사용자에 게 원격 통화 제어 기능을 제공 하기 위해 해당 환경의 Lync Server 및 기존 PBX (private branch exchange) 둘 다에 연결할 수 있는 SIP/CSTA 게이트웨이를 하나 이상 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="60d56-110">SIP/CSTA 게이트웨이는 SIP와 CSTA(Computer-Supported Telecommunications Application) 사이에 있는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="60d56-111">게이트웨이를 여러 개 설치하든 하나만 설치하든 관계없이 하나의 게이트웨이 또는 PBX만 사용하여 각 사용자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="60d56-112">기존 PBX에 SIP/CSTA 인터페이스가 없는 경우에는 소유 PBX 공급업체별 신호 프로토콜에 대한 지원을 포함하여 PBX를 지원할 수 있는 SIP/CSTA 게이트웨이를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="60d56-113">기능에 대한 자세한 내용은 각 공급업체에 직접 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="60d56-114">원격 통화 제어를 위해 Lync Server와 통합할 수 있는 SIP/CSTA 게이트웨이를 배포할 준비가 되 면 게이트웨이 공급 업체나 공급 업체의 게이트웨이 설명서에서 다음 정보에 대 한 게이트웨이에 필요한 구문을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60d56-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="60d56-115">게이트웨이의 회선 서버 URI</span><span class="sxs-lookup"><span data-stu-id="60d56-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="60d56-116">게이트웨이에 할당할 사용자에 대한 줄 URI</span><span class="sxs-lookup"><span data-stu-id="60d56-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="60d56-117">위 설정은 사용자 구성 중에 필요하며, 게이트웨이에서 예상대로 지정해야 PBX를 올바르게 라우팅하고 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="60d56-118">의 Microsoft 통합 통신 오픈 상호 운용성 프로그램 웹 사이트에서 공급 업체를 참조할 수 있습니다 [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .</span><span class="sxs-lookup"><span data-stu-id="60d56-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="60d56-119">2 단계: CSTA 요청을 SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 구성</span><span class="sxs-lookup"><span data-stu-id="60d56-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="60d56-120">원격 통화 제어 요청을 라우팅할 배포에 있는 모든 SIP/CSTA 게이트웨이의 대상 주소 (서버 URI)에 대 한 고정 경로를 Lync Server 풀에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="60d56-121">또한 각 대상 주소에 해당하는 신뢰할 수 있는 응용 프로그램 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="60d56-122">게이트웨이를 신뢰할 수 있는 응용 프로그램으로 지정 하는 경우, 타사에서 개발 하는 경우에도 신뢰할 수 있는 상태가 Lync Server 환경의 일부로 실행 되도록 지정 되며,이는 제품의 기본 제공 부분이 아닌 서비스 이기 때문에 *외부 서비스로* 참조 되는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="60d56-123">마지막으로 Lync Server에서 TLS (전송 계층 보안) 연결 대신 TCP (전송 제어 프로토콜) 연결을 사용 하 여 SIP/CSTA 게이트웨이에 연결 하는 경우 토폴로지 작성기를 사용 하 여 게이트웨이 IP 주소도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="60d56-124">고정 경로를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성을](lync-server-2013-configure-a-static-route-for-remote-call-control.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="60d56-125">신뢰할 수 있는 응용 프로그램 항목 구성에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성을](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="60d56-126">토폴로지 작성기에서 SIP/CSTA 게이트웨이 IP 주소를 정의 하는 방법에 대 한 자세한 내용은 [Define a sip/CSTA GATEWAY ip address in a Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="60d56-127">3 단계: 원격 통화 제어에 대 한 Lync 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="60d56-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="60d56-128">Lync Server를 사용 하도록 설정한 후 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 원격 통화 제어에 대해 사용자를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="60d56-129">각 사용자에 게 줄 서버 URI와 줄 URI를 할당 하는이 배포 단계 중에 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="60d56-130">회선 서버 URI는 사용자에 게 할당할 SIP/CSTA 게이트웨이의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="60d56-131">줄 URI는 사용자에 게 할당 되는 고유한 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="60d56-132">원격 통화 제어에 대 한 사용자를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 lync 사용자에 대 한 원격 통화 제어 사용](lync-server-2013-enable-lync-users-for-remote-call-control.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="60d56-133">4단계: Lync Server 전화 번호 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="60d56-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="60d56-134">원격 통화 제어 시나리오에서 Lync Server는 전화 번호 정규화 규칙을 사용 하 여 SIP/CSTA 게이트웨이에서 수신 하는 전화 번호를 E. 164 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="60d56-135">특정 원격 통화 제어 기능이 제대로 작동 하려면 전화 번호가이 표준화 된 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="60d56-136">원격 통화 제어는 Enterprise Voice에 사용 되는 전화 번호 정규화 규칙과는 다른, 주소록 서비스 전화 번호 정규화에 대해 구성한 것과 동일한 전화 번호 정규화 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60d56-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="60d56-137">원격 통화 제어에서 전화 번호 정규화 규칙을 사용 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어 및 전화 번호 정규화](lync-server-2013-remote-call-control-and-phone-number-normalization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60d56-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="60d56-138">주소록 서비스에 대 한 전화 번호 정규화 규칙에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 주소록 서비스 관리](lync-server-2013-administering-the-address-book-service.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d56-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

