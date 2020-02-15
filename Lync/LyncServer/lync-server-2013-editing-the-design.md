---
title: 'Lync Server 2013: 디자인 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="c800b-102">Lync Server 2013에서 디자인 편집</span><span class="sxs-lookup"><span data-stu-id="c800b-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c800b-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c800b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c800b-104">초기 인터뷰 질문을 완료 한 후에는 사이트의 FQDN (정규화 된 도메인 이름) 및 IP 주소를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="c800b-105">이렇게 하려면 **글로벌 토폴로지** 페이지에서 편집할 사이트를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="c800b-106">계획 도구는 선택한 사이트에 대 한 사이트 토폴로지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="c800b-107">사이트 페이지 아래쪽에는 다음과 같은 네 개의 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="c800b-108">![계획 도구 사이트 토폴로지](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "계획 도구 사이트 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="c800b-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="c800b-109">사이트 토폴로지 - 현재 표시되어 있는 페이지로, 권장 토폴로지의 개요가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="c800b-110">에 지 네트워크 다이어그램-에 지 네트워크 다이어그램 페이지에서는 디자이너가 계획 도구에서 대부분의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="c800b-111">이 다이어그램에서는 서버, 풀 및 하드웨어 및 DNS (Domain Name System) 부하 분산 장치 모두에 대해 IP 주소 및 Fqdn에 대 한 편집 가능한 항목과 함께 권장 Lync Server 2013 토폴로지의 네트워크 구성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="c800b-112">경계 관리 보고서 - 경계 관리 보고서에는 총 네 개의 보고서가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="c800b-113">![에 지 관리 보고서 페이지](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "에 지 관리 보고서 페이지")</span><span class="sxs-lookup"><span data-stu-id="c800b-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="c800b-114">요약 보고서 - 경계 네트워크 구성에 대한 일반 설정 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="c800b-115">에 **지 네트워크 다이어그램** 페이지의 값을 실제 배포에 사용 되는 토폴로지 TCP/IP 및 FQDN 값으로 편집 하면 해당 주소와 이름이 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="c800b-116">그렇지 않으면 기본 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="c800b-117">인증서 보고서 - 토폴로지에 필요한 인증서의 주체 이름 및 주체 대체 이름이 나열되는 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="c800b-118">방화벽 보고서 - 인프라에서 경계 방화벽을 구성하는 데 필요한 정보가 나열되는 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="c800b-119">여기에는 IP 주소 (기본값 또는 편집 된 값), 서버 역할, 원본 IP 및 포트, 대상 IP 및 포트, 전송 프로토콜, 응용 프로그램 프로토콜 및 관련 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="c800b-120">DNS 보고서-DNS 보고서에는 만들어야 하는 DNS 항목에 대 한 관련 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="c800b-121">보고서 유형, FQDN, IP 주소 및 적절한 작업을 위한 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="c800b-122">사이트 요약-사이트 요약은 초기 인터뷰 질문에 응답 하거나 **디자인 사이트**의 값을 채워 선택한 사항에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="c800b-123">또한 용량 정보도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c800b-124">사이트 요약 페이지의 정보는 각 디자인에 대해 사용자 지정되며, 여기서 설명하는 모든 섹션이나 정보를 포함하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c800b-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="c800b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c800b-125">See Also</span></span>


[<span data-ttu-id="c800b-126">Lync Server 2013에서 네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="c800b-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

