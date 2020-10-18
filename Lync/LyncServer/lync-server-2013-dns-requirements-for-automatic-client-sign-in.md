---
title: 'Lync Server 2013: 자동 클라이언트 로그인에 대 한 DNS 요구 사항'
description: 'Lync Server 2013: 자동 클라이언트 로그인에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574374"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="b9172-103">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9172-103">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9172-104">_**마지막으로 수정 된 항목:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="b9172-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="b9172-105">이 섹션에서는 자동 클라이언트 로그인에 필요한 DNS(Domain Name System) 레코드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-105">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="b9172-106">Standard Edition 서버 또는 프런트 엔드 풀을 배포할 때는 클라이언트가 자동 검색을 사용하여 적절한 Standard Edition 서버 또는 프런트 엔드 풀에 로그인하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-106">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="b9172-107">클라이언트를 Lync Server 2013에 수동으로 연결 해야 하는 경우에는이 항목을 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-107">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="b9172-108">자동 클라이언트 로그인을 지원하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-108">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="b9172-p102">클라이언트 로그인 요청을 분산시키고 인증하는 단일 서버 또는 풀을 지정합니다. 사용자를 호스팅하는 조직 내의 기존 서버나 풀일 수도 있고, 이 목적을 위해 어떤 사용자도 호스팅하고 있지 않은 전용 서버나 풀을 지정할 수도 있습니다. 고가용성을 위해서는 이 기능에 프런트 엔드 풀을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="b9172-112">이 서버 또는 풀에 대한 자동 클라이언트 로그인을 지원하는 내부 DNS SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-112">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9172-p103">다음의 레코드 요구 사항에서 SIP 도메인은 사용자에게 할당된 SIP URI의 호스트 부분을 나타냅니다. 예를 들어 SIP URI의 형식이 \*@contoso.com인 경우에는 contoso.com이 SIP 도메인입니다. SIP 도메인은 대개 내부 Active Directory 도메인과 다릅니다. 조직에서 여러 SIP 도메인을 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="b9172-117">클라이언트에 대해 자동 구성을 사용 하도록 설정 하려면 다음 레코드 중 하나를 Lync 클라이언트의 로그인 요청을 배포 하는 프런트 엔드 풀 또는 Standard Edition 서버의 FQDN (정규화 된 도메인 이름)에 매핑하는 내부 DNS SRV 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-117">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="b9172-118">\_\_sipinternaltls rdp-tcp.\<domain\></span><span class="sxs-lookup"><span data-stu-id="b9172-118">\_sipinternaltls.\_tcp.\<domain\></span></span> <span data-ttu-id="b9172-119">-내부 TLS 연결의 경우</span><span class="sxs-lookup"><span data-stu-id="b9172-119">- for internal TLS connections</span></span>

<span data-ttu-id="b9172-120">로그인 요청을 분산할 프런트 엔드 풀 또는 Standard Edition 서버에 대해 하나의 SRV 레코드만 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-120">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="b9172-121">다음 표에서는 contoso.com 및 retail.contoso.com이라는 SIP 도메인을 지원하는 Contoso라는 가상 회사에 필요한 일부 예제 레코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-121">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="b9172-122">SIP 도메인이 여러 개인 자동 클라이언트 로그인에 필요한 DNS 레코드의 예</span><span class="sxs-lookup"><span data-stu-id="b9172-122">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9172-123">로그인 요청을 분산하는 데 사용되는 프런트 엔드 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="b9172-123">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="b9172-124">SIP 도메인</span><span class="sxs-lookup"><span data-stu-id="b9172-124">SIP domain</span></span></th>
<th><span data-ttu-id="b9172-125">DNS SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="b9172-125">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9172-126">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9172-126">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9172-127">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9172-127">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9172-128">pool01.contoso.com에 매핑되는 _sipinternaltls._tcp.contoso.com 도메인(포트 5061)에 대한 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="b9172-128">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9172-129">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9172-129">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9172-130">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9172-130">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9172-131">pool01.contoso.com에 매핑되는 _sipinternaltls._tcp.retail.contoso.com 도메인(포트 5061)에 대한 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="b9172-131">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b9172-132">기본적으로 DNS 레코드에 대한 쿼리는 SRV 레코드 및 사용자 이름에 있는 도메인 간의 엄격한 도메인 이름 일치를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-132">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="b9172-133">접미사 일치를 대신 사용하도록 클라이언트 DNS 쿼리를 설정하려면 DisableStrictDNSNaming 그룹 정책을 구성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-133">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="b9172-134">자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013에서 클라이언트 및 장치에 대 한 계획</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9172-134">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="b9172-135">자동 클라이언트 로그인에 필요한 인증서 및 DNS 레코드의 예</span><span class="sxs-lookup"><span data-stu-id="b9172-135">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="b9172-p106">이 예에서는 앞의 표에 있는 것과 같은 예제 이름을 사용합니다. Contoso 조직은 contoso.com 및 retail.contoso.com이라는 SIP 도메인을 지원하고 이 조직의 모든 사용자는 다음 중 한 형태의 SIP URI를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9172-p106">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="b9172-138">\<user\>@retail contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9172-138">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="b9172-139">\<user\>@contoso .com</span><span class="sxs-lookup"><span data-stu-id="b9172-139">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

