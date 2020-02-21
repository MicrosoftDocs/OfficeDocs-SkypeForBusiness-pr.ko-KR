---
title: 'Lync Server 2013: 단순 Url 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6bbbe8650ae1d7746c9b87ecf4518236f8b1575
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="692a0-102">Lync Server 2013의 단순 Url 계획</span><span class="sxs-lookup"><span data-stu-id="692a0-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="692a0-103">_**마지막으로 수정 된 항목:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="692a0-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="692a0-104">단순 Url은 사용자에 게 모임 참석을 보다 용이 하 게 하며, 관리자가 Lync Server 관리 도구를 보다 쉽게 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="692a0-105">Lync Server에서는 다음과 같은 세 가지 단순 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="692a0-106">**모임**은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="692a0-107">모임 단순 URL의 예는 https://meet.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="692a0-108">특정 모임에 대 한 URL은 https://meet.contoso.com/ *사용자 이름*/7322994이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="692a0-109">모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="692a0-110">**전화 접속** 을 사용 하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="692a0-111">이 페이지에는 전화 회의 전화 번호를 사용 가능한 언어로 표시 하 고, 전화 회의 정보 (예약 하지 않아도 되는 모임의 경우)와 개인 식별 번호 관리를 지원 합니다 ( PIN)을 지정 하 고 회의 정보를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="692a0-112">전화 접속 단순 URL은 모임에 전화를 거는 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="692a0-113">전화 접속 단순 URL의 예는 https://dialin.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="692a0-114">**관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="692a0-115">조직의 방화벽 내에 있는 모든 컴퓨터에서 관리자는 브라우저에 관리 단순 URL을 입력 하 여 Lync Server 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="692a0-116">관리 단순 URL은 조직의 내부 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="692a0-117">관리 단순 URL의 예는https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="692a0-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="692a0-118">단순 URL 범위</span><span class="sxs-lookup"><span data-stu-id="692a0-118">Simple URL Scope</span></span>

<span data-ttu-id="692a0-119">전역 범위에서 적용되도록 단순 URL을 구성하거나 조직의 각 중앙 사이트에 대해 서로 다른 단순 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="692a0-120">전역 범위 단순 URL과 사이트 범위 단순 URL이 모두 지정 된 경우 사이트 범위 단순 URL이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="692a0-p105">대부분의 경우 전역 수준에서만 단순 URL을 설정하여 사이트 간에 이동하더라도 사용자의 모임 단순 URL이 변경되지 않도록 하는 것이 좋습니다. 단, 여러 사이트의 전화 접속 사용자에 서로 다른 전화 번호를 사용해야 하는 조직은 예외입니다. 사이트에서 하나의 단순 URL(예: 전화 접속 단순 URL)을 사이트 수준 단순 URL로 설정한 경우에는 해당 사이트의 다른 단순 URL도 사이트 수준으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="692a0-124">사이트 범위가 지정 된 단순 Url을 사용 하도록 선택 하는 경우 사용자가 다른 사이트의 프런트 엔드 풀 사이를 이동할 수 없는 경우 모임 단순 Url이 사이트 간에 다른 사용자가 예약 된 모든 모임에 대해 일정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="692a0-125">여기에는 백업 관계의 풀이 별도의 사이트에 있는 장애 조치 (failover) 시나리오가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="692a0-126">사이트 범위가 지정 된 단순 Url이 배포 되는 사이트 간에 장애 조치 (failover)를 수행 해야 하는 경우에는 URL 범위로 인해 사용자가 자신의 모임에 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="692a0-127">자세한 내용을 보려면 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">get-cssimpleurlconfiguration</A>를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="692a0-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="692a0-128">토폴로지 작성기에서 전역 단순 Url을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="692a0-129">사이트 수준에서 단순 URL을 설정하려면 Set-CsSimpleURLConfiguration cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="692a0-130">단순 URL 이름 지정</span><span class="sxs-lookup"><span data-stu-id="692a0-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="692a0-p108">단순 URL의 이름을 지정할 때 권장되는 세 가지 옵션이 있습니다. 선택한 옵션에 따라 단순 URL을 지원하는 DNS A 레코드 및 인증서 설정 방법이 결정됩니다. 각 옵션에서는 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="692a0-134">보유한 SIP 도메인 수에 관계없이 전화 접속 단순 URL과 관리 단순 URL은 항상 전체 조직에서 각각 하나씩만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="692a0-135">필요한 DNS A 레코드 및 인증서에 대 한 자세한 내용은 계획 설명서에서 lync server [2013의 단순 url에 대 한 DNS 요구](lync-server-2013-dns-requirements-for-simple-urls.md) 사항 및 [lync server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="692a0-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="692a0-136">옵션 1에서는 각 단순 URL에 대한 새 SIP 도메인 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="692a0-137">이 옵션을 사용하는 경우 각 단순 URL에 대해 별도의 DNS A 레코드가 필요하며 각 모임 단순 URL의 이름이 인증서에 지정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="692a0-138">단순 URL 이름 지정 옵션 1</span><span class="sxs-lookup"><span data-stu-id="692a0-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="692a0-139"><strong>단순 URL</strong></span><span class="sxs-lookup"><span data-stu-id="692a0-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="692a0-140"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="692a0-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692a0-141">조건</span><span class="sxs-lookup"><span data-stu-id="692a0-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="692a0-142">https://meet.contoso.com, https://meet.fabrikam.com등은 (조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="692a0-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="692a0-143">전화 접속</span><span class="sxs-lookup"><span data-stu-id="692a0-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692a0-144">관리자</span><span class="sxs-lookup"><span data-stu-id="692a0-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="692a0-p109">옵션 2를 사용하는 경우에는 단순 URL이 도메인 이름 lync.contoso.com을 기반으로 하므로 세 가지 유형의 단순 URL 모두에서 사용할 수 있는 DNS A 레코드가 하나만 있으면 됩니다. 이 DNS A 레코드는 lync.contoso.com을 참조합니다. 조직의 다른 SIP 도메인에 대해서는 여전히 별도의 DNS A 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="692a0-149">단순 URL 이름 지정 옵션 2</span><span class="sxs-lookup"><span data-stu-id="692a0-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="692a0-150"><strong>단순 URL</strong></span><span class="sxs-lookup"><span data-stu-id="692a0-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="692a0-151"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="692a0-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692a0-152">조건</span><span class="sxs-lookup"><span data-stu-id="692a0-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="692a0-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet등은 (조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="692a0-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="692a0-154">전화 접속</span><span class="sxs-lookup"><span data-stu-id="692a0-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692a0-155">관리자</span><span class="sxs-lookup"><span data-stu-id="692a0-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="692a0-156">옵션 3은 많은 SIP 도메인이 있고 각각에 별도의 모임 단순 URL을 사용하지만 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려는 경우에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="692a0-157">단순 URL 이름 지정 옵션 3</span><span class="sxs-lookup"><span data-stu-id="692a0-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="692a0-158"><strong>단순 URL</strong></span><span class="sxs-lookup"><span data-stu-id="692a0-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="692a0-159"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="692a0-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692a0-160">조건</span><span class="sxs-lookup"><span data-stu-id="692a0-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="692a0-161">전화 접속</span><span class="sxs-lookup"><span data-stu-id="692a0-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692a0-162">관리자</span><span class="sxs-lookup"><span data-stu-id="692a0-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="692a0-163">단순 URL 이름 지정 및 유효성 검사 규칙</span><span class="sxs-lookup"><span data-stu-id="692a0-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="692a0-164">토폴로지 작성기 및 Lync Server 관리 셸 cmdlet은 단순 Url에 대 한 몇 가지 유효성 검사 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="692a0-165">모임 및 전화 접속 단순 URL은 필수 설정이지만 관리 단순 URL은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="692a0-166">모임 단순 URL은 SIP 도메인마다 별도의 URL이 있어야 하지만 전화 접속 단순 URL과 관리 단순 URL은 전체 조직에 하나만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="692a0-167">조직의 각 단순 URL은 고유한 이름을 사용해야 하며 다른 단순 URL의 접두사가 될 수 없습니다(예: lync.contoso.com/Meet를 모임 단순 URL로 설정하고 lync.contoso.com/Meet/Dialin을 전화 접속 단순 URL로 설정할 수는 없음).</span><span class="sxs-lookup"><span data-stu-id="692a0-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="692a0-168">단순 URL 이름에는 풀의 FQDN을 포함할 수 없으며 모든 포트 정보 (예: 허용 되지 않음 https://FQDN:88/meet )가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="692a0-169">모든 단순 URL은 https:// 접두사로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="692a0-p112">단순 URL은 영숫자(즉, a-z, A-Z, 0-9 및 마침표(.))만 포함할 수 있습니다. 다른 문자를 사용하면 단순 URL이 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="692a0-172">배포 후 단순 URL 변경</span><span class="sxs-lookup"><span data-stu-id="692a0-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="692a0-173">초기 배포 후 단순 URL을 변경하려면 단순 URL의 DNS 레코드 및 인증서가 이러한 변경으로 인해 받을 수 있는 영향을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="692a0-174">단순 URL의 기준이 변경되면 DNS 레코드 및 인증서도 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="692a0-175">예를 들어에서 https://lync.contoso.com/Meet 를 https://meet.contoso.com 변경 하면 기본 URL이 lync.contoso.com에서 MEET.CONTOSO.COM으로 변경 되므로 DNS 레코드 및 인증서를 변경 하 여 meet.contoso.com를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="692a0-176">단순 URL을에서 https://lync.contoso.com/Meet 로 https://lync.contoso.com/Meetings변경한 경우 lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="692a0-177">그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 **CsComputer를 사용** 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a0-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="692a0-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="692a0-178">See Also</span></span>


[<span data-ttu-id="692a0-179">Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="692a0-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

