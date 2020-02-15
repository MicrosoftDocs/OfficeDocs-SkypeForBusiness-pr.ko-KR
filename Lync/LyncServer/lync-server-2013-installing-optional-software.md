---
title: 'Lync Server 2013: 선택적 소프트웨어 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080f27b1e01f86d23fd5fd7bf6fdb9e9a05c0742
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="db7a4-102">Lync Server 2013에 선택적 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="db7a4-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db7a4-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="db7a4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="db7a4-104">Microsoft Lync Server 2013, 계획 도구는 Microsoft Excel 및 Microsoft Visio로 내보내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="db7a4-105">이러한 응용 프로그램은 계획 도구를 운영 하는 데 필요 하지 않지만 디자인의 배포 및 설명서에 중요 한 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="db7a4-106">선택적 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="db7a4-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="db7a4-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="db7a4-107">Microsoft Excel</span></span>

<span data-ttu-id="db7a4-108">Microsoft Excel로 디자인을 내보내면 스프레드시트에 7 개의 탭이 표시 되는 보고서가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="db7a4-109">요약-사용자 수, 용량 설정 및 서버 프로필 정보를 포함 하 여 사이트 구성에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="db7a4-110">하드웨어 프로필 – CPU, 메모리, 디스크 및 네트워크 인터페이스 등을 비롯한 토폴로지에서 지정된 서버의 권장 하드웨어 구성에 대한 보고서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="db7a4-111">서버 구성 요소의 수량 및 권장 사양도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="db7a4-112">또한 각 서버는 사이트별로 서버 요구 사항의 전체 표현을 제공 하도록 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="db7a4-113">포트 요구 사항-사용 하도록 설정 된 모든 포트에 대 한 보고서와 도메인 이름 시스템 부하 분산 (DNS LB) 및 HLB (하드웨어 부하 분산 장치)에 대 한 연결을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="db7a4-114">이 보고서를 사용 하 여 방화벽과 DNS LB 및 HLB 구성을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="db7a4-115">요약 보고서-에 지 서버 네트워크를 설정 하는 데 필요한 설정에 대 한 일반적인 요약 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="db7a4-116">인증서 보고서-에 지 서버를 실행 하는 데 필요한 인증서에 필요한 주체 이름 및 주체 대체 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="db7a4-117">방화벽 보고서-원본 및 대상 포트와 외부 및 내부 인터페이스에 대 한 IP 주소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="db7a4-118">DNS 보고서-사용자가 만드는 각 DNS 항목에 필요한 FQDN (정규화 된 도메인 이름) 및 IP/VIP 주소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="db7a4-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="db7a4-119">Microsoft Visio</span></span>

<span data-ttu-id="db7a4-p104">설계를 Microsoft Visio로 내보내면 구성된 토폴로지 및 인프라에 대한 설명서에서 사용할 다이어그램이 만들어집니다. 가져온 다이어그램은 설명서 요구 사항에 맞게 편집하고 재정렬할 수 있습니다. 일반적인 Visio 다이어그램에 포함되는 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db7a4-123">프런트 엔드 서버를 3 개 이상 필요로 하는 설계가 충분히 큰 경우 프런트 엔드 풀, 프런트 엔드 서버, SQL Server를 실행 하는 컴퓨터, IP 주소 및 Fqdn에 대 한 추가 페이지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="db7a4-124">전역 토폴로지-구성 된 Lync Server 2013 사이트의 다이어그램입니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="db7a4-125">Site Name 탭-Edge Server, 방화벽, 공중 전화망 (PSTN)이 있는 사이트 구성 토폴로지 및 내부 서버 배포를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="db7a4-126">내부 배포는 프런트 엔드 풀, SQL Server 기반 서버, Active Directory 도메인 서비스, 디렉터, Exchange UM (통합 메시징) 서버, Exchange 사서함 서버, Office Web Apps 서버를 포함 하 여 구성 된 서버 및 풀로 구성 됩니다. 중재 서버 및 영구 채팅 서버</span><span class="sxs-lookup"><span data-stu-id="db7a4-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="db7a4-127">에 지 네트워크 다이어그램-연결 된 IP 주소와 Fqdn을 사용 하 여에 지 서버 구성을 자세히 설명 하는 다이어그램입니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="db7a4-128">DNS 부하 분산 및 하드웨어 부하 분산 장치도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="db7a4-129">또한 디렉터 및 프런트 엔드 서버 또는 프런트 엔드 풀은 연결 된 DNS LB 또는 HLB 및 할당 된 IP 주소 (계획 도구에서 IPv4 및 IPv6 주소를 모두 지원) 및 FQDN과 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db7a4-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db7a4-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db7a4-130">See Also</span></span>


[<span data-ttu-id="db7a4-131">Lync Server 2013에서 계획 도구 설치</span><span class="sxs-lookup"><span data-stu-id="db7a4-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

