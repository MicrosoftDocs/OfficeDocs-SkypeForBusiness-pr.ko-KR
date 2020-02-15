---
title: 'Lync Server 2013: 클라이언트 부트스트랩 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3827bf913c4108c1105376a6f178598a2fb45a06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="5db44-102">Lync Server 2013에서 클라이언트 부트스트랩 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5db44-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db44-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5db44-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5db44-104">GPMC (그룹 정책 관리 콘솔) 및 그룹 정책 개체 편집기는 그룹 정책을 관리 하는 데 사용 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="5db44-105">Office 그룹 정책 관리 템플릿에는 도메인의 그룹 정책 개체에 대해 구성 하는 레지스트리 기반 정책 설정을 포함 하는 adml (ADML) 관리 템플릿, Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5db44-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="5db44-106">ADML 파일은 ADMX 파일에 대 한 언어 관련 보완 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="5db44-107">각 ADMX 및 ADML 파일에는 단일 Office 응용 프로그램에 대 한 정책 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="5db44-108">자세한 내용은 Office 2013 설명서에서 "Office 2013 관리 템플릿 파일 (ADMX, ADML)"를 참조 하세요 <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span><span class="sxs-lookup"><span data-stu-id="5db44-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="5db44-109">Lync 2013에는 사용자가 처음으로 서버에 로그인 하기 전에 구성 해야 하는 몇 가지 클라이언트 부트스트랩 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="5db44-110">예를 들어 클라이언트에서 로그인이 완료 될 때까지 사용 해야 하는 기본 서버 및 보안 모드를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="5db44-111">그룹 정책을 사용 하 여 사용자의 컴퓨터 레지스트리를 설정 하 고 서버에서 대역내 프로 비전 설정을 받기 시작 하기 전에 이러한 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="5db44-112">다음 표에는 Lync 2013에 사용할 수 있는 그룹 정책 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="5db44-113">Lync 2013용 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5db44-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5db44-114">그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5db44-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="5db44-115">설명</span><span class="sxs-lookup"><span data-stu-id="5db44-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5db44-116">서버 지정</span><span class="sxs-lookup"><span data-stu-id="5db44-116">Specify Server</span></span><br />
<span data-ttu-id="5db44-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="5db44-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="5db44-118">Lync 2013에서 로그인 중에 사용할 전송 및 서버를 식별 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="5db44-119">이 설정 내에서 다음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5db44-120">ServerAddressExternal: 외부 방화벽 외부에서 연결할 때 클라이언트 및 페더레이션 대화 상대에 사용 되는 서버 이름 또는 IP 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="5db44-121">ServerAddressInternal: 조직의 방화벽 내부에서 클라이언트에 연결할 때 사용 되는 서버 이름이 나 IP 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="5db44-122">Transport: TCP (전송 제어 프로토콜) 또는 TLS (전송 계층 보안)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-123">추가 서버 버전 지원</span><span class="sxs-lookup"><span data-stu-id="5db44-123">Additional server versions supported</span></span><br />
<span data-ttu-id="5db44-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="5db44-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="5db44-125">Lync Server 2013에서 로그온 하는 서버 버전 이름 목록을 세미콜론으로 구분 하 여 지정 하며, 기본적으로 지원 되는 서버 버전과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-126">로그인 오류 로그의 자동 업로드 사용 안 함 (Disable자동 Sendtracing)</span><span class="sxs-lookup"><span data-stu-id="5db44-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="5db44-127">분석을 위해 Lync Server에 로그인 오류 로그를 자동으로 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="5db44-128">로그인이 성공한 경우 로그가 자동으로 업로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="5db44-129">이 정책을 구성 하지 않으면 다음과 같은 결과가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5db44-130">Lync Online 사용자의 경우: 로그인 오류 로그가 자동으로 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5db44-131">Lync 온-프레미스 사용자: 업로드 하기 전에 사용자에 게 확인 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="5db44-132">이 설정을 사용 하지 않으면 Lync 온-프레미스 및 Lync Online 사용자에 대해 로그인 로그가 Lync Server에 자동으로 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="5db44-133">이 설정을 사용 하도록 설정 하면 로그인 로그가 자동으로 업로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-134">SIP 연결에 대해 HTTP 대체 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5db44-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="5db44-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="5db44-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="5db44-136">TLS 또는 TCP를 사용할 수 없는 경우 Lync Server에서 HTTP를 사용 하 여 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="5db44-137">기본적으로 Lync에서는 먼저 TLS 또는 TCP를 사용 하 여 서버에 연결을 시도 하며, 이러한 전송 방법이 모두 실패 하면 Lync는 HTTP를 사용 하 여 연결을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="5db44-138">이 정책을 사용하여 대체 HTTP 연결 시도를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-139">로그온 자격 증명 필요</span><span class="sxs-lookup"><span data-stu-id="5db44-139">Require logon credentials</span></span><br />
<span data-ttu-id="5db44-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="5db44-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="5db44-141">사용자가 SIP 서버에 로그인 하는 동안 Windows 자격 증명을 자동으로 사용 하지 않고 Lync에 대 한 로그온 자격 증명을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-142">서버 버전 검사 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5db44-142">Disable server version check</span></span><br />
<span data-ttu-id="5db44-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="5db44-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="5db44-144">이 정책을 1로 설정 하면 Lync에서 로그인 하기 전에 서버 이름과 버전을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="5db44-145">기본적으로 Lync는 로그인 하기 전에 이러한 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-146">BITS를 사용 하 여 주소록 서비스 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="5db44-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="5db44-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="5db44-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="5db44-148">Lync에서 BITS (Background Intelligent Transfer Service)를 사용 하 여 주소록 서비스 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-149">SIP 보안 모드 구성</span><span class="sxs-lookup"><span data-stu-id="5db44-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="5db44-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="5db44-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="5db44-151">Lync에서 인스턴트 메시지를 보다 안전 하 게 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="5db44-152">이 정책은 Windows .NET 또는 Microsoft Exchange Server 서비스에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="5db44-153">이 정책 설정을 구성 하지 않으면 Lync에서 모든 전송을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="5db44-154">그러나 TLS를 사용 하지 않고 서버에서 사용자를 인증 하는 경우 Lync에서 NTLM 또는 Kerberos 인증을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-155">전체 주소록 다운로드 초기 지연</span><span class="sxs-lookup"><span data-stu-id="5db44-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="5db44-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="5db44-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="5db44-157">GAL (전체 주소 목록)이 다운로드 될 때 까지의 기간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="5db44-158">기본값은 60 분 이며,이는 서버가 GAL 파일의 다운로드를 대기 하는 시간을 0 ~ 60 분 사이의 임의 기간 동안 지연 시키는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-159">사용자가 Microsoft Lync를 실행 하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="5db44-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="5db44-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="5db44-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="5db44-161">사용자가 Lync를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-161">Prevents users from running Lync.</span></span> <span data-ttu-id="5db44-162">컴퓨터 구성 및 사용자 구성 모두에서 이 정책 설정을 구성할 수 있지만 컴퓨터 구성의 정책 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-163">사용자 암호 저장 허용</span><span class="sxs-lookup"><span data-stu-id="5db44-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="5db44-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="5db44-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="5db44-165">Lync에서 암호를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-166">SIP 압축 모드 구성</span><span class="sxs-lookup"><span data-stu-id="5db44-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="5db44-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="5db44-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="5db44-p112">SIP 압축을 설정할 시점을 지정합니다. 기본적으로 SIP 압축은 어댑터 속도에 따라 설정됩니다. 이 정책을 설정하면 로그인 시간이 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-171">신뢰할 수 있는 도메인 목록</span><span class="sxs-lookup"><span data-stu-id="5db44-171">Trusted Domain List</span></span><br />
<span data-ttu-id="5db44-172">(TrustModelData)</span><span class="sxs-lookup"><span data-stu-id="5db44-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="5db44-173">고객 SIP 도메인의 접두사와 일치 하지 않는 신뢰할 수 있는 도메인을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5db44-p113">서버에 구성된 정책은 사용자가 구성한 그룹 정책 설정 또는 클라이언트 옵션보다 우선적으로 적용됩니다. 다음 표에는 설정이 충돌하는 경우의 적용되는 순서가 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="5db44-176">그룹 정책 우선 순위</span><span class="sxs-lookup"><span data-stu-id="5db44-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5db44-177">우선권</span><span class="sxs-lookup"><span data-stu-id="5db44-177">Precedence</span></span></th>
<th><span data-ttu-id="5db44-178">설정 위치 또는 방법</span><span class="sxs-lookup"><span data-stu-id="5db44-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5db44-179">1 </span><span class="sxs-lookup"><span data-stu-id="5db44-179">1</span></span></p></td>
<td><p><span data-ttu-id="5db44-180">Lync Server 2013 대역내 프로 비전</span><span class="sxs-lookup"><span data-stu-id="5db44-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-181">2 </span><span class="sxs-lookup"><span data-stu-id="5db44-181">2</span></span></p></td>
<td><p><span data-ttu-id="5db44-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="5db44-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db44-183">3 </span><span class="sxs-lookup"><span data-stu-id="5db44-183">3</span></span></p></td>
<td><p><span data-ttu-id="5db44-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="5db44-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db44-185">4 </span><span class="sxs-lookup"><span data-stu-id="5db44-185">4</span></span></p></td>
<td><p><span data-ttu-id="5db44-186">Lync 2013의 Lync-옵션 대화 상자</span><span class="sxs-lookup"><span data-stu-id="5db44-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="5db44-187">Lync 2013 관리 템플릿 파일을 사용 하 여 그룹 정책 설정을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="5db44-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="5db44-188">모든 언어 중립적 ADMX 파일을 포함할 루트 수준 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="5db44-189">예를 들어 다음과 같이 이 위치에 도메인 컨트롤러의 중앙 저장소에 대한 루트 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5db44-190">이 절차에서는 도메인의 여러 컴퓨터를 관리 하려는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="5db44-191">이 경우에는 주 도메인 컨트롤러의 Sysvol 폴더에 있는 중앙 저장소에 템플릿을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="5db44-192">이를 통해 도메인 관리 템플릿에 대한 복제된 중앙 저장 위치가 마련됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="5db44-193">사용할 각 언어에 대 한 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="5db44-194">이러한 하위 폴더는 언어별 ADML 리소스 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="5db44-195">예를 들어 다음 위치에는 미국 영어 (EN-US) 용 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5db44-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

