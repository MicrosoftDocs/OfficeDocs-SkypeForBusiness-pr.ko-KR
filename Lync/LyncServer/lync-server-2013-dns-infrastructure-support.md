---
title: 'Lync Server 2013: DNS 인프라 지원'
description: 'Lync Server 2013: DNS 인프라 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea65907eba13367fd92e546d62994d10907bf89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574454"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="6e2ab-103">Lync Server 2013의 DNS 인프라 지원</span><span class="sxs-lookup"><span data-stu-id="6e2ab-103">DNS infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e2ab-104">_**마지막으로 수정 된 항목:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="6e2ab-104">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="6e2ab-105">Lync Server 2013에는 DNS (Domain Name System)가 필요 하며 다음과 같은 방식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-105">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="6e2ab-106">서버 간 통신을 위한 내부 서버 또는 풀을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="6e2ab-107">클라이언트가 다양한 SIP 트랜잭션에 사용되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-107">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="6e2ab-108">회의용 단순 URL을 해당 회의를 호스팅하는 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-108">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="6e2ab-109">외부 서버 및 클라이언트가 IM(인스턴트 메시징) 또는 회의를 위해 에지 서버 또는 HTTP 역방향 프록시에 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-109">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="6e2ab-110">로그인하지 않은 UC(통합 통신) 장치가 장치 업데이트 웹 서비스를 실행하는 프런트 엔드 풀이나 Standard Edition 서버를 검색하고 업데이트를 가져오고 로그를 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-110">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="6e2ab-111">사용자가 장치 설정에 URL을 수동으로 입력할 필요 없이 모바일 클라이언트가 웹 서비스 리소스를 자동으로 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-111">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="6e2ab-112">DNS 부하 분산에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-112">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e2ab-113">Lync Server 2013는 다국어 도메인 이름 (Idn)을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-113">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e2ab-114">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-114">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="6e2ab-115">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN(정규화된 이름)이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-115">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="6e2ab-116">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-116">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6e2ab-117">따라서 도메인이 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-117">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="6e2ab-118">Lync Server, 에지 서버 및 풀의 FQDN을 지정할 때는 <STRONG>표준 문자</STRONG>(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-118"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="6e2ab-119">유니코드 문자나 밑줄을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6e2ab-119">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6e2ab-120">FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="6e2ab-120">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

