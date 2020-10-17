---
title: 'Lync Server 2013: 역방향 프록시 서버에 대 한 DNS 레코드 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af1c3179d8101a7e2f9942e15553b5831bce95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532215"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="d761a-102">Lync Server 2013에서 역방향 프록시 서버에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="d761a-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d761a-103">_**마지막으로 수정 된 항목:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="d761a-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="d761a-104">[Lync server 2013에서에 지 지원에 대 한 DNS 구성](lync-server-2013-configure-dns-for-edge-support.md)에 설명 된 대로 Microsoft 인터넷 보안 및 가속 (ISA) 서버 2006 SP1, Forefront Threat Management Gateway 2010 Server 또는 Internet Information Server 응용 프로그램 요청 라우팅의 공용 외부 인터페이스를 가리키는 외부 DNS A 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d761a-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="d761a-105">각 풀, 디렉터 (또는 디렉터 풀) 및 각 단순 URL에 대 한 외부 웹 서비스 Fqdn에 대 한 DNS 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d761a-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="d761a-106">클라이언트의 역방향 프록시 확인을 위한 최소한의 DNS 레코드를 위해 다음 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d761a-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="d761a-107">디렉터 및 디렉터 풀에 대해 게시 된 외부 웹 서비스를 정의 하는 호스트 (A) 레코드 (예: **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="d761a-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="d761a-108">모든 프런트 엔드 풀 및 Standard Edition 서버 역할 (예: **webext.contoso.com**)에 호스트 되는 외부 웹 서비스에 대해 게시 된 외부 웹 서비스를 정의 하는 호스트 (A) 레코드</span><span class="sxs-lookup"><span data-stu-id="d761a-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="d761a-109">단순 URL에 대한 호스트 (A) 레코드(예: **dialin.contoso.com** 및 **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="d761a-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="d761a-110">Lync 검색 외부 레코드의 호스트 (A) 레코드 및 Lync 웹 앱, 스케줄러 및 모바일 기능을 비롯 한 모든 웹 응용 프로그램에 대 한 자동 검색에 대 한 포인터 (예: **lyncdiscover.contoso.com**)도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d761a-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="d761a-111">Office Web Apps 서버 URL에 대 한 호스트 (A) 레코드 (예: **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="d761a-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="d761a-112">자세한 내용은 [Lync Server 2013의 DNS 요약-역방향 프록시](lync-server-2013-dns-summary-reverse-proxy.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d761a-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

