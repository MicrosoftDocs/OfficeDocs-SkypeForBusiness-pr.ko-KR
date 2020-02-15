---
title: 'Lync Server 2013: 자동 검색을 위한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f84e07deea6540370d8358683b474e14d767046
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d8b92-102">Lync Server 2013에서 자동 검색을 위한 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="d8b92-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8b92-103">_**마지막으로 수정 된 항목:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="d8b92-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="d8b92-104">Lync 클라이언트에 대해 자동 검색을 지원 하려면 다음 DNS (Domain Name System) 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="d8b92-105">조직 네트워크 내에서 연결 하는 Lync 클라이언트를 지원 하기 위한 내부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="d8b92-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="d8b92-106">인터넷에서 연결 하는 Lync 클라이언트를 지원 하기 위한 외부 또는 공용 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="d8b92-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="d8b92-107">각 SIP 도메인에 대해 내부 DNS 레코드 및 외부 DNS 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="d8b92-108">DNS 레코드는 추가 SAN (주체 대체 이름)을 사용 하 여 새 인증서를 만드는 기능을 기반으로 하는 (호스트) 레코드나 CNAME 레코드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="d8b92-109">Lyncdiscover를 사용 하 여 새 외부 (공개) 인증서를 요청 하 고 배포할 수 없는 경우 \<도메인 이름\> SAN에서는 HTTP/TCP 포트 80을 사용 하는 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="d8b92-110">다음 절차에서는 내부 및 외부 DNS 레코드를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="d8b92-111">DNS CNAME 레코드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d8b92-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="d8b92-112">다음과 같이 DNS 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="d8b92-113">내부 DNS 레코드를 만들려면 Domain Admins 그룹 또는 DnsAdmins 그룹의 구성원으로 네트워크의 DNS 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="d8b92-114">외부 DNS레코드를 만들려면 공용 DNS 공급자에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="d8b92-115">**시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="d8b92-116">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="d8b92-117">내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Active Directory 도메인(예: contoso.local)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d8b92-118">이 도메인은 Lync Server 2013&nbsp;디렉터 풀 및 프런트 엔드 풀이 설치 된 Active Directory 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="d8b92-119">외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="d8b92-120">디렉터 풀에 대 한 호스트 A 레코드가 다음과 같이 존재 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="d8b92-121">내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A 레코드가 있어야 합니다 (예:: lyncwebdir01.contoso.local).</span><span class="sxs-lookup"><span data-stu-id="d8b92-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="d8b92-122">외부 DNS 레코드의 경우에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextdir.contoso.com)에 대 한 호스트 A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="d8b92-123">프런트 엔드 풀에 대 한 호스트 A 레코드가 다음과 같이 존재 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="d8b92-124">내부 DNS 레코드의 경우 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대 한 호스트 A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="d8b92-125">외부 DNS 레코드의 경우 프런트 엔드 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextpool01.contoso.com)에 대해 호스트 A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="d8b92-126">내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8b92-127">외부 DNS 레코드를 만드는 경우에는 3단계에서 SIP 도메인에 대해 <STRONG>정방향 조회 영역</STRONG>이 이미 확장된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="d8b92-128">SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 별칭(CNAME)** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="d8b92-129">**별칭 이름**에 다음 중 하나를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="d8b92-130">내부 DNS 레코드의 경우 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="d8b92-131">외부 DNS 레코드의 경우 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="d8b92-132">**대상 호스트의 FQDN(정규화된 도메인 이름)** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="d8b92-133">내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncwebdir01.contoso.local)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="d8b92-134">외부 DNS 레코드의 경우에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextdir.contoso.com)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8b92-135">디렉터를 사용 하지 않는 경우 프런트 엔드 풀의 내부 및 외부 웹 서비스 FQDN을 사용 하거나 단일 서버에 대해 프런트 엔드 서버 또는 Standard Edition 서버의 FQDN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d8b92-136">Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="d8b92-137">DNS A 레코드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d8b92-137">To create DNS A records</span></span>

1.  <span data-ttu-id="d8b92-138">다음과 같이 DNS 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="d8b92-139">내부 DNS 레코드를 만들려면 Domain Admins 그룹 또는 DnsAdmins 그룹의 구성원으로 네트워크의 DNS 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="d8b92-140">외부 DNS 레코드를 만들려면 공용 DNS 공급자 또는 외부 DNS 서버에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="d8b92-141">**시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="d8b92-142">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="d8b92-143">내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Active Directory 도메인(예: contoso.local)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d8b92-144">이 도메인은 Lync Server 2013&nbsp;디렉터 풀 및 프런트 엔드 풀이 설치 된 Active Directory 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="d8b92-145">외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="d8b92-146">디렉터 풀에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="d8b92-147">내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncwebdir01.contoso.local)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="d8b92-148">외부 DNS 레코드의 경우에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextdir.contoso.com)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="d8b92-149">프런트 엔드 풀에 대해 호스트 A (i p v 6에 AAAA) 레코드가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="d8b92-150">내부 DNS 레코드의 경우 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="d8b92-151">외부 DNS 레코드의 경우 프런트 엔드 풀의 외부 웹 서비스 FQDN (예: lyncwebextpool01.contoso.com)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="d8b92-152">내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8b92-153">외부 DNS 레코드를 만드는 경우에는 3단계에서 SIP 도메인에 대해 <STRONG>정방향 조회 영역</STRONG>이 이미 확장된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="d8b92-154">SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 호스트(A 또는 AAAA)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="d8b92-155">**이름**에 호스트 이름을 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="d8b92-156">내부 DNS 레코드의 경우 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="d8b92-157">외부 DNS 레코드의 경우 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8b92-158">도메인 이름은 레코드가 정의된 영역에서 가져온 것으로 가정되므로 A 레코드의 일부로 입력할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="d8b92-159">**IP 주소**에 IP 주소를 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="d8b92-160">내부 DNS 레코드의 경우 디렉터의 내부 웹 서비스 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 디렉터 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d8b92-161">디렉터를 사용 하지 않는 경우에는 프런트 엔드 서버 또는 Standard Edition 서버의 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 프런트 엔드 풀 부하 분산 장치의 VIP를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="d8b92-162">외부 DNS 레코드의 경우 역방향 프록시의 외부(공용) IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="d8b92-163">**호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="d8b92-164">A 레코드를 추가로 만들려면 8-10단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d8b92-165">Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에 새 llyncdiscoverinternal cdiscover 및 A 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="d8b92-166">A(IPv6의 경우 AAAA) 레코드를 모두 만든 후에 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b92-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

