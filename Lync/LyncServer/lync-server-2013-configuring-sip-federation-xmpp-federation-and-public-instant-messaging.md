---
title: SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d97966d0a5062b133e9802f97ff77934ba29300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

페더레이션, 공용 인스턴트 메시징 연결 및 XMPP(Extensible Messaging and Presence Protocol)는 페더레이션 사용자라는 새로운 클래스의 사용자를 정의합니다. 페더레이션 Lync Server 배포 또는 XMPP 배포의 사용자는 제한 된 서비스 집합에 액세스 하 고 외부 배포에서 인증을 받습니다. 원격 사용자는 Lync Server 배포의 구성원이 며 배포에서 제공 하는 모든 서비스에 액세스할 수 있습니다.

<div>


> [!NOTE]
> AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.



</div>

공용 인스턴트 메시징 연결은 lync Server 클라이언트가 Lync 2013를 사용 하 여 구성 된 공용 인스턴트 메시징 파트너에 액세스할 수 있도록 하는 특별 한 유형의 페더레이션입니다. 현재 공용 인스턴트 메시징 연결 파트너는 다음과 같습니다.

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

공용 인스턴트 메시징 연결 구성을 사용하면 Lync 사용자가 다음을 통해 공용 인스턴트 메시징 연결 사용자에 액세스할 수 있습니다.

  - IM 및 현재 상태

  - Lync 클라이언트에 공용 인스턴트 메시징 연결 대화 상대 표시

  - 대화 상대와 개인간 IM 대화

  - Windows Live 사용자와 오디오 및 비디오 통화

Lync Server 페더레이션은 조직의 Lync Server 배포와 다른 Office Communications Server 2007 R2 또는 Lync Server 배포 간의 규약을 정의합니다. 페더레이션 구성을 사용하면 Lync 사용자가 다음을 통해 페더레이션 사용자에 액세스할 수 있습니다.

  - IM 및 현재 상태

  - Lync 클라이언트에 페더레이션 대화 상대 만들기

XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)을 기반으로 외부 배포를 정의합니다. XMPP 구성을 사용하면 Lync 사용자가 다음을 통해 허용된 XMPP 도메인 사용자에 액세스할 수 있습니다.

  - IM 및 현재 상태 – 개인간에만 가능

  - Lync 클라이언트에서 XMPP 페더레이션 연락처 만들기

<div>


> [!IMPORTANT]
> Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>에지 서버 외부 페더레이션, 공용 인스턴트 메시징 연결 및 XMPP 사용자 배포 프로세스


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
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기존 에지 배포에 추가할 옵션 결정</p></td>
<td><p>토폴로지 작성기를 실행 하 여에 지 서버 설정을 편집 하 고 토폴로지를 만들고 게시 합니다. 기존에 지 토폴로지가 중앙 관리 저장소에서에 지 서버로 변경 내용을 복제 합니다.</p></td>
<td><p>Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹</p>



> [!NOTE]
> 로컬 사용자 그룹의 구성원인 계정을 사용하여 토폴로지를 편집할 수 있지만 토폴로지를 게시하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정이 필요합니다.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서에 지 및 디렉터 토폴로지 구축</a></p></td>
</tr>
<tr class="even">
<td><p>설치 준비</p></td>
<td><ol>
<li><p>시스템 필수 구성 요소를 충족하는지 확인합니다.</p></li>
<li><p>공용 인스턴트 메시징 연결, Lync 페더레이션 및 XMPP 페더레이션을 지원하도록 내부/외부 DNS 레코드를 구성합니다.</p></li>
<li><p>배포하려는 페더레이션 유형을 지원하도록 방화벽의 포트와 프로토콜을 구성합니다.</p></li>
<li><p>공용 인증서를 얻어 설치합니다. 인증서를 얻는 데 소요되는 시간은 인증서를 발급하는 CA(인증 기관)에 따라 다릅니다. 이 시점에서는 이 단계가 배포의 선택 사항이지만 이 시점에 이 단계를 수행하지 않을 경우 에지 서버 구성 중에 수행해야 합니다. 인증서를 얻어야만 에지 서버 서비스를 시작할 수 있습니다.</p></li>
</ol></td>
<td><p>일반적으로 이러한 역할은 여러 작업 그룹으로 분할되므로 조직의 필요에 따라 지정하면 됩니다.</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획</a></p></td>
</tr>
<tr class="odd">
<td><p>페더레이션 시나리오를 위한 에지 서버 설정</p></td>
<td><ol>
<li><p>내보낸 토폴로지 구성 파일을 각 에지 서버로 전송합니다. 즉, 복제가 완료되도록 합니다.</p></li>
<li><p>배포 마법사를 다시 실행하여 페더레이션을 위한 지원 구성 요소를 설치합니다.</p></li>
<li><p>에지 서버를 구성합니다.</p></li>
<li><p>각 에지 서버에 대한 인증서를 요청하고 설치합니다.</p></li>
<li><p>에지 서버 서비스를 다시 시작합니다.</p></li>
</ol></td>
<td><p>Administrators 그룹</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013에서 Lync 페더레이션 설정</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013에서 공용 인스턴트 메시징 연결 설정</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013에서 XMPP 페더레이션 설정</a></p></td>
</tr>
<tr class="even">
<td><p>외부 사용자 액세스에 대한 지원 구성</p></td>
<td><ol>
<li><p>Lync Server 제어판 외부 사용자 액세스 사용</p></li>
<li><p>페더레이션 사용자 또는 공용 사용자와의 통신을 사용할 수 있도록 외부 액세스 정책을 구성합니다.</p></li>
<li><p>도메인을 허용하거나 차단하도록 SIP 페더레이션 도메인을 구성합니다.</p></li>
<li><p>공용 인스턴트 메시징 연결 공급자에 대해 SIP 페더레이션 공급자를 사용하도록 설정합니다.</p></li>
<li><p>XMPP 도메인별로 XMPP 페더레이션 파트너를 구성합니다.</p></li>
</ol></td>
<td><p>CSAdministrator 역할에 할당된 RTCUniversalServerAdmins 그룹 또는 사용자 계정</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013에서 공용 공급자에 대해 미디어 암호화 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>에지 서버 구성 확인</p></td>
<td><p>서버 연결과 내부 서버에서의 구성 데이터 복제를 확인합니다.</p></td>
<td><p>복제 확인을 위해서는 CSAdministrator 역할에 할당된 RTCUniversalServerAdmins 그룹 또는 사용자 계정, 사용자 연결 확인을 위해서는 각 페더레이션 사용자 유형의 사용자</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서에 지 배포 확인</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

