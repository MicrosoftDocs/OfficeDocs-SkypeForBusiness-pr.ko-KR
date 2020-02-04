---
title: 'Lync Server 2013: 단순 URL 계획'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="913e8-102">Lync Server 2013의 단순 URL 계획</span><span class="sxs-lookup"><span data-stu-id="913e8-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="913e8-103">_**마지막으로 수정한 주제:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="913e8-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="913e8-104">간단한 Url을 사용 하면 사용자가 쉽게 모임에 참가할 수 있으며 Lync Server 관리 도구를 사용 하는 것이 관리자에 게 더욱 간편해 집니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="913e8-105">Lync Server는 다음과 같은 세 가지 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="913e8-106">**회의** 는 사이트 또는 조직의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="913e8-107">소개 간단한 URL의 예는 https://meet.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="913e8-108">특정 모임의 URL은 https://meet.contoso.com/ *사용자 이름*/7322994이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="913e8-109">모임에 참여 하는 간단한 URL을 사용 하 여 모임을 연결 하는 링크는 이해 하기 쉬우며, 의사 소통 및 배포 하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="913e8-110">**전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="913e8-111">이 페이지에는 전화 회의 전화 접속 번호가 사용 가능한 언어로 표시 되 고, 회의 정보 (예약할 필요는 없음), 전화 회의 DTMF 컨트롤, 개인 식별 번호 관리 지원 ( PIN) 및 지정 된 회의 정보.</span><span class="sxs-lookup"><span data-stu-id="913e8-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="913e8-112">모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="913e8-113">전화 접속 간단한 URL의 예는 https://dialin.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="913e8-114">**관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="913e8-115">조직의 방화벽 내에 있는 컴퓨터에서 관리자는 브라우저에 관리 간단한 URL을 입력 하 여 Lync Server 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="913e8-116">관리 단순 URL은 조직 내부입니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="913e8-117">관리 간단한 URL의 예는https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="913e8-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="913e8-118">간단한 URL 범위</span><span class="sxs-lookup"><span data-stu-id="913e8-118">Simple URL Scope</span></span>

<span data-ttu-id="913e8-119">전역 범위를 포함 하도록 간단한 Url을 구성 하거나 조직의 각 중앙 사이트에 대해 서로 다른 간단한 Url을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="913e8-120">전역 범위 단순 URL과 사이트 범위 단순 URL이 모두 지정 된 경우 사이트 범위 단순 URL이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="913e8-121">대부분의 경우 사용자가 한 사이트에서 다른 사이트로 이동 하는 경우 단순한 URL이 변경 되지 않도록 전역 수준 에서만 간단한 Url을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="913e8-122">이 예외는 다른 사이트의 전화 접속 사용자에 게 다른 전화 번호를 사용 해야 하는 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="913e8-123">사이트의 간단한 URL (예: 전화 접속 간단한 URL)을 사이트 수준 간단한 URL로 설정한 경우에는 해당 사이트의 다른 간단한 url도 사이트 수준으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="913e8-124">사이트 범위 단순 Url을 사용 하도록 선택한 경우에는 사용자가 다른 사이트의 프런트 엔드 풀 간을 이동할 수 없습니다. 모임 단순 Url이 사이트 간에 서로 다르기 때문에 사용자가 예약 된 모든 모임에 대 한 일정을 재조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="913e8-125">여기에는 백업 관계의 풀이 별도의 사이트에 있는 장애 조치 시나리오가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="913e8-126">사이트 범위 단순 Url이 배포 되는 사이트 간에 장애 조치를 해야 하는 경우 URL 범위 때문에 사용자가 자신의 모임에 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="913e8-127">자세한 내용은 Get-help를 확인 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="913e8-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="913e8-128">토폴로지 작성기에서 전역 단순 Url을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="913e8-129">사이트 수준에서 간단한 URL을 설정 하려면 Set-CsSimpleURLConfiguration cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="913e8-130">간단한 Url 이름 지정</span><span class="sxs-lookup"><span data-stu-id="913e8-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="913e8-131">간단한 Url의 이름을 지정 하는 데 권장 되는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="913e8-132">선택 하는 옵션에 따라 간단한 Url을 지 원하는 DNS 레코드 및 인증서 설정 방법에 대 한 영향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="913e8-133">각 옵션에서 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="913e8-134">사용 중인 SIP 도메인의 수에 관계 없이 모든 조직에서 전화 접속 및 관리자 용으로 하나의 간단한 URL만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="913e8-135">필요한 DNS A 레코드 및 인증서에 대 한 자세한 내용은 [Lync server 2013의 간단한 url에 대 한 DNS 요구 사항](lync-server-2013-dns-requirements-for-simple-urls.md) 및 계획 설명서의 [lync server 2013의 내부 서버에 대 한 인증서 요구](lync-server-2013-certificate-requirements-for-internal-servers.md) 사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="913e8-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="913e8-136">옵션 1에서 각 단순 URL에 대 한 새 SIP 도메인 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="913e8-137">이 옵션을 사용 하는 경우 각 단순 URL에 대 한 별도의 DNS A 레코드가 필요 하며, 각 일치 하는 단순 URL은 인증서에 명명 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="913e8-138">간단한 URL 명명 옵션 1</span><span class="sxs-lookup"><span data-stu-id="913e8-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="913e8-139"><strong>간단한 URL</strong></span><span class="sxs-lookup"><span data-stu-id="913e8-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="913e8-140"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="913e8-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e8-141">시켜</span><span class="sxs-lookup"><span data-stu-id="913e8-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="913e8-142">https://meet.contoso.comhttps://meet.fabrikam.com(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="913e8-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="913e8-143">전화 접속</span><span class="sxs-lookup"><span data-stu-id="913e8-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e8-144">관리자</span><span class="sxs-lookup"><span data-stu-id="913e8-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="913e8-145">옵션 2에서는 간단한 Url이 도메인 이름 lync.contoso.com를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="913e8-146">따라서 세 가지 유형의 간단한 Url을 모두 사용할 수 있는 하나의 DNS A 레코드도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="913e8-147">이 DNS A 레코드는 lync.contoso.com를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="913e8-148">또한 조직의 다른 SIP 도메인에 대 한 별도의 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="913e8-149">간단한 URL 명명 옵션 2</span><span class="sxs-lookup"><span data-stu-id="913e8-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="913e8-150"><strong>간단한 URL</strong></span><span class="sxs-lookup"><span data-stu-id="913e8-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="913e8-151"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="913e8-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e8-152">시켜</span><span class="sxs-lookup"><span data-stu-id="913e8-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="913e8-153">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="913e8-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="913e8-154">전화 접속</span><span class="sxs-lookup"><span data-stu-id="913e8-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e8-155">관리자</span><span class="sxs-lookup"><span data-stu-id="913e8-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="913e8-156">옵션 3은 많은 SIP 도메인이 있는 경우 각 사용자에 게 별도의 단순 Url을 사용 하도록 하 고, 이러한 간단한 Url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려는 경우에 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="913e8-157">간단한 URL 명명 옵션 3</span><span class="sxs-lookup"><span data-stu-id="913e8-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="913e8-158"><strong>간단한 URL</strong></span><span class="sxs-lookup"><span data-stu-id="913e8-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="913e8-159"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="913e8-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e8-160">시켜</span><span class="sxs-lookup"><span data-stu-id="913e8-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="913e8-161">전화 접속</span><span class="sxs-lookup"><span data-stu-id="913e8-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e8-162">관리자</span><span class="sxs-lookup"><span data-stu-id="913e8-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="913e8-163">간단한 URL 명명 및 유효성 검사 규칙</span><span class="sxs-lookup"><span data-stu-id="913e8-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="913e8-164">토폴로지 작성기 및 Lync Server Management Shell cmdlet은 간단한 Url에 대 한 여러 가지 유효성 검사 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="913e8-165">간단한 Url을 시작 및 전화 접속으로 설정 해야 하지만 관리자 용으로 설정 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="913e8-166">각 SIP 도메인에는 별도의 단순 URL이 필요 하지만, 전체 조직에 대해 하나의 전화 접속 단순 url과 하나의 관리자 단순 URL만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="913e8-167">조직의 각 단순 URL은 고유한 이름을 가져야 하 고 다른 간단한 URL의 접두사가 될 수 없습니다 (예를 들어, lync.contoso.com/Meet를 사용 하 여 단순한 url로 시작 하 고 lync.contoso.com/Meet/Dialin를 전화 접속 간단한 URL로 설정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="913e8-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="913e8-168">간단한 URL 이름에는 풀의 FQDN 또는 포트 정보 (예: 허용 되지 않음) https://FQDN:88/meet 가 포함 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="913e8-169">모든 단순 Url은 https://접두사로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="913e8-170">간단한 Url에는 영숫자 문자 (a-z, A-z, 0-9, 마침표 (.)만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="913e8-171">다른 문자를 사용 하는 경우 간단한 Url이 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="913e8-172">배포 후 간단한 Url 변경</span><span class="sxs-lookup"><span data-stu-id="913e8-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="913e8-173">초기 배포 후 간단한 URL을 변경 하는 경우에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 영향을 주는 방식을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="913e8-174">간단한 URL의 기본이 변경 되는 경우 DNS 레코드 및 인증서도 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="913e8-175">예를 들어 lync.contoso.com에서 https://lync.contoso.com/Meet 로 https://meet.contoso.com 변경 하면 기본 URL이 MEET.CONTOSO.COM로 변경 되므로 DNS 레코드와 인증서를 변경 해야 meet.contoso.com을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="913e8-176">간단한 URL을에서 https://lync.contoso.com/Meet 으로 https://lync.contoso.com/Meetings변경한 경우 lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="913e8-177">그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 **-CsComputer** 를 실행 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913e8-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="913e8-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="913e8-178">See Also</span></span>


[<span data-ttu-id="913e8-179">Lync Server 2013의 단순 URL에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="913e8-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

