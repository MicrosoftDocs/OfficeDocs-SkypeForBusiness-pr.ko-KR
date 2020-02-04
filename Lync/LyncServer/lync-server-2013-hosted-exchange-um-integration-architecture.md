---
title: 'Lync Server 2013: 호스팅된 Exchange UM 통합 아키텍처'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49fbb815514d9a338412b638bdf373a285ebf6f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="a937c-102">Lync Server 2013의 호스팅된 Exchange UM 통합 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a937c-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a937c-103">_**마지막으로 수정한 주제:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="a937c-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="a937c-104">Lync Server 2013 ExUM 라우팅 응용 프로그램은 온-프레미스 Exchange UM (통합 메시징) 배포, 서비스 공급자가 호스트 하는 Exchange UM 또는 두 가지 조합으로 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="a937c-105">다음 다이어그램에서는 세 가지 가능성을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="a937c-106">**온-프레미스 Exchange UM 배포 및 호스트 된 두 개의 Exchange 공급자와의 통합**</span><span class="sxs-lookup"><span data-stu-id="a937c-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="a937c-107">![온-프레미스 Lync Server Exchange UM 배포](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "온-프레미스 Lync Server Exchange UM 배포")</span><span class="sxs-lookup"><span data-stu-id="a937c-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="a937c-108">지원 되는 모드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-108">The following modes are supported:</span></span>

  - <span data-ttu-id="a937c-109">온 **-프레미스 배포:** Lync Server 2013 및 Exchange UM은 모두 엔터프라이즈 내의 로컬 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="a937c-110">**교차 프레미스 배포:** Lync Server 2013는 엔터프라이즈 내의 로컬 서버에 배포 되며 Exchange UM은 Microsoft Exchange Online 데이터 센터와 같은 온라인 서비스 공급자의 기능에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="a937c-111">**혼합 배포:** Lync Server 2013 배포에는 엔터프라이즈 내의 로컬 Exchange 서버와 호스트 된 Exchange 서비스 데이터 센터에 있는 일부 사서함에 일부 사용자 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a937c-112">혼합 배포는 사용자에 대 한 평가 및 호스팅 Exchange UM에 대 한 단계별 마이그레이션 중에 사용 하거나 다른 사용자의 Exchange UM 서비스를 사용 하도록 선택 하는 경우 영구 해결 솔루션으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="a937c-113">공유 SIP 주소 공간</span><span class="sxs-lookup"><span data-stu-id="a937c-113">Shared SIP Address Space</span></span>

<span data-ttu-id="a937c-114">Lync Server 2013를 온-프레미스 Exchange UM 배포와 통합 하려면 Exchange UM Active Directory 도메인 서비스 개체를 읽을 수 있도록 Lync Server 2013 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="a937c-115">이 접근 방식은 Lync Server 2013 및 Exchange UM이 서로 간에 트러스트 관계 없이 별도의 포리스트에 설치 되어 있기 때문에 호스팅된 Exchange UM과 통합 하는 경우에는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="a937c-116">Lync Server 2013을 호스트 된 Exchange UM과 통합 하려면 *공유 SIP 주소 공간*을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="a937c-117">이 구성에서는 Lync Server 2013와 호스팅된 Exchange UM 서비스 공급자 모두에 동일한 SIP 도메인 주소 공간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a937c-118">공유 된 SIP 주소 공간 사용은 일부 사용자가 온-프레미스 배포에 설정 되어 있고 그 일부가 호스팅된 배포 (예: Lync Online)에 속해 있는 교차 프레미스 Lync Server 2013 환경에서 사용 되는 방법과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="a937c-119">SIP 도메인이 그 사이를 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-119">The SIP domain is split between them.</span></span> <span data-ttu-id="a937c-120">Lync Server 2013을 호스트 된 Exchange UM과 통합 하는 경우 공유 SIP 주소 공간에 Exchange UM 서비스 공급자를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="a937c-121">Exchange UM 서비스 공급자와 통합할 공유 SIP 주소 공간을 구성 하려면 아래와 같이 Edge 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="a937c-122">**Set-CsAccessEdgeConfiguration** cmdlet을 실행 하 여 다음 매개 변수를 설정 하 여 페더레이션의 Edge 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="a937c-123">\*\*UseDnsSrvRouting \*\*은 페더레이션 요청을 보내고 받을 때 에지 서버가 DNS SRV 레코드를 기반으로 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="a937c-p105">\*\*AllowFederatedUsers \*\*는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다. 이 속성은 내부 사용자가 분할 도메인 시나리오의 사용자와 통신할 수 있는지 여부도 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="a937c-126">**Enablepartnerdiscovery** Lync Server 2013에서 DNS 레코드를 사용 하 여 Active Directory에서 허용 된 도메인 목록에 나열 되지 않은 파트너 도메인을 검색 하려고 할 때 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="a937c-127">False 인 경우, Lync Server 2013는 허용 된 도메인 목록에 있는 도메인에만 페더레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="a937c-128">이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="a937c-129">대부분의 배포에서는 페더레이션을 일부 파트너로 제한하기 위해 이 값이 false로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="a937c-130">중앙 관리 저장소를 Edge 서버에 복제 하 고 복제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="a937c-131">자세한 내용은 [Lync Server 2013 토폴로지 내보내기를 참조 하 여 edge 설치에 대 한 배포 설명서의 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="a937c-132">**새-CsHostingProvider** cmdlet을 실행 하 여 다음 매개 변수를 설정 하 여 Edge 서버에서 *호스팅 공급자* 를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="a937c-133">**Id** 는 만들려는 호스팅 공급자 (예: **호스팅된 Exchange UM**)에 대 한 고유한 문자열 값 식별자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="a937c-134">\*\*Enabled \*\*는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-134">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="a937c-135">**True**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-135">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="a937c-136">**EnabledSharedAddressSpace** 는 호스팅 공급자가 공유 SIP 주소 공간 시나리오에 사용 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-136">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="a937c-137">**True**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-137">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="a937c-138">**HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Lync Server 2013 계정을 호스트 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="a937c-139">**False**로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="a937c-140">**Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버에 대 한 FQDN (정규화 된 도메인 이름)을 지정 합니다 (예: **proxyserver.fabrikam.com**).</span><span class="sxs-lookup"><span data-stu-id="a937c-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="a937c-141">이 정보는 호스팅 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a937c-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="a937c-142">이 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-142">This value cannot be modified.</span></span> <span data-ttu-id="a937c-143">호스팅 공급자가 프록시 서버를 변경 하는 경우 해당 공급자에 대 한 항목을 삭제 한 다음 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="a937c-144">**Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 2013 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="a937c-145">**False**로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a937c-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

