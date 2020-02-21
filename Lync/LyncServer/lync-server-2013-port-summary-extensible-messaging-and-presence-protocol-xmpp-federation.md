---
title: 포트 요약-XMPP (Extensible messaging and 현재 상태 프로토콜) 페더레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb2eb7695cfcc3b1ed6166f7768128dc48fb8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="d4dda-102">포트 요약-Lync Server 2013의 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="d4dda-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4dda-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d4dda-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d4dda-104">에 지 서버에 배포 된 XMPP (extensible messaging and 거점 protocol) 프록시에 대해 정의 된 포트 및 프로토콜은 XMPP 페더레이션 파트너에서에 지 서버로의 통신을 허용 하 고,에 지 서버에서 XMPP로의 통신도 가능 합니다. 페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="d4dda-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="d4dda-105">또한 프런트 엔드 서버 또는 프런트 엔드 풀에서에 지 서버 또는에 지 풀에 대 한 내부 연결 방화벽에서 규칙이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4dda-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d4dda-106">확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="d4dda-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4dda-107">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="d4dda-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d4dda-108">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d4dda-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="d4dda-109">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d4dda-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d4dda-110">설명</span><span class="sxs-lookup"><span data-stu-id="d4dda-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4dda-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d4dda-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d4dda-112">모두</span><span class="sxs-lookup"><span data-stu-id="d4dda-112">Any</span></span></p></td>
<td><p><span data-ttu-id="d4dda-113">액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d4dda-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d4dda-114">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4dda-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d4dda-115">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4dda-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4dda-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d4dda-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d4dda-117">액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d4dda-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d4dda-118">모두</span><span class="sxs-lookup"><span data-stu-id="d4dda-118">Any</span></span></p></td>
<td><p><span data-ttu-id="d4dda-119">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4dda-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d4dda-120">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4dda-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4dda-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="d4dda-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="d4dda-122">모두</span><span class="sxs-lookup"><span data-stu-id="d4dda-122">Any</span></span></p></td>
<td><p><span data-ttu-id="d4dda-123">내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="d4dda-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="d4dda-124">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버에 대 한 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="d4dda-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4dda-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4dda-125">See Also</span></span>


[<span data-ttu-id="d4dda-126">Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="d4dda-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="d4dda-127">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="d4dda-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

