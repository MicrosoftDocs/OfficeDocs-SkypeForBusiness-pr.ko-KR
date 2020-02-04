---
title: 'Lync Server 2013: 내부 서버에 대한 인증서 요구 사항'
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
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="d640f-102">Lync Server 2013의 내부 서버에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d640f-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d640f-103">_**마지막으로 수정한 주제:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="d640f-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="d640f-104">Lync Server를 실행 중이 고 인증서가 필요한 내부 서버에는 표준 버전 서버, Enterprise Edition 프런트 엔드 서버, 중재 서버, 이사 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="d640f-105">다음 표에는 이러한 서버에 대 한 인증서 요구 사항이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="d640f-106">Lync 서버 인증서 마법사를 사용 하 여 이러한 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d640f-107">와일드 카드 인증서는 프런트 엔드 풀, 프런트 엔드 서버 또는 디렉터에 있는 간단한 Url과 연결 된 주체 대체 이름에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="d640f-108">와일드 카드 인증서 지원에 대 한 자세한 내용은 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013의 와일드 카드 인증서 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d640f-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d640f-109">내부 서버에는 내부 엔터프라이즈 CA (인증 기관)가 권장 되지만 공용 CA를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="d640f-110">UC (통합 커뮤니케이션) 인증서에 대 한 특정 요구 사항을 준수 하 고 Lync Server 인증서 마법사와 함께 사용할 수 있도록 Microsoft와 제휴 하는 인증서를 제공 하는 공개 Ca 목록은 Microsoft 기술 자료 929395, "Exchange Server 및 통신 서버용 통합 커뮤니케이션 인증서 파트너" 문서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="d640f-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="d640f-111">Exchange 2013와 같은 다른 응용 프로그램 및 서버와의 통신에는 다른 응용 프로그램 및 제품에서 지원 되는 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="d640f-112">2013 릴리스, Lync Server 2013 및 Exchange 2013 및 SharePoint Server를 비롯 한 기타 Microsoft 서버 제품은 서버 간 인증 및 권한 부여를 위한 개방형 권한 부여 (OAuth) 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="d640f-113">자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d640f-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="d640f-114">Windows 7 운영 체제, Windows Server 2008 운영 체제, Windows Server 2008 R2 운영 체제, Windows Vista 운영 체제, Microsoft Lync Phone Edition을 실행 하는 클라이언트에서 연결 하는 경우 Lync Server 2013에 대 한 지원이 포함 되지만 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="d640f-115">SHA-256를 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 SHA-256를 사용 하 여 공용 CA에서 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="d640f-116">다음 표에는 프런트 엔드 풀 및 스탠더드 버전 서버에 대 한 서버 역할별 인증서 요구 사항이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="d640f-117">이러한 모든 기능을 표준 웹 서버 인증서, 개인 키, 내보낼 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="d640f-118">인증서 마법사를 사용 하 여 인증서를 요청할 때 EKU (서버 확장 키 사용)가 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d640f-119">각 인증서 이름은 컴퓨터 스토어에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d640f-120">DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com을 구성한 경우 인증서의 주체 대체 이름에이를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="d640f-121">스탠더드 버전 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="d640f-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="d640f-122">인증</span><span class="sxs-lookup"><span data-stu-id="d640f-122">Certificate</span></span></th>
<th><span data-ttu-id="d640f-123">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d640f-124">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="d640f-125">예</span><span class="sxs-lookup"><span data-stu-id="d640f-125">Example</span></span></th>
<th><span data-ttu-id="d640f-126">메모</span><span class="sxs-lookup"><span data-stu-id="d640f-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d640f-127">기본값</span><span class="sxs-lookup"><span data-stu-id="d640f-127">Default</span></span></p></td>
<td><p><span data-ttu-id="d640f-128">풀의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="d640f-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="d640f-129">풀의 FQDN과 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="d640f-130">여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="d640f-131">이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 DNS (strict Domain Name System) 일치가 필요 하면 sipdomain (각 SIP 도메인에 대해)에 대 한 항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="d640f-132">SN = se01; SAN = se01</span><span class="sxs-lookup"><span data-stu-id="d640f-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-133">이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p</span><span class="sxs-lookup"><span data-stu-id="d640f-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="d640f-134">스탠더드 버전의 서버에서 서버 FQDN은 풀 FQDN과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="d640f-135">마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="d640f-136">서버 간 인증에도이 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d640f-137">웹 내부</span><span class="sxs-lookup"><span data-stu-id="d640f-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="d640f-138">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d640f-139">다음을 각각 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d640f-140">내부 웹 FQDN (서버의 FQDN과 동일)</span><span class="sxs-lookup"><span data-stu-id="d640f-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="d640f-141">간단한 Url 소개</span><span class="sxs-lookup"><span data-stu-id="d640f-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="d640f-142">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-143">관리 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-144">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d640f-145">SN = se01; SAN = se01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-146">와일드 카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="d640f-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d640f-147">SN = se01; SAN = se01. SAN = \*. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d640f-148">토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="d640f-149">여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d640f-150">간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d640f-151">웹 외부</span><span class="sxs-lookup"><span data-stu-id="d640f-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="d640f-152">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d640f-153">다음을 각각 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d640f-154">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-155">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-156">SIP 도메인당 간단한 Url 소개</span><span class="sxs-lookup"><span data-stu-id="d640f-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="d640f-157">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d640f-158">SN = se01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-159">와일드 카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="d640f-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d640f-160">SN = se01; SAN = webcon01. SAN = \*. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d640f-161">여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d640f-162">간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="d640f-163">프런트 엔드 풀의 프론트 엔드 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="d640f-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="d640f-164">인증</span><span class="sxs-lookup"><span data-stu-id="d640f-164">Certificate</span></span></th>
<th><span data-ttu-id="d640f-165">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d640f-166">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="d640f-167">예</span><span class="sxs-lookup"><span data-stu-id="d640f-167">Example</span></span></th>
<th><span data-ttu-id="d640f-168">메모</span><span class="sxs-lookup"><span data-stu-id="d640f-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d640f-169">기본값</span><span class="sxs-lookup"><span data-stu-id="d640f-169">Default</span></span></p></td>
<td><p><span data-ttu-id="d640f-170">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d640f-171">풀의 FQDN 및 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="d640f-172">여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="d640f-173">이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sipdomain (사용 하는 각 SIP 도메인)에 대 한 항목도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="d640f-174">SN = eepool. m a c. SAN = eepool. m a c. SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="d640f-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-175">이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p</span><span class="sxs-lookup"><span data-stu-id="d640f-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="d640f-176">마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="d640f-177">서버 간 인증에도이 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d640f-178">웹 내부</span><span class="sxs-lookup"><span data-stu-id="d640f-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="d640f-179">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d640f-180">다음을 각각 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d640f-181">내부 웹 FQDN (서버의 FQDN과 같지 않음)</span><span class="sxs-lookup"><span data-stu-id="d640f-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="d640f-182">서버 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-183">Lync 풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-184">간단한 Url 소개</span><span class="sxs-lookup"><span data-stu-id="d640f-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="d640f-185">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-186">관리 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-187">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d640f-188">SN = ee01; SAN = ee01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-189">와일드 카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="d640f-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d640f-190">SN = ee01; SAN = ee01. SAN = \*. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d640f-191">여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d640f-192">간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d640f-193">웹 외부</span><span class="sxs-lookup"><span data-stu-id="d640f-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="d640f-194">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d640f-195">다음을 각각 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d640f-196">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-197">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-198">관리 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-199">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d640f-200">SN = ee01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-201">와일드 카드 인증서 사용:</span><span class="sxs-lookup"><span data-stu-id="d640f-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d640f-202">SN = ee01; SAN = webcon01. SAN = \*. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d640f-203">여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d640f-204">간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="d640f-205">디렉터에 대 한 인증서</span><span class="sxs-lookup"><span data-stu-id="d640f-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d640f-206">인증</span><span class="sxs-lookup"><span data-stu-id="d640f-206">Certificate</span></span></th>
<th><span data-ttu-id="d640f-207">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d640f-208">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="d640f-209">예</span><span class="sxs-lookup"><span data-stu-id="d640f-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d640f-210">기본값</span><span class="sxs-lookup"><span data-stu-id="d640f-210">Default</span></span></p></td>
<td><p><span data-ttu-id="d640f-211">디렉터 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="d640f-212">디렉터의 FQDN, 디렉터 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="d640f-213">이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sipdomain (사용 하는 각 SIP 도메인)에 대 한 항목도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="d640f-214">SN = dir-pool.contoso.com SAN = dir-pool.contoso.com SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="d640f-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-215">이 디렉터 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a m;이 필요 합니다. SAN = sip. c a p</span><span class="sxs-lookup"><span data-stu-id="d640f-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d640f-216">웹 내부</span><span class="sxs-lookup"><span data-stu-id="d640f-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="d640f-217">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d640f-218">다음을 각각 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d640f-219">내부 웹 FQDN (서버의 FQDN과 동일)</span><span class="sxs-lookup"><span data-stu-id="d640f-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="d640f-220">서버 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-221">Lync 풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-222">간단한 Url 소개</span><span class="sxs-lookup"><span data-stu-id="d640f-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="d640f-223">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-224">관리 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-225">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d640f-226">SN = dir01; SAN = dir01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-227">SN = dir01; SAN = dir01 SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="d640f-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d640f-228">웹 외부</span><span class="sxs-lookup"><span data-stu-id="d640f-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="d640f-229">서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d640f-230">다음을 각각 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d640f-231">외부 웹 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="d640f-232">전화 접속 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-233">관리 간단한 URL</span><span class="sxs-lookup"><span data-stu-id="d640f-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d640f-234">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d640f-235">디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="d640f-236">SN = dir01; SAN = directorwebcon01 SAN =. m a c. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c</span><span class="sxs-lookup"><span data-stu-id="d640f-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d640f-237">SN = dir01; SAN = directorwebcon01 SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="d640f-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d640f-238">독립 실행형 중재 서버 풀을 사용 하는 경우에는 다음 표에 나열 된 인증서가 각 서버의 중재 서버에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="d640f-239">프런트 엔드 서버와 중재 서버를 collocate 경우이 항목의 앞부분에 있는 "프런트 엔드 서버에 대 한 인증서" 표에 나열 된 인증서가 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="d640f-240">독립 실행형 중재 서버용 인증서</span><span class="sxs-lookup"><span data-stu-id="d640f-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d640f-241">인증</span><span class="sxs-lookup"><span data-stu-id="d640f-241">Certificate</span></span></th>
<th><span data-ttu-id="d640f-242">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d640f-243">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="d640f-244">예</span><span class="sxs-lookup"><span data-stu-id="d640f-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d640f-245">기본값</span><span class="sxs-lookup"><span data-stu-id="d640f-245">Default</span></span></p></td>
<td><p><span data-ttu-id="d640f-246">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d640f-247">풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="d640f-248">풀 구성원 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="d640f-249">SN = medsvr-pool.contoso.net SAN = medsvr-pool.contoso.net SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="d640f-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="d640f-250">Survivable Branch 기기에 대 한 인증서</span><span class="sxs-lookup"><span data-stu-id="d640f-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d640f-251">인증</span><span class="sxs-lookup"><span data-stu-id="d640f-251">Certificate</span></span></th>
<th><span data-ttu-id="d640f-252">주체 이름/일반 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d640f-253">주체 대체 이름</span><span class="sxs-lookup"><span data-stu-id="d640f-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="d640f-254">예</span><span class="sxs-lookup"><span data-stu-id="d640f-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d640f-255">기본값</span><span class="sxs-lookup"><span data-stu-id="d640f-255">Default</span></span></p></td>
<td><p><span data-ttu-id="d640f-256">기기의 FQDN</span><span class="sxs-lookup"><span data-stu-id="d640f-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="d640f-257">SIP. &lt;SIPDOMAIN&gt; (SIP 도메인당 하나의 항목이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="d640f-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="d640f-258">SN = sba01; SAN = sip. SAN = sip. c a p</span><span class="sxs-lookup"><span data-stu-id="d640f-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d640f-259">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d640f-259">See Also</span></span>


[<span data-ttu-id="d640f-260">Lync Server 2013의 와일드카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="d640f-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

