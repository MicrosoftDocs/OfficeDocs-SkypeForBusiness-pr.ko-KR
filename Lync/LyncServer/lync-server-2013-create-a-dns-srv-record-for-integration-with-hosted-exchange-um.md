---
title: 호스트되는 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="bc69f-102">호스트되는 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="bc69f-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc69f-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bc69f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bc69f-104">이 항목에서는 Lync Server 2013 Edge 서버에서 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스로 라우팅하는 데 필요한 DNS (Domain Name System) SRV 레코드를 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="bc69f-105">호스팅된 Exchange 서비스에 대 한 외부 DNS SRV 레코드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="bc69f-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="bc69f-106">DnsAdmins 그룹의 구성원으로 외부 DNS 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="bc69f-107">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="bc69f-108">SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 하 고 Lync Server 2013을 설치할 SIP 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="bc69f-109">Lync Server를 설치 하려는 SIP 도메인에서 DNS SRV 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-109">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="bc69f-110">SRV 레코드를 만들 때이 서비스 필드를 제공 하는 호스트에 사용 되는 FQDN이 Edge 풀의 외부 FQDN 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-110">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="bc69f-111">예를 들어 Edge 풀의 외부 FQDN이 edge01.contoso.net 인 경우 해당 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-111">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="bc69f-112">이는 DNS 호스트 (A) 레코드와 동일한 도메인에도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-112">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="bc69f-113">선택한 도메인을 마우스 오른쪽 단추로 클릭 한 다음 **다른 새 레코드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="bc69f-114">**리소스 레코드 종류**에서 **서비스 위치 (SRV)** 를 클릭 한 다음 **레코드 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="bc69f-115">**새 리소스 레코드**에서 **서비스**를 클릭 한 다음 \*\* \_sipfederationtls\*\*를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="bc69f-116">**프로토콜**을 클릭 한 다음 \*\* \_tcp\*\*를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="bc69f-117">**포트 번호**를 클릭 한 다음 **5061**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="bc69f-118">**이 서비스를 제공**하는 호스트를 클릭 한 다음 신뢰할 수 있는 외부 클라이언트에 대 한 lync server 2013 시스템에 대 한 액세스를 제공 하는 lync Server 2013 Edge 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bc69f-119">또한 도메인은 Exchange Online 설정에서 신뢰할 수 있는 허용 도메인으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="bc69f-120">자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>허용 도메인 만들기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc69f-120">For details, see Create Accepted Domains at <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="bc69f-121">**확인**을 클릭 한 다음 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="bc69f-122">DNS SRV 레코드가 성공적으로 만들어졌는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="bc69f-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="bc69f-123">도메인의 클라이언트 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="bc69f-124">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="bc69f-125">명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="bc69f-126">FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc69f-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc69f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc69f-127">See Also</span></span>


[<span data-ttu-id="bc69f-128">Lync Server 2013에서 역방향 프록시 서버에 대한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="bc69f-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

