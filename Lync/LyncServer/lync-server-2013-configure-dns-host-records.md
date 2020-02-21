---
title: 'Lync Server 2013: DNS 호스트 레코드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c688d09e1aababd384c28c5a79989fc5d93e69b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="c900c-102">Lync Server 2013에 대 한 DNS 호스트 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="c900c-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c900c-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c900c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c900c-104">이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="c900c-105">DNS 호스트 A 레코드를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="c900c-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="c900c-106">DNS(Domain Name System) 서버에서 **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="c900c-107">도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 도메인을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="c900c-108">**새 호스트(A 또는 AAAA)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="c900c-109">**이름**을 클릭하고 풀의 호스트 이름을 입력합니다(도메인 이름은 레코드가 정의된 영역에서 가져온 것으로 가정되며 A 레코드의 일부로 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="c900c-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="c900c-110">**IP 주소**를 클릭 하 고 프런트 엔드 풀에 대 한 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c900c-111">디렉터 풀을 사용하는 배포에서 단순 URL에 대한 호스트(A) 레코드는 디렉터 부하 분산 장치의 VIP를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c900c-p101">부하 분산 장치가 없는 토폴로지에 연결된 하나의 Enterprise Edition 서버 또는 디렉터를 배포하는 경우 Enterprise Edition 서버, Standard Edition 서버 또는 디렉터의 IP 주소를 입력합니다. 풀에 둘 이상의 Enterprise Edition 서버 또는 디렉터를 배포하는 경우 부하 분산 장치가 필요합니다. Standard Edition 서버에는 부하 분산 장치를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="c900c-115">**호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="c900c-116">A 레코드를 추가로 만들려면 4단계와 5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="c900c-117">필요한 A 레코드를 모두 만들었으면 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c900c-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

