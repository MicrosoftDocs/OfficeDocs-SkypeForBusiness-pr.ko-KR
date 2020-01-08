---
title: 'Lync Server 2013: DNS 인프라 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa9670761e16032abf0c205bbb740cbe1f43c4a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="77261-102">Lync Server 2013의 DNS 인프라 지원</span><span class="sxs-lookup"><span data-stu-id="77261-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77261-103">_**마지막으로 수정한 주제:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="77261-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="77261-104">Lync Server 2013에는 DNS (Domain Name System)가 필요 하며 다음과 같은 방식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77261-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="77261-105">서버 간 통신을 위한 내부 서버 또는 풀을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="77261-106">클라이언트가 다양 한 SIP 트랜잭션에 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="77261-107">해당 회의를 호스트 하는 서버와 회의를 위한 간단한 Url을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="77261-108">외부 서버 및 클라이언트가 Edge 서버에 연결 하거나 인스턴트 메시징 (IM) 또는 회의에 대 한 HTTP 역방향 프록시에 연결할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="77261-109">로그인 하지 않은 통합 커뮤니케이션 (UC) 장치를 사용 하도록 설정 하려면 Device Update 웹 서비스를 실행 하는 Standard Edition server를 검색 하 고 업데이트를 얻고 로그를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77261-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="77261-110">사용자가 수동으로 장치 설정에 Url을 입력할 필요 없이 모바일 클라이언트가 웹 서비스 리소스를 자동으로 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="77261-111">DNS 로드 균형 조정.</span><span class="sxs-lookup"><span data-stu-id="77261-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77261-112">Lync Server 2013는 다국어 도메인 이름 (IDNs)을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77261-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77261-113">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="77261-114">기본적으로 도메인에 연결 되지 않은 컴퓨터의 컴퓨터 이름은 정식 도메인 이름 (FQDN)이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="77261-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="77261-115">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="77261-116">따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="77261-117">Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함) <STRONG>만 사용</STRONG> 합니다.</span><span class="sxs-lookup"><span data-stu-id="77261-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="77261-118">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="77261-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="77261-119">FQDN의 비표준 문자는 외부 DNS 및 공개 Ca (즉 FQDN을 인증서의 SN에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="77261-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

