---
title: 'Lync Server 2013: 자동 검색 서비스에 대 한 DNS 레코드 만들기'
description: 'Lync Server 2013: 자동 검색 서비스에 대 한 DNS 레코드를 만듭니다.'
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
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563104"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="58433-103">Lync Server 2013의 자동 검색 서비스에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="58433-103">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58433-104">_**마지막으로 수정 된 항목:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="58433-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="58433-105">Lync Mobile 사용자는 자동 검색을 사용 하도록 설정 하 고 일부는 DNS (Domain Name System) 레코드를 만드는 과정을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-105">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="58433-106">필요에 따라 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-106">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="58433-107">조직의 네트워크 내에서 연결 하는 모바일 사용자를 지원 하기 위한 내부 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="58433-107">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="58433-108">인터넷에서 연결 하는 모바일 사용자를 지원 하기 위한 외부 또는 공용 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="58433-108">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="58433-109">두 가지 이유</span><span class="sxs-lookup"><span data-stu-id="58433-109">Why both?</span></span> <span data-ttu-id="58433-110">각 SIP 도메인에 대해 내부 DNS 레코드 및 외부 DNS 레코드를 모두 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-110">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="58433-111">만드는 DNS 레코드는 (호스트) 레코드나 CNAME 레코드 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-111">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="58433-112">이를 위해 아래에서 이러한 내부 및 외부 DNS 레코드를 만드는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-112">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="58433-113">모바일 사용자의 DNS 요구 사항에 대 한 추가 정보를 확인 해야 하는 경우 [Lync Server 2013에서 모바일 기능에 대 한 기술적 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-113">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="58433-114">내부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="58433-114">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="58433-115">내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 이거나 DnsAdmins 그룹의 구성원 인 도메인 계정을 사용 하 여 네트워크의 DNS 서버에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-115">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="58433-116">**시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="58433-116">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="58433-117">DNS 서버의 콘솔 트리에서 Lync Server 2013 디렉터 풀 및 프런트 엔드 풀이 설치 된 Active Directory 도메인의 **정방향 조회 영역** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-117">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="58433-118">(예: contoso. 로컬)</span><span class="sxs-lookup"><span data-stu-id="58433-118">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="58433-119">확인 및 내부 DNS 레코드에 대 한 디렉터 풀에 대 한 호스트 A (AAAA for i p a p) 레코드가 있는 경우 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A 레코드가 있어야 합니다 (예:: lyncwebdir01.contoso.local).</span><span class="sxs-lookup"><span data-stu-id="58433-119">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="58433-120">여기에 없는 경우 디렉터 풀을 사용 하지 않고 프런트 엔드 풀 또는 단일 서버 FQDN (설치 인 경우)에 FQDN을 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-120">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="58433-121">이 점에 유의 하 고, 내부 DNS 레코드에 대 한 프런트 엔드 풀에 대해 호스트 a (AAAA for IPv6) 레코드가 있는지 확인 한 후 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대해 호스트 A (또는 AAAA) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-121">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="58433-122">그렇지 않은 경우에는 프런트 엔드 서버 또는 Standard Edition Server에 대 한 FQDN을 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-122">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="58433-123">호스트 A (또는 AAAA) 레코드가 있는지 확인 한 다음 DNS 서버의 콘솔 트리에서 SIP 도메인 (예: contoso.com)에 대 한 **정방향 조회 영역** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-123">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="58433-124">SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 별칭(CNAME)** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-124">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="58433-125">**별칭 이름**에 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-125">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="58433-126">**대상 호스트의 FQDN (정규화 된 도메인 이름)** 에서 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncwebdir01.contoso.local)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-126">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="58433-127">Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-127">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="58433-128">외부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="58433-128">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="58433-129">외부 DNS CNAME 레코드를 만들려면 공용 DNS 공급자에 연결 하 고 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-129">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="58433-130">외부 DNS를 관리 하는 방법에는 여러 가지가 있을 수 있으므로 DNS 공급자 환경에서 어떤 위치를 정확히 설명할 수는 없지만, 이러한 단계를 도움이 되길 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="58433-130">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="58433-131">해당 환경에서 DNS 레코드를 만들 수 있는 계정을 사용 하 여 외부 DNS 공급자에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-131">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="58433-132">이 환경에 대 한 SIP 도메인이 이미 만들어져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-132">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="58433-133">이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나 사용 중인 외부 DNS 인터페이스에 따라이를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-133">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="58433-134">디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 호스트 A (AAAA for IPv6) 레코드가 이미 표시 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-134">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="58433-135">그렇지 않은 경우에는 디렉터 풀을 사용 하지 않는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-135">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="58433-136">이 경우 프런트 엔드 풀의 FQDN을 사용 하거나, Front-End 서버 또는 Standard Edition server에 대 한 단일 서버에 대해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-136">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="58433-137">프런트 엔드 풀의 외부 웹 서비스 FQDN (정규화 된 도메인 이름) (예: lyncwebextpool01.contoso.com) 또는 프런트 엔드 풀이 없는 경우 단일 서버 FQDN에 대 한 FQDN에 대해 호스트 A (AAAA for IPv6) 레코드가 있는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-137">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="58433-138">이전 단계에서 설명한 것 처럼 디렉터 풀이 없는 경우 아래와 같은 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-138">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="58433-139">이제 외부 DNS 공급자에 적합 한 형식으로 **새 별칭 (CNAME)** 을 만드는 옵션을 선택 합니다 (DNS 공급자의 형식에 따라 메뉴 옵션이 나 링크 일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="58433-139">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="58433-140">내부 DNS와 마찬가지로 **별칭 이름** 텍스트 상자의 형태가 필요한 경우 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-140">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="58433-141">또한 **대상 호스트의 fqdn (정규화 된 도메인 이름)** 텍스트 상자에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebexdir01.contoso.com)을 입력 하 고 확인을 클릭 하거나 외부 DNS에서이 항목 만들기를 허용 하는 모든 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-141">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="58433-142">위의 4 단계에 나와 있는 것 처럼, 디렉터 풀이 없는 경우에는 프런트 엔드 풀 FQDN 또는 설정한 단일 서버 FQDN (해당 하는 경우)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-142">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="58433-143">Lync 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에 새 자동 검색 CNAME 레코드를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-143">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="58433-144">내부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="58433-144">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="58433-145">내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 이거나 DnsAdmins 그룹의 구성원 인 도메인 계정을 사용 하 여 네트워크의 DNS 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-145">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="58433-146">**시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="58433-146">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="58433-147">내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Lync Server 2013 디렉터 풀 및 프런트 엔드 풀이 설치 되어 있는 Active Directory 도메인 (예: contoso)에 대해 **정방향 조회 영역** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-147">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="58433-148">확인 및 내부 DNS 레코드에 대 한 디렉터 풀에 대 한 호스트 A (AAAA for i p a p) 레코드가 있는 경우 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A 레코드가 있어야 합니다 (예:: lyncwebdir01.contoso.local).</span><span class="sxs-lookup"><span data-stu-id="58433-148">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="58433-149">여기에 없는 경우 디렉터 풀을 사용 하지 않고 프런트 엔드 풀 또는 단일 서버 IP 주소 (설치 인 경우)에 대해 IP 주소를 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-149">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="58433-150">이 점에 유의 하 고, 내부 DNS 레코드에 대 한 프런트 엔드 풀에 대해 호스트 a (AAAA for IPv6) 레코드가 있는지 확인 한 후 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대해 호스트 A (또는 AAAA) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-150">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="58433-151">그렇지 않으면 프런트 엔드 서버 또는 Standard Edition 서버에 대 한 IP 주소를 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-151">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="58433-152">호스트 A (또는 AAAA) 레코드가 있는지 확인 한 다음 DNS 서버의 콘솔 트리에서 SIP 도메인 (예: contoso.com)에 대 한 **정방향 조회 영역** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-152">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="58433-153">SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 호스트(A 또는 AAAA)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-153">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="58433-154">**이름**에 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-154">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="58433-155">**IP 주소**에 디렉터의 내부 웹 서비스 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 디렉터 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-155">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="58433-156">위의 4 단계에서 설명한 것 처럼 디렉터를 사용 하지 않는 경우에는 프런트 엔드 서버 또는 Standard Edition 서버의 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 프런트 엔드 풀 부하 분산 장치의 VIP를 입력 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-156">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="58433-157">**호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-157">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="58433-158">추가 A 또는 AAAA 레코드를 만들려면 8 ~ 10 단계를 반복 하 여 Lync Server 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 A 또는 AAAA 레코드를 만들어야 한다는 것을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-158">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="58433-159">A(IPv6의 경우 AAAA) 레코드를 모두 만든 후에 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-159">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="58433-160">외부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="58433-160">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="58433-161">외부 DNS 레코드를 만들려면 공용 DNS 공급자에 연결 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-161">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="58433-162">외부 DNS를 관리 하는 방법에는 여러 가지가 있을 수 있으므로 DNS 공급자 환경에서 어떤 위치를 정확히 설명할 수는 없지만, 이러한 단계를 도움이 되길 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="58433-162">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="58433-163">해당 환경에서 DNS 레코드를 만들 수 있는 계정으로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-163">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="58433-164">외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="58433-165">외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-165">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="58433-166">디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 호스트 A (AAAA for IPv6) 레코드가 이미 표시 되어 있는지와 IP 주소가 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-166">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="58433-167">그렇지 않은 경우에는 디렉터 풀을 사용 하지 않는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-167">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="58433-168">이 경우 프런트 엔드 풀의 IP 주소를 사용 하거나, Front-End 서버 또는 Standard Edition server에 대 한 단일 서버에 대해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-168">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="58433-169">서버가 부하 분산 장치 또는 역방향 프록시를 사용 하는 중일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58433-169">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="58433-170">아래 단계를 수행 하는 경우에도 IP 주소를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="58433-170">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="58433-171">프런트 엔드 풀의 외부 웹 서비스 FQDN (정규화 된 도메인 이름) (예: lyncwebextpool01.contoso.com) 또는 프런트 엔드 풀이 없는 경우 단일 서버 Lync 설치의 IP 주소에 대해 호스트 A (AAAA for IPv6) 레코드가 있는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-171">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="58433-172">이전 단계에서 설명한 것 처럼 디렉터 풀이 없는 경우 아래와 같은 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-172">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="58433-173">이제 외부 DNS 공급자에 적합 한 형식으로 **새 호스트 a 또는 AAAA** 를 만드는 옵션 (DNS 공급자의 형식에 따라 메뉴 옵션 또는 링크 일 수 있음)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-173">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="58433-174">**이름을**입력 하 고 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-174">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="58433-175">또한 **Ip 주소** 텍스트 상자가 있어야 하며, 여기에는 디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 ip를 입력 하거나 풀의 부하 분산 장치 (또는 같은 작업을 수행 하는 역방향 프록시 ip)를 입력할 수 있습니다 .를 클릭 하 고 확인 또는 외부 DNS를 사용 하 여이 항목 만들기를 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-175">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="58433-176">위의 4 단계에 나와 있는 것 처럼, 디렉터 풀이 없는 경우에는 설정 했던 프런트 엔드 풀 IP 주소나 단일 서버 IP 주소를 적절 하 게 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-176">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="58433-177">Lync 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에 새 자동 검색 A 또는 AAAA 레코드를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58433-177">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

