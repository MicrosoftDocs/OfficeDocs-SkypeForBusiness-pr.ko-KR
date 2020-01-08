---
title: SIP 페더레이션, XMPP 페더레이션 및 공용 메신저 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 메신저 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

페더레이션, 공용 인스턴트 메시지 연결 및 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP)은 외부 사용자의 다른 클래스 (페더레이션 사용자)를 정의 합니다. 페더레이션된 Lync Server 배포 또는 XMPP 배포의 사용자는 제한 된 서비스 집합에 액세스할 수 있으며 외부 배포에서 인증 됩니다. 원격 사용자는 Lync Server 배포의 구성원이 며 배포 시 제공 되는 모든 서비스에 액세스할 수 있습니다.

<div>


> [!NOTE]
> AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.



</div>

공용 인스턴트 메시징 연결은 Lync Server 클라이언트가 Lync 2013를 사용 하 여 구성 된 공개 인스턴트 메시징 파트너에 액세스할 수 있도록 하는 특별 한 유형의 페더레이션입니다. 현재 공개 인스턴트 메시징 연결 파트너는 다음과 같습니다.

  - <span></span>  
    아메리카 온라인

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

공용 인스턴트 메시징 연결 구성을 통해 Lync 사용자는 다음과 같은 방법으로 공용 인스턴트 메시징 연결 사용자에 액세스할 수 있습니다.

  - 메신저 대화 및 현재 상태

  - Lync 클라이언트의 공개 인스턴트 메시지 연결 연락처 표시

  - 대화 상대에 게 연락처와 대화를 주고 받을 수 있습니다.

  - Windows Live 사용자와의 음성 및 영상 통화

Lync server federation는 Lync Server 배포와 다른 Office Communications Server 2007 R2 또는 Lync Server 배포 간의 계약을 정의 합니다. Lync Server 페더레이션된 구성을 사용 하면 Lync 사용자가 다음과 같은 방법으로 페더레이션 사용자에 액세스할 수 있습니다.

  - 메신저 대화 및 현재 상태

  - Lync 클라이언트에 페더레이션 대화 상대 만들기

XMPP federation는 확장 가능한 메시징 및 현재 상태 프로토콜을 기반으로 외부 배포를 정의 합니다. XMPP 구성을 사용 하면 Lync 사용자는 다음과 같은 방법으로 허용 된 XMPP 도메인 사용자에 액세스할 수 있습니다.

  - IM 및 현재 상태 – 사용자에만 해당

  - Lync 클라이언트에서 XMPP 페더레이션 대화 만들기

<div>


> [!IMPORTANT]
> Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Edge 서버 외부 페더레이션, 공개 인스턴트 메시지 연결 및 XMPP 사용자 배포 프로세스


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>필요한</th>
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기존 Edge 배포에 추가할 옵션 결정</p></td>
<td><p>토폴로지 작성기를 실행 하 여 Edge 서버 설정을 편집 하 고 토폴로지를 만들고 게시 합니다. 기존 Edge 토폴로지가 중앙 관리 저장소의 변경 내용을 Edge 서버로 복제 합니다.</p></td>
<td><p>Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹</p>



> [!NOTE]
> 로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 편집할 수 있지만 토폴로지를 게시 하려면 Domain Admins 그룹의 구성원 인 계정 및 RTCUniversalServerAdmins 그룹이 필요 합니다.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서 에지 및 디렉터 토폴로지 구성</a></p></td>
</tr>
<tr class="even">
<td><p>설치 준비</p></td>
<td><ol>
<li><p>시스템 필수 조건이 충족 되었는지 확인 합니다.</p></li>
<li><p>공용 인스턴트 메시징 연결, Lync Federation 및 XMPP 페더레이션을 지원 하도록 내부 및 외부 DNS 레코드 구성</p></li>
<li><p>배포 하는 페더레이션 유형을 지원 하도록 방화벽에서 포트 및 프로토콜 구성</p></li>
<li><p>공용 인증서를 구하여 설치 합니다. 인증서를 획득 하는 데 필요한 시간은 인증서를 발급 하는 CA (인증 기관)에 따라 달라 집니다. 이 단계는 배포의이 시점에서 선택 사항입니다. 이 단계를 수행 하지 않는 경우에는 Edge Server 구성 중에 수행 해야 합니다. 인증서를 가져올 때까지 Edge 서버 서비스를 시작할 수 없습니다.</p></li>
</ol></td>
<td><p>이러한 역할은 일반적으로 많은 작업 그룹에서 분리 되므로 조직에 따라</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">SIP, XMPP 페더레이션 및 Lync Server 2013에서 공개 인스턴트 메시지에 대 한 계획</a></p></td>
</tr>
<tr class="odd">
<td><p>페더레이션 시나리오에 대 한 Edge 서버 설정</p></td>
<td><ol>
<li><p>내보낸 토폴로지 구성 파일을 각 Edge 서버로 전송 하거나 복제를 완료 하도록 허용</p></li>
<li><p>배포 마법사를 다시 실행 하 여 페더레이션에 대 한 지원 구성 요소 설치</p></li>
<li><p>Edge 서버 구성</p></li>
<li><p>각 Edge 서버용 인증서 요청 및 설치</p></li>
<li><p>Edge 서버 서비스 다시 시작</p></li>
</ol></td>
<td><p>관리자 그룹</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013에서 Lync 페더레이션 설정</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013에서 공용 메신저 연결 설정</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013에서 XMPP 페더레이션 설정</a></p></td>
</tr>
<tr class="even">
<td><p>외부 사용자 액세스에 대 한 지원을 구성 합니다.</p></td>
<td><ol>
<li><p>Lync Server 제어판 외부 사용자 액세스 사용</p></li>
<li><p>페더레이션 사용자 또는 공용 사용자와의 통신을 가능 하 게 하는 외부 액세스 정책 구성</p></li>
<li><p>도메인을 허용 하거나 차단 하도록 SIP 페더레이션 도메인 구성</p></li>
<li><p>공용 인스턴트 메시징 연결 공급자에 대해 SIP 페더레이션 공급자 사용</p></li>
<li><p>XMPP 도메인 당 XMPP 페더레이션 파트너 구성</p></li>
</ol></td>
<td><p>CSAdministrator 역할에 할당 된 RTCUniversalServerAdmins group 또는 사용자 계정</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대한 지원 구성</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013에서 공용 공급자용 미디어 암호화 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>Edge 서버 구성 확인</p></td>
<td><p>내부 서버에서 서버 연결 및 구성 데이터 복제 확인</p></td>
<td><p>사용자 연결 확인을 위해 CSAdministrator 역할에 할당 된 복제, RTCUniversalServerAdmins group 또는 사용자 계정에 대 한 확인을 위해 각 유형의 페더레이션 사용자에 대 한 사용자입니다.</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서 에지 배포 확인</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

