---
title: 'Lync Server 2013: 디자인 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 601c313231a26341c3c4cf8a4897d11872dec9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="06271-102">Lync Server 2013에서 디자인 편집</span><span class="sxs-lookup"><span data-stu-id="06271-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06271-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="06271-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="06271-104">초기 인터뷰 질문을 완료 한 후에는 사이트의 FQDN (정규화 된 도메인 이름) 및 IP 주소를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06271-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="06271-105">이렇게 하려면 **전역 토폴로지** 페이지에서 편집 하려는 사이트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06271-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="06271-106">계획 도구에 선택한 사이트의 사이트 토폴로지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="06271-107">사이트 페이지의 맨 아래에는 4 개의 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06271-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="06271-108">![계획 도구 사이트 토폴로지](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "계획 도구 사이트 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="06271-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="06271-109">사이트 토폴로지 – 권장 되는 토폴로지 시각적 개요를 포함 하는 현재 표시 된 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="06271-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="06271-110">Edge 네트워크 다이어그램-Edge 네트워크 다이어그램 페이지는 디자이너가 계획 도구에서 대부분의 작업을 수행 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="06271-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="06271-111">다이어그램에는 권장 Lync Server 2013 토폴로지에 대 한 네트워크 구성, 서버, 풀 및 하드웨어 및 DNS (Domain Name System) 부하 분산 장치에 대 한 IP 주소 및 Fqdn에 대 한 편집 가능한 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="06271-112">Edge 관리 보고서 – Edge 관리 보고서에는 총 4 개의 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06271-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="06271-113">![Edge 관리 보고서 페이지](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "edge 관리 보고서 페이지")</span><span class="sxs-lookup"><span data-stu-id="06271-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="06271-114">요약 보고서-Edge 네트워크 구성에 대 한 설정의 일반적인 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="06271-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="06271-115">**Edge 네트워크 다이어그램** 페이지의 값을 실제 배포에 사용 되는 토폴로지 TCP/IP 및 FQDN 값으로 편집 하면 해당 주소와 이름이 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="06271-116">그렇지 않으면 기본 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="06271-117">인증서 보고서-인증서 보고서에는 토폴로지에 필요한 인증서의 주체 이름 및 주체 대체 이름이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="06271-118">방화벽 보고서-방화벽 보고서에는 인프라에서 경계 방화벽을 구성 하는 데 필요한 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="06271-119">여기에는 IP 주소 (기본값 또는 편집 된 값), 서버 역할, 원본 IP 및 포트, 대상 IP 및 포트, 전송 프로토콜, 응용 프로그램 프로토콜, 관련 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="06271-120">DNS 보고서 – DNS 보고서에는 사용자가 만들어야 하는 DNS 항목에 대 한 관련 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="06271-121">적절 한 작동에 필요한 레코드 종류, FQDN, IP 주소, 메모 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="06271-122">사이트 요약-사이트 요약에는 초기 인터뷰 질문에 응답 하거나 **디자인 사이트**의 값을 입력 하 여 선택한 내용이 간략하게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="06271-123">또한 용량 정보도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06271-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06271-124">사이트 요약 페이지의 정보는 각 디자인에 대해 사용자 지정 되며 여기에서 자세히 설명 하는 일부 섹션 또는 정보는 포함 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06271-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="06271-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06271-125">See Also</span></span>


[<span data-ttu-id="06271-126">Lync Server 2013에서 네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="06271-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

