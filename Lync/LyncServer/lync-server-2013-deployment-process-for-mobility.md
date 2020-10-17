---
title: 'Lync Server 2013: 모바일 기능 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7d0e78cd4a8705178b3704a716846755d5c46f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514485"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="e673c-102">Lync Server 2013의 모바일 기능 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="e673c-102">Deployment process for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e673c-103">_**마지막으로 수정 된 항목:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e673c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="e673c-104">이 섹션에서는 Lync Server 2013 모바일 기능을 배포 하는 데 필요한 일련의 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="e673c-105">모바일 기능 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="e673c-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e673c-106">단계</span><span class="sxs-lookup"><span data-stu-id="e673c-106">Phase</span></span></th>
<th><span data-ttu-id="e673c-107">단계</span><span class="sxs-lookup"><span data-stu-id="e673c-107">Steps</span></span></th>
<th><span data-ttu-id="e673c-108">권한</span><span class="sxs-lookup"><span data-stu-id="e673c-108">Permissions</span></span></th>
<th><span data-ttu-id="e673c-109">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="e673c-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e673c-110">DNS(Domain Name System) 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="e673c-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e673c-111">내부 자동 검색 서비스 URL을 확인 하는 내부용 DNS CNAME 또는 A (호스트, if IPv6, AAAA) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="e673c-112">외부 자동 검색 서비스 URL을 확인 하기 위해 external DNS CNAME 또는 A (호스트, if i v 6) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e673c-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="e673c-113">Domain Admins</span></span></p>
<p><span data-ttu-id="e673c-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="e673c-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="e673c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013의 자동 검색 서비스에 대 한 DNS 레코드 만들기</a></span><span class="sxs-lookup"><span data-stu-id="e673c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e673c-116">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="e673c-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="e673c-117">모바일 사용자에 대한 보안 연결을 지원하기 위해 다음 인증서에 주체 대체 이름 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="e673c-118">디렉터 인증서</span><span class="sxs-lookup"><span data-stu-id="e673c-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="e673c-119">프런트 엔드 풀 인증서</span><span class="sxs-lookup"><span data-stu-id="e673c-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="e673c-120">역방향 프록시 인증서</span><span class="sxs-lookup"><span data-stu-id="e673c-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e673c-121">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="e673c-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="e673c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 인증서 수정</a></span><span class="sxs-lookup"><span data-stu-id="e673c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e673c-123">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="e673c-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e673c-124">주체 대체 이름으로 업데이트된 인증서를 SSL(Secure Sockets Layer) 수신기에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="e673c-125">외부 자동 검색 서비스 URL에 대 한 웹 게시 규칙을 다시 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="e673c-126">프런트 엔드 풀에 외부 Lync Server 2013 웹 서비스 URL에 대 한 웹 게시 규칙이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="e673c-127">또는</span><span class="sxs-lookup"><span data-stu-id="e673c-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="e673c-128">초기 자동 검색 요청에 대해 HTTP를 사용 하 고 인증서의 주체 대체 이름 목록을 업데이트 하지 않으려는 경우에는 새 웹 게시 규칙을 구성 하거나 포트 80 HTTP에 대 한 기존 게시 규칙을 다시 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e673c-129">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="e673c-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="e673c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</a></span><span class="sxs-lookup"><span data-stu-id="e673c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e673c-131">Mcx Mobility Service를 사용 하 여 Lync 2010 Mobile의 모바일 기능 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="e673c-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="e673c-132"><strong>Test-CsMcxP2PIM</strong>을 실행하여 사용자 간의 인스턴트 메시지 전송을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="e673c-133">전체 옵션 목록을 보려면 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-csmcxp2pim</a> 에 대 한 Lync Server 관리 셸 cmdlet 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e673c-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="e673c-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e673c-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e673c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013에서 모바일 기능 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="e673c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e673c-136">웹 구성 요소를 사용 하 여 Lync 2013 모바일 클라이언트에 대 한 모바일 기능 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="e673c-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="e673c-137"><strong>Test-csucwaconference</strong> cmdlet을 사용 하 여 미리 정의 된 테스트 사용자 또는 실제 사용자의 쌍이 c u c e c e c를 사용 하 여 회의를 만들고 참가할 수 있는지를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="e673c-138">전체 옵션 목록을 보려면 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-csucwaconference</a> 에 대 한 Lync Server 관리 셸 cmdlet 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e673c-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="e673c-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e673c-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e673c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013에서 모바일 기능 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="e673c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e673c-141">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="e673c-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e673c-142">Lync Server 2013에 지 서버의 경우 Lync Server online 호스팅 공급자를 추가 하 고 호스팅 공급자 페더레이션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="e673c-143">Lync Server 2010에 지 서버의 경우 Lync Server online 호스팅 공급자를 추가 하 고 호스팅 공급자 페더레이션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="e673c-144">Office Communications Server 2007 R2에 지 서버의 경우 페더레이션 파트너를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="e673c-145">Wi-Fi 네트워크를 통해 푸시 알림을 지원하려면 TCP 포트 5223로 나가는 방화벽 규칙을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="e673c-146"><strong>Set-CsPushNotificationConfiguration</strong> cmdlet을 사용하여 APNS(Apple 푸시 알림 서비스) 및 MPNS(Microsoft 푸시 알림 서비스)에 대해 푸시 알림을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="e673c-147">기본적으로 이 기능은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="e673c-148"><strong>Test-CsFederatedPartner</strong> cmdlet을 사용하여 페더레이션 구성을 테스트하고 <strong>Test-CsMCXPushNotification</strong> cmdlet을 사용하여 푸시 알림을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e673c-149">푸시 알림은 Apple 장치 및 Windows Phone의 Lync 2010 모바일 클라이언트에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="e673c-150">Windows Phone 전용 Lync 2013 모바일 클라이언트에는 푸시 알림이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="e673c-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e673c-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="e673c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013에서 푸시 알림 구성</a></span><span class="sxs-lookup"><span data-stu-id="e673c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e673c-153">모바일 기능 정책 구성</span><span class="sxs-lookup"><span data-stu-id="e673c-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="e673c-154">Get-csmobilitypolicy cmdlet을 사용 하 여 다음을 허용 하거나 허용 하지 않도록 <strong>설정</strong> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e673c-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="e673c-155">회사 번호로 전화</span><span class="sxs-lookup"><span data-stu-id="e673c-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="e673c-156">IP 오디오 및 IP 비디오 사용</span><span class="sxs-lookup"><span data-stu-id="e673c-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="e673c-157">IP 오디오 및/또는 IP 비디오에 WiFi 필요</span><span class="sxs-lookup"><span data-stu-id="e673c-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e673c-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e673c-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e673c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013에서 모바일 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="e673c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

