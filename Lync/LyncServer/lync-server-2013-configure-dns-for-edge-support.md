---
title: 'Lync Server 2013: 에지 지원에 대한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="4fad9-102">Lync Server 2013에서 에지 지원에 대한 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="4fad9-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fad9-103">_**마지막으로 수정한 주제:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="4fad9-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="4fad9-104">Edge 서버와 리버스 프록시 인터페이스를 모두 포함 하 여 내부 및 외부에 지 인터페이스에 대해 DNS (Domain Name System) 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="4fad9-105">기본적으로 Edge 서버는 도메인에 가입 되어 있지 않으며 정규화 된 도메인 이름 (정식 도메인 이름)이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="4fad9-106">Edge 서버는 정규화 된 도메인 이름이 아닌 짧은 (컴퓨터) 이름 으로만 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="4fad9-107">그러나 토폴로지 작성기는 약식 이름이 아닌 Fqdn을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="4fad9-108">Edge 서버의 이름은 토폴로지 작성기에 사용 되는 FQDN과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="4fad9-109">이렇게 하려면 컴퓨터 이름과 결합 하 여 FQDN이 예상 되는 DNS 접미사를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="4fad9-110">"Dns 접미사를 컴퓨터 이름에 추가 하 고 도메인에 참가 하지 않은에 지 서버"에 있는 다음 절차를 사용 하 여 컴퓨터 이름에 DNS 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fad9-111">기본적으로 DNS는 라운드 로빈 알고리즘을 사용 하 여 쿼리 된 DNS 도메인 이름에 대해 동일한 형식의 여러 리소스 레코드가 있는 리소스 레코드 데이터의 순서를 쿼리 응답으로 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="4fad9-112">Lync Server 2013 DNS 부하 분산은 dns 부하 분산 메커니즘의 일부로 서 DNS 라운드 로빈에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="4fad9-113">라운드 로빈 설정이 비활성화 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="4fad9-114">Windows 운영 체제를 실행 하 고 있지 않은 DNS 서버를 사용 하는 경우 라운드 로빈 리소스 레코드 순서가 활성화 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="4fad9-115">"**DNS srv 레코드 만들기**"에서 다음 절차를 사용 하 여 각 DNS SRV 레코드를 만들고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="4fad9-116">"**Dns a 레코드를 만들려면**"의 절차를 사용 하 여 외부 사용자 액세스에 필요한 DNS 레코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="4fad9-117">레코드가 구성 되 고 제대로 작동 하는지 확인 하려면이 항목의 "**DNS 레코드를 확인 하려면**"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fad9-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="4fad9-118">외부 사용자 액세스를 지 원하는 데 필요한 각 레코드에 대 한 자세한 내용은 [Lync Server 2013의 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fad9-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="4fad9-119">도메인에 가입 되어 있지 않은 Edge 서버의 컴퓨터 이름에 DNS 접미사를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="4fad9-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="4fad9-120">컴퓨터에서 **시작**을 클릭 하 고 **컴퓨터**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="4fad9-121">**컴퓨터 이름, 도메인 및 작업 그룹 설정**에서 **설정 변경을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="4fad9-122">**컴퓨터 이름** 탭에서 **변경을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="4fad9-123">**컴퓨터 이름/도메인 변경**에서 **자세히**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="4fad9-124">**DNS 접미사 및 NetBIOS 컴퓨터 이름**에 **이 컴퓨터의 주 DNS 접미사**에 내부 도메인의 이름 (예: corp.contoso.com)을 입력 한 다음 **확인** 을 세 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="4fad9-125">컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="4fad9-126">DNS SRV 레코드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4fad9-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="4fad9-127">적절 한 DNS 서버에서 **시작**을 클릭 하 고 **제어판**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **DNS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4fad9-128">원격 사용자 및 페더레이션 파트너가 외부 DNS 조회에 대 한 외부 DNS 항목에 대 한 DNS를 구성 해야 합니다 (1). 2) 주변 네트워크 (DMZ, 완충 존, 스크린 된 서브넷이 라고도 함) 내의 Edge 서버에서 사용할 DNS 조회에 대 한 항목을 포함 하 여 Lync Server 2013을 실행 하는 내부 서버의 레코드 3) 내부 클라이언트 및 Lync Server 2013를 실행 하는 서버에서 조회 하는 데 사용할 내부 DNS 항목</span><span class="sxs-lookup"><span data-stu-id="4fad9-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="4fad9-129">SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013이 설치 되어 있는 도메인을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="4fad9-130">**다른 새 레코드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="4fad9-131">**리소스 레코드 종류 선택**에서 **서비스 위치 (SRV)** 를 입력 한 다음 **레코드 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="4fad9-132">DNS SRV 레코드에 대해 필요한 모든 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="4fad9-133">DNS A 레코드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4fad9-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="4fad9-134">DNS 서버에서 **시작**을 클릭 하 고 **제어판**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **DNS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4fad9-135">SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013이 설치 되어 있는 도메인을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="4fad9-136">**새 호스트 (A)** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="4fad9-137">DNS SRV 레코드에 대해 필요한 모든 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="4fad9-138">DNS 레코드를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="4fad9-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="4fad9-139">도메인의 클라이언트 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="4fad9-140">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="4fad9-141">명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="4fad9-142">FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad9-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fad9-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fad9-143">See Also</span></span>


[<span data-ttu-id="4fad9-144">호스트되는 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="4fad9-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="4fad9-145">Lync Server 2013에 대한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="4fad9-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

