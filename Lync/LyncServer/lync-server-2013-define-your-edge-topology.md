---
title: Lync Server 2013:에 지 토폴로지 정의
description: Lync Server 2013:에 지 토폴로지를 정의 합니다.
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
ms.openlocfilehash: bd4aa16ca23d24f0edd92189216030ef926fc841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572944"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="7a541-103">Lync Server 2013에서에 지 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="7a541-103">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a541-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7a541-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7a541-105">토폴로지를 작성 하려면 토폴로지 작성기를 사용 해야 하며,에 지 서버를 배포 하려면 먼저 하나 이상의 내부 프런트 엔드 풀 또는 Standard Edition server를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-105">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="7a541-106">다음 절차에 따라 단일에 지 서버에 대 한에 지 토폴로지를 정의한 다음 [Lync server 2013 2013에서 토폴로지 게시](lync-server-2013-publish-your-topology.md) 의 절차를 수행 하 고, [edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 하 여에 지 서버에서 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-106">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a541-p102">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="7a541-109">서버 역할을 추가하거나 제거할 때 토폴로지를 성공적으로 게시하거나 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹 구성원인 사용자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-109">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="7a541-110">또한 사용자에게 서버 역할을 추가하기 위해 필요한 권한을 관리자에게 부여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-110">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="7a541-111">자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서에서 [Lync Server 2013의 대리인 설치 권한](lync-server-2013-delegate-setup-permissions.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="7a541-112">기타 구성을 변경하려는 경우에는 RTCUniversalServerAdmins 그룹 구성원 자격만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-112">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="7a541-113">내부 토폴로지를 정의 및 게시할 때 에지 토폴로지를 정의한 경우 이전에 정의한 에지 토폴로지를 변경할 필요가 없으면 토폴로지를 다시 정의하고 게시하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-113">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="7a541-114">에지 토폴로지를 변경해야 하는 경우에만 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-114">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="7a541-115">Lync Server 2013 토폴로지 내보내기의 절차를 사용 하 여에 지 서버에서 이전에 정의 및 게시 된 토폴로지를 사용 하도록 설정 하 [고 edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-115">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7a541-116">에 지 서버에서 토폴로지 작성기를 실행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-116">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="7a541-117">프런트 엔드 서버 또는 Standard Edition 서버에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-117">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="7a541-118">에 지 서버 토폴로지를 정의 하는 프로세스는 토폴로지 작성기에서 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-118">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="7a541-119">계획 및 구성해야 하는 세 가지 기본 에지 서버 토폴로지 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-119">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="7a541-120">단일 에지 서버에 대한 토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7a541-120">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="7a541-121">부하 분산된 에지 서버 풀에 대한 토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7a541-121">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="7a541-122">하드웨어 부하 분산 에지 풀에 대한 토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7a541-122">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="7a541-123">단일 에지 서버에 대한 토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7a541-123">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="7a541-124">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-124">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7a541-125">콘솔 트리에서 에지 서버를 배포할 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-125">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="7a541-126">에 **지 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새에 지 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-126">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="7a541-127">**새 에지 풀 정의**에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-127">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="7a541-128">**에지 풀 FQDN 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-128">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-129">**풀 FQDN**에 에지 서버 내부 인터페이스의 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-129">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a541-130">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-130">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="7a541-131">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-131">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="7a541-132">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-132">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7a541-133">따라서 도메인이 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-133">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7a541-134">Lync Server, 에지 서버 및 풀의 FQDN을 지정할 때는 표준 문자(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-134">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="7a541-135">유니코드 문자나 밑줄은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-135">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7a541-136">FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="7a541-136">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="7a541-137">컴퓨터 이름에 DNS 접미사를 추가 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013에서 dns에 지 지원에 대 한 구성</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-137">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-138">**단일 컴퓨터 풀**을 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-138">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="7a541-139">**기능 선택**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-139">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-140">SIP 액세스 서비스, Lync Server 2013 웹 회의 서비스 및 A/V에 지 서비스에 대해 단일 FQDN 및 IP 주소를 사용 하려는 경우에는 **단일 fqdn 및 Ip 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-140">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="7a541-141">페더레이션을 사용하도록 설정하려면 **이 에지 풀에 대해 페더레이션 사용(포트 5061)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-141">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-p108">이 옵션을 선택할 수 있지만 페더레이션을 위해서는 조직의 에지 풀 또는 에지 서버 하나만 외부에 게시할 수 있습니다. 공용 IM(인스턴트 메시징) 사용자를 포함하여 페더레이션 사용자의 모든 액세스는 같은 에지 풀 또는 단일 에지 서버를 통해 전송됩니다. 예를 들어 배포에 각각 뉴욕과 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에 대한 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통해 전송됩니다. 이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-146">배포에서 XMPP(Extensible Messaging and Presence Protocol)를 지원하려면 **XMPP 페더레이션 사용(포트 5269)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-146">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="7a541-147">**IP 옵션 선택**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-147">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-148">**내부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-148">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="7a541-149">**내부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-149">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="7a541-150">**외부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-150">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="7a541-151">**외부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-151">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="7a541-152">외부 IP 주소에 대 한 네트워크 주소 변환 주소를 사용 하도록에 지 서버 또는에 지 풀을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-152">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="7a541-153">확인란을 선택 하 여이 작업을 수행 하는 경우이에 **지 풀의 외부 IP 주소가 NAT에 의해 변환 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="7a541-153">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="7a541-154">**외부 FQDN**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-154">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-155">**기능 선택**에서 SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 대해 단일 FQDN 및 IP 주소를 사용하기로 선택한 경우 **SIP 액세스**에 외부 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-155">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-p110">이 옵션을 선택한 경우 각 에지 서비스에 대해 서로 다른 포트 번호를 지정해야 합니다(권장 포트 설정: 액세스 에지 서비스의 경우 5061, 웹 회의 에지 서비스의 경우 444, A/V 에지 서비스의 경우 443). 이 옵션을 선택하면 나중에 세 서비스 모두에 같은 포트 번호(예: 443)를 사용할 수 있으므로 잠재적 연결 문제를 방지하고 구성을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-158">**기능 선택**에서 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 기본 포트를 유지한 상태로 **SIP 액세스**, **웹 회의** 및 **오디오 비디오**에 대한 외부 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-158">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="7a541-159">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-159">Click **Next**.</span></span>

10. <span data-ttu-id="7a541-p111">**내부 IP 주소 정의**에서 **내부 IPv4 주소** 및 **내부 IPv6 주소**에 요구 사항에 따라 에지 서버의 IP 주소를 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="7a541-162">**외부 IP 주소 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-162">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-163">SIP 주소, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택한 경우 **SIP 액세스**에 에지 서버의 외부 IPv4 주소를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-163">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="7a541-164">IPv6 주소를 사용하도록 선택한 경우 **SIP 액세스**에 에지 서버의 외부 IPv6 주소를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-164">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="7a541-165">SIP 주소, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**, **웹 회의** 및 **A/V 회의**에 에지 서버의 외부 IPv4 주소를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-165">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="7a541-166">IPv6 주소를 사용하도록 선택하고 SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 대해 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**, **웹 회의** 및 **A/V 회의**에 에지 서버의 외부 IPv6 주소를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-166">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-167">IPv6 주소 지정을 사용 및 지정하도록 선택하지 않았으면 이 대화 상자가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-167">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="7a541-p112">NAT를 사용하도록 선택한 경우 대화 상자가 나타납니다. **A/V 에지 서비스의 공용 IPv4 주소**에 NAT로 변환할 공용 IPv4 주소를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-170">이 주소는 A/V 에지 서비스의 외부 IP 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-170">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="7a541-p113">NAT 및 IPv6 주소를 사용하도록 선택한 경우 대화 상자가 나타납니다. **A/V 에지 서비스의 공용 IPv6 주소**에 NAT로 변환할 공용 IPv6 주소를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-173">이 주소는 A/V 에지 서비스의 외부 IP 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-173">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="7a541-p114">**다음 홉 정의**의 **다음 홉 풀** 목록에서 프런트 엔드 풀 또는 Standard Edition 풀로 사용할 내부 풀의 이름을 선택합니다. 또는 배포에 디렉터가 포함된 경우 디렉터를 선택합니다. 그런 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="7a541-177">**프런트 엔드 풀 연결**에서 이 에지 서버를 사용하여 지원되는 외부 사용자와 통신할 내부 풀 이름을 선택하여 이 에지 서버와 연결할 하나 이상의 내부 풀을 지정합니다. 여기에는 프런트 엔드 풀 및 Standard Edition 서버가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-177">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-p115">A/V 트래픽에 대해 하나의 부하 분산 에지 풀 또는 단일 에지 서버만 각 내부 풀과 연결할 수 있습니다. 에지 서버 또는 에지 서버와 연결된 내부 풀이 이미 있는 경우 내부 풀이 에지 풀 또는 에지 서버와 이미 연결되었음을 나타내는 경고가 표시됩니다. 다른 에지 서버와 이미 연결되어 있는 풀을 선택하는 경우 해당 연결이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="7a541-181">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-181">Click **Finish**.</span></span>

17. <span data-ttu-id="7a541-182">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-182">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="7a541-183">DNS 부하 분산 에지 서버 풀에 대한 토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7a541-183">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="7a541-184">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-184">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7a541-185">콘솔 트리에서 에지 서버를 배포할 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-185">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="7a541-186">**에지 풀**을 마우스 오른쪽 단추로 클릭한 다음 **새 에지 풀**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-186">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="7a541-187">**새 에지 풀 정의**에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-187">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="7a541-188">**에지 풀 FQDN 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-188">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-189">**풀 FQDN**에 에지 풀의 내부 연결에 대한 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-189">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a541-190">풀에 대해 지정하는 이름은 내부 에지 풀 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-190">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="7a541-191">이 이름은 FQDN으로 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-191">This must be defined as a FQDN.</span></span> <span data-ttu-id="7a541-192">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-192">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7a541-193">Lync Server, 에지 서버 및 풀의 FQDN을 지정할 때는 표준 문자(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-193">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="7a541-194">유니코드 문자나 밑줄은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-194">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7a541-195">FQDN에서 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(FQDN을 인증서의 SN에 지정해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="7a541-195">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-196">**다중 컴퓨터 풀**을 클릭한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-196">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="7a541-197">**기능 선택**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-197">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-198">SIP 액세스, Lync Server 2013 웹 회의 서비스 및 A/V에 지 서비스에 대해 단일 FQDN 및 IP 주소를 사용 하려는 경우에는 **단일 fqdn 및 Ip 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-198">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="7a541-p117">페더레이션을 사용하도록 설정하려면 **이 에지 풀에 대해 페더레이션 사용(포트 5061)** 확인란을 선택합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-p118">이 옵션을 선택할 수는 있지만, 조직의 에지 풀 또는 에지 서버는 하나만 외부에 페더레이션용으로 게시할 수 있습니다. 공용 IM(인스턴트 메시징) 사용자를 비롯한 페더레이션 사용자의 모든 액세스는 같은 에지 풀 또는 단일 에지 서버를 통해 전송됩니다. 예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다. 런던 페더레이션 사용자를 호출하는 런던 내부 사용자의 경우에는 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만, 런던 사용자와의 통신에도 이러한 방식이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-205">배포에서 XMPP(Extensible Messaging and Presence Protocol)를 지원하려면 **XMPP 페더레이션 사용(포트 5269)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-205">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="7a541-206">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-206">Click **Next**.</span></span>

8.  <span data-ttu-id="7a541-207">**IP 옵션 선택**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-207">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-208">**내부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-208">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="7a541-209">**내부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-209">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="7a541-210">**외부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-210">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="7a541-211">**외부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-211">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="7a541-212">외부 IP 주소에 대 한 네트워크 주소 변환 주소를 사용 하도록에 지 서버 또는에 지 풀을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-212">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="7a541-213">확인란을 선택 하 여이 작업을 수행 하는 경우이에 **지 풀의 외부 IP 주소가 NAT에 의해 변환 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="7a541-213">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="7a541-214">**외부 FQDN**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-214">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-215">**기능 선택**에서 SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 대해 단일 FQDN 및 IP 주소를 사용하기로 선택한 경우 **SIP 액세스**에 외부 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-215">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-p120">이 옵션을 선택한 경우 각 에지 서비스에 대해 서로 다른 포트 번호를 지정해야 합니다(권장 포트 설정: 액세스 에지 서비스의 경우 5061, 웹 회의 에지 서비스의 경우 444, A/V 에지 서비스의 경우 443). 이 옵션을 선택하면 나중에 세 서비스 모두에 같은 포트 번호(예: 443)를 사용할 수 있으므로 잠재적 연결 문제를 방지하고 구성을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-p121">**기능 선택**에서 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**에 에지 풀의 공용 측에 대해 선택한 FQDN을 입력합니다. **웹 회의**에 에지 풀의 공용 측에 대해 선택한 FQDN을 입력합니다. **오디오/비디오**에 에지 풀의 공용 측에 대해 선택한 FQDN을 입력합니다. 기본 포트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="7a541-222">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-222">Click **Next**.</span></span>

11. <span data-ttu-id="7a541-223">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-223">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="7a541-224">**내부 FQDN 및 IP 주소**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-224">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-225">이 풀에 만들려는 첫 번째 에지 서버의 요구 사항에 따라 **내부 IPv4 주소** 및 **내부 IPv6 주소**에 IPv4 또는 IPv6 주소를 적절하게 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-225">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="7a541-226">**내부 FQDN**에 이 풀에 만들려는 첫 번째 에지 서버의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-226">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-227">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-227">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="7a541-228">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-228">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="7a541-229">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-229">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7a541-230">따라서 도메인이 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-230">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7a541-231">Lync Server, 에지 서버, 풀 및 배열의 FQDN을 지정할 때는 표준 문자(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-231">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="7a541-232">유니코드 문자나 밑줄은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-232">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7a541-233">FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="7a541-233">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="7a541-234">컴퓨터 이름에 DNS 접미사를 추가 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013에서 dns에 지 지원에 대 한 구성</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-234">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="7a541-235">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-235">Click **Next**.</span></span>

14. <span data-ttu-id="7a541-236">**외부 IP 주소 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-236">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-237">SIP 주소, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택한 경우 **SIP 액세스**에 에지 서버의 외부 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-237">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="7a541-p123">SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**에 이 에지 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력합니다. **웹 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력합니다. **A/V 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="7a541-241">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-241">Click **Next**.</span></span>

16. <span data-ttu-id="7a541-242">IPv6 주소를 사용하도록 선택한 경우, **외부 IP 주소 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-242">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-243">SIP 주소, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택한 경우 **SIP 액세스**에 에지 서버의 외부 IPv6 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-243">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="7a541-p124">SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**에 이 에지 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력합니다. **웹 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력합니다. **A/V 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-247">IPv6 주소 지정을 사용 및 지정하도록 선택하지 않았으면 이 대화 상자가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-247">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="7a541-248">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-248">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-249">이제 풀에 만든 첫 번째 에지 서버가 <STRONG>이 풀의 컴퓨터 정의</STRONG> 대화 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-249">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="7a541-250">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭한 다음 에지 풀에 추가할 두 번째 에지 서버에 대해 11~14단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-250">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="7a541-251">11~14단계를 반복한 후 **이 풀의 컴퓨터 정의**에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-251">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-252">이제 풀의 두 에지 서버가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-252">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="7a541-p125">NAT를 사용하도록 선택한 경우 대화 상자가 표시됩니다. **공용 IP 주소**에 NAT를 통해 변환할 공용 IPv4 및 IPv6 주소를 적절하게 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-255">이 주소는 A/V 에지의 외부 IP 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-255">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="7a541-p126">**다음 홉 정의**의 **다음 홉 풀** 목록에서 프런트 엔드 풀 또는 Standard Edition 풀로 사용할 내부 풀의 이름을 선택합니다. 또는 배포에 디렉터가 포함된 경우 디렉터 이름을 선택합니다. 그런 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="7a541-259">**프런트 엔드 풀 연결**에서 이 에지 서버를 사용하여 지원되는 외부 사용자와 통신할 내부 풀 이름을 선택하여 이 에지 서버와 연결할 하나 이상의 내부 풀을 지정합니다. 여기에는 프런트 엔드 풀 및 Standard Edition Server가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-259">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-p127">A/V 트래픽에 대해 하나의 부하 분산 에지 풀 또는 단일 에지 서버만 각 내부 풀과 연결할 수 있습니다. 에지 풀 또는 에지 서버와 연결된 내부 풀이 이미 있는 경우 내부 풀이 에지 풀 또는 에지 서버와 이미 연결되었음을 나타내는 경고가 표시됩니다. 다른 에지 서버와 이미 연결되어 있는 풀을 선택하는 경우 해당 연결이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="7a541-263">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-263">Click **Finish**.</span></span>

24. <span data-ttu-id="7a541-264">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-264">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="7a541-265">하드웨어 부하 분산 에지 서버 풀에 대한 토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7a541-265">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="7a541-266">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-266">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7a541-267">콘솔 트리에서 에지 서버를 배포할 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-267">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="7a541-268">에 **지 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새에 지 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-268">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="7a541-269">**새 에지 풀 정의**에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-269">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="7a541-270">**에지 풀 FQDN 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-270">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-271">**FQDN**에 에지 풀의 내부 쪽에 대해 선택한 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-271">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a541-272">풀에 대해 지정하는 이름은 내부 에지 풀 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-272">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="7a541-273">이 이름은 FQDN으로 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-273">This must be defined as a FQDN.</span></span> <span data-ttu-id="7a541-274">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-274">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7a541-275">Lync Server, 에지 서버 및 풀의 FQDN을 지정할 때는 표준 문자(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-275">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="7a541-276">유니코드 문자나 밑줄은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7a541-276">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7a541-277">FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="7a541-277">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="7a541-278">**다중 컴퓨터 풀**을 클릭 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-278">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="7a541-279">**기능 선택**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-279">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="7a541-280">SIP 액세스 서비스, Lync Server 웹 회의 서비스 및 A/V에 지 서비스에 대해 단일 FQDN 및 IP 주소를 사용 하려는 경우에는 **단일 fqdn & Ip 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-280">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="7a541-281">페더레이션을 사용하도록 설정하려면 **이 에지 풀에 페더레이션 사용(포트 5061)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-281">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-p129">이 옵션을 선택할 수 있지만 페더레이션을 위해서는 조직의 에지 풀 또는 에지 서버 하나만 외부에 게시할 수 있습니다. 공용 IM(인스턴트 메시징) 사용자를 포함하여 페더레이션 사용자의 모든 액세스는 같은 에지 풀 또는 단일 에지 서버를 통해 전송됩니다. 예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다. 이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-286">배포에서 XMPP(Extensible Messaging and Presence Protocol)를 지원하려면 **XMPP 페더레이션 사용(포트 5269)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-286">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="7a541-287">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-287">Click **Next**.</span></span>

8.  <span data-ttu-id="7a541-288">**IP 옵션 선택**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-288">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-289">**내부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-289">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="7a541-290">**내부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-290">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="7a541-291">**외부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-291">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="7a541-292">**외부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-292">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a541-p130"><STRONG>에지 풀의 외부 IP 주소가 NAT에 의해 변환됨</STRONG> 확인란은 선택하지 <STRONG>마십시오</STRONG>. 하드웨어 부하 분산을 사용하는 경우에는 NAT(Network Address Translation)가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="7a541-295">**외부 FQDN**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-295">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-296">**기능 선택**에서 SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 대해 단일 FQDN 및 IP 주소를 사용하기로 선택한 경우 **SIP 액세스**에 외부 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-296">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-p131">이 옵션을 선택한 경우 각 에지 서비스에 대해 서로 다른 포트 번호를 지정해야 합니다(권장 포트 설정: 액세스 에지 서비스의 경우 5061, 웹 회의 에지 서비스의 경우 444, A/V 에지 서비스의 경우 443). 이 옵션을 선택하면 나중에 세 서비스 모두에 같은 포트 번호(예: 443)를 사용할 수 있으므로 잠재적 연결 문제를 방지하고 구성을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a541-p132">**기능 선택**에서 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**에 에지 풀의 공용 측에 대해 선택한 FQDN을 입력합니다. **웹 회의**에 에지 풀의 공용 측에 대해 선택한 FQDN을 입력합니다. **오디오/비디오**에 에지 풀의 공용 측에 대해 선택한 FQDN을 입력합니다. 기본 포트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a541-303">이러한 FQDN은 풀의 공용 측 VIP(가상 IP)입니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-303">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="7a541-304">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-304">Click **Next**.</span></span>

11. <span data-ttu-id="7a541-305">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-305">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="7a541-306">**외부 IP 주소 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-306">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-307">SIP 주소, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택한 경우 **SIP 액세스**에 에지 서버의 외부 IPv4 주소를 입력합니다. **SIP 액세스**에 에지 서버의 외부 IP 주소를 입력한 후 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-307">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="7a541-p133">SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**에 이 에지 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력합니다. **웹 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력합니다. **A/V 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="7a541-311">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-311">Click **Next**.</span></span>

14. <span data-ttu-id="7a541-312">IPv6 주소를 사용하도록 선택한 경우, **외부 IP 주소 정의**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-312">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="7a541-313">SIP 주소, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택한 경우 **SIP 액세스**에 에지 서버의 외부 IPv6 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-313">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="7a541-p134">SIP 액세스, 웹 회의 서비스 및 A/V 에지 서비스에 단일 FQDN 및 IP 주소를 사용하도록 선택하지 않은 경우 **SIP 액세스**에 이 에지 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력합니다. **웹 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력합니다. **A/V 회의**에 이 에지 풀 서버의 공용 측에 대해 선택한 IPv6 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-317">IPv6 주소 지정을 사용 및 지정하도록 선택하지 않았으면 이 대화 상자가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-317">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="7a541-318">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-318">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-319">이제 풀에 만든 첫 번째 에지 서버가 <STRONG>이 풀의 컴퓨터 정의</STRONG> 대화 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-319">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="7a541-320">**이 풀의 컴퓨터 정의**에서 **추가**를 클릭한 다음 에지 풀에 추가할 두 번째 에지 서버에 대해 11~14단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-320">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="7a541-321">11~14단계를 반복한 후 **이 풀의 컴퓨터 정의**에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-321">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-322">이제 풀의 두 에지 서버가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-322">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="7a541-p135">**다음 홉 정의**의 **다음 홉 풀** 목록에서 프런트 엔드 풀 또는 Standard Edition 풀로 사용할 내부 풀의 이름을 선택합니다. 또는 배포에 디렉터가 포함된 경우 디렉터 이름을 선택합니다. 그런 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="7a541-326">**프런트 엔드 풀 연결**에서 이 에지 서버를 사용하여 지원되는 외부 사용자와 통신할 내부 풀 이름을 선택하여 이 에지 서버와 연결할 하나 이상의 내부 풀을 지정합니다. 여기에는 프런트 엔드 풀 및 Standard Edition Server가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-326">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a541-p136">A/V 트래픽에 대해 하나의 부하 분산 에지 풀 또는 단일 에지 서버만 각 내부 풀과 연결할 수 있습니다. 에지 풀 또는 에지 서버와 연결된 내부 풀이 이미 있는 경우 내부 풀이 에지 풀 또는 에지 서버와 이미 연결되었음을 나타내는 경고가 표시됩니다. 다른 에지 서버와 이미 연결되어 있는 풀을 선택하는 경우 해당 연결이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="7a541-330">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-330">Click **Finish**.</span></span>

21. <span data-ttu-id="7a541-331">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7a541-331">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

