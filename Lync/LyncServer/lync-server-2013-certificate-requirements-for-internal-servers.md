---
title: 'Lync Server 2013: 내부 서버에 대 한 인증서 요구 사항'
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
ms.openlocfilehash: f5b3da640ca4aa9f7b53c072802a2f7f727759dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="73969-102">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="73969-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73969-103">_**마지막으로 수정 된 항목:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="73969-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="73969-104">Lync Server를 실행 중이 고 인증서가 필요한 내부 서버에는 Standard Edition Server, Enterprise Edition 프런트 엔드 서버, 중재 서버 및 디렉터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="73969-105">다음 표에서는 이러한 서버에 대한 인증서 요구 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73969-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="73969-106">Lync Server 인증서 마법사를 사용 하 여 이러한 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="73969-107">프런트 엔드 풀, 프런트 엔드 서버 또는 디렉터에서 단순 Url과 관련 된 주체 대체 이름에 대해 와일드 카드 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="73969-108">와일드 카드 인증서 지원에 대 한 자세한 내용은 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013에서 와일드 카드 인증서 지원을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73969-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="73969-109">내부 서버에는 내부 엔터프라이즈 CA(인증 기관)를 사용하는 것이 좋지만 공용 CA를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="73969-110">UC (통합 통신) 인증서에 대 한 특정 요구 사항을 준수 하 고 Microsoft와 제휴 하 여 Lync Server 인증서 마법사를 사용할 수 있도록 하는 인증서를 제공 하는 공용 Ca 목록을 보려면 Microsoft 기술 자료 929395, "Exchange Server 및 통신 서버용 통합 통신 인증서 파트너" 문서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="73969-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="73969-111">Exchange 2013와 같은 다른 응용 프로그램 및 서버와 통신 하려면 다른 응용 프로그램 및 제품에서 지 원하는 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="73969-112">2013 릴리스의 경우 Lync Server 2013 및 기타 Microsoft 서버 제품 (Exchange 2013 및 SharePoint Server 포함)은 서버 간 인증 및 권한 부여를 위한 OAuth (Open Authorization) 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="73969-113">자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73969-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="73969-114">Windows 7 운영 체제, Windows Server 2008 운영 체제, Windows Server 2008 R2 운영 체제, Windows Vista 운영 체제 및 Microsoft Lync Phone Edition을 실행 하는 클라이언트에서 연결 하려면 Lync Server 2013에 대 한 지원이 포함 되어 있지만 그렇지 않습니다. 필수) SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서</span><span class="sxs-lookup"><span data-stu-id="73969-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="73969-115">SHA-256을 사용한 외부 액세스를 지원하기 위해 SHA-256을 사용하여 공용 CA에서 외부 인증서가 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="73969-p106">다음 표에서는 프런트 엔드 풀 및 Standard Edition Server에 대한 서버 역할별 인증서 요구 사항을 보여 줍니다. 이는 모두 표준 웹 서버 인증서로서, 개인 키를 사용하고 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="73969-118">인증서 마법사를 사용하여 인증서를 요청하면 서버 EKU(확장된 키 사용)가 자동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73969-119">각 인증서 이름은 컴퓨터 저장소에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="73969-120">DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com를 구성한 경우에는 인증서의 주체 대체 이름에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="73969-121">Standard Edition Server용 인증서</span><span class="sxs-lookup"><span data-stu-id="73969-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="73969-122">인증서</span><span class="sxs-lookup"><span data-stu-id="73969-122">Certificate</span></span></th>
<th><span data-ttu-id="73969-123">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="73969-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="73969-124">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="73969-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="73969-125">예제</span><span class="sxs-lookup"><span data-stu-id="73969-125">Example</span></span></th>
<th><span data-ttu-id="73969-126">설명</span><span class="sxs-lookup"><span data-stu-id="73969-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73969-127">기본</span><span class="sxs-lookup"><span data-stu-id="73969-127">Default</span></span></p></td>
<td><p><span data-ttu-id="73969-128">풀의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="73969-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="73969-129">풀의 FQDN 및 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="73969-130">SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="73969-131">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="73969-132">SN = se01; SAN = se01</span><span class="sxs-lookup"><span data-stu-id="73969-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="73969-133">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="73969-134">Standard Edition Server에서는 서버 FQDN이 풀 FQDN과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="73969-135">이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="73969-136">서버 간 인증에도이 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73969-137">웹 내부</span><span class="sxs-lookup"><span data-stu-id="73969-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="73969-138">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="73969-139">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="73969-140">내부 웹 FQDN(서버의 FQDN과 같음)</span><span class="sxs-lookup"><span data-stu-id="73969-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="73969-141">모임 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="73969-142">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-143">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-144">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="73969-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="73969-145">SN = se01; SAN = se01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</span><span class="sxs-lookup"><span data-stu-id="73969-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="73969-146">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="73969-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="73969-147">SN = se01; SAN = se01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="73969-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73969-148">토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="73969-149">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="73969-150">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73969-151">웹 외부</span><span class="sxs-lookup"><span data-stu-id="73969-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="73969-152">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="73969-153">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="73969-154">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-155">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-156">SIP 도메인당 단순 Url 충족</span><span class="sxs-lookup"><span data-stu-id="73969-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="73969-157">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="73969-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="73969-158">SN = se01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</span><span class="sxs-lookup"><span data-stu-id="73969-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="73969-159">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="73969-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="73969-160">SN = se01; SAN = webcon01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="73969-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73969-161">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="73969-162">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="73969-163">프런트 엔드 풀의 프런트 엔드 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="73969-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="73969-164">인증서</span><span class="sxs-lookup"><span data-stu-id="73969-164">Certificate</span></span></th>
<th><span data-ttu-id="73969-165">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="73969-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="73969-166">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="73969-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="73969-167">예제</span><span class="sxs-lookup"><span data-stu-id="73969-167">Example</span></span></th>
<th><span data-ttu-id="73969-168">설명</span><span class="sxs-lookup"><span data-stu-id="73969-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73969-169">기본</span><span class="sxs-lookup"><span data-stu-id="73969-169">Default</span></span></p></td>
<td><p><span data-ttu-id="73969-170">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="73969-171">풀의 FQDN 및 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="73969-172">SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="73969-173">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="73969-174">SN = eepool .com; SAN = eepool .com; SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="73969-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="73969-175">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="73969-176">이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="73969-177">서버 간 인증에도이 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73969-178">웹 내부</span><span class="sxs-lookup"><span data-stu-id="73969-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="73969-179">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="73969-180">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="73969-181">내부 웹 FQDN (서버의 FQDN과 같지 않음)</span><span class="sxs-lookup"><span data-stu-id="73969-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="73969-182">서버 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-183">Lync 풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-184">모임 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="73969-185">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-186">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-187">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="73969-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="73969-188">SN = ee01; SAN = ee01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</span><span class="sxs-lookup"><span data-stu-id="73969-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="73969-189">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="73969-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="73969-190">SN = ee01; SAN = ee01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="73969-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73969-191">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="73969-192">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73969-193">웹 외부</span><span class="sxs-lookup"><span data-stu-id="73969-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="73969-194">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="73969-195">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="73969-196">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-197">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-198">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-199">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="73969-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="73969-200">SN = ee01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</span><span class="sxs-lookup"><span data-stu-id="73969-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="73969-201">와일드카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="73969-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="73969-202">SN = ee01; SAN = webcon01; SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="73969-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73969-203">모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="73969-204">와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73969-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="73969-205">디렉터용 인증서</span><span class="sxs-lookup"><span data-stu-id="73969-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73969-206">인증서</span><span class="sxs-lookup"><span data-stu-id="73969-206">Certificate</span></span></th>
<th><span data-ttu-id="73969-207">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="73969-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="73969-208">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="73969-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="73969-209">예제</span><span class="sxs-lookup"><span data-stu-id="73969-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73969-210">기본</span><span class="sxs-lookup"><span data-stu-id="73969-210">Default</span></span></p></td>
<td><p><span data-ttu-id="73969-211">디렉터 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="73969-212">디렉터의 FQDN 및 디렉터 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="73969-213">이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="73969-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="73969-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="73969-215">이 디렉터 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73969-216">웹 내부</span><span class="sxs-lookup"><span data-stu-id="73969-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="73969-217">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="73969-218">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="73969-219">내부 웹 FQDN(서버의 FQDN과 같음)</span><span class="sxs-lookup"><span data-stu-id="73969-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="73969-220">서버 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-221">Lync 풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-222">모임 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="73969-223">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-224">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-225">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="73969-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="73969-226">SN = dir01; SAN = dir01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</span><span class="sxs-lookup"><span data-stu-id="73969-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="73969-227">SN = dir01; SAN = dir01 SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="73969-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73969-228">웹 외부</span><span class="sxs-lookup"><span data-stu-id="73969-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="73969-229">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="73969-230">각각 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73969-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="73969-231">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="73969-232">전화 접속 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-233">관리 단순 URL</span><span class="sxs-lookup"><span data-stu-id="73969-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="73969-234">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="73969-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="73969-235">디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="73969-236">SN = dir01; SAN = directorwebcon01 SAN = contoso .com; SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</span><span class="sxs-lookup"><span data-stu-id="73969-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="73969-237">SN = dir01; SAN = directorwebcon01 SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="73969-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="73969-p107">독립 실행형 중재 서버 풀이 있는 경우 풀의 각 중재 서버에 다음 표에 나열된 인증서가 필요합니다. 중재 서버를 프런트 엔드 서버와 함께 배치한 경우에는 이 항목의 앞부분에서 설명한 "프런트 엔드 풀의 프런트 엔드 서버용 인증서" 표만으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="73969-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="73969-240">독립 실행형 중재 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="73969-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73969-241">인증서</span><span class="sxs-lookup"><span data-stu-id="73969-241">Certificate</span></span></th>
<th><span data-ttu-id="73969-242">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="73969-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="73969-243">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="73969-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="73969-244">예제</span><span class="sxs-lookup"><span data-stu-id="73969-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73969-245">기본</span><span class="sxs-lookup"><span data-stu-id="73969-245">Default</span></span></p></td>
<td><p><span data-ttu-id="73969-246">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="73969-247">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="73969-248">풀 구성원 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="73969-249">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="73969-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="73969-250">SBA(Survivable Branch Appliance)용 인증서</span><span class="sxs-lookup"><span data-stu-id="73969-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73969-251">인증서</span><span class="sxs-lookup"><span data-stu-id="73969-251">Certificate</span></span></th>
<th><span data-ttu-id="73969-252">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="73969-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="73969-253">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="73969-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="73969-254">예제</span><span class="sxs-lookup"><span data-stu-id="73969-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73969-255">기본</span><span class="sxs-lookup"><span data-stu-id="73969-255">Default</span></span></p></td>
<td><p><span data-ttu-id="73969-256">SBA의 FQDN</span><span class="sxs-lookup"><span data-stu-id="73969-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="73969-257">호흡. &lt;MICROSOFT.RTC.MANAGEMENT.XDS.SIPDOMAIN OBJECT&gt; (SIP 도메인 당 하나의 항목 필요)</span><span class="sxs-lookup"><span data-stu-id="73969-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="73969-258">SN = sba01; SAN = sip .com; SAN = sip. p m c</span><span class="sxs-lookup"><span data-stu-id="73969-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="73969-259">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73969-259">See Also</span></span>


[<span data-ttu-id="73969-260">Lync Server 2013의 와일드 카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="73969-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

