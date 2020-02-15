---
title: 'Lync Server 2013: 온-프레미스 통합 메시징 통합을 위한 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be763250edf7222b900aef88665b3e360e8125c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="c157b-102">온-프레미스 통합 메시징과 Lync Server 2013의 통합 지침</span><span class="sxs-lookup"><span data-stu-id="c157b-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c157b-103">_**마지막으로 수정 된 항목:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="c157b-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="c157b-104">다음은 Enterprise Voice를 배포할 때 고려해 야 할 지침 및 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c157b-105">Exchange UM (통합 메시징)은 c u 3을 함께 사용 하는 경우에만 i p v를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="c157b-106">Lync Server 2013 Standard Edition Server 또는 프런트 엔드 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="c157b-107">설치에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c157b-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="c157b-108">Exchange 관리자와 함께 원활하고 성공적인 통합을 위해 각자가 수행할 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="c157b-109">Exchange UM에 대해 사용자를 사용 하도록 설정할 각 Exchange UM (통합 메시징) 포리스트에 Exchange 사서함 서버 역할을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="c157b-110">Exchange 서버 역할을 설치 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c157b-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c157b-111">Exchange UM (통합 메시징)을 설치 하면 자체 서명 된 인증서를 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="c157b-112">그러나 자체 서명 된 인증서를 사용 하는 경우 Lync Server 2013 및 Exchange UM에서 서로를 신뢰 하지 않으므로 두 서버에서 모두 신뢰 하는 인증 기관과 별도의 인증서를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="c157b-113">Lync Server 2013 및 Exchange UM이 서로 다른 포리스트에 설치 된 경우 lync server 2013 포리스트와 Lync Server 2013 포리스트를 트러스트 하도록 각 exchange 포리스트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="c157b-114">또한 일반적으로 스크립트 또는 ILM (Identity 수명 주기 관리자) 같은 크로스 포리스트 도구를 사용 하 여 Lync Server 2013 포리스트의 사용자 개체에 대 한 사용자의 Exchange UM 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="c157b-115">필요한 경우 통합 메시징 서버를 관리할 Exchange 관리 콘솔을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="c157b-116">Outlook Voice Access 및 자동 전화 교환을 위한 유효한 전화 번호를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="c157b-117">Microsoft Exchange Server 2010 SP1 (서비스 팩 1) 이전 버전의 Exchange UM을 사용 하는 경우 Exchange UM SIP URI 다이얼 플랜 및 Enterprise Voice 다이얼 플랜에 대 한 좌표 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="c157b-118">중복 Exchange UM 서버 배포</span><span class="sxs-lookup"><span data-stu-id="c157b-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c157b-119">조직에 대해 구성 하는 각 Exchange UM SIP URI 다이얼 플랜에 대해 Exchange UM 서비스가 실행 되는 최소 두 대의 서버를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="c157b-120">확장 된 용량을 제공 하는 것 외에도 중복 서버를 배포 하면 고가용성이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="c157b-121">서버 오류가 발생할 경우 Lync Server 2013를 다른 서버로 장애 조치 (failover) 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="c157b-122">다음 구성 예에서는 Exchange UM 복구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="c157b-123">**예 1: Exchange UM 복구**</span><span class="sxs-lookup"><span data-stu-id="c157b-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="c157b-124">![Exchange UM 예제 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 예제 1")</span><span class="sxs-lookup"><span data-stu-id="c157b-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="c157b-125">예 1에서 Exchange UM 서버 1과 2는 Tukwila 데이터 센터에서 사용되고, Exchange UM 서버 3과 4는 Dublin 데이터 센터에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="c157b-126">Tukwila의 Exchange UM 중단 시에는 DNS (Domain Name System)가 서버 3과 4를 가리키도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="c157b-127">Exchange UM 중단 시간이 더블린 이면 서버 3과 4에 대 한 DNS A 레코드를 각각 서버 1과 2를 가리키도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c157b-128">예 1의 경우 각 Exchange UM 서버에서 다음 인증서 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c157b-129">SAN(주체 대체 이름)에 와일드카드가 포함된 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="c157b-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="c157b-130">SAN에 있는 4 대의 Exchange UM 서버 각각의 FQDN (정규화 된 도메인 이름)을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c157b-131">**예 2: Exchange UM 복구**</span><span class="sxs-lookup"><span data-stu-id="c157b-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="c157b-132">![Exchange UM 예제 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 예제 2")</span><span class="sxs-lookup"><span data-stu-id="c157b-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="c157b-p106">예 2의 경우 정상 작동 조건에서 Exchange UM 서버 1과 2는 Tukwila 데이터 센터에서 사용되고, Exchange UM 서버 3과 4는 Dublin 데이터 센터에서 사용됩니다. 네 서버 모두 Tukwila 사용자의 SIP URI 다이얼 플랜에 포함되어 있지만 서버 3과 4는 사용하지 않도록 설정되어 있습니다. Tukwila에서 Exchange UM의 작동이 중단된 경우 예를 들어 Exchange UM 서버 1과 2가 사용할 수 없게 되고, Exchange UM 서버 3과 4를 사용할 수 있으므로 Tukwila Exchange UM 트래픽이 Dublin의 서버로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="c157b-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="c157b-136">Exchange 2013에서 통합 메시징을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은의 "Exchange 2013 UM과 [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)Lync Server 통합"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c157b-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="c157b-137">Microsoft Exchange Server 2010에서 통합 메시징을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c157b-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="c157b-138">"Exchange 2010에서 통합 메시징 사용" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)</span><span class="sxs-lookup"><span data-stu-id="c157b-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="c157b-139">"Exchange 2010에서 통합 메시징 사용 안 함 [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)"</span><span class="sxs-lookup"><span data-stu-id="c157b-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c157b-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c157b-140">See Also</span></span>


[<span data-ttu-id="c157b-141">온-프레미스 통합 메시징과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="c157b-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

