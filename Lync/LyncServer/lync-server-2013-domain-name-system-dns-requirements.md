---
title: 'Lync Server 2013: DNS (Domain Name System) 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ddbab6e4d0b1a0654c91027cbf0676ad6445f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501135"
---
# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="bf5ac-102">Lync Server 2013에 대 한 DNS (Domain Name System) 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf5ac-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf5ac-103">_**마지막으로 수정 된 항목:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="bf5ac-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="bf5ac-104">Lync Server를 배포 하려면 클라이언트와 서버에 대 한 검색을 가능 하 게 하는 DNS (Domain Name System) 레코드를 만들고, 필요에 따라 조직에서 지원 하려는 경우 자동 클라이언트 로그인을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="bf5ac-105">Lync Server에서는 다음과 같은 방식으로 DNS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="bf5ac-106">서버 간 통신을 위한 내부 서버 또는 풀을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="bf5ac-107">클라이언트가 다양 한 SIP 트랜잭션에 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="bf5ac-108">로그온 하지 않은 UC (통합 통신) 장치가 장치 업데이트 웹 서비스를 실행 하는 프런트 엔드 풀 또는 Standard Edition 서버를 검색 하 고 업데이트를 가져오고 로그를 보낼 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="bf5ac-109">외부 서버 및 클라이언트가 IM (인스턴트 메시징) 또는 회의를 위해에 지 서버 또는 HTTP 역방향 프록시에 연결할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="bf5ac-110">외부 UC 장치에서에 지 서버 또는 HTTP 역방향 프록시를 통해 장치 업데이트 웹 서비스에 연결 하 여 업데이트를 가져올 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="bf5ac-111">사용자가 장치 설정에 URL을 수동으로 입력할 필요 없이 모바일 클라이언트가 웹 서비스 리소스를 자동으로 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5ac-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf5ac-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bf5ac-112">In This Section</span></span>

  - [<span data-ttu-id="bf5ac-113">Lync Server 2013에 대 한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="bf5ac-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="bf5ac-114">Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf5ac-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="bf5ac-115">Lync Server 2013의 Standard Edition server에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf5ac-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="bf5ac-116">Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf5ac-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="bf5ac-117">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf5ac-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="bf5ac-118">Lync Server 2013의 모바일 기능에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf5ac-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="bf5ac-119">Lync Server 2013의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="bf5ac-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

