---
title: DNS 요약-SIP, XMPP 페더레이션 및 공용 인스턴트 메시징
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="21d9e-102">DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="21d9e-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d9e-103">_**마지막으로 수정 된 항목:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="21d9e-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="21d9e-104">Office Communications Server 또는 Lync Server 파트너와의 페더레이션을 정의 하는 데 필요한 DNS (Domain Name System) 레코드는 다른 측면 파트너가 사용자의 도메인에 대 한 자동 DNS 검색을 허용 하는지 결정에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="21d9e-105">Sipfederationtls를 게시 하 \_는 경우 \_tcp를</span><span class="sxs-lookup"><span data-stu-id="21d9e-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="21d9e-106">*SIP 도메인 이름\> \<* SRV 레코드의 경우 다른 SIP 페더레이션 도메인은 해당 페더레이션을 "검색" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="21d9e-107">Lync Server 제어판에서 도메인 및 차단 된 도메인 설정을 사용 하거나, Lync Server 관리 셸 및 **Get**, **Set**, **New**, **csalloweddomain** 및 **-get-csblockeddomain** PowerShell cmdlet을 사용 하 여 허용 또는 차단 된 도메인 구성을 설정 하 여 사용자와 통신할 수 있는 페더레이션 도메인을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="21d9e-108">이러한 설정을 구성하는 방법 및 PowerShell cmdlet을 사용하는 방법에 대한 자세한 내용은 이 항목 끝부분의 **관련 항목**을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21d9e-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="21d9e-109">DNS 레코드 요약 표에는 공개(검색 가능) 페더레이션에 필요한 항목이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="21d9e-110">페더레이션 검색을 구현 하지 않으려는 경우에는 \_sipfederationtls를 구성 하지 않기로 결정할 수 있습니다. \_tcp를</span><span class="sxs-lookup"><span data-stu-id="21d9e-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="21d9e-111">*SIP 도메인 이름\> 레코드입니다. \<*</span><span class="sxs-lookup"><span data-stu-id="21d9e-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="21d9e-112">_sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="21d9e-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="21d9e-113"><EM>SIP 도메인 이름&gt; &lt;</EM> SRV 레코드 이지만 검색 가능한 페더레이션을 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="21d9e-114">이와 같은 시나리오의 한 가지 예로 사용자를 위해 모바일 기능을 배포한 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="21d9e-115">PNCH (mobility push notification clearinghouse)는 lync 2010 모바일 클라이언트 또는 lync 2013 모바일 클라이언트를 사용 하 여 Apple iPhone 또는 iPad에서 Microsoft Lync Mobile client에 사용 되는 특별 한 유형의 페더레이션 이며, Lync 2010 모바일 클라이언트나 Windows Phone을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="21d9e-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="21d9e-116">모바일 기능 및 PNCH의 경우에는 _sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="21d9e-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="21d9e-117"><EM>SIP 도메인 이름&gt; &lt;</EM> SRV 레코드는 이동성 및 푸시 알림의 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="21d9e-118">이 문제를 완화하고 검색 가능성을 제어하려면 <STRONG>파트너 도메인 검색 사용</STRONG> 설정 선택을 취소하여 검색을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="21d9e-119">배포에 XMPP (extensible messaging and 현재 상태 프로토콜)를 구성 하려면에 지 서버 또는에 지 풀의 액세스에 지 서비스에 대 한 레코드를 확인 하는 두 개의 DNS (domain name system) 레코드를 외부 DNS 서버에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="21d9e-120">공용 인스턴트 메시징 연결에 대 한 DNS (domain name system)를 구성 하는 경우 외부 사용자를 지 원하는 구성에서 공용 IM 연결을 지원 한다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="21d9e-121">에 지 서버 또는에 지 풀을 이미 구성한 경우에는 공용 IM 연결을 지 원하는 데 필요한 DNS 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="21d9e-122">DNS 요약-공용 인스턴트 메시징 연결을 포함 하는 SIP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="21d9e-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d9e-123">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="21d9e-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="21d9e-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="21d9e-124">FQDN</span></span></th>
<th><span data-ttu-id="21d9e-125">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="21d9e-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="21d9e-126">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="21d9e-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d9e-127">외부 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="21d9e-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="21d9e-128">_sipfederationtls _tcp. contoso.</span><span class="sxs-lookup"><span data-stu-id="21d9e-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="21d9e-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21d9e-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="21d9e-130">액세스에 지 서비스 외부 인터페이스는 다른 잠재적 페더레이션 파트너에 대 한 페더레이션 자동 검색에 필요 하며, "허용 SIP 도메인" (이전 릴리스의 향상 된 페더레이션 이라고 함) 이라고 합니다. Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 필요에 따라 반복</span><span class="sxs-lookup"><span data-stu-id="21d9e-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="21d9e-131">이 SRV 레코드는 모바일 기능 및 푸시 알림 클리어링 하우스에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="21d9e-132">SIP 도메인이 두 개 이상 있는 경우 Lync 모바일 클라이언트를 사용할 각 도메인에 대해 SRV 레코드를 만들고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="21d9e-133">배포에서 지 원하는 각 SIP 도메인에 대 한 명시적 SRV 레코드가 없는 경우 푸시 알림 서비스와 Apple 푸시 알림 서비스가 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="21d9e-134">DNS 요약-XMPP (Extensible Messaging and 현재 상태 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="21d9e-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d9e-135">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="21d9e-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="21d9e-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="21d9e-136">FQDN</span></span></th>
<th><span data-ttu-id="21d9e-137">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="21d9e-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="21d9e-138">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="21d9e-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d9e-139">외부 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="21d9e-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="21d9e-140">_xmpp-.com. _tcp</span><span class="sxs-lookup"><span data-stu-id="21d9e-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="21d9e-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21d9e-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="21d9e-142">액세스에 지 서비스 또는에 지 풀의 XMPP 프록시 외부 인터페이스 Lync 사용 가능 사용자가 있는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책 또는 도메인에 적용 되는 사용자 정책을 통해 외부 액세스 정책을 구성 하 여 XMPP 대화 상대와의 연결을 허용 합니다. Lync 사용 가능 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="21d9e-143">XMPP 페더레이션 파트너 정책 에서도 허용 되는 XMPP 도메인을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="21d9e-144">자세한 내용은 관련 <strong>항목을 참조</strong> 하십시오.</span><span class="sxs-lookup"><span data-stu-id="21d9e-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d9e-145">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="21d9e-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="21d9e-146">xmpp.contoso.com(예제)</span><span class="sxs-lookup"><span data-stu-id="21d9e-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="21d9e-147">XMPP 프록시를 호스팅하는에 지 서버 또는에 지 풀에 있는 액세스에 지 서비스의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="21d9e-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="21d9e-148">XMPP 프록시 서비스를 호스팅하는 액세스에 지 서비스 또는에 지 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="21d9e-149">일반적으로 사용자가 만드는 SRV 레코드는 이 호스트(A 또는 AAAA) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="21d9e-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21d9e-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21d9e-150">See Also</span></span>


[<span data-ttu-id="21d9e-151">Lync Server 2013에서 XMPP 페더레이션 설정</span><span class="sxs-lookup"><span data-stu-id="21d9e-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="21d9e-152">Lync Server 2013에서 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="21d9e-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="21d9e-153">Lync Server 2013에서 페더레이션 파트너 검색을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="21d9e-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="21d9e-154">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="21d9e-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="21d9e-155">Lync Server 2013에 대 한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="21d9e-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="21d9e-156">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="21d9e-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

