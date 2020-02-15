---
title: 'Lync Server 2013: 네트워크 어댑터 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c114766bffb665e2c7da2850fefc6113365e4c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="54411-102">Lync Server 2013에서 네트워크 어댑터 구성</span><span class="sxs-lookup"><span data-stu-id="54411-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54411-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="54411-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="54411-104">외부 네트워크 어댑터에 하나 이상의 IP 주소를 할당 하 고 내부 네트워크 어댑터에 대 한 IP 주소를 하나 이상 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="54411-105">다음 절차에서 Forefront Threat Management Gateway (TMG) 2010 또는 Internet Information Server 응용 프로그램 요청 라우팅을 실행 하는 서버에는 두 개의 네트워크 어댑터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54411-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="54411-106">웹 사이트에 연결을 시도 하는 클라이언트 (일반적으로 인터넷을 통해)에 대 한 공용 또는 외부 네트워크 어댑터</span><span class="sxs-lookup"><span data-stu-id="54411-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="54411-107">웹 서비스를 호스팅하는 Lync Server를 실행 하는 내부 서버의 개인 또는 내부 네트워크 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="54411-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="54411-108">에 지 서버와 마찬가지로 외부 네트워크 어댑터에만 기본 게이트웨이를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="54411-109">기본 게이트웨이는 트래픽을 인터넷으로 연결 하는 라우터 또는 외부에 연결 된 방화벽의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="54411-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="54411-110">역방향 프록시에서 내부 연결 된 네트워크 어댑터에서 향하는 트래픽에 대해 웹 게시 규칙에서 참조 하는 서버가 포함 된 모든 서브넷에 대해 영구 고정 경로 (예: Windows Server의 경로 명령)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="54411-111">영구 경로를 설정 해도 컴퓨터가 라우터가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54411-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="54411-112">IP 전달이 사용 하도록 설정 되지 않은 경우 컴퓨터는 다른 네트워크에 연결 된 특정 트래픽을 적절 한 인터페이스로 연결 하는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="54411-113">이는 기본적으로 외부 네트워크를 가리키는 기본 및 내부 인터페이스로 향하는 트래픽 및 라우터나 기타 네트워크에 각각 하나씩 두 개의 게이트웨이를 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54411-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="54411-114">그러나 네트워크 라우터가 경로를 요약 하도록 구성 된 경우에는 모든 서브넷에 대해 영구 경로를 만드는 것이 필요 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54411-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="54411-115">라우터가 정의 된 네트워크에 대 한 영구 경로를 만들고이 라우터를 기본 게이트웨이로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="54411-116">네트워크가 구성 되는 방식을 잘 모르는 경우에는 회사의 네트워크 엔지니어에 게 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="54411-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="54411-117">역방향 프록시는 웹 게시 규칙에 사용 되는 내부 디렉터 또는 프런트 엔드 서버 및 다음 홉 풀 Fqdn에 대 한 DNS 호스트 (A) 레코드를 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="54411-118">에 지 서버와 마찬가지로 보안상의 이유로, 내부 네트워크에 있는 DNS 서버를 사용 하도록 역방향 프록시를 구성 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="54411-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="54411-119">즉, 경계에 DNS 서버가 필요 하거나, 이러한 각 Fqdn을 서버의 내부 IP 주소로 확인 하는 호스트 파일 항목이 역방향 프록시에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="54411-120">역방향 프록시 컴퓨터에서 네트워크 어댑터 카드를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="54411-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="54411-121">역방향 프록시로 실행 되는 windows Server 2008, windows server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2 서버에서 **시작**을 클릭 하 고 **제어판**을 가리킨 다음 **네트워크 및 공유 센터**를 클릭 하 고 **어댑터 설정 변경을**클릭 하 여 **어댑터 설정 변경을** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54411-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="54411-122">외부 인터페이스에 사용할 외부 네트워크 연결을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="54411-123">**속성** 페이지에서 **네트워킹** 탭을 클릭 하 고 **이 연결에 다음 항목 사용** 목록에서 **인터넷 프로토콜 버전 4 (TCP/IPv4)** 를 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="54411-124">**인터넷 프로토콜 (tcp/ip) 속성** 페이지에서 네트워크 어댑터를 연결할 네트워크 서브넷에 대 한 IP 주소를 적절 하 게 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54411-125">HTTPS/TCP/443을 사용 하는 다른 응용 프로그램에서 역방향 프록시를 이미 사용 하 고 있는 경우 예를 들어 Outlook Web Access 게시와 같은 경우에는 다른 IP 주소를 추가 해야 기존 규칙과 웹 수신기를 방해 하지 않고 Lync Server 2013 웹 서비스를 HTTPS/TCP/443에 게시 하거나, 기존 인증서를 주체 대체 이름에 새 외부 FQDN 이름을 추가 하는 것으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="54411-126">**확인**을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="54411-127">**네트워크 연결**에서 내부 인터페이스에 사용할 내부 네트워크 연결을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="54411-128">3 ~ 5 단계를 반복 하 여 내부 네트워크 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54411-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

