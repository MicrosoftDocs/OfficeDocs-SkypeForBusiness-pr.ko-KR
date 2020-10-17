---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 배포 검사 목록'
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
ms.openlocfilehash: 010d4437f2eb90d596ace15cc392690dba5544d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522775"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스에 대 한 배포 검사 목록

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-04_

경계 네트워크를 배포 하 고 외부 사용자에 대 한 지원을 구현 하기 전에 이미 프런트 엔드 풀 또는 Standard Edition 서버를 비롯 한 Microsoft Lync Server 2013 내부 서버를 배포 해야 합니다. 내부 네트워크에 선택적 디렉터를 배포 하려는 경우에는에 지 서버를 배포 하기 전에이를 배포 해야 합니다. 디렉터 배포 프로세스에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하십시오.

Microsoft Lync Server 2013에는 내부 서버와에 지 서버를 모두 계획 하 고 배포 하는 데 도움이 되는 도구가 포함 되어 있습니다. 토폴로지를 완료한 후 결과 토폴로지 정의를 프로덕션 환경으로 게시합니다. 이렇게 하려면 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원이어야 합니다.

  - **계획 도구**     Office Communications Server 2007 R2에는 토폴로지 디자인을 안내 하는 데 사용할 수 있는 계획 도구와 Edge 계획 도구가 포함 되어 있습니다. Lync Server 2010에서는 이러한 두 도구를 계획 된 사용자 수, 음성 요구 사항, 외부 사용자 액세스 유형 및 페더레이션 옵션 수집과 같은 추가 기능을 제공 하는 단일 기획 도구로 결합 했습니다. 또한 IP 주소, 부하 분산 장치 유형 및 기타 경계 네트워크 고려 사항과 같은 인프라의 네트워크 매개 변수를 계획할 수 있습니다.

  - **토폴로지 작성기**     Lync Server 2013 토폴로지 작성기를 사용 하면 토폴로지 및 구성 요소를 쉽게 정의할 수 있습니다. Lync Server 2013를 실행 하는 서버를 배포 하려면 토폴로지 작성기가 필수적입니다. 토폴로지 작성기는 조직에서 Lync Server 2013을 실행 하는 모든 서버를 구성 하는 데 사용 되는 중앙 관리 저장소에 결과를 게시 합니다. 토폴로지 작성기를 사용 하지 않고 서버에 Lync Server 2013을 설치할 수는 없습니다.

에 지 토폴로지를 정의 하기 위해 토폴로지 작성기를 실행 하는 것을 포함 하 여 계획 프로세스 중에에 지 토폴로지를 디자인 한 경우 이러한 결과를 사용 하 여에 지 서버 배포를 시작할 수 있습니다. 이전에에 지 토폴로지의 작성을 완료 하지 않았거나 이전에 지정한 정보를 변경 하려는 경우에는 다른 배포 단계를 진행 하기 전에 토폴로지 작성기 실행을 완료 해야 합니다. 토폴로지를 작성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.

계획 도구 및 토폴로지 작성기에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하십시오.

다음 표에는 에지 서버 배포 프로세스에 대한 개요가 나와 있습니다. 외부 사용자 액세스를 배포 하기 전에 수행 해야 하는 계획 결정을 검토 하려면 [Lync Server 2013에서 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.

<div>


> [!WARNING]  
> 다음 표에서는 새 배포를 중심으로 관련 정보를 설명합니다. Lync Server 2010, Office Communications Server 2007 R2 또는 Office Communications Server 2007 환경에에 지 서버를 배포한 경우 Lync Server 2013로 마이그레이션하는 방법에 대 한 자세한 내용은 <A href="migration.md">마이그레이션을</A> 참조 하십시오. Office Communications Server 2007, Live Communications Server 2005 및 Live Communications Server 2003를 포함 하 여 Office Communications Server 2007 R2 이전 버전에서는 마이그레이션이 지원 되지 않습니다.



</div>

에지 서버 성능과 보안을 향상시키고 배포를 용이하게 하려면 경계 네트워크 및 에지 서버를 배포할 때 다음의 모범 사례를 적용하십시오.

  - 조직 내에서 Lync Server 2013의 작동을 테스트 하 고 확인 한 후에만에 지 서버를 배포 합니다.

  - 도메인이 아닌 작업 그룹에서 에지 서버를 배포하는 것이 좋습니다. 이렇게 하면 설치가 간단해지고 AD DS(Active Directory 도메인 서비스)가 경계 네트워크에 포함되지 않습니다. AD DS를 경계 네트워크 내에 배치하면 상당한 보안 위험이 초래될 수 있습니다.

  - 완전히 경계 네트워크에 있는 도메인에 에지 서버를 가입시킬 수는 있지만 권장되지 않습니다. 내부 도메인의 일부인 에지 서버가 신뢰할 수 있는 네트워크 경계를 위반하게 됩니다. 인터넷은 신뢰 수준이 가장 낮고, 경계 네트워크는 인터넷보다 신뢰 수준이 높으며, 내부 네트워크는 신뢰 수준이 가장 높습니다. 도메인의 구성원인 에지 서버는 자동적으로 가장 신뢰할 수 있는 네트워크의 일부가 되지만 신뢰 수준이 낮은 네트워크(경계 네트워크)에 존재하기 때문입니다.

<div>

## <a name="deployment-process-for-edge-servers"></a>에지 서버 배포 프로세스


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
<td><p>적절한 에지 토폴로지를 만들고 해당 구성 요소 확인</p></td>
<td><ul>
<li><p>토폴로지 작성기를 실행 하 여 Edge Server 설정을 구성 하 고 토폴로지를 만들고 게시 한 다음 Lync Server 관리 셸을 사용 하 여 토폴로지 구성 파일을 내보냅니다.</p></li>
</ul></td>
<td><p><strong>Domain Admins</strong> 그룹 및 <strong>RTCUniversalServerAdmins</strong> 또는 <strong>csadmins</strong> 그룹</p>
<div>

> [!NOTE]  
> 로컬 사용자 그룹의 구성원인 계정을 사용하여 토폴로지를 정의할 수 있지만 토폴로지를 게시하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원인 계정이 필요합니다.


</div></td>
<td><p>배포 설명서의 <a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서에 지 및 디렉터 토폴로지 구축</a></p></td>
</tr>
<tr class="even">
<td><p>설치 준비</p></td>
<td><ol>
<li><p>시스템 필수 구성 요소를 충족하는지 확인합니다.</p></li>
<li><p>각 에지 서버에서 내부 인터페이스와 공용 네트워크 인터페이스에 대한 IP 주소(IPv4 및 IPv6)를 구성합니다.</p></li>
<li><p>에지 서버로 배포할 컴퓨터에 대한 DNS 접미사 구성을 포함하여 내부 및 외부 DNS 레코드(IPv4 및 IPv6의 경우 호스트 A 및 AAAA)를 구성합니다.</p></li>
<li><p>(선택 사항) 공용 인증서를 만들고 설치합니다. 인증서를 얻는 데 소용되는 시간은 인증서를 발급하는 CA(인증 기관)에 따라 다릅니다. 지금 이 단계를 수행하지 않은 경우 에지 서버 설치 시 이 단계를 수행해야 합니다. 인증서를 얻고 설치할 때까지 에지 서버 서비스를 시작할 수 없습니다.</p></li>
<li><p>Windows Live, AOL 또는 Yahoo! 사용자와의 통신을 지원하려면 공용 IM 연결에 대한 지원을 프로비전합니다.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>


</div></li>
<li><p>배포에 사용 되는 경우 Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 파트너에 대 한 XMPP 및 페더레이션 지원을 프로 비전 합니다.</p></li>
<li><p>방화벽을 구성합니다.</p></li>
</ol></td>
<td><p>조직에 적절한 권한</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">경계 네트워크에서 Lync Server 2013에 대 한 서버 설치 준비</a></p></td>
</tr>
<tr class="odd">
<td><p>역방향 프록시 설정</p></td>
<td><ul>
<li><p>경계 네트워크에 역방향 프록시 (예: Microsoft Forefront Threat Management Gateway 2010 또는 Microsoft Internet Security and 가속도 (ISA) Server 서비스 팩 1)를 설정 하 고, 필요한 공용 인증서를 획득 하 고, 역방향 프록시 서버에서 웹 게시 규칙을 구성 합니다.</p>
<p>이동성을 계획하고 Mobility Service를 프런트 엔드 풀 또는 Standard Edition 서버에 배포 중인 경우 Mobility Service에 대한 역방향 프록시를 준비합니다.</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 그룹 또는 역방향 프록시 관리자</p></td>
<td><p>배포 설명서에서 <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013에 대 한 역방향 프록시 서버 설정</a></p></td>
</tr>
<tr class="even">
<td><p>디렉터를 설치합니다(선택 사항).</p></td>
<td><ul>
<li><p>(선택 사항) 내부 네트워크에 하나 이상의 디렉터를 설치 및 구성합니다.</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 그룹</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013에서 디렉터 설정</a></p></td>
</tr>
<tr class="odd">
<td><p>에지 서버 설정</p></td>
<td><ol>
<li><p>필수 소프트웨어를 설치합니다.</p></li>
<li><p>내보낸 토폴로지 구성 파일을 각 에지 서버로 전송합니다.</p></li>
<li><p>각에 지 서버에 Lync Server 2013 소프트웨어를 설치 합니다.</p></li>
<li><p>에지 서버를 구성합니다.</p></li>
<li><p>각 에지 서버에 대한 인증서를 요청하고 설치합니다.</p></li>
<li><p>에지 서버 서비스를 시작합니다.</p></li>
</ol></td>
<td><p><strong>Administrators</strong> 그룹</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013에서에 지 서버 설정</a></p></td>
</tr>
<tr class="even">
<td><p>외부 사용자 액세스에 대한 배포를 구성합니다.</p></td>
<td><ol>
<li><p>Lync Server 제어판을 사용 하 여 다음 각 사항에 대 한 지원을 구성 합니다 (해당 하는 경우).</p>
<ul>
<li><p>미디어 중계</p></li>
<li><p>페더레이션 경로</p></li>
<li><p>원격 사용자 액세스</p></li>
<li><p>Lync Server, Office Communications Server 및 Live Communications Server와의 페더레이션</p></li>
<li><p>공용 IM 연결</p></li>
<li><p>XMPP 페더레이션</p></li>
<li><p>익명 사용자</p></li>
</ul></li>
<li><p>원격 사용자 액세스, 페더레이션, 공용 IM 연결, XMPP 및 익명 사용자 지원을 구성합니다(적용 가능한 경우).</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> 그룹 또는 <strong>CSAdministrator</strong> 역할에 지정된 사용자 계정</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>에지 서버 구성 확인</p></td>
<td><ol>
<li><p>서버 연결 및 내부 서버의 구성 데이터 복제를 확인합니다.</p></li>
<li><p>원격 사용자, 페더레이션 도메인의 사용자, 공용 IM 사용자 및 익명 사용자를 포함하여 배포에 해당되는 외부 사용자가 연결할 수 있는지 확인합니다.</p></li>
<li><p>Lync Server 원격 연결 분석기를 사용 하 여 구성 및 통신 확인 <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>구성 및 통신 문제를 해결합니다.</p></li>
</ol></td>
<td><p>복제 확인의 경우 <strong>RTCUniversalServerAdmins</strong> 그룹 또는 <strong>CSAdministrator</strong> 역할에 지정된 사용자 계정</p>
<p>사용자 연결 확인의 경우 지원할 각 외부 사용자 액세스 유형의 사용자</p>
<p>원격 사용자</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서에 지 배포 확인</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

