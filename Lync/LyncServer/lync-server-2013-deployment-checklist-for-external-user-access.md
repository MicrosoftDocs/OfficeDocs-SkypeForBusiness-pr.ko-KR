---
title: 'Lync Server 2013: 외부 사용자 액세스를 위한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스를 위한 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-04_

경계 네트워크를 배포 하 고 외부 사용자에 대 한 지원을 구현 하기 전에 먼저 프런트 엔드 풀 또는 Standard Edition 서버를 포함 하 여 Microsoft Lync Server 2013 내부 서버를 배포 해야 합니다. 내부 네트워크에 선택 디렉터를 배포 하려는 경우에는 Edge 서버를 배포 하기 전에 해당 감독도 배포 해야 합니다. 디렉터 배포 프로세스에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하세요.

Microsoft Lync Server 2013에는 내부 서버와 Edge 서버를 쉽게 계획 하 고 배포할 수 있는 도구가 포함 되어 있습니다. 토폴로지가 완료 되 면 결과 토폴로지 정의를 프로덕션 환경에 게시 합니다. 이렇게 하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원 이어야 합니다.

  - **계획 도구**   Office Communications Server 2007 R2에는 토폴로지 디자인을 안내 하는 데 사용할 수 있는 계획 도구와 Edge 계획 도구가 포함 되어 있습니다. Lync Server 2010에서 이러한 두 가지 도구는 계획 된 사용자 수, 음성 요구 사항, 외부 사용자 액세스 형식, 페더레이션 옵션 수집 등의 추가 기능 및 기능을 제공 하는 단일 계획 도구로 결합 되었습니다. 또한 IP 주소, 부하 분산 장치 유형 및 기타 경계 네트워크 고려 사항 등 인프라의 네트워크 매개 변수를 계획할 수 있습니다.

  - **토폴로지 작성기**   Lync Server 2013 토폴로지 작성기를 사용 하 여 토폴로지와 구성 요소를 정의할 수 있습니다. 토폴로지 작성기는 Lync Server 2013를 실행 하는 서버를 배포 하는 데 필요 합니다. 토폴로지 작성기는 조직에서 Lync Server 2013을 실행 하는 모든 서버를 구성 하는 데 사용 되는 중앙 관리 저장소에 결과를 게시 합니다. 토폴로지 작성기를 사용 하지 않고 서버에 Lync Server 2013을 설치할 수 없습니다.

Edge 토폴로지를 정의 하기 위한 토폴로지 작성기 실행을 비롯 하 여 계획 프로세스 중에 edge 토폴로지를 디자인 한 경우 해당 결과를 사용 하 여 Edge 서버 배포를 시작할 수 있습니다. 앞에 edge 토폴로지 빌드가 완료 되지 않았거나 이전에 지정한 정보를 변경 하려는 경우에는 다른 배포 단계를 진행 하기 전에 토폴로지 작성기 실행을 완료 해야 합니다. 토폴로지를 빌드하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.

계획 도구 및 토폴로지 작성기에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하세요.

다음 표에서는 Edge 서버 배포 프로세스에 대해 간략하게 설명 합니다. 외부 사용자 액세스를 배포 하기 전에 수행 해야 하는 계획 결정을 검토 하려면 [Lync Server 2013에서 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.

<div>


> [!WARNING]  
> 다음 표의 정보는 새 배포에 대해 중점적으로 설명 합니다. Lync Server 2010, Office Communications Server 2007 R2 또는 Office Communications Server 2007 환경에 Edge 서버를 배포한 경우 Lync Server 2013로 마이그레이션하는 방법에 대 한 자세한 내용은 <A href="migration.md">마이그레이션을</A> 참조 하세요. Office communications server 2007, Live Communications Server 2005 및 Live Communications Server 2003을 포함 하 여 Office Communications Server 2007 R2 이전의 모든 버전에서 마이그레이션이 지원 되지 않습니다.



</div>

Edge 서버 성능 및 보안을 개선 하 고 배포를 용이 하 게 하려면 경계 네트워크 및 Edge 서버를 배포할 때 다음과 같은 모범 사례를 적용 하세요.

  - 조직 내에서 Lync Server 2013의 작동을 테스트 하 고 확인 한 후에만 Edge 서버를 배포 합니다.

  - 도메인이 아닌 작업 그룹에 Edge 서버를 배포 하는 것이 좋습니다. 이렇게 하면 설치를 간소화 하 고 주변 네트워크의 AD DS (Active Directory 도메인 서비스)를 유지할 수가 있습니다. 주변 네트워크에서 AD DS를 찾으면 심각한 보안 위험을 일으킬 수 있습니다.

  - 경계 네트워크에 있는 도메인에 대 한 Edge 서버 참가는 지원 되지만 권장 되지 않습니다. Edge 서버는 내부 도메인의 일부인 신뢰할 수 있는 네트워크 경계를 위반 하며,이는 인터넷이 가장 신뢰 되 고 주변 네트워크는 인터넷 보다 신뢰 하 고 내부 네트워크는 가장 신뢰 하는 것입니다. Edge 서버는 도메인의 구성원으로 서 가장 신뢰할 수 있는 네트워크의 일부 이며 신뢰할 수 있는 네트워크 (경계)에 위치 합니다.

<div>

## <a name="deployment-process-for-edge-servers"></a>Edge 서버의 배포 프로세스


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
<td><p>적절 한 가장자리 토폴로지를 만들고 적절 한 구성 요소를 결정 합니다.</p></td>
<td><ul>
<li><p>토폴로지 작성기를 실행 하 여 Edge 서버 설정을 구성 하 고 토폴로지를 만들고 게시 한 다음 Lync Server Management Shell을 사용 하 여 토폴로지 구성 파일을 내보냅니다.</p></li>
</ul></td>
<td><p><strong>Domain admins</strong> 그룹 및 <strong>RTCUniversalServerAdmins</strong> 또는 <strong>csadmins</strong> 그룹</p>
<div>

> [!NOTE]  
> 로컬 users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정이 필요 합니다.


</div></td>
<td><p>배포 설명서의 <a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서 edge 및 디렉터 토폴로지 빌드</a></p></td>
</tr>
<tr class="even">
<td><p>설치 준비.</p></td>
<td><ol>
<li><p>시스템 필수 조건이 충족 되었는지 확인 합니다.</p></li>
<li><p>각 Edge 서버의 내부 및 공용 네트워크 인터페이스 모두에 대해 IP 주소 (IPv4 및 IPv6 (사용 되는 경우)를 구성 합니다.</p></li>
<li><p>컴퓨터의 DNS 접미사를 Edge 서버로 배포할 수 있도록 구성 하는 것을 포함 하 여 내부 및 외부 DNS 레코드 (IPv4 및 IPv6 용 호스트 A 및 AAAA)를 구성 합니다.</p></li>
<li><p>) 공용 인증서를 만들고 설치 합니다. 인증서를 획득 하는 데 필요한 시간은 인증서를 발급 하는 CA (인증 기관)에 따라 달라 집니다. 이 단계를 수행 하지 않는 경우에는 Edge Server 설치 중에 수행 해야 합니다. Edge 서버 서비스는 인증서를 얻고 설치할 때까지 시작할 수 없습니다.</p></li>
<li><p>배포에서 Windows Live, AOL 또는 Yahoo!와의 통신을 지 원하는 경우 공용 IM 연결에 대 한 지원을 제공 합니다. 사용자.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>


</div></li>
<li><p>배포에 사용 하는 경우 Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 파트너에 대해 XMPP 및 페더레이션 지원에 대 한 지원을 제공 합니다.</p></li>
<li><p>방화벽을 구성 합니다.</p></li>
</ol></td>
<td><p>조직에 맞게</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 경계 네트워크에서 서버 설치 준비</a></p></td>
</tr>
<tr class="odd">
<td><p>역방향 프록시를 설정 합니다.</p></td>
<td><ul>
<li><p>경계 네트워크에서 역방향 프록시 (예: Microsoft Forefront 위협 관리 게이트웨이 2010 또는 Microsoft 인터넷 보안 및 가속 (ISA) 서버)를 설정 하 고 필요한 공개 인증서를 얻고 다음을 구성 합니다. 리버스 프록시 서버의 웹 게시 규칙</p>
<p>이동성을 계획 하 고 프런트 엔드 풀 또는 Standard Edition 서버에 모바일 서비스를 배포 하는 경우 모바일 서비스에 대 한 리버스 프록시를 준비 합니다.</p></li>
</ul></td>
<td><p><strong>관리자</strong> 그룹 또는 리버스 프록시 관리자</p></td>
<td><p>배포 설명서에서 <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013에 대 한 역방향 프록시 서버 설정</a></p></td>
</tr>
<tr class="even">
<td><p>디렉터를 설정 합니다 (선택 사항).</p></td>
<td><ul>
<li><p>) 내부 네트워크에 하나 이상의 디렉터를 설치 하 고 구성 합니다.</p></li>
</ul></td>
<td><p><strong>관리자</strong> 그룹</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013에서 디렉터 설정</a></p></td>
</tr>
<tr class="odd">
<td><p>Edge 서버를 설정 합니다.</p></td>
<td><ol>
<li><p>필수 구성 요소 소프트웨어를 설치 합니다.</p></li>
<li><p>내보낸 토폴로지 구성 파일을 각 Edge 서버로 전송 합니다.</p></li>
<li><p>각 Edge 서버에 Lync Server 2013 소프트웨어를 설치 합니다.</p></li>
<li><p>Edge 서버를 구성 합니다.</p></li>
<li><p>각 Edge 서버에 대 한 인증서를 요청 하 고 설치 합니다.</p></li>
<li><p>Edge 서버 서비스를 시작 합니다.</p></li>
</ol></td>
<td><p><strong>관리자</strong> 그룹</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013에서 Edge 서버 설정</a></p></td>
</tr>
<tr class="even">
<td><p>외부 사용자 액세스를 위한 배포를 구성 합니다.</p></td>
<td><ol>
<li><p>Lync Server 제어판을 사용 하 여 다음에 대 한 지원을 구성 합니다 (해당 하는 경우).</p>
<ul>
<li><p>미디어 릴레이</p></li>
<li><p>페더레이션 경로</p></li>
<li><p>원격 사용자 액세스</p></li>
<li><p>Lync Server, Office Communications Server 및 Live Communications Server의 페더레이션</p></li>
<li><p>공용 메신저 연결</p></li>
<li><p>XMPP 페더레이션</p></li>
<li><p>익명 사용자</p></li>
</ul></li>
<li><p>원격 사용자 액세스, 페더레이션, 공용 IM 연결, XMPP 및 익명 사용자 지원 (해당 되는 경우)에 대 한 사용자 계정 구성</p></li>
</ol></td>
<td><p><strong>Csadministrator</strong> 역할에 할당 된 <strong>RTCUniversalServerAdmins</strong> group 또는 사용자 계정</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>Edge 서버 구성을 확인 합니다.</p></td>
<td><ol>
<li><p>내부 서버에서 구성 데이터의 복제 및 서버 연결을 확인 합니다.</p></li>
<li><p>원격 사용자, 페더레이션 도메인의 사용자, 공용 IM 사용자, 익명 사용자를 비롯 한 외부 사용자가 배포에 적절 하 게 연결할 수 있는지 확인 합니다.</p></li>
<li><p>Lync Server 원격 연결 분석기를 사용 하 여 구성 및 통신 확인<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>구성 및 통신 문제 해결</p></li>
</ol></td>
<td><p><strong>Csadministrator</strong> 역할에 할당 된 복제, <strong>RTCUniversalServerAdmins</strong> group 또는 사용자 계정 확인</p>
<p>사용자 연결 확인을 위해 지원 되는 각 외부 사용자 액세스 유형에 대 한 사용자</p>
<p>원격 사용자</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서 edge 배포 확인</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

