---
title: 'Lync Server 2013: 자동 클라이언트 로그인을 위한 DNS 요구 사항'
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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="bc86f-102">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc86f-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc86f-103">_**마지막으로 수정한 주제:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="bc86f-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="bc86f-104">이 섹션에서는 자동 클라이언트 로그인에 필요한 DNS (Domain Name System) 레코드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="bc86f-105">스탠더드 버전의 서버 또는 프런트 엔드 풀을 배포 하는 경우 자동 검색을 사용 하도록 클라이언트를 구성 하 여 적절 한 Standard Edition server 또는 프런트 엔드 풀에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="bc86f-106">클라이언트가 Lync Server 2013에 수동으로 연결 해야 하는 경우이 항목을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="bc86f-107">자동 클라이언트 로그인을 지원 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="bc86f-108">단일 서버 또는 풀을 지정 하 여 클라이언트 로그인 요청을 배포 하 고 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="bc86f-109">이는 사용자를 호스트 하는 조직의 기존 서버 또는 풀 일 수도 있고 사용자를 호스트 하지 않는이 용도의 전용 서버 또는 풀을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="bc86f-110">고가용성을 위해이 함수의 프런트 엔드 풀을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="bc86f-111">이 서버 또는 풀에 대 한 자동 클라이언트 로그인을 지원 하기 위해 내부 DNS SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bc86f-112">다음 레코드 요구 사항에서 SIP 도메인은 사용자에 게 할당 된 SIP Uri의 호스트 부분을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="bc86f-113">예를 들어 SIP Uri가 \* @contoso .com 인 경우 contoso.com는 SIP 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="bc86f-114">SIP 도메인은 내부 Active Directory 도메인과 다른 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="bc86f-115">조직에서 여러 SIP 도메인을 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="bc86f-116">클라이언트에 자동 구성을 사용 하도록 설정 하려면 다음 레코드 중 하나를 Lync에서 로그인 요청을 배포 하는 프런트 엔드 풀 또는 스탠더드 버전 서버의 FQDN (정규화 된 도메인 이름)에 매핑하는 내부 DNS SRV 레코드를 만들어야 합니다. 클라이언트</span><span class="sxs-lookup"><span data-stu-id="bc86f-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="bc86f-117">\_sipinternaltls. \_tcp. \<domain\> -내부 TLS 연결용</span><span class="sxs-lookup"><span data-stu-id="bc86f-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="bc86f-118">프런트 엔드 풀 또는 Standard Edition 서버에 대해 단일 SRV 레코드만 만들거나 로그인 요청을 배포 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="bc86f-119">다음 표에서는 contoso.com 및 retail.contoso.com의 SIP 도메인을 지 원하는 가상 회사 Contoso에 필요한 몇 가지 예제 레코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="bc86f-120">여러 SIP 도메인에 대 한 자동 클라이언트 로그인에 필요한 DNS 레코드의 예</span><span class="sxs-lookup"><span data-stu-id="bc86f-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc86f-121">로그인 요청을 배포 하는 데 사용 되는 프런트 엔드 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="bc86f-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="bc86f-122">SIP 도메인</span><span class="sxs-lookup"><span data-stu-id="bc86f-122">SIP domain</span></span></th>
<th><span data-ttu-id="bc86f-123">DNS SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="bc86f-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc86f-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc86f-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bc86f-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc86f-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bc86f-126">_Sipinternaltls에 대 한 SRV 레코드 (pool01.contoso.com에 매핑되는 5061 포트를 통한 _tcp .com 도메인</span><span class="sxs-lookup"><span data-stu-id="bc86f-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc86f-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc86f-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bc86f-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc86f-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bc86f-129">Pool01.contoso.com에 매핑되는 5061 포트를 통해 _tcp _sipinternaltls에 대 한 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="bc86f-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bc86f-130">기본적으로 DNS 레코드에 대 한 쿼리는 사용자 이름 및 SRV 레코드의 도메인 간에 엄격한 도메인 이름 일치를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="bc86f-131">클라이언트 DNS 쿼리에서 접미사 일치를 대신 사용 하려는 경우 DisableStrictDNSNaming 그룹 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="bc86f-132">자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013에서 클라이언트 및 장치 계획</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc86f-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="bc86f-133">자동 클라이언트 로그인에 필요한 인증서 및 DNS 레코드의 예</span><span class="sxs-lookup"><span data-stu-id="bc86f-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="bc86f-134">이 예제에서는 앞의 표에 같은 예제 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="bc86f-135">Contoso 조직에서는 contoso.com 및 retail.contoso.com의 SIP 도메인을 지원 하며, 모든 사용자는 다음 형식 중 하나로 SIP URI를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="bc86f-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="bc86f-136">\<contoso.com\>사용자 @retail</span><span class="sxs-lookup"><span data-stu-id="bc86f-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="bc86f-137">\<사용자\>@contoso</span><span class="sxs-lookup"><span data-stu-id="bc86f-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

