---
title: 인증서 요약-SIP, XMPP 페더레이션 및 공개 인스턴트 메시지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aede53e06493fab89a843ccc2de543aed7f05dae
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="1e6d6-102">인증서 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="1e6d6-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e6d6-103">_**마지막으로 수정한 주제:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="1e6d6-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="1e6d6-104">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server와 페더레이션 하는 데 필요한 인증서는 일반적으로 사용자가 구성 하 고, 요청 하 고, Edge 서버에 할당 하는 인증서에 의해 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="1e6d6-105">확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 파트너와 통신을 설정 하 고 설정 하기 위한 인증서 요구 사항은 XMPP 도메인에 대 한 항목을 추가로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="1e6d6-106">인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참여할 수 있는 도메인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="1e6d6-107">사용자의 하위 집합에 대해 XMPP를 사용 하는 경우 도메인은 전체 도메인에 대해 XMPP를 사용 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있는 경우 루트 수준 도메인 (예: contoso.com)이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="1e6d6-108">공용 인스턴트 메시징 연결에 대 한 인증서를 구성 하려면 다른 SIP 페더레이션 형식 또는 표준 Edge 서버 인증서 (AOL)에 인증서 나 인증서가 필요 하다는 점을 제외 하 고는 아무 것도 없음에 유의 하세요 ( 클라이언트 EKU도 포함 하는 Edge 풀의 케이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="1e6d6-109">클라이언트 EKU는 인증서에 추가 되며, 사용자의 Edge 서버에 할당 된 외부 공용 인증서의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="1e6d6-110">Edge 서버 배포에 대 한 올바른 인증서 요구 사항이 충족 되었는지 확인 하려면 **참고**항목 섹션에 나열 된 항목을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e6d6-111">요소가</span><span class="sxs-lookup"><span data-stu-id="1e6d6-111">Component</span></span></th>
<th><span data-ttu-id="1e6d6-112">주체 이름</span><span class="sxs-lookup"><span data-stu-id="1e6d6-112">Subject name</span></span></th>
<th><span data-ttu-id="1e6d6-113">주제 대체 이름 (SAN)</span><span class="sxs-lookup"><span data-stu-id="1e6d6-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="1e6d6-114">메모</span><span class="sxs-lookup"><span data-stu-id="1e6d6-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e6d6-115">외부/액세스에 지</span><span class="sxs-lookup"><span data-stu-id="1e6d6-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="1e6d6-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e6d6-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e6d6-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e6d6-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="1e6d6-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e6d6-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="1e6d6-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e6d6-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="1e6d6-120">Contoso.com XMPP 네임 스페이스를 지원 하려면</span><span class="sxs-lookup"><span data-stu-id="1e6d6-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="1e6d6-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1e6d6-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="1e6d6-122">Fabrikam.com SIP 네임 스페이스를 지원 하려면</span><span class="sxs-lookup"><span data-stu-id="1e6d6-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="1e6d6-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1e6d6-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="1e6d6-124">Fabrikam.com XMPP 네임 스페이스를 지원 하려면</span><span class="sxs-lookup"><span data-stu-id="1e6d6-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="1e6d6-125">인증서는 공용 CA에서 가져와야 하며 AOL과의 공용 IM 연결이 배포 될 경우 서버 EKU 및 클라이언트 EKU가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="1e6d6-126">인증서는 다음에 대 한 외부에 지 서버 인터페이스에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6d6-127">액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="1e6d6-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="1e6d6-128">웹 회의에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="1e6d6-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="1e6d6-129">A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="1e6d6-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="1e6d6-130">기술적으로 인증서는 A/V에 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="1e6d6-131">보안 통신 및 인증은 MRAS (미디어 릴레이 인증 서비스)를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="1e6d6-132">MRAS는 Edge 서버 내부 인터페이스에 할당 된 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="1e6d6-133">San은 토폴로지 작성기의 정의에 따라 인증서에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="1e6d6-134">추가 SIP 도메인 및 지원 해야 하는 기타 항목에 대해 필요한 경우 SAN 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="1e6d6-135">주체 이름이 SAN에 복제 되 고 올바른 작업을 위해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6d6-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e6d6-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e6d6-136">See Also</span></span>


[<span data-ttu-id="1e6d6-137">Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="1e6d6-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="1e6d6-138">Lync Server 2013의 에지 서버 인증서 계획</span><span class="sxs-lookup"><span data-stu-id="1e6d6-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="1e6d6-139">인증서 요약 - Lync Server 2013의 NAT 사용 개인 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="1e6d6-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="1e6d6-140">Lync Server 2013의 인증서 요약 - 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="1e6d6-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="1e6d6-141">Lync Server 2013의 인증서 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="1e6d6-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="1e6d6-142">Lync Server 2013의 인증서 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="1e6d6-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="1e6d6-143">Lync Server 2013의 인증서 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</span><span class="sxs-lookup"><span data-stu-id="1e6d6-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

