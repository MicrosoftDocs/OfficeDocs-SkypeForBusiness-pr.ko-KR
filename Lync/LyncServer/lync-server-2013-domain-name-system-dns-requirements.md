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
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="3c8bf-102">Lync Server 2013의 DNS (Domain Name System) 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c8bf-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c8bf-103">_**마지막으로 수정한 주제:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="3c8bf-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="3c8bf-104">Lync Server를 배포 하려면 클라이언트와 서버의 검색을 가능 하 게 하는 DNS (Domain Name System) 레코드를 만들어야 하며, 조직에서 지원 하려는 경우 자동 클라이언트 로그인을 선택적으로 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="3c8bf-105">Lync Server는 다음과 같은 방법으로 DNS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="3c8bf-106">서버 간 통신을 위한 내부 서버 또는 풀을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="3c8bf-107">클라이언트가 다양 한 SIP 트랜잭션에 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="3c8bf-108">프론트 엔드 풀이나 장치 업데이트 웹 서비스를 실행 하는 Standard Edition 서버를 검색 하기 위해 로그온 되지 않은 UC (통합 통신) 장치를 허용 하려면 업데이트를 얻고 로그를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="3c8bf-109">외부 서버 및 클라이언트가 Edge 서버 또는 메신저 (인스턴트 메시징) 또는 회의에 대 한 HTTP 역방향 프록시에 연결할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="3c8bf-110">외부 UC 장치에서 Edge 서버 또는 HTTP 리버스 프록시를 통해 디바이스 업데이트 웹 서비스에 연결 하 고 업데이트를 가져올 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="3c8bf-111">모바일 클라이언트가 사용자에 게 수동으로 장치 설정에 Url을 입력할 필요 없이 웹 서비스 리소스를 자동으로 검색할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8bf-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c8bf-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3c8bf-112">In This Section</span></span>

  - [<span data-ttu-id="3c8bf-113">Lync Server 2013에 대한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="3c8bf-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="3c8bf-114">Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c8bf-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="3c8bf-115">Lync Server 2013의 Standard Edition server에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c8bf-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="3c8bf-116">Lync Server 2013의 단순 URL에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c8bf-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="3c8bf-117">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c8bf-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="3c8bf-118">Lync Server 2013을 사용 하 여 이동성을 위한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c8bf-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="3c8bf-119">Lync Server 2013의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="3c8bf-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

