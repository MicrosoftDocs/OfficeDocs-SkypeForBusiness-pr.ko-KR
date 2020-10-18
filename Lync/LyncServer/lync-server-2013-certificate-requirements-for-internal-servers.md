---
title: 'Lync Server 2013: 내부 서버에 대 한 인증서 요구 사항'
description: 'Lync Server 2013: 내부 서버에 대 한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575214"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="6ab8e-103">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ab8e-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ab8e-104">_**마지막으로 수정 된 항목:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="6ab8e-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="6ab8e-105">Lync Server를 실행 중이 고 인증서가 필요한 내부 서버에는 Standard Edition Server, Enterprise Edition 프런트 엔드 서버, 중재 서버 및 디렉터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="6ab8e-106">다음 표에서는 이러한 서버에 대한 인증서 요구 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="6ab8e-107">Lync Server 인증서 마법사를 사용 하 여 이러한 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6ab8e-108">프런트 엔드 풀, 프런트 엔드 서버 또는 디렉터에서 단순 Url과 관련 된 주체 대체 이름에 대해 와일드 카드 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="6ab8e-109">와일드 카드 인증서 지원에 대 한 자세한 내용은 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013에서 와일드 카드 인증서 지원을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6ab8e-110">내부 서버에는 내부 엔터프라이즈 CA(인증 기관)를 사용하는 것이 좋지만 공용 CA를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="6ab8e-111">UC (통합 통신) 인증서에 대 한 특정 요구 사항을 준수 하 고 Microsoft와 제휴 하 여 Lync Server 인증서 마법사를 사용할 수 있도록 하는 인증서를 제공 하는 공용 Ca 목록을 보려면 Microsoft 기술 자료 929395, "Exchange Server 및 통신 서버용 통합 통신 인증서 파트너" 문서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="6ab8e-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="6ab8e-112">Exchange 2013와 같은 다른 응용 프로그램 및 서버와 통신 하려면 다른 응용 프로그램 및 제품에서 지 원하는 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="6ab8e-113">2013 릴리스의 경우 Lync Server 2013 및 기타 Microsoft 서버 제품 (Exchange 2013 및 SharePoint Server 포함)은 서버 간 인증 및 권한 부여를 위한 OAuth (Open Authorization) 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="6ab8e-114">자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="6ab8e-115">Windows 7 운영 체제를 실행 하는 클라이언트, Windows Server 2008 운영 체제, Windows Server 2008 R2 운영 체제, Windows Vista 운영 체제 및 Microsoft Lync Phone Edition에 연결 하는 경우 Lync Server 2013에는 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서에 대 한 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="6ab8e-116">SHA-256을 사용한 외부 액세스를 지원하기 위해 SHA-256을 사용하여 공용 CA에서 외부 인증서가 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="6ab8e-p106">다음 표에서는 프런트 엔드 풀 및 Standard Edition Server에 대한 서버 역할별 인증서 요구 사항을 보여 줍니다. 이는 모두 표준 웹 서버 인증서로서, 개인 키를 사용하고 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="6ab8e-119">인증서 마법사를 사용하여 인증서를 요청하면 서버 EKU(확장된 키 사용)가 자동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ab8e-120">각 인증서 이름은 컴퓨터 저장소에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6ab8e-121">DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com를 구성한 경우에는 인증서의 주체 대체 이름에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="6ab8e-122">Standard Edition Server용 인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-122">Certificates for Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ab8e-123">인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-123">Certificate</span></span></th>
<th><span data-ttu-id="6ab8e-124">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6ab8e-125">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="6ab8e-126">예제</span><span class="sxs-lookup"><span data-stu-id="6ab8e-126">Example</span></span></th>
<th><span data-ttu-id="6ab8e-127">설명</span><span class="sxs-lookup"><span data-stu-id="6ab8e-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-128">기본</span><span class="sxs-lookup"><span data-stu-id="6ab8e-128">Default</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-129">풀의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="6ab8e-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-130">풀의 FQDN 및 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="6ab8e-131">SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="6ab8e-132">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-133">SN = se01; SAN = se01</span><span class="sxs-lookup"><span data-stu-id="6ab8e-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-134">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-135">Standard Edition Server에서는 서버 FQDN이 풀 FQDN과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="6ab8e-136">이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="6ab8e-137">서버 간 인증에도이 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab8e-138">웹 내부</span><span class="sxs-lookup"><span data-stu-id="6ab8e-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-139">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-140">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab8e-141">내부 웹 FQDN(서버의 FQDN과 같음)</span><span class="sxs-lookup"><span data-stu-id="6ab8e-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-142">모임 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-143">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-144">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-145">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab8e-146">SN = se01; SAN = se01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-147">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="6ab8e-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6ab8e-148">SN = se01; SAN = se01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-149">토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="6ab8e-150">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6ab8e-151">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-152">웹 외부</span><span class="sxs-lookup"><span data-stu-id="6ab8e-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-153">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-154">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab8e-155">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-156">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-157">SIP 도메인당 단순 Url 충족</span><span class="sxs-lookup"><span data-stu-id="6ab8e-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-158">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab8e-159">SN = se01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-160">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="6ab8e-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6ab8e-161">SN = se01; SAN = webcon01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-162">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6ab8e-163">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="6ab8e-164">프런트 엔드 풀의 프런트 엔드 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-164">Certificates for Front End Server in a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ab8e-165">인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-165">Certificate</span></span></th>
<th><span data-ttu-id="6ab8e-166">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6ab8e-167">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="6ab8e-168">예제</span><span class="sxs-lookup"><span data-stu-id="6ab8e-168">Example</span></span></th>
<th><span data-ttu-id="6ab8e-169">설명</span><span class="sxs-lookup"><span data-stu-id="6ab8e-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-170">기본</span><span class="sxs-lookup"><span data-stu-id="6ab8e-170">Default</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-171">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-172">풀의 FQDN 및 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="6ab8e-173">SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="6ab8e-174">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-175">SN = eepool .com; SAN = eepool .com; SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="6ab8e-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-176">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-177">이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="6ab8e-178">서버 간 인증에도이 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab8e-179">웹 내부</span><span class="sxs-lookup"><span data-stu-id="6ab8e-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-180">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-181">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab8e-182">내부 웹 FQDN (서버의 FQDN과 같지 않음)</span><span class="sxs-lookup"><span data-stu-id="6ab8e-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-183">서버 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-184">Lync 풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-185">모임 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-186">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-187">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-188">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab8e-189">SN = ee01; SAN = ee01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-190">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="6ab8e-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6ab8e-191">SN = ee01; SAN = ee01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-192">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6ab8e-193">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-194">웹 외부</span><span class="sxs-lookup"><span data-stu-id="6ab8e-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-195">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-196">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab8e-197">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-198">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-199">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-200">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab8e-201">SN = ee01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-202">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="6ab8e-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6ab8e-203">SN = ee01; SAN = webcon01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-204">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6ab8e-205">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="6ab8e-206">디렉터용 인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ab8e-207">인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-207">Certificate</span></span></th>
<th><span data-ttu-id="6ab8e-208">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6ab8e-209">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="6ab8e-210">예제</span><span class="sxs-lookup"><span data-stu-id="6ab8e-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-211">기본</span><span class="sxs-lookup"><span data-stu-id="6ab8e-211">Default</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-212">디렉터 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-213">디렉터의 FQDN 및 디렉터 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="6ab8e-214">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-215">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="6ab8e-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-216">이 디렉터 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab8e-217">웹 내부</span><span class="sxs-lookup"><span data-stu-id="6ab8e-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-218">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-219">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab8e-220">내부 웹 FQDN(서버의 FQDN과 같음)</span><span class="sxs-lookup"><span data-stu-id="6ab8e-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-221">서버 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-222">Lync 풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-223">모임 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-224">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-225">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-226">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab8e-227">SN = dir01; SAN = dir01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-228">SN = dir01; SAN = dir01 SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-229">웹 외부</span><span class="sxs-lookup"><span data-stu-id="6ab8e-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-230">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-231">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab8e-232">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-233">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-234">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="6ab8e-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6ab8e-235">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab8e-236">디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="6ab8e-237">SN = dir01; SAN = directorwebcon01 SAN = contoso .com; SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6ab8e-238">SN = dir01; SAN = directorwebcon01 SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="6ab8e-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ab8e-p107">독립 실행형 중재 서버 풀이 있는 경우 풀의 각 중재 서버에 다음 표에 나열된 인증서가 필요합니다. 중재 서버를 프런트 엔드 서버와 함께 배치한 경우에는 이 항목의 앞부분에서 설명한 "프런트 엔드 풀의 프런트 엔드 서버용 인증서" 표만으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="6ab8e-241">독립 실행형 중재 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ab8e-242">인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-242">Certificate</span></span></th>
<th><span data-ttu-id="6ab8e-243">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6ab8e-244">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="6ab8e-245">예제</span><span class="sxs-lookup"><span data-stu-id="6ab8e-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-246">기본</span><span class="sxs-lookup"><span data-stu-id="6ab8e-246">Default</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-247">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-248">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="6ab8e-249">풀 구성원 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-250">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="6ab8e-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="6ab8e-251">SBA(Survivable Branch Appliance)용 인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ab8e-252">인증서</span><span class="sxs-lookup"><span data-stu-id="6ab8e-252">Certificate</span></span></th>
<th><span data-ttu-id="6ab8e-253">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6ab8e-254">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="6ab8e-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="6ab8e-255">예제</span><span class="sxs-lookup"><span data-stu-id="6ab8e-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab8e-256">기본</span><span class="sxs-lookup"><span data-stu-id="6ab8e-256">Default</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-257">SBA의 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ab8e-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-258">SIP. &lt; microsoft.rtc.management.xds.sipdomain object &gt; (SIP 도메인 당 하나의 항목 필요)</span><span class="sxs-lookup"><span data-stu-id="6ab8e-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="6ab8e-259">SN = sba01; SAN = sip .com; SAN = sip. p m c</span><span class="sxs-lookup"><span data-stu-id="6ab8e-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6ab8e-260">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ab8e-260">See Also</span></span>


[<span data-ttu-id="6ab8e-261">Lync Server 2013의 와일드 카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="6ab8e-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

