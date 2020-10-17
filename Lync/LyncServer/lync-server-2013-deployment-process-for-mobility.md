---
title: 'Lync Server 2013: 모바일 기능 배포 프로세스'
description: 'Lync Server 2013: 모바일 기능 배포 프로세스'
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
ms.openlocfilehash: b49d69af899f6d9f2ac1db5040d017a9d62ce9eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551044"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능 배포 프로세스

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

이 섹션에서는 Lync Server 2013 모바일 기능을 배포 하는 데 필요한 일련의 단계를 설명 합니다.

### <a name="mobility-deployment-process"></a>모바일 기능 배포 프로세스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>권한</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS(Domain Name System) 레코드 만들기</p></td>
<td><ul>
<li><p>내부 자동 검색 서비스 URL을 확인 하는 내부용 DNS CNAME 또는 A (호스트, if IPv6, AAAA) 레코드를 만듭니다.</p></li>
<li><p>외부 자동 검색 서비스 URL을 확인 하기 위해 external DNS CNAME 또는 A (호스트, if i v 6) 레코드를 만듭니다.</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013의 자동 검색 서비스에 대 한 DNS 레코드 만들기</a></p></td>
</tr>
<tr class="even">
<td><p>인증서 수정</p></td>
<td><p>모바일 사용자에 대한 보안 연결을 지원하기 위해 다음 인증서에 주체 대체 이름 항목을 추가합니다.</p>
<ul>
<li><p>디렉터 인증서</p></li>
<li><p>프런트 엔드 풀 인증서</p></li>
<li><p>역방향 프록시 인증서</p></li>
</ul></td>
<td><p>로컬 관리자</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 인증서 수정</a></p></td>
</tr>
<tr class="odd">
<td><p>역방향 프록시 구성</p></td>
<td><ul>
<li><p>주체 대체 이름으로 업데이트된 인증서를 SSL(Secure Sockets Layer) 수신기에 할당합니다.</p></li>
<li><p>외부 자동 검색 서비스 URL에 대 한 웹 게시 규칙을 다시 구성 합니다.</p></li>
<li><p>프런트 엔드 풀에 외부 Lync Server 2013 웹 서비스 URL에 대 한 웹 게시 규칙이 있는지 확인 합니다.</p></li>
</ul>
<p>또는</p>
<ul>
<li><p>초기 자동 검색 요청에 대해 HTTP를 사용 하 고 인증서의 주체 대체 이름 목록을 업데이트 하지 않으려는 경우에는 새 웹 게시 규칙을 구성 하거나 포트 80 HTTP에 대 한 기존 게시 규칙을 다시 구성 합니다.</p></li>
</ul></td>
<td><p>로컬 관리자</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</a></p></td>
</tr>
<tr class="even">
<td><p>Mcx Mobility Service를 사용 하 여 Lync 2010 Mobile의 모바일 기능 배포 테스트</p></td>
<td><p><strong>Test-CsMcxP2PIM</strong>을 실행하여 사용자 간의 인스턴트 메시지 전송을 테스트합니다.</p>
<p>전체 옵션 목록을 보려면 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-csmcxp2pim</a> 에 대 한 Lync Server 관리 셸 cmdlet 설명서를 참조 하십시오.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013에서 모바일 기능 배포 확인</a></p></td>
</tr>
<tr class="odd">
<td><p>웹 구성 요소를 사용 하 여 Lync 2013 모바일 클라이언트에 대 한 모바일 기능 배포 테스트</p></td>
<td><p><strong>Test-csucwaconference</strong> cmdlet을 사용 하 여 미리 정의 된 테스트 사용자 또는 실제 사용자의 쌍이 c u c e c e c를 사용 하 여 회의를 만들고 참가할 수 있는지를 테스트 합니다.</p>
<p>전체 옵션 목록을 보려면 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-csucwaconference</a> 에 대 한 Lync Server 관리 셸 cmdlet 설명서를 참조 하십시오.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013에서 모바일 기능 배포 확인</a></p></td>
</tr>
<tr class="even">
<td><p>푸시 알림 구성</p></td>
<td><ul>
<li><p>Lync Server 2013에 지 서버의 경우 Lync Server online 호스팅 공급자를 추가 하 고 호스팅 공급자 페더레이션을 구성 합니다.</p></li>
<li><p>Lync Server 2010에 지 서버의 경우 Lync Server online 호스팅 공급자를 추가 하 고 호스팅 공급자 페더레이션을 구성 합니다.</p></li>
<li><p>Office Communications Server 2007 R2에 지 서버의 경우 페더레이션 파트너를 추가 합니다.</p></li>
<li><p>Wi-Fi 네트워크를 통해 푸시 알림을 지원하려면 TCP 포트 5223로 나가는 방화벽 규칙을 구성합니다.</p></li>
<li><p><strong>Set-CsPushNotificationConfiguration</strong> cmdlet을 사용하여 APNS(Apple 푸시 알림 서비스) 및 MPNS(Microsoft 푸시 알림 서비스)에 대해 푸시 알림을 사용하도록 설정합니다. 기본적으로 이 기능은 사용되지 않습니다.</p></li>
<li><p><strong>Test-CsFederatedPartner</strong> cmdlet을 사용하여 페더레이션 구성을 테스트하고 <strong>Test-CsMCXPushNotification</strong> cmdlet을 사용하여 푸시 알림을 테스트합니다.</p>
<div>

> [!NOTE]  
> 푸시 알림은 Apple 장치 및 Windows Phone의 Lync 2010 모바일 클라이언트에 사용 됩니다.<BR>Windows Phone 전용 Lync 2013 모바일 클라이언트에는 푸시 알림이 필요 합니다.


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013에서 푸시 알림 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>모바일 기능 정책 구성</p></td>
<td><p>Get-csmobilitypolicy cmdlet을 사용 하 여 다음을 허용 하거나 허용 하지 않도록 <strong>설정</strong> 합니다.</p>
<ul>
<li><p>회사 번호로 전화</p></li>
<li><p>IP 오디오 및 IP 비디오 사용</p></li>
<li><p>IP 오디오 및/또는 IP 비디오에 WiFi 필요</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013에서 모바일 정책 구성</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

