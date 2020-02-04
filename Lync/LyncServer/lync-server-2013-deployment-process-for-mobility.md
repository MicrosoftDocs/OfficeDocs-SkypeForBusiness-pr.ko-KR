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
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="837d8-102">Lync Server 2013의 모바일 기능 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="837d8-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="837d8-103">_**마지막으로 수정한 주제:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="837d8-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="837d8-104">이 섹션에서는 Lync Server 2013 mobility 기능을 배포 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="837d8-105">모바일 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="837d8-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d8-106">단계의</span><span class="sxs-lookup"><span data-stu-id="837d8-106">Phase</span></span></th>
<th><span data-ttu-id="837d8-107">방법은</span><span class="sxs-lookup"><span data-stu-id="837d8-107">Steps</span></span></th>
<th><span data-ttu-id="837d8-108">필요한</span><span class="sxs-lookup"><span data-stu-id="837d8-108">Permissions</span></span></th>
<th><span data-ttu-id="837d8-109">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="837d8-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d8-110">DNS (Domain Name System) 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="837d8-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="837d8-111">내부 자동 검색 서비스 URL을 확인 하기 위해 내부 DNS CNAME 또는 A (호스트, if IPv6, AAAA) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="837d8-112">외부 자동 검색 서비스 URL을 확인 하기 위해 외부 DNS CNAME 또는 A (호스트, if IPv6, AAAA) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="837d8-113">도메인 관리자</span><span class="sxs-lookup"><span data-stu-id="837d8-113">Domain Admins</span></span></p>
<p><span data-ttu-id="837d8-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="837d8-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="837d8-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013에서 자동 검색 서비스용 DNS 레코드 만들기</a></span><span class="sxs-lookup"><span data-stu-id="837d8-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d8-116">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="837d8-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="837d8-117">모바일 사용자의 보안 연결을 지원 하기 위해 다음 인증서에 주체 대체 이름 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="837d8-118">디렉터 인증서</span><span class="sxs-lookup"><span data-stu-id="837d8-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="837d8-119">프런트 엔드 풀 인증서</span><span class="sxs-lookup"><span data-stu-id="837d8-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="837d8-120">역방향 프록시 인증서</span><span class="sxs-lookup"><span data-stu-id="837d8-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="837d8-121">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="837d8-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="837d8-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013에서 모바일 기능용으로 인증서 수정</a></span><span class="sxs-lookup"><span data-stu-id="837d8-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d8-123">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="837d8-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="837d8-124">SSL (Secure Sockets layer) 수신기에 주체 대체 이름을 사용 하 여 업데이트 된 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="837d8-125">외부 자동 검색 서비스 URL에 대 한 웹 게시 규칙을 다시 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="837d8-126">프런트 엔드 풀에서 외부 Lync Server 2013 웹 서비스 URL에 대 한 웹 게시 규칙이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="837d8-127">또는</span><span class="sxs-lookup"><span data-stu-id="837d8-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="837d8-128">초기 자동 검색 요청에 대해 HTTP를 사용 하도록 선택 하 고 인증서의 주체 대체 이름 목록을 업데이트 하지 않으면 새 웹 게시 규칙을 구성 하거나 포트 80 HTTP에 대 한 기존 게시 규칙을 다시 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="837d8-129">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="837d8-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="837d8-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대해 역방향 프록시 구성</a></span><span class="sxs-lookup"><span data-stu-id="837d8-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d8-131">Mcx Mobility Service를 사용 하 여 Lync 2010 Mobile에 대 한 모바일 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="837d8-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="837d8-132"><strong>CsMcxP2PIM</strong> 를 실행 하 여 한 사람이 다른 사람에 게 인스턴트 메시지를 전송 하도록 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="837d8-133">전체 옵션 목록은 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">테스트 CsMcxP2PIM</a> 의 Lync Server 관리 셸 cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="837d8-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="837d8-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="837d8-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="837d8-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013에서 모바일 기능 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="837d8-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d8-136">웹 구성 요소를 사용 하 여 Lync 2013 모바일 클라이언트에 대 한 모바일 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="837d8-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="837d8-137"><strong>테스트 CsUcwaConference</strong> cmdlet을 사용 하 여 미리 정의 된 테스트 사용자 또는 실제 사용자 쌍이 (가) 회의를 만들고 참가할 수 있는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="837d8-138">전체 옵션 목록은 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">테스트 CsUcwaConference</a> 의 Lync Server 관리 셸 cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="837d8-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="837d8-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="837d8-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="837d8-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013에서 모바일 기능 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="837d8-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d8-141">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="837d8-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="837d8-142">Lync Server 2013 Edge 서버의 경우 Lync Server online 호스팅 공급자를 추가 하 고 호스팅 공급자 페더레이션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="837d8-143">Lync Server 2010 Edge 서버의 경우 Lync Server online 호스팅 공급자를 추가 하 고 호스팅 공급자 페더레이션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="837d8-144">Office Communications Server 2007 R2 Edge 서버의 경우 페더레이션 파트너를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="837d8-145">Wi-fi 네트워크를 통해 푸시 알림을 지원 하려면 TCP 포트 5223에 대 한 방화벽 규칙 아웃 바운드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="837d8-146"><strong>CsPushNotificationConfiguration</strong> cmdlet을 사용 하 여 APNS (Apple Push notification service) 및 MPNS (Microsoft 푸시 알림 서비스)에 푸시 알림을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="837d8-147">이 기능은 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="837d8-148"><strong>CsFederatedPartner</strong> cmdlet을 사용 하 여 페더레이션 구성을 테스트 하 고 <strong>테스트-CsMCXPushNotification</strong> cmdlet을 사용해 푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="837d8-149">푸시 알림은 Apple 장치 및 Windows Phone에서 Lync 2010 모바일 클라이언트에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="837d8-150">Windows Phone의 Lync 2013 모바일 클라이언트에는 푸시 알림이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="837d8-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="837d8-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="837d8-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013의 푸시 알림 구성</a></span><span class="sxs-lookup"><span data-stu-id="837d8-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d8-153">이동성 정책 구성</span><span class="sxs-lookup"><span data-stu-id="837d8-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="837d8-154"><strong>Set-CsMobilityPolicy</strong> cmdlet을 사용 하 여 다음을 허용 하거나 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="837d8-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="837d8-155">직장을 통한 통화</span><span class="sxs-lookup"><span data-stu-id="837d8-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="837d8-156">IP 오디오 및 IP 비디오 사용</span><span class="sxs-lookup"><span data-stu-id="837d8-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="837d8-157">IP 오디오 및/또는 IP 비디오에 WiFi 필요</span><span class="sxs-lookup"><span data-stu-id="837d8-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="837d8-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="837d8-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="837d8-159"><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013에서 모바일 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="837d8-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

