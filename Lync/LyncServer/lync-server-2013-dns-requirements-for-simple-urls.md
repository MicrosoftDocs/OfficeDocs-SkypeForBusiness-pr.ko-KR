---
title: 'Lync Server 2013: 단순 URL에 대한 DNS 요구 사항'
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
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="6ab15-102">Lync Server 2013의 단순 URL에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ab15-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ab15-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6ab15-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6ab15-104">Lync Server 2013는 사용자에 게 모임 참가를 더욱 쉽게 할 수 있도록 하는 간단한 Url을 지원 하 고, 관리자에 게 Lync Server 관리 도구를 더 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="6ab15-105">간단한 Url에 대 한 자세한 내용은 [Lync Server 2013의 간단한 Url 계획](lync-server-2013-planning-for-simple-urls.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ab15-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="6ab15-106">Lync Server는 회의, 전화 접속, 관리자의 세 가지 간단한 Url을 지원 합니다. 시작 및 전화 접속에 대 한 간단한 Url을 설정 해야 하며, 관리자 단순 URL은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="6ab15-107">간단한 url을 지원 하기 위해 필요한 DNS (Domain Name System) 레코드는 간단한 url을 정의한 방법과 간단한 Url에 대 한 재해 복구를 지원 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="6ab15-108">간단한 URL 옵션 1</span><span class="sxs-lookup"><span data-stu-id="6ab15-108">Simple URL Option 1</span></span>

<span data-ttu-id="6ab15-109">옵션 1에서는 각 단순 URL에 대 한 새 기본 URL을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6ab15-110">사용자가 간단한 URL 모임 링크를 클릭 하면 DNS A 레코드가 확인 되는 서버가 시작 하도록 올바른 클라이언트 소프트웨어를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="6ab15-111">클라이언트 소프트웨어가 시작 되 면 회의가 호스팅되는 풀과 자동으로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="6ab15-112">이 방법으로 사용자는 레코드가 확인 되는 단순 URL DNS 서버 또는 풀에 관계 없이 모임 콘텐츠를 위해 적절 한 서버로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="6ab15-113">간단한 URL 옵션 1</span><span class="sxs-lookup"><span data-stu-id="6ab15-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab15-114"><strong>간단한 URL</strong></span><span class="sxs-lookup"><span data-stu-id="6ab15-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="6ab15-115"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6ab15-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab15-116">시켜</span><span class="sxs-lookup"><span data-stu-id="6ab15-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="6ab15-117">https://meet.contoso.comhttps://meet.fabrikam.com(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="6ab15-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab15-118">전화 접속</span><span class="sxs-lookup"><span data-stu-id="6ab15-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab15-119">관리자</span><span class="sxs-lookup"><span data-stu-id="6ab15-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ab15-120">옵션 1을 사용 하는 경우 다음을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="6ab15-121">각각의 단순 URL에 대해 배포 된 경우 디렉터 IP 주소에 대 한 URL을 확인 하는 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="6ab15-122">그렇지 않으면 프런트 엔드 풀의 부하 분산 장치에 대 한 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="6ab15-123">풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="6ab15-124">조직에 둘 이상의 SIP 도메인이 있고이 옵션을 사용 하는 경우 각 SIP 도메인에 대해 간단한 Url을 생성 해야 하며 각 사용자에 게 맞는 단순 URL에 대 한 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="6ab15-125">예를 들어 contoso.com와 fabrikam.com가 모두 있는 경우 및 https://meet.contoso.com https://meet.fabrikam.com의 두 가지 모두에 대해 DNS A 레코드를 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="6ab15-126">또는 여러 SIP 도메인이 있고 이러한 간단한 Url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려면이 항목의 뒷부분에 설명 된 대로 옵션 3을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="6ab15-127">전화 접속 간단한 URL의 경우 배포 된 URL을 사용 하는 경우 디렉터 IP 주소를 확인 하는 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="6ab15-128">그렇지 않으면 프런트 엔드 풀의 부하 분산 장치에 대 한 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="6ab15-129">풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="6ab15-130">관리 단순 URL은 내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="6ab15-131">배포 된 사용자가 있는 경우 해당 URL을 디렉터 IP 주소로 확인 하는 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="6ab15-132">그렇지 않으면 프런트 엔드 풀의 부하 분산 장치에 대 한 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="6ab15-133">풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="6ab15-134">간단한 URL 옵션 2</span><span class="sxs-lookup"><span data-stu-id="6ab15-134">Simple URL Option 2</span></span>

<span data-ttu-id="6ab15-135">옵션 2를 사용 하는 경우, 모임 시작, 전화 접속 로그인, 관리자 단순 Url에는 모두 lync.contoso.com와 같은 일반적인 기본 URL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="6ab15-136">따라서 이러한 간단한 Url에 대해 하나의 DNS A 레코드만 필요 하며, 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 lync.contoso.com 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="6ab15-137">풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="6ab15-138">조직에 둘 이상의 SIP 도메인이 있는 경우 각 SIP 도메인에 대해 간단한 Url을 사용 해야 하며 각 사용자에 게 맞는 단순 URL에 대 한 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="6ab15-139">이 예제에서는 세 개의 간단한 Url이 모두 lync.contoso.com에 기반을 둔 반면 fabrikam.com에 대 한 추가 소개 간단한 URL이 다른 기본 URL로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="6ab15-140">이 예제에서는 https://lync.contoso.com 및 https://lync.fabrikam.com에 대 한 DNS A 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="6ab15-141">간단한 URL 옵션 3에는 여러 SIP 도메인이 있는 경우 이름 지정 및 DNS A 레코드를 처리 하는 다른 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="6ab15-142">간단한 URL 옵션 2</span><span class="sxs-lookup"><span data-stu-id="6ab15-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab15-143"><strong>간단한 URL</strong></span><span class="sxs-lookup"><span data-stu-id="6ab15-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="6ab15-144"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6ab15-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab15-145">시켜</span><span class="sxs-lookup"><span data-stu-id="6ab15-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="6ab15-146">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="6ab15-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab15-147">전화 접속</span><span class="sxs-lookup"><span data-stu-id="6ab15-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab15-148">관리자</span><span class="sxs-lookup"><span data-stu-id="6ab15-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="6ab15-149">간단한 URL 옵션 3</span><span class="sxs-lookup"><span data-stu-id="6ab15-149">Simple URL Option 3</span></span>

<span data-ttu-id="6ab15-150">옵션 3은 많은 SIP 도메인이 있고, 별도의 간단한 Url을 사용 하 려 하지만 간단한 url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려는 경우에 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="6ab15-151">이 예제에서는 lync.contoso.com를 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 확인 하는 하나의 DNS A 레코드만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="6ab15-152">간단한 URL 옵션 3</span><span class="sxs-lookup"><span data-stu-id="6ab15-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab15-153"><strong>간단한 URL</strong></span><span class="sxs-lookup"><span data-stu-id="6ab15-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="6ab15-154"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6ab15-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab15-155">시켜</span><span class="sxs-lookup"><span data-stu-id="6ab15-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab15-156">전화 접속</span><span class="sxs-lookup"><span data-stu-id="6ab15-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab15-157">관리자</span><span class="sxs-lookup"><span data-stu-id="6ab15-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="6ab15-158">간단한 Url에 대 한 재해 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="6ab15-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="6ab15-159">프런트 엔드 풀을 포함 하는 사이트가 여러 개 있고 DNS 공급자가 GeoDNS를 지 원하는 경우, 장애 복구를 지원 하도록 간단한 Url에 대 한 DNS 레코드를 설정 하 여 전체 프론트 엔드 풀 하나가 다운 되어도 간단한 URL 기능이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="6ab15-160">이 재해 복구 기능은 모임 및 전화 접속 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="6ab15-161">이를 구성 하려면 두 개의 GeoDNS 주소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="6ab15-162">각 주소에는 재해 복구용으로 서로 연결 된 두 개의 풀로 확인 되는 두 개의 DNS A 또는 CNAME 레코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="6ab15-163">하나의 GeoDNS 주소는 내부 액세스에 사용 되며, 두 풀의 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="6ab15-164">다른 GeoDNS 주소는 외부 액세스에 사용 되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="6ab15-165">다음은 풀에 대 한 Fqdn을 사용 하 여 단순 URL을 충족 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="6ab15-166">그런 다음 두 GeoDNS 주소에 대 한 meet.contoso.com (예:)와 일치 하는 단순 URL을 확인 하는 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6ab15-167">네트워크에서 <EM>hairpinning</EM> 를 사용 하는 경우 (조직 내에서 제공 하는 트래픽을 포함 하 여 외부 링크를 통해 모든 간단한 URL 트래픽을 라우팅하는 경우), 외부 geodns 주소를 구성 하 고 해당 하는 단순 url을 해당 외부 주소로만 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="6ab15-168">이 메서드를 사용 하는 경우 라운드 로빈 메서드를 사용 하 여 두 개의 풀에 요청을 분산 하거나, 기본 풀 (예: 지리적으로 가까운 풀)에 연결 하 고, 다음의 경우에만 다른 풀을 사용 하도록 각 GeoDNS 주소를 구성할 수 있습니다. 연결 실패.</span><span class="sxs-lookup"><span data-stu-id="6ab15-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="6ab15-169">전화 접속 단순 URL에 대해 동일한 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="6ab15-170">이렇게 하려면 이전 예제와 같은 추가 레코드를 만들고 DNS 레코드 `dialin` `meet` 에서 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="6ab15-171">관리 간단한 URL의 경우이 섹션의 앞에 나열 된 세 가지 옵션 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="6ab15-172">이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용 하 여 오류를 감시 하도록 HTTP 모니터링을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="6ab15-173">외부 액세스의 경우 모니터에서 외부 웹 FQDN 또는 부하 분산 장치에 대 한 자동 검색 요청이 두 풀에 대해 성공적으로 제공 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="6ab15-174">예를 들어 다음 요청에는 **ACCEPT** 헤더가 없어야 하 고 **200 OK**를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

<span data-ttu-id="6ab15-175">내부 액세스의 경우 두 풀에 대 한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="6ab15-176">연결 실패가 감지 되는 경우 이러한 풀의 VIP는 포트 80, 443 및 444을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab15-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

