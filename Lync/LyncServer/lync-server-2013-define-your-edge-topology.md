---
title: 'Lync Server 2013: 에지 토폴로지 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a04dca4b935caf8f07546babd2c53f65fff4e89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="204d4-102">Lync Server 2013에서 에지 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="204d4-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="204d4-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="204d4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="204d4-104">토폴로지를 작성 하려면 토폴로지 작성기를 사용 해야 하며, Edge 서버를 배포 하려면 먼저 하나 이상의 내부 프런트 엔드 풀 또는 Standard Edition 서버를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="204d4-105">다음 절차를 사용 하 여 단일 Edge 서버에 대 한 edge 토폴로지를 정의한 다음 Lync server 2013 [2013에서 토폴로지 게시](lync-server-2013-publish-your-topology.md) 의 절차를 사용 하 여 [edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 하 여 edge 서버에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="204d4-106">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="204d4-107">즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="204d4-108">서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="204d4-109">또한 사용자 계정에 서버 역할을 추가 하는 데 필요한 관리자 권한과 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="204d4-110">자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서의 [Lync Server 2013에서 설정 위임을](lync-server-2013-delegate-setup-permissions.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="204d4-111">다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="204d4-112">내부 토폴로지를 정의 하 고 게시 했을 때 edge 토폴로지를 정의 했지만 이전에 정의한 edge 토폴로지에 대 한 변경이 필요 하지 않은 경우에는이를 정의 하 고 다시 게시할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="204d4-113">Edge 토폴로지를 변경 해야 하는 경우에만 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="204d4-114">이전에 정의 하 고 게시 한 토폴로지를 Edge 서버에서 사용할 수 있도록 설정 해야 하며, [이는 Lync Server 2013 토폴로지 내보내기 및 edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)하는 절차를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="204d4-115">Edge 서버에서 토폴로지 작성기를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="204d4-116">프런트 엔드 서버 또는 Standard Edition 서버에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="204d4-117">Edge 서버 토폴로지를 정의 하는 프로세스는 토폴로지 작성기에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="204d4-118">계획 및 구성 하는 세 가지 기본 Edge 서버 토폴로지 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="204d4-119">단일 Edge 서버의 토폴로지를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="204d4-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="204d4-120">부하 분산 된 Edge 서버 풀에 대 한 토폴로지를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="204d4-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="204d4-121">하드웨어 부하 분산 된 Edge 풀에 대 한 토폴로지를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="204d4-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="204d4-122">단일 Edge 서버의 토폴로지를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="204d4-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="204d4-123">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="204d4-124">콘솔 트리에서 Edge 서버를 배포 하려는 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="204d4-125">**Edge 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="204d4-126">**새 Edge 풀 정의**에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="204d4-127">**Edge 풀 FQDN 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-128">**풀 fqdn**에 Edge 서버의 내부 인터페이스에 대 한 fqdn (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="204d4-129">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="204d4-130">기본적으로 도메인에 가입 되어 있지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="204d4-131">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="204d4-132">따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="204d4-133">Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함)만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="204d4-134">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="204d4-135">FQDN의 비표준 문자는 외부 DNS 및 공용 Ca에서 지원 되지 않습니다 (FQDN을 인증서의 SN에 할당 해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="204d4-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="204d4-136">컴퓨터 이름에 DNS 접미사를 추가 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013에서 edge 용 dns 지원을 구성</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-137">**단일 컴퓨터 풀**을 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="204d4-138">**선택 된 기능**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-139">SIP 액세스 서비스, Lync Server 2013 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하려는 경우 **단일 fqdn 및 IP 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="204d4-140">페더레이션을 사용 하려는 경우 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-141">이 옵션을 선택할 수 있지만 조직에서 페더레이션에 대해 외부에서 하나의 Edge 풀 또는 Edge 서버만 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="204d4-142">공용 인스턴트 메시징 (IM) 사용자를 비롯 한 페더레이션 사용자의 모든 액세스는 동일한 Edge 풀 또는 단일 Edge 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="204d4-143">예를 들어 배포에 Edge 풀 또는 뉴욕에 배포 된 단일 Edge 서버와 London에 배포 되 고 뉴욕의 Edge 풀 또는 단일 Edge 서버에서 페더레이션 지원을 사용 하도록 설정 하는 경우 페더레이션 사용자에 대 한 신호 소통량이 뉴욕에서 진행 됩니다. Edge 풀 또는 싱글 Edge 서버.</span><span class="sxs-lookup"><span data-stu-id="204d4-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="204d4-144">이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-145">배포에 대해 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜)를 지원 하려는 경우 **xmpp 페더레이션 사용 (포트 5269)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="204d4-146">**IP 옵션 선택**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-147">**내부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="204d4-148">**내부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="204d4-149">**외부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="204d4-150">**외부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="204d4-151">또한 외부 IP 주소에 대 한 네트워크 주소 변환 주소를 사용 하도록 Edge 서버 또는 Edge 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="204d4-152">확인란을 선택 하 여이 작업을 수행 합니다. **이 Edge 풀의 외부 IP 주소가 NAT에서 번역 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="204d4-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="204d4-153">**외부 fqdn**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-154">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN 및 IP 주소를 사용 **하도록 선택한 경우** **sip ACCESS**에 외부 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-155">이 옵션을 선택 하는 경우 각 edge services에 대해 다른 포트 번호를 지정 해야 합니다 (권장 포트 설정: 액세스에 지 서비스의 경우 5061, 웹 회의 Edge 서비스의 경우 444, A/V Edge 서비스의 경우 443).</span><span class="sxs-lookup"><span data-stu-id="204d4-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="204d4-156">이 옵션을 선택 하면 잠재적인 연결 문제를 방지 하 고 세 가지 서비스에 동일한 포트 번호 (예: 443)를 사용할 수 있기 때문에 구성을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-157">선택 된 **기능** 에 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우 **SIP 액세스**, **웹 회의** 및 **오디오 비디오**에 대 한 외부 fqdn을 입력 하 고 기본 포트를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="204d4-158">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-158">Click **Next**.</span></span>

10. <span data-ttu-id="204d4-159">**내부 IP 주소 정의**에 경계 서버의 IP 주소를 **내부 IPv4 주소** 와 **내부 IPv6 주소로** 입력 하 여 요구 사항에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="204d4-160">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-160">Click **Next**.</span></span>

11. <span data-ttu-id="204d4-161">**외부 IP 주소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-162">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택한 경우에는 **Sip access**에 Edge 서버의 외부 IPv4 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="204d4-163">IPv6 주소를 사용 하도록 선택한 경우에는에 지 서버의 외부 IPv6 주소를 **SIP 액세스**에 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="204d4-164">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우에는 **Sip access**, **웹 회의**및 **a/v 회의**에 Edge 서버의 외부 IPv4 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="204d4-165">IPv6 주소를 사용 하도록 선택 했지만 SIP access, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우에는 **Sip 액세스**, **웹 회의**및 **a/v 회의**에 Edge 서버의 외부 IPv6 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-166">IPv6 주소 지정을 사용 하도록 선택 하지 않은 경우에는이 대화 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="204d4-167">NAT를 사용 하도록 선택한 경우 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="204d4-168">**A/V Edge 서비스의 공용 ipv4 주소**에서 NAT에서 번역할 공용 ipv4 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-169">A/V Edge 서비스의 외부 IP 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="204d4-170">NAT 및 IPv6 주소를 사용 하도록 선택한 경우 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="204d4-171">**A/V Edge 서비스의 공개 ipv6 주소**에서 NAT에서 번역할 공용 ipv6 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-172">A/V Edge 서비스의 외부 IP 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="204d4-173">**다음**홉 그룹의 다음 홉 **풀**에서 내부 풀의 이름을 선택 합니다 (프런트 엔드 풀 또는 Standard Edition 풀이 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="204d4-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="204d4-174">또는 배포에 디렉터가 포함 된 경우에는 디렉터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="204d4-175">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="204d4-176">**프런트 엔드 풀 연결**에서 지원 되는 외부 사용자와의 통신에이 edge 서버를 사용 하는 내부 풀의 이름을 선택 하 여 프런트 엔드 풀 및 스탠더드 버전 서버와 연결할 수 있는 하나 이상의 내부 풀을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-177">1 개의 부하 분산 된 Edge 풀 또는 단일 Edge 서버만 A/V 트래픽에 대 한 각 내부 풀에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="204d4-178">Edge 풀 또는 Edge 서버와 연결 된 내부 풀이 이미 있는 경우 내부 풀이 이미 Edge 풀 또는 Edge 서버에 연결 되어 있음을 나타내는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="204d4-179">다른 Edge 서버와 이미 연결 된 풀을 선택 하면 연결이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="204d4-180">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-180">Click **Finish**.</span></span>

17. <span data-ttu-id="204d4-181">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="204d4-182">DNS 부하 분산 Edge 서버 풀에 대 한 토폴로지를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="204d4-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="204d4-183">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="204d4-184">콘솔 트리에서 Edge 서버를 배포 하려는 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="204d4-185">**Edge 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="204d4-186">**새 Edge 풀 정의**에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="204d4-187">**Edge 풀 FQDN 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-188">**풀 fqdn**에 Edge 풀의 내부 연결에 대 한 fqdn (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="204d4-189">풀에 대해 지정 하는 이름은 내부에 지 풀 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="204d4-190">이는 FQDN으로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="204d4-191">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="204d4-192">Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함)만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="204d4-193">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="204d4-194">FQDN의 비표준 문자는 외부 DNS 및 공용 Ca에서 지원 되지 않습니다 (FQDN을 인증서의 SN에 할당 해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="204d4-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-195">**여러 컴퓨터 풀**을 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="204d4-196">**선택 된 기능**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-197">SIP 액세스에 대 한 단일 FQDN과 IP 주소를 사용 하려는 경우 Lync Server 2013 웹 회의 서비스 및 A/V Edge 서비스에서 **단일 fqdn 및 Ip 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="204d4-198">페더레이션을 사용 하려는 경우 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="204d4-199">**다음** 클릭</span><span class="sxs-lookup"><span data-stu-id="204d4-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-200">이 옵션을 선택할 수 있지만 조직에서 페더레이션에 대해 외부에서 하나의 Edge 풀 또는 Edge 서버만 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="204d4-201">공용 인스턴트 메시징 (IM) 사용자를 비롯 한 페더레이션 사용자의 모든 액세스는 동일한 Edge 풀 또는 단일 Edge 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="204d4-202">예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="204d4-203">이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-204">배포에 대해 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜)를 지원 하려는 경우 **xmpp 페더레이션 사용 (포트 5269)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="204d4-205">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-205">Click **Next**.</span></span>

8.  <span data-ttu-id="204d4-206">**IP 옵션 선택**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-207">**내부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="204d4-208">**내부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="204d4-209">**외부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="204d4-210">**외부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="204d4-211">또한 외부 IP 주소에 대 한 네트워크 주소 변환 주소를 사용 하도록 Edge 서버 또는 Edge 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="204d4-212">확인란을 선택 하 여이 작업을 수행 합니다. **이 Edge 풀의 외부 IP 주소가 NAT에서 번역 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="204d4-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="204d4-213">**외부 fqdn**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-214">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN 및 IP 주소를 사용 **하도록 선택한 경우** **sip ACCESS**에 외부 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-215">이 옵션을 선택 하는 경우 각 Edge services에 대해 다른 포트 번호를 지정 해야 합니다 (권장 포트 설정: 액세스에 지 서비스의 경우 5061, 웹 회의 Edge 서비스의 경우 444, A/V Edge 서비스의 경우 443).</span><span class="sxs-lookup"><span data-stu-id="204d4-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="204d4-216">이 옵션을 선택 하면 세 가지 서비스에 동일한 포트 번호 (예: 443)를 사용할 수 있기 때문에 잠재적인 연결 문제를 방지 하 고 구성을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-217">**선택한 기능** 에서 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우에는 **SIP 액세스**에서 edge 풀의 공용 측에 대해 선택한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="204d4-218">**웹 회의**에서 Edge 풀의 공용 측에 대해 선택한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="204d4-219">**오디오/비디오**에서 Edge 풀의 공용 측에 대해 선택한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="204d4-220">기본 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-220">Use the default ports.</span></span>

10. <span data-ttu-id="204d4-221">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-221">Click **Next**.</span></span>

11. <span data-ttu-id="204d4-222">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="204d4-223">**내부 FQDN 및 IP 주소**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-224">**내부 ipv4**주소에 IPv4 주소와 **내부 IPv6 주소** 를이 풀에 만들려는 첫 번째 Edge 서버의 요구 사항에 맞게 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="204d4-225">**내부 FQDN**에서이 풀에 만들려는 첫 번째 EDGE 서버의 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-226">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="204d4-227">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="204d4-228">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="204d4-229">따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="204d4-230">Lync Server, Edge 서버, 풀, 배열에 대 한 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함)만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="204d4-231">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="204d4-232">FQDN의 비표준 문자는 외부 DNS 및 공용 Ca에서 지원 되지 않습니다 (FQDN을 인증서의 SN에 할당 해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="204d4-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="204d4-233">컴퓨터 이름에 DNS 접미사를 추가 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013에서 edge 용 dns 지원을 구성</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="204d4-234">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-234">Click **Next**.</span></span>

14. <span data-ttu-id="204d4-235">**외부 IP 주소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-236">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택한 경우 **Sip 액세스**에 Edge 서버의 외부 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="204d4-237">SIP 액세스, 웹 회의 서비스 및 A/V 회의 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우 **Sip 액세스**를 위해이 Edge 풀 서버의 공용 측에 대해 선택한 ip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="204d4-238">**웹 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="204d4-239">**A/V 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="204d4-240">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-240">Click **Next**.</span></span>

16. <span data-ttu-id="204d4-241">IPv6 주소를 사용 하도록 선택한 경우 **외부 IP 주소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-242">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택한 경우 **Sip access**에 Edge 서버의 외부 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="204d4-243">SIP 액세스, 웹 회의 서비스 및 A/V 회의 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우 **Sip 액세스**를 위해이 Edge 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="204d4-244">**웹 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="204d4-245">**A/V 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-246">IPv6 주소 지정을 사용 하도록 선택 하지 않은 경우에는이 대화 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="204d4-247">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-248">이제 풀에서 만든 첫 번째 Edge 서버가 <STRONG>이 풀의 컴퓨터 정의</STRONG> 대화 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="204d4-249">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭 한 다음 edge 풀에 추가 하려는 두 번째 edge 서버에 대해 11 ~ 14 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="204d4-250">11 ~ 14 단계를 반복한 후 다음을 클릭 하 **여이 풀의 컴퓨터 정의**에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-251">이 시점에서 풀에 있는 Edge 서버 두 개를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="204d4-252">NAT를 사용 하도록 선택한 경우 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="204d4-253">**공용 IP 주소**에서 NAT에서 번역할 공용 IPv4 및 IPv6 (적절 한) 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-254">A/V 가장자리의 외부 IP 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="204d4-255">**다음 홉 정의**의 **다음 홉 풀** 목록에서 내부 풀의 이름을 선택 합니다 (프런트 엔드 풀 또는 Standard Edition 풀이 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="204d4-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="204d4-256">또는 배포에 디렉터가 포함 된 경우에는 디렉터 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="204d4-257">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="204d4-258">**프런트 엔드 풀 연결**에서 지원 되는 외부 사용자와의 통신에이 edge 서버를 사용 하는 내부 풀의 이름을 선택 하 여 프런트 엔드 풀 및 스탠더드 버전 서버와 연결할 수 있는 하나 이상의 내부 풀을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-259">1 개의 부하 분산 된 Edge 풀 또는 단일 Edge 서버만 A/V 트래픽에 대 한 각 내부 풀에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="204d4-260">Edge 풀 또는 Edge 서버와 연결 된 내부 풀이 이미 있는 경우 내부 풀이 이미 Edge 풀 또는 Edge 서버에 연결 되어 있음을 나타내는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="204d4-261">다른 Edge 서버와 이미 연결 된 풀을 선택 하면 연결이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="204d4-262">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-262">Click **Finish**.</span></span>

24. <span data-ttu-id="204d4-263">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="204d4-264">하드웨어 부하 분산 된 Edge 서버 풀에 대 한 토폴로지를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="204d4-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="204d4-265">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="204d4-266">콘솔 트리에서 Edge 서버를 배포 하려는 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="204d4-267">**Edge 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 edge 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="204d4-268">**새 Edge 풀 정의**에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="204d4-269">**Edge 풀 FQDN 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-270">**Fqdn**에 Edge 풀의 내부 쪽에 대해 선택한 fqdn (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="204d4-271">풀에 대해 지정 하는 이름은 내부에 지 풀 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="204d4-272">이는 FQDN으로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="204d4-273">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="204d4-274">Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함)만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="204d4-275">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="204d4-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="204d4-276">FQDN의 비표준 문자는 외부 DNS 및 공용 Ca에서 지원 되지 않습니다 (FQDN을 인증서의 SN에 할당 해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="204d4-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="204d4-277">**여러 컴퓨터 풀**을 클릭 한 다음 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="204d4-278">**선택 기능** 에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="204d4-279">SIP 액세스 서비스, Lync Server 웹 회의 서비스 및 A/V Edge 서비스에 대 한 단일 FQDN 및 IP 주소를 사용 하려는 경우 **단일 fqdn & Ip 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="204d4-280">페더레이션을 사용 하려는 경우 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-281">이 옵션을 선택할 수 있지만 조직에서 페더레이션에 대해 외부에서 하나의 Edge 풀 또는 Edge 서버만 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="204d4-282">공용 인스턴트 메시징 (IM) 사용자를 비롯 한 페더레이션 사용자의 모든 액세스는 동일한 Edge 풀 또는 단일 Edge 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="204d4-283">예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="204d4-284">이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-285">배포에 대해 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜)를 지원 하려는 경우 **xmpp 페더레이션 사용 (포트 5269)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="204d4-286">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-286">Click **Next**.</span></span>

8.  <span data-ttu-id="204d4-287">**IP 옵션 선택**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-288">**내부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="204d4-289">**내부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="204d4-290">**외부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="204d4-291">**외부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="204d4-292"><STRONG>Edge 풀의 외부 IP 주소는 NAT에서 번역 됨</STRONG> 확인란을 선택 <STRONG>하지 마세요</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="204d4-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="204d4-293">하드웨어 부하 분산을 사용 하는 경우 NAT (Network address translation)가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="204d4-294">**외부 fqdn**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-295">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN 및 IP 주소를 사용 **하도록 선택한 경우** **sip ACCESS**에 외부 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-296">이 옵션을 선택 하는 경우 각 Edge services에 대해 다른 포트 번호를 지정 해야 합니다 (권장 포트 설정: 액세스에 지 서비스의 경우 5061, 웹 회의 Edge 서비스의 경우 444, A/V Edge 서비스의 경우 443).</span><span class="sxs-lookup"><span data-stu-id="204d4-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="204d4-297">이 옵션을 선택 하면 세 가지 서비스에 동일한 포트 번호 (예: 443)를 사용할 수 있기 때문에 잠재적인 연결 문제를 방지 하 고 구성을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="204d4-298">**선택한 기능** 에서 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우에는 **SIP 액세스**에서 edge 풀의 공용 측에 대해 선택한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="204d4-299">**웹 회의**에서 Edge 풀의 공용 측에 대해 선택한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="204d4-300">**오디오/비디오**에서 Edge 풀의 공용 측에 대해 선택한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="204d4-301">기본 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="204d4-302">이는 풀에 대해 공개적으로 연결 된 VIP (가상 IP) Fqdn입니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="204d4-303">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-303">Click **Next**.</span></span>

11. <span data-ttu-id="204d4-304">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="204d4-305">**외부 IP 주소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-306">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택한 경우 **Sip 액세스**에서 edge 서버의 외부 IPv4 주소를 입력 합니다. **Sip Access**의 edge 서버에 대 한 외부 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="204d4-307">SIP 액세스, 웹 회의 서비스 및 A/V 회의 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우 **Sip 액세스**를 위해이 Edge 풀 서버의 공용 측에 대해 선택한 ip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="204d4-308">**웹 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="204d4-309">**A/V 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="204d4-310">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-310">Click **Next**.</span></span>

14. <span data-ttu-id="204d4-311">IPv6 주소를 사용 하도록 선택한 경우 **외부 IP 주소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="204d4-312">SIP 액세스, 웹 회의 서비스 및 A/V Edge 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택한 경우 **Sip access**에 Edge 서버의 외부 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="204d4-313">SIP 액세스, 웹 회의 서비스 및 A/V 회의 서비스에 대해 단일 FQDN과 IP 주소를 사용 하도록 선택 하지 않은 경우 **Sip 액세스**를 위해이 Edge 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="204d4-314">**웹 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="204d4-315">**A/V 회의**에서이 Edge 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-316">IPv6 주소 지정을 사용 하도록 선택 하지 않은 경우에는이 대화 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="204d4-317">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-318">이제 풀에서 만든 첫 번째 Edge 서버가 <STRONG>이 풀의 컴퓨터 정의</STRONG> 대화 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="204d4-319">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭 한 다음 edge 풀에 추가 하려는 두 번째 edge 서버에 대해 11 ~ 14 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="204d4-320">11 ~ 14 단계를 반복한 후 다음을 클릭 하 **여이 풀의 컴퓨터 정의**에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-321">이 시점에서 풀에 있는 Edge 서버 두 개를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="204d4-322">**다음 홉 정의**의 **다음 홉 풀** 목록에서 내부 풀의 이름을 선택 합니다 (프런트 엔드 풀 또는 Standard Edition 풀이 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="204d4-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="204d4-323">또는 배포에 디렉터가 포함 된 경우에는 디렉터 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="204d4-324">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="204d4-325">**프런트 엔드 풀 연결**에서 지원 되는 외부 사용자와의 통신에이 edge 서버를 사용 하는 내부 풀의 이름을 선택 하 여 프런트 엔드 풀 및 스탠더드 버전 서버와 연결할 수 있는 하나 이상의 내부 풀을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="204d4-326">1 개의 부하 분산 된 Edge 풀 또는 단일 Edge 서버만 A/V 트래픽에 대 한 각 내부 풀에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="204d4-327">Edge 풀 또는 Edge 서버와 연결 된 내부 풀이 이미 있는 경우 내부 풀이 이미 Edge 풀 또는 Edge 서버에 연결 되어 있음을 나타내는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="204d4-328">다른 Edge 서버와 이미 연결 된 풀을 선택 하면 연결이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="204d4-329">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-329">Click **Finish**.</span></span>

21. <span data-ttu-id="204d4-330">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="204d4-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

