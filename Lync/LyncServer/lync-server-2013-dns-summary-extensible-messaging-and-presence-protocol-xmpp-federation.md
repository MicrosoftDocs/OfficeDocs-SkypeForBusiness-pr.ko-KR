---
title: DNS 요약-XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="8f360-102">DNS 요약-Lync Server 2013의 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="8f360-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f360-103">_**마지막으로 수정한 주제:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="8f360-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="8f360-104">배포에 대해 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)를 구성 하려면 외부 DNS 서버에 Edge 서버 또는 Edge 풀의 액세스 경계 서비스에 대 한 레코드를 확인 하는 두 개의 DNS (Domain Name System) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f360-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8f360-105">확장 가능 메시지 및 현재 상태 프로토콜에 대 한 DNS 요약</span><span class="sxs-lookup"><span data-stu-id="8f360-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f360-106">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="8f360-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8f360-107">Q</span><span class="sxs-lookup"><span data-stu-id="8f360-107">FQDN</span></span></th>
<th><span data-ttu-id="8f360-108">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="8f360-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8f360-109">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="8f360-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f360-110">외부 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="8f360-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="8f360-111">_xmpp-서버 _tcp. c a m.</span><span class="sxs-lookup"><span data-stu-id="8f360-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8f360-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8f360-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8f360-113">액세스에 지 서비스 또는 Edge 풀의 XMPP 프록시 외부 인터페이스. Lync를 사용 하는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책, 또는에 적용 된 사용자 정책을 통해 외부 액세스 정책의 구성을 통해 XMPP 연락처와의 연결을 허용 하는 사용자가 Lync를 사용할 수 있는 사용자.</span><span class="sxs-lookup"><span data-stu-id="8f360-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="8f360-114">허용 되는 XMPP 도메인은 XMPP 페더레이션 파트너 정책 에서도 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f360-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="8f360-115">자세한 내용은 관련 <strong>항목을 참조 하세요.</strong></span><span class="sxs-lookup"><span data-stu-id="8f360-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f360-116">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="8f360-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8f360-117">xmpp.contoso.com (예:)</span><span class="sxs-lookup"><span data-stu-id="8f360-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="8f360-118">XMPP 프록시를 호스팅하는 Edge 서버 또는 Edge 풀에 있는 액세스에 지 서비스의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8f360-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="8f360-119">XMPP 프록시 서비스를 호스트 하는 액세스에 지 서비스 또는 Edge 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="8f360-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="8f360-120">일반적으로 사용자가 만든 SRV 레코드는이 호스트 (A 또는 AAAA) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="8f360-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f360-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f360-121">See Also</span></span>


[<span data-ttu-id="8f360-122">Lync Server 2013에서 XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="8f360-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="8f360-123">Lync Server 2013에 대한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="8f360-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

