---
title: 'Lync Server 2013: 단순 Url에 대 한 DNS 요구 사항'
description: 'Lync Server 2013: 단순 Url에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564964"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="bd732-103">Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd732-103">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd732-104">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="bd732-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bd732-105">Lync Server 2013은 사용자에 게 모임을 보다 쉽게 참가할 수 있도록 하는 단순 Url을 지원 하며, 관리자에 게 Lync Server 관리 도구를 보다 쉽게 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-105">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="bd732-106">단순 Url에 대 한 자세한 내용은 [Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd732-106">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="bd732-107">Lync Server에서는 모임, 전화 접속, 관리자의 세 가지 간단한 Url을 지원 합니다. 모임 및 전화 접속에 대 한 단순 Url을 설정 해야 하며, 관리자 단순 URL은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-107">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="bd732-108">단순 URL을 지원하는 데 필요한 DNS(Domain Name System) 레코드는 이러한 단순 URL을 정의한 방법 및 단순 URL에 대해 재해 복구를 지원할지 여부에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="bd732-109">단순 URL 옵션 1</span><span class="sxs-lookup"><span data-stu-id="bd732-109">Simple URL Option 1</span></span>

<span data-ttu-id="bd732-110">옵션 1에서는 각 단순 URL에 대한 새로운 기본 URL을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-110">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="bd732-p103">사용자가 단순 URL 모임 링크를 클릭하면 DNS A 레코드에서 확인하는 서버에서 시작할 올바른 클라이언트 소프트웨어를 결정합니다. 클라이언트 소프트웨어는 시작되는 즉시 전화 회의가 호스팅되는 풀과 자동으로 통신합니다. 따라서 사용자가 단순 URL DNS A 레코드에서 확인한 서버 또는 풀에 관계없이 모임 콘텐츠에 적절한 서버로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="bd732-114">단순 URL 옵션 1</span><span class="sxs-lookup"><span data-stu-id="bd732-114">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd732-115"><strong>단순 URL</strong></span><span class="sxs-lookup"><span data-stu-id="bd732-115"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="bd732-116"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bd732-116"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd732-117">조건</span><span class="sxs-lookup"><span data-stu-id="bd732-117">Meet</span></span></p></td>
<td><p><span data-ttu-id="bd732-118">https://meet.contoso.com, https://meet.fabrikam.com 등은 (조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="bd732-118">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd732-119">전화 접속</span><span class="sxs-lookup"><span data-stu-id="bd732-119">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd732-120">관리자</span><span class="sxs-lookup"><span data-stu-id="bd732-120">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd732-121">옵션 1을 사용하는 경우 다음을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-121">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="bd732-p104">디렉터를 배포한 경우 각 모임 단순 URL에 대해 URL을 디렉터의 IP 주소로 확인하는 DNS A 레코드가 있어야 합니다. 그렇지 않으면 DNS A 레코드에서 프런트 엔드 풀 부하 분산 장치의 IP 주소를 확인해야 합니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="bd732-125">조직에 둘 이상의 SIP 도메인이 있는 경우 이 옵션을 사용하려면 각 SIP 도메인에 대해 모임 단순 URL을 만들어야 하며 각 모임 단순 URL에 대한 DNS A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-125">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="bd732-126">예를 들어 contoso.com 및 fabrikam.com가 둘 다 있는 경우 및에 대 한 DNS A 레코드를 https://meet.contoso.com 만듭니다 https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="bd732-126">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="bd732-127">또는 여러 SIP 도메인이 있는 경우 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려면 옵션 3(이 항목의 뒷부분에 나오는 설명 참조)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-127">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="bd732-p106">디렉터를 배포한 경우 각 전화 접속 단순 URL에 대해 URL을 디렉터의 IP 주소로 확인하는 DNS A 레코드가 있어야 합니다. 그렇지 않으면 DNS A 레코드에서 프런트 엔드 풀 부하 분산 장치의 IP 주소를 확인해야 합니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="bd732-p107">관리 단순 URL은 내부 전용입니다. 이 URL에는 디렉터를 배포한 경우 URL을 디렉터의 IP 주소로 확인하는 DNS A 레코드가 있어야 합니다. 그렇지 않으면 DNS A 레코드에서 프런트 엔드 풀 부하 분산 장치의 IP 주소를 확인해야 합니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="bd732-135">단순 URL 옵션 2</span><span class="sxs-lookup"><span data-stu-id="bd732-135">Simple URL Option 2</span></span>

<span data-ttu-id="bd732-p108">옵션 2를 사용하는 경우에는 모임, 전화 접속 및 관리 단순 URL 모두 공통 기본 URL(예: lync.contoso.com)을 사용합니다. 따라서 이러한 단순 URL에 대해 lync.contoso.com을 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 확인하는 DNS A 레코드가 하나만 있으면 됩니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="bd732-139">조직에 둘 이상의 SIP 도메인이 있는 경우 여전히 각 SIP 도메인에 대해 모임 단순 URL을 만들어야 하며 각 모임 단순 URL에 대한 DNS A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-139">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="bd732-140">이 예에서는 세 가지 단순 URL이 모두 lync.contoso.com을 기반으로 하지만 fabrikam.com에 대한 추가 모임 단순 URL이 다른 기본 URL로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-140">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="bd732-141">이 예에서는 및에 대 한 DNS A 레코드를 만들어야 https://lync.contoso.com 합니다 https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="bd732-141">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="bd732-142">단순 URL 옵션 3에서는 여러 SIP 도메인이 있는 이름 지정 및 DNS A 레코드를 처리하는 다른 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-142">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="bd732-143">단순 URL 옵션 2</span><span class="sxs-lookup"><span data-stu-id="bd732-143">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd732-144"><strong>단순 URL</strong></span><span class="sxs-lookup"><span data-stu-id="bd732-144"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="bd732-145"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bd732-145"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd732-146">조건</span><span class="sxs-lookup"><span data-stu-id="bd732-146">Meet</span></span></p></td>
<td><p><span data-ttu-id="bd732-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet 등은 (조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="bd732-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd732-148">전화 접속</span><span class="sxs-lookup"><span data-stu-id="bd732-148">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd732-149">관리자</span><span class="sxs-lookup"><span data-stu-id="bd732-149">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="bd732-150">단순 URL 옵션 3</span><span class="sxs-lookup"><span data-stu-id="bd732-150">Simple URL Option 3</span></span>

<span data-ttu-id="bd732-p110">옵션 3은 많은 SIP 도메인이 있고 각각에 별도의 단순 URL을 사용하지만 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려는 경우에 가장 유용합니다. 이 예에서는 lync.contoso.com을 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 확인하는 DNS A 레코드가 하나만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="bd732-153">단순 URL 옵션 3</span><span class="sxs-lookup"><span data-stu-id="bd732-153">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd732-154"><strong>단순 URL</strong></span><span class="sxs-lookup"><span data-stu-id="bd732-154"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="bd732-155"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bd732-155"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd732-156">조건</span><span class="sxs-lookup"><span data-stu-id="bd732-156">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd732-157">전화 접속</span><span class="sxs-lookup"><span data-stu-id="bd732-157">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd732-158">관리자</span><span class="sxs-lookup"><span data-stu-id="bd732-158">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="bd732-159">단순 URL용 재해 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="bd732-159">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="bd732-160">프런트 엔드 풀이 포함 된 사이트가 여러 개 있고 DNS 공급자가 GeoDNS를 지 원하는 경우에는 간단한 url에 대 한 DNS 레코드를 설정 하 여 재해 복구를 지원할 수 있으므로 하나의 전체 프런트 엔드 풀이 다운 되더라도 간단한 URL 기능이 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-160">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="bd732-161">이 재해 복구 기능은 모임 및 전화 접속 단순 URL을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-161">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="bd732-p112">이와 같이 구성하려면 GeoDNS 주소 두 개를 만듭니다. 각 주소에는 재해 복구용으로 쌍으로 지정된 두 개의 풀로 확인되는 DNS A 또는 CNAME 레코드 두 개가 포함됩니다. GeoDNS 주소 중 하나는 내부 액세스용으로 사용되며, 두 풀에 대한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 나머지 GeoDNS 주소는 외부 액세스용으로 사용되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 아래에는 풀의 FQDN을 사용하는 모임 단순 URL의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="bd732-167">그런 후에 meet.contoso.com과 같은 모임 단순 URL을 두 개의 GeoDNS 주소로 확인하는 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-167">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="bd732-168">네트워크에서 <EM>헤어핀</EM>(조직 내부에서 생성되는 트래픽을 비롯하여 모든 단순 URL 트래픽을 외부 링크를 통해 라우팅)을 사용하는 경우에는 외부 GeoDNS 주소만 구성하고 모임 단순 URL을 해당 외부 주소로만 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-168">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="bd732-169">이 방법을 사용하는 경우 각 GeoDNS 주소가 라운드 로빈 방법을 사용하여 요청을 두 풀로 분산시키거나, 기본적으로 한 풀(예: 지리적으로 더 가까이 있는 풀)에 연결하고 다른 풀은 연결 오류 시에만 사용하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-169">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="bd732-170">전화 접속 단순 URL에 대해 같은 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-170">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="bd732-171">이렇게 하려면 앞의 예에서와 같은 추가 레코드를 DNS 레코드로 대체 하 여 `dialin` 만듭니다 `meet` .</span><span class="sxs-lookup"><span data-stu-id="bd732-171">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="bd732-172">관리 단순 URL의 경우 이 섹션 앞부분에 나와 있는 세 가지 옵션 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-172">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="bd732-173">이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용하여 오류를 감시할 HTTP 모니터링을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-173">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="bd732-174">외부 액세스의 경우 모니터를 사용 하 여 HTTPS에서 외부 웹 FQDN에 대 한 자동 검색 요청 또는 두 풀의 부하 분산 장치에 대 한 IP 주소를 모두 올바르게 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-174">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="bd732-175">예를 들어 다음 요청은 **ACCEPT** 헤더를 포함하면 안 되며 **200 OK**를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-175">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="bd732-p115">내부 액세스의 경우에는 두 풀에 대해 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링해야 합니다. 연결 오류가 감지되면 이러한 풀의 VIP가 포트 80, 443 및 444를 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd732-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

