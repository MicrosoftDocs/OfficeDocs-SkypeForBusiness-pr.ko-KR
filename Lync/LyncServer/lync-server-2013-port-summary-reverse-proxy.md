---
title: 'Lync Server 2013: 포트 요약 - 역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="109ef-102">Lync Server 2013의 포트 요약 - 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="109ef-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="109ef-103">_**마지막으로 수정한 주제:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="109ef-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="109ef-104">역방향 프록시에는 방화벽과 포트/프로토콜에 대 한 최소 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="109ef-105">외부 방화벽 요구 사항은 HTTPS/TCP/443 및 선택적 HTTP/TCP/80입니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="109ef-106">HTTPS는 역방향 프록시를 통해 SSL 및 TLS 보안 통신에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="109ef-107">HTTP는 인증서를 수정 하는 것이 어렵거나 비용을 정당화 하지 않을 때 자동 검색 서비스에 대 한 액세스를 허용 하도록 선택한 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="109ef-108">클라이언트가 HTTPS의 Office Web Apps 서버에 접속 하는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="109ef-109">Office Web Apps 서버는 HTTPS/TCP/443의 내부 클라이언트 통신이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="109ef-110">권장 되는 구성은 역방향 프록시에서 Office Web Apps 서버로 HTTPS/TCP/443을 허용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="109ef-111">포트 8080는 역방향 프록시 내부 인터페이스의 트래픽을 프런트 엔드 서버, 프론트 엔드 풀 VIP (가상 IP) 또는 선택 디렉터 또는 디렉터 풀 VIP로 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="109ef-112">Lync를 실행 하는 모바일 장치에서는 외부 웹 서비스 게시 규칙 인증서 (예: 많은 수의 SIP 도메인이 있는 경우)를 수정 하는 경우 자동 검색 서비스를 찾기 위해 TCP 8080 포트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="109ef-113">필요한 SAN 항목을 사용 하 여 새 인증서를 획득 하도록 선택 하는 경우 포트 TCP 8080이 필요 하지 않으며 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="109ef-114">포트 4443는 역방향 프록시 내부 인터페이스에서 프런트 엔드 서버로의 트래픽, 프론트 엔드 풀 VIP (가상 IP) 또는 선택 사항인 디렉터 또는 디렉터 풀 VIP에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="109ef-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="109ef-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="109ef-116">원본 버전 서버 또는 중앙 관리 저장소 역할을 관리 하는 프런트 엔드 풀의 TCP 트래픽을 통해 포트 4443에서 TCP를 통해 4443를 역방향 프록시에서 내부 배포로 혼동 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="109ef-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="109ef-117">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="109ef-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="109ef-118">리버스 프록시 서버에 대 한 방화벽 세부 정보: 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109ef-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="109ef-119">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="109ef-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="109ef-120">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="109ef-120">Source IP Address</span></span></th>
<th><span data-ttu-id="109ef-121">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="109ef-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="109ef-122">상속자</span><span class="sxs-lookup"><span data-stu-id="109ef-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="109ef-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="109ef-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="109ef-124">이상</span><span class="sxs-lookup"><span data-stu-id="109ef-124">Any</span></span></p></td>
<td><p><span data-ttu-id="109ef-125">역방향 프록시 수신기</span><span class="sxs-lookup"><span data-stu-id="109ef-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="109ef-126">) 사용자가 http://&lt;publishedSiteFQDN&gt;를 입력 하는 경우 HTTPS로 리디렉션.</span><span class="sxs-lookup"><span data-stu-id="109ef-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="109ef-127">회의에 Office Web Apps를 사용 하는 경우 및 조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 경우 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용할 때도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="109ef-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="109ef-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="109ef-129">이상</span><span class="sxs-lookup"><span data-stu-id="109ef-129">Any</span></span></p></td>
<td><p><span data-ttu-id="109ef-130">역방향 프록시 수신기</span><span class="sxs-lookup"><span data-stu-id="109ef-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="109ef-131">주소록 다운로드, 주소록 웹 쿼리 서비스, 자동 검색, 클라이언트 업데이트, 모임 콘텐츠, 장치 업데이트, 그룹 확장, 회의 용 Office Web Apps, 전화 접속 회의, 모임</span><span class="sxs-lookup"><span data-stu-id="109ef-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="109ef-132">리버스 프록시 서버에 대 한 방화벽 세부 정보: 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109ef-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="109ef-133">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="109ef-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="109ef-134">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="109ef-134">Source IP Address</span></span></th>
<th><span data-ttu-id="109ef-135">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="109ef-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="109ef-136">상속자</span><span class="sxs-lookup"><span data-stu-id="109ef-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="109ef-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="109ef-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="109ef-138">내부 리버스 프록시 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109ef-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="109ef-139">프런트 엔드 서버, 프론트 엔드 풀, 이사, 이사 풀</span><span class="sxs-lookup"><span data-stu-id="109ef-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="109ef-140">조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 경우 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용 하는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="109ef-141">역방향 프록시 외부 인터페이스에서 포트 80로 전송 된 트래픽은 역방향 프록시 내부 인터페이스에서 포트 8080의 풀로 리디렉션되어,이는 풀 웹 서비스가 내부 웹 트래픽과 구별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="109ef-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="109ef-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="109ef-143">내부 리버스 프록시 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109ef-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="109ef-144">프런트 엔드 서버, 프론트 엔드 풀, 이사, 이사 풀</span><span class="sxs-lookup"><span data-stu-id="109ef-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="109ef-145">역방향 프록시 외부 인터페이스에서 포트 443로 전송 된 트래픽은 역방향 프록시 내부 인터페이스에서 포트 4443의 풀로 리디렉션되어,이는 풀 웹 서비스가 내부 웹 트래픽과 구별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="109ef-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="109ef-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="109ef-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="109ef-147">내부 리버스 프록시 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109ef-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="109ef-148">회의를 위한 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="109ef-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

