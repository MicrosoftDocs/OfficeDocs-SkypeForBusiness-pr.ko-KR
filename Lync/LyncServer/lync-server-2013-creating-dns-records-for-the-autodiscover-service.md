---
title: 'Lync Server 2013: 자동 검색 서비스용 DNS 레코드 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d91c67620a87fdd91a1755592175e8cf2964d259
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="10a0d-102">Lync Server 2013에서 자동 검색 서비스용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10a0d-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10a0d-103">_**마지막으로 수정한 주제:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="10a0d-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="10a0d-104">Lync 모바일 사용자는 자동 검색을 사용 하도록 설정 해야 하며, 일부는 DNS (Domain Name System) 레코드 만들기와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="10a0d-105">필요에 따라 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="10a0d-106">조직의 네트워크 내에서 연결 하는 모바일 사용자를 지 원하는 내부 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="10a0d-107">인터넷에서 연결 하는 모바일 사용자를 지 원하는 외부 또는 공용 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="10a0d-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="10a0d-108">그 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="10a0d-108">Why both?</span></span> <span data-ttu-id="10a0d-109">각 SIP 도메인에 대 한 내부 DNS 레코드와 외부 DNS 레코드를 모두 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="10a0d-110">사용자가 만드는 DNS 레코드는 (호스트) 레코드나 CNAME 레코드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="10a0d-111">이를 돕기 위해 아래에서 이러한 내부 및 외부 DNS 레코드를 만드는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="10a0d-112">모바일 사용자에 대 한 DNS 요구 사항에 대 한 추가 정보를 참조 해야 하는 경우 [Lync Server 2013에서 이동성에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="10a0d-113">내부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10a0d-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="10a0d-114">내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 이거나 DnsAdmins 그룹의 구성원 인 도메인 계정을 사용 하 여 네트워크에서 DNS 서버에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="10a0d-115">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 하 여 dns 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="10a0d-116">DNS 서버의 콘솔 트리에서 Lync Server 2013 디렉터 풀과 프런트 엔드 풀이 설치 된 Active Directory 도메인에 대해 **정방향 조회 영역** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="10a0d-117">(예: contoso.)</span><span class="sxs-lookup"><span data-stu-id="10a0d-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="10a0d-118">확인 및 참조 내부 DNS 레코드에 대 한 디렉터 풀에 대 한 호스트 A (AAAA for IPv6) 레코드가 있는지, 호스트 a 레코드가 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대해 존재 해야 합니다 (예: lyncwebdir01).</span><span class="sxs-lookup"><span data-stu-id="10a0d-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="10a0d-119">여기에 없는 경우에는 디렉터 풀을 사용 하지 않을 수 있으며, 사용자는 프런트 엔드 풀 또는 단일 서버 FQDN (설치 하는 경우)에 대 한 FQDN을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="10a0d-120">이 점에 유의 하 여, 내부 DNS 레코드에 대 한 프런트 엔드 풀에 대 한 호스트 A (AAAA for IPv6) 레코드가 있는지 확인 하 고 프런트 엔드 풀의 내부 웹 서비스 FQDN에 대 한 호스트 A (또는 AAAA) 레코드가 있어야 합니다 (예: , lyncwebpool01).</span><span class="sxs-lookup"><span data-stu-id="10a0d-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="10a0d-121">그렇지 않은 경우 프런트 엔드 서버 또는 Standard Edition 서버에 대 한 FQDN을 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="10a0d-122">DNS 서버의 콘솔 트리에서 호스트 A (또는 AAAA) 레코드가 존재 하는지 알고 있으면 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10a0d-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="10a0d-123">SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 **새 별칭 (CNAME)** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="10a0d-124">**별칭 이름**에 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="10a0d-125">**대상 호스트의 FQDN (정규화 된 도메인 이름)** 에서 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예: lyncwebdir01)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="10a0d-126">Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="10a0d-127">외부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10a0d-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="10a0d-128">외부 DNS CNAME 레코드를 만들려면 공용 DNS 공급자에 연결 하 고 나 서 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="10a0d-129">외부 DNS를 관리 하는 방법이 다를 수 있으므로 DNS 공급자의 환경에서 어디에서 진행 되는지 정확히 설명할 수는 없지만 이러한 단계를 수행 하는 데 도움이 되길 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="10a0d-130">해당 환경에서 DNS 레코드를 만들 수 있는 계정을 사용 하 여 외부 DNS 공급자에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="10a0d-131">이 환경에 대 한 SIP 도메인이 이미 생성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="10a0d-132">이 SIP 도메인의 **정방향 조회 영역** 을 확장 하거나, 사용 중인 외부 DNS 인터페이스에 따라이를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="10a0d-133">디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 호스트 A (IPv6의 AAAA) 레코드가 이미 표시 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="10a0d-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="10a0d-134">그렇지 않은 경우에는 디렉터 풀을 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="10a0d-135">이런 경우 프런트 엔드 풀의 FQDN을 사용 하거나, 프런트 엔드 서버 또는 Standard Edition 서버에 대해 단일 서버에 대해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="10a0d-136">또한 프런트 엔드 풀 (예: lyncwebextpool01.contoso.com)의 외부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A (AAAA for IPv6) 레코드가 있는지, 그리고 프런트 엔드 풀을가지고 있지 않은 경우 단일 서버 FQDN에 대 한 FQDN을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="10a0d-137">이전 단계에서 언급 한 것 처럼 디렉터 풀이 없는 경우 아래와 같이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="10a0d-138">이제 외부 DNS 공급자에 적합 한 형식으로 **새 별칭 (CNAME)** 을 만드는 옵션을 선택 합니다 (DNS 공급자의 형식에 따라 메뉴 옵션이 나 링크가 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="10a0d-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="10a0d-139">내부 DNS와 같은 몇 가지 형식의 **별칭 이름** 텍스트 상자를 사용 하는 경우 외부 자동 검색 서비스 URL에 대 한 호스트 이름으로 lyncdiscover를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="10a0d-140">또한 **대상 호스트의 fqdn (정규화 된 도메인 이름)** 입력란에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebexdir01.contoso.com)을 입력 하 고 확인을 클릭 하거나 외부 DNS에서 모든 작업을 수행 하 여이 항목의 생성을 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="10a0d-141">위의 4 단계에 명시 된 것 처럼, 디렉터 풀이 없는 경우에는 프런트 엔드 풀 FQDN 또는 설정한 단일 서버 FQDN (적절 한)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="10a0d-142">Lync 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="10a0d-143">내부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10a0d-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="10a0d-144">내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 이거나 DnsAdmins 그룹의 구성원 인 도메인 계정을 사용 하 여 네트워크의 DNS 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="10a0d-145">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 하 여 dns 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="10a0d-146">내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Lync Server 2013 디렉터 풀과 프런트 엔드 풀이 설치 되어 있는 Active Directory 도메인 (예: contoso)에 대해 **정방향 조회 영역** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="10a0d-147">확인 및 참조 내부 DNS 레코드에 대 한 디렉터 풀에 대 한 호스트 A (AAAA for IPv6) 레코드가 있는지, 호스트 a 레코드가 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대해 존재 해야 합니다 (예: lyncwebdir01).</span><span class="sxs-lookup"><span data-stu-id="10a0d-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="10a0d-148">여기에 없는 경우에는 디렉터 풀을 사용 하지 않을 수 있으며, 사용자는 프런트 엔드 풀의 IP 주소 또는 단일 서버 IP 주소를 사용 해야 합니다 (설정 된 경우).</span><span class="sxs-lookup"><span data-stu-id="10a0d-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="10a0d-149">이 점에 유의 하 여, 내부 DNS 레코드에 대 한 프런트 엔드 풀에 대 한 호스트 A (AAAA for IPv6) 레코드가 있는지 확인 하 고 프런트 엔드 풀의 내부 웹 서비스 FQDN에 대 한 호스트 A (또는 AAAA) 레코드가 있어야 합니다 (예: , lyncwebpool01).</span><span class="sxs-lookup"><span data-stu-id="10a0d-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="10a0d-150">그렇지 않으면 프런트 엔드 서버 또는 Standard Edition 서버에 대 한 IP 주소를 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="10a0d-151">DNS 서버의 콘솔 트리에서 호스트 A (또는 AAAA) 레코드가 존재 하는지 알고 있으면 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10a0d-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="10a0d-152">SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 **새 호스트 (A 또는 AAAA)** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="10a0d-153">**Name (이름**)에 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="10a0d-154">**IP 주소**에 디렉터의 내부 웹 서비스 IP 주소를 입력 하거나 (부하 분산 장치를 사용 하는 경우 디렉터 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.)</span><span class="sxs-lookup"><span data-stu-id="10a0d-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="10a0d-155">위의 4 단계에서 설명한 것 처럼 디렉터를 사용 하지 않는 경우에는 프런트 엔드 서버 또는 Standard Edition 서버의 IP 주소를 입력 하거나 부하 분산 장치를 사용 하는 경우 프런트 엔드 풀 부하 분산 장치의 VIP를 입력 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="10a0d-156">**호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="10a0d-157">추가 A 또는 AAAA 레코드를 만들려면 8 ~ 10 단계를 반복 하 여 Lync Server 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 또는 AAAA 레코드를 만들어야 한다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="10a0d-158">(IPv6, AAAA) 레코드 만들기를 마쳤으면 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="10a0d-159">외부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10a0d-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="10a0d-160">외부 DNS 레코드를 만들려면 공용 DNS 공급자에 연결 하 고 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="10a0d-161">외부 DNS를 관리 하는 방법이 다를 수 있으므로 DNS 공급자의 환경에서 어디에서 진행 되는지 정확히 설명할 수는 없지만 이러한 단계를 수행 하는 데 도움이 되길 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="10a0d-162">해당 환경에서 DNS 레코드를 만들 수 있는 계정으로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="10a0d-163">외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10a0d-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="10a0d-164">외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10a0d-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="10a0d-165">디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 호스트 A (ip for IPv6) 레코드가 이미 표시 되어 있는지 확인 하 고 IP 주소가이에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="10a0d-166">그렇지 않은 경우에는 디렉터 풀을 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="10a0d-167">그러한 경우 프런트 엔드 풀의 IP 주소를 사용 하거나, 프런트 엔드 서버 또는 Standard Edition 서버에서 단일 서버에 대해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="10a0d-168">서버는 부하 분산 장치 뒤에 있거나 역방향 프록시를 사용 하는 것일 수도 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="10a0d-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="10a0d-169">다음 단계에 따라 IP 주소를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="10a0d-170">또한 프런트 엔드 풀 (예: lyncwebextpool01.contoso.com)의 외부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A (ip for IPv6) 레코드가 있는지, 아니면 단일 서버 Lync 설치의 경우 IP 주소를 확인 해야 합니다. 프런트 엔드 풀이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="10a0d-171">이전 단계에서 언급 한 것 처럼 디렉터 풀이 없는 경우 아래와 같이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="10a0d-172">이제 외부 DNS 공급자에 적합 한 형식으로 **새 호스트 a 또는 AAAA** 를 만드는 옵션을 선택 합니다 (DNS 공급자의 형식에 따라 메뉴 옵션이 나 링크가 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="10a0d-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="10a0d-173">**이름을**입력 해야 하는 위치에 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="10a0d-174">또한 **Ip 주소** 입력란 (예: lyncwebexdir01.contoso.com)에 대 한 ip를 입력 하거나 풀의 로드 균형 조정기 (또는 동일한 작업을 수행 하는 역방향 프록시 ip)의 ip를 입력할 수 있습니다. 그런 다음 확인을 클릭 하거나 외부 DNS에서 해당 항목의 생성을 허용 하는 모든 조치를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="10a0d-175">위의 4 단계에 명시 된 것 처럼, 디렉터 풀이 없는 경우에는 설정 된 프런트 엔드 풀 IP 주소나 적절 하 게 설정한 단일 서버 IP 주소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="10a0d-176">Lync 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색을 만들거나 A 또는 AAAA 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a0d-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

