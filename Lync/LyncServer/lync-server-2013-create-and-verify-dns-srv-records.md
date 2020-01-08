---
title: 'Lync Server 2013: DNS SRV 레코드 만들기 및 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="754e3-102">Lync Server 2013에서 DNS SRV 레코드 만들기 및 확인</span><span class="sxs-lookup"><span data-stu-id="754e3-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="754e3-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="754e3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="754e3-104">이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="754e3-105">이 항목에서는 Lync Server 2013 배포에서 만들어야 하는 DNS (Domain Name System) 레코드와 자동 클라이언트가 로그인 하는 데 필요한 사용자를 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="754e3-106">프런트 엔드 풀을 만들면 설치 프로그램에서 풀의 Active Directory 개체와 설정 (FQDN (정규화 된 도메인 이름) 포함)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="754e3-107">스탠더드 버전 서버에 대 한 유사한 개체와 설정이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="754e3-108">클라이언트가 풀 또는 Standard Edition 서버에 연결할 수 있으려면 풀 또는 Standard Edition 서버의 FQDN이 DNS에 등록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="754e3-109">모든 SIP 도메인에 대해 내부 DNS에 DNS SRV 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="754e3-110">이 절차에서는 내부 DNS에 SIP 사용자 도메인에 대 한 영역이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="754e3-111">DNS SRV 레코드를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="754e3-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="754e3-112">DNS 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **dns**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="754e3-113">SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 SIP 도메인을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="754e3-114">**다른 새 레코드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="754e3-115">**리소스 레코드 종류 선택**에서 **서비스 위치 (SRV)** 를 클릭 한 다음 **레코드 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="754e3-116">**서비스**를 클릭 한 다음 \*\* \_sipinternaltls\*\*를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="754e3-117">**프로토콜**을 클릭 한 다음 \*\* \_tcp\*\*를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="754e3-118">**포트 번호**를 클릭 한 다음 **5061**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="754e3-119">**이 서비스를 제공**하는 호스트를 클릭 한 다음 풀 또는 Standard EDITION 서버의 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="754e3-120">**확인**을 클릭 한 다음 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="754e3-121">DNS SRV 레코드의 생성을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="754e3-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="754e3-122">인증 된 사용자 그룹의 구성원 이거나 동등한 권한이 있는 계정을 사용 하 여 도메인의 클라이언트 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="754e3-123">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="754e3-124">**열기** 상자에 **cmd**를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="754e3-125">명령 프롬프트에서 **nslookup**을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="754e3-126">**Set type = srv**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="754e3-127">\*\* \_Sipinternaltls를 입력\_ 합니다. tcp.contoso.com\*\*을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="754e3-128">TLS (전송 계층 보안) 레코드에 대해 표시 되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="754e3-129">서버: \<dns server\>. contoso.com</span><span class="sxs-lookup"><span data-stu-id="754e3-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="754e3-130">주소: \<DNS 서버의 IP 주소\></span><span class="sxs-lookup"><span data-stu-id="754e3-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="754e3-131">비 정식 답변:</span><span class="sxs-lookup"><span data-stu-id="754e3-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="754e3-132">\_sipinternaltls. \_tcp.contoso.com SRV 서비스 위치:</span><span class="sxs-lookup"><span data-stu-id="754e3-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="754e3-133">우선 순위 = 0</span><span class="sxs-lookup"><span data-stu-id="754e3-133">priority = 0</span></span>
    
    <span data-ttu-id="754e3-134">weight = 0</span><span class="sxs-lookup"><span data-stu-id="754e3-134">weight = 0</span></span>
    
    <span data-ttu-id="754e3-135">port = 5061</span><span class="sxs-lookup"><span data-stu-id="754e3-135">port = 5061</span></span>
    
    <span data-ttu-id="754e3-136">poolname.contoso.com (또는 Standard Edition server A 레코드)</span><span class="sxs-lookup"><span data-stu-id="754e3-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="754e3-137">poolname.contoso.com internet address = \<하나의\> Enterprise Edition server \<\> 또는 \<Standard edition server의 ip 주소를 포함 하는 풀에 대 한 단일 enterprise edition 서버의 부하 분산 또는 ip 주소에 대 한 가상 IP 주소\></span><span class="sxs-lookup"><span data-stu-id="754e3-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="754e3-138">작업이 완료 되 면 명령 프롬프트에 **exit**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="754e3-139">프런트 엔드 풀 또는 Standard Edition 서버의 FQDN을 확인할 수 있는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="754e3-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="754e3-140">도메인의 클라이언트 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="754e3-141">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="754e3-142">**열기** 상자에 **cmd**를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="754e3-143">명령 프롬프트에서 프런트 엔드 풀 \*\*\*\* \<\> 의 nslookup fqdn 또는 \<Standard Edition server\>의 fqdn을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="754e3-144">FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="754e3-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

