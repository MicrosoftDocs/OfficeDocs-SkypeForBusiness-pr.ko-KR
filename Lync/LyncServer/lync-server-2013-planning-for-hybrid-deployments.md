---
title: 'Lync Server 2013: 하이브리드 배포 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Lync Server 2013 하이브리드 배포 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-05-25_

하이브리드 배포를 계획 하는 동안 사용자 및 네트워크 인프라에 대 한 다음과 같은 요구 사항을 고려해 야 합니다.

<div>

## <a name="infrastructure-requirements"></a>인프라 요구 사항

하이브리드 배포를 구현 하 고 배포 하려면 환경에 다음이 구성 되어 있어야 합니다.

  - 비즈니스용 Skype Online이 활성화 된 Microsoft Office 365 테 넌 트 온-프레미스 배포의 경우 단일 테 넌 트만 하이브리드 구성에 사용할 수 있습니다.

  - 지원 되는 토폴로지에서 배포 되는 비즈니스용 Skype 서버 또는 Lync Server의 단일 온 프레미스 배포 (인프라)입니다. 토폴로지 요구 사항을 참조 하세요.
    
    하이브리드 용 Lync Server 2013 또는 Lync Server 2010 배포를 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013 하이브리드 배포 구성을](lync-server-2013-configuring-hybrid-deployments.md)참조 하세요.

  - 비즈니스용 Skype 서버 2015 관리 도구. Lync Server 2013 또는 Lync Server 2010를 사용 하는 경우 Lync Server 2013 관리 도구를 사용할 수 있습니다.

  - 사용자가 온-프레미스에서 Office에 로그인 할 때 동일한 로그인 자격 증명을 사용할 수 있도록 Office 365의 Single Sign-on을 지원 하려면 Azure Active Directory (AAD) Connect의 암호 동기화 기능을 사용할 수 있습니다. Office 365에서 single sign-on에 AD FS (Active Directory Federation Services)를 사용할 수도 있습니다.
    
    자세한 내용은 [온-프레미스 id를 Azure Active Directory와 통합](http://go.microsoft.com/fwlink/p/?linkid=619754)을 참조 하세요.

  - 온-프레미스 및 온라인 Active Directory 개체를 동기화 된 상태로 유지 하는 단일 디렉터리 동기화 솔루션입니다. 디렉터리 동기화에 대 한 자세한 내용은 [디렉터리 통합 도구](http://go.microsoft.com/fwlink/p/?linkid=530320)를 참조 하세요.

</div>

<div>

## <a name="lync-client-support"></a>Lync 클라이언트 지원

Lync 클라이언트에서 지원 되는 기능 외에도 온-프레미스 및 온라인 환경에서 사용할 수 있는 기능에는 몇 가지 차이점이 있습니다. 조직의 사용자를 집에 배치할 위치를 결정 하기 전에 Lync Server의 다양 한 구성에 대 한 클라이언트 지원을 볼 수 있습니다. Lync 하이브리드 배포의 비즈니스용 Skype Online에서 지원 되는 클라이언트는 다음과 같습니다.

  - Lync 2010

  - Lync 2013

  - Lync Windows 스토어 앱

  - Lync Web App

  - Lync 모바일

  - Mac용 Lync 2011

  - Lync 채팅방 시스템

  - Lync Basic 2013

클라이언트 지원에 대 한 자세한 내용은 다음 항목을 참조 하세요.

  - [Lync Online 용 클라이언트](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 의 클라이언트 비교 표](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 의 모바일 클라이언트 비교 표](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>토폴로지 요구 사항

비즈니스용 Skype Online으로 하이브리드 배포를 구성 하려면 다음 지원 토폴로지 중 하나가 있어야 합니다.

  - 비즈니스용 skype server 2015를 실행 하는 모든 서버와의 비즈니스용 Skype 서버 2015 배포

  - Lync server 2013를 실행 하는 모든 서버에 2013 배포

  - Lync server 2010는 최신 누적 업데이트로 Lync Server 2010를 실행 하는 모든 서버에 배포 됩니다.
    
      - 페더레이션 edge 서버의 페더레이션 Edge 서버와 다음 홉 서버는 최신 누적 업데이트로 Lync Server 2010을 실행 해야 합니다.
    
      - 비즈니스용 Skype 서버 2015 또는 Lync Server 2013 관리 도구는 하나 이상의 서버 또는 관리 워크스테이션에 설치 되어 있어야 합니다.

  - 비즈니스용 Skype 서버 2015을 실행 하는 하나 이상의 사이트에서 다음 서버 역할을 사용 하는 혼합 Lync Server 2013 및 비즈니스용 Skype Server 2015 배포:
    
      - 하나 이상의 엔터프라이즈 풀 또는 Standard Edition 서버
    
      - SIP 페더레이션과 연결 된 디렉터 풀 (있는 경우)
    
      - SIP 페더레이션과 연결 된 Edge 풀

  - 비즈니스용 Skype 서버 2015을 실행 하는 하나 이상의 사이트에서 다음 서버 역할이 포함 된 혼합 Lync Server 2010 및 비즈니스용 Skype Server 2015 배포:
    
      - 하나 이상의 엔터프라이즈 풀 또는 Standard Edition 서버
    
      - SIP 페더레이션과 연결 된 디렉터 풀 (있는 경우)
    
      - 사이트의 SIP 페더레이션과 연결 된 Edge 풀

  - Lync server 2013을 실행 하는 하나 이상의 사이트에서 다음 서버 역할을 사용 하 여 lync server 2010 및 Lync Server 2013 배포가 혼합 되었습니다.
    
      - 사이트에서 하나 이상의 엔터프라이즈 풀 또는 Standard Edition 서버
    
      - 사이트에 있는 경우 SIP 페더레이션과 연결 된 디렉터 풀
    
      - 사이트의 SIP 페더레이션과 연결 된 Edge 풀

<div>


> [!IMPORTANT]  
> 온라인에서 온-프레미스와 UNRESOLVED_TOKEN_VAL (입력) 간에 사용자 이동을 비롯 한 모든 사용자 관리는 최신 버전의 관리 도구를 사용 하 여 수행 해야 합니다. 관리 도구는 기존 온-프레미스 배포 및 인터넷에 대 한 연결 액세스 권한이 있는 별도의 서버에 설치 되어 있어야 합니다. 온-프레미스 배포의 사용자를 UNRESOLVED_TOKEN_VAL (skype16_online)으로 이동 하려면 온-프레미스 배포에 연결 된 관리 도구를 사용 하 여 온- <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">CsUser</A> cmdlet을 실행 해야 합니다.



</div>

지원 되는 토폴로지에 대 한 자세한 내용은 [Lync server 2013에서 지원 되](lync-server-2013-supported-topologies.md)는 토폴로지와 [엔터프라이즈 하이브리드 배포에 대 한 Lync Server 2013 참조 토폴로지](http://go.microsoft.com/fwlink/p/?linkid=398709)를 참조 하세요.

Lync Online에 하이브리드 배포 및 PowerShell 연결에 대 한 문제 해결 정보는 lync [online: Lync PowerShell 및 하이브리드 문제 해결](http://go.microsoft.com/fwlink/p/?linkid=306718)을 참조 하세요.

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>페더레이션 허용/차단 목록에 대 한 요구 사항

허용 된 도메인 목록에는 파트너의 Edge FQDN (정규화 된 도메인 이름)이 구성 된 도메인이 포함 됩니다. 이를 *허용 된 파트너 서버* 또는 *직접 페더레이션 파트너*라고 하기도 합니다. 온-프레미스 배포에서 각각 *파트너 검색* 및 *허용 된 파트너 도메인 목록*이라고 하는 열려 있는 페더레이션과 닫힌 페더레이션 간의 차이에 대해 잘 알고 있어야 합니다.

하이브리드 배포를 성공적으로 구성 하려면 다음 요구 사항을 충족 해야 합니다.

  - 도메인 일치는 온-프레미스 배포 및 Office 365 테 넌 트에 대해 동일 하 게 구성 되어야 합니다. 온-프레미스 배포에서 파트너 검색을 사용 하도록 설정한 경우 온라인 테 넌 트에 대해 open federation를 구성 해야 합니다. 파트너 검색을 사용할 수 없는 경우에는 사용자의 온라인 테 넌 트에 대해 닫힌 페더레이션이 구성 되어야 합니다.

  - 온-프레미스 배포의 차단 된 도메인 목록이 온라인 테 넌 트에 대 한 차단 된 도메인 목록과 정확히 일치 해야 합니다.

  - 온-프레미스 배포의 허용 도메인 목록이 온라인 테 넌 트에 대해 허용 된 도메인 목록과 정확히 일치 해야 합니다.

  - Lync Online 제어판을 사용 하 여 구성 된 온라인 테 넌 트의 외부 통신에 대해 페더레이션을 사용 하도록 설정 해야 합니다.

</div>

<div>

## <a name="dns-settings"></a>DNS 설정

하이브리드 배포에 대 한 DNS 레코드를 만들 때 모든 Lync 외부 DNS 레코드는 온-프레미스 인프라를 가리켜야 합니다. 필수 DNS 레코드에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS (Domain Name System) 요구 사항을](lync-server-2013-domain-name-system-dns-requirements.md)참조 하세요.

또한 다음 표에 설명 된 DNS 확인이 온-프레미스 배포에서 작동 하도록 해야 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS 레코드</p></td>
<td><p>확인할 사람</p></td>
<td><p>DNS 요구 사항</p></td>
</tr>
<tr class="even">
<td><p>_Tcp에 대 한 DNS SRV 레코드 _sipfederationtls. &lt;EDGE&gt; 외부 IP에 액세스 하기 위해 지원 되는 모든 SIP 도메인이 sipdomain.com.</p></td>
<td><p>Edge 서버 (s)</p></td>
<td><p>하이브리드 구성에서 페더레이션된 통신을 사용 하도록 설정 합니다. Edge 서버는 온-프레미스와 온라인 간에 분할 된 SIP 도메인의 페더레이션 트래픽을 라우팅하는 위치를 알고 있어야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>DNS A Edge 웹 회의 서비스의 FQDN (예: 웹 회의에 대 한 webcon.contoso.com 해결) 외부 IP에 대 한 i d A A</p></td>
<td><p>내부 회사 네트워크에 연결 된 사용자 컴퓨터</p></td>
<td><p>온라인 사용자가 온-프레미스 호스트 모임에서 콘텐츠를 프레젠테이션 하거나 볼 수 있도록 설정 합니다. 콘텐츠에는 PowerPoint 파일, 화이트 보드, 설문 조사 및 공유 메모가 포함 됩니다.</p></td>
</tr>
</tbody>
</table>


조직에서 DNS를 구성 하는 방법에 따라 해당 SIP 도메인에 대 한 내부 호스팅 DNS 영역에 이러한 레코드를 추가 하 여 해당 레코드에 대 한 내부 DNS 확인을 제공 해야 할 수 있습니다.

</div>

<div>

## <a name="firewall-considerations"></a>방화벽 고려 사항

네트워크의 컴퓨터는 표준 인터넷 DNS 조회를 수행할 수 있어야 합니다. 이러한 컴퓨터가 표준 인터넷 사이트에 도달할 수 있는 경우 네트워크는이 요구 사항을 충족 합니다.

Microsoft Online Services 데이터 센터의 위치에 따라 와일드 카드 도메인 이름 (예: outlook.com의 \*모든 트래픽)을 기준으로 연결을 허용 하도록 네트워크 방화벽 장치를 구성 해야 합니다. 조직의 방화벽이 와일드 카드 이름 구성을 지원 하지 않는 경우 허용 하려는 IP 주소 범위 및 지정 된 포트를 수동으로 확인 해야 합니다.

[Office 365 url 및 IP 주소 범위](http://go.microsoft.com/fwlink/p/?linkid=252942)에 대 한 도움말 항목을 참조 하세요.

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>포트 및 프로토콜 요구 사항

내부 Lync Server 2013 통신의 포트 요구 사항 외에도 다음 포트를 구성 해야 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜/포트</th>
<th>프로그램도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>인바운드 열기</p>
<ul>
<li><p>페더레이션 서버 역할 (Active Directory Federation Services)</p>
<p>자세한 내용은 <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">AD FS 역할 서비스 이해</a>를 참조 하세요.</p></li>
<li><p>Active Directory Federation Services (프록시 서버 역할)</p></li>
<li><p>Microsoft Online Services 포털</p></li>
<li><p>내 회사 포털</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 클라이언트 (온-프레미스 Lync Server에서 Lync Online으로 통신)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 및 443</p></td>
<td><p>인바운드 열기</p>
<ul>
<li><p>Microsoft Online Services 디렉터리 동기화 도구</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Edge 서버의 인바운드/아웃 바운드 열기</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>데이터 공유 세션에 대 한 열기 인바운드/아웃 바운드</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>오디오, 비디오, 응용 프로그램 공유 세션에 대 한 열기 인바운드/아웃 바운드</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>오디오 및 비디오 세션에 대 한 열기 인바운드/아웃 바운드</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>오디오 및 비디오 세션에 대 한 아웃 바운드 열기</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>사용자 계정 및 데이터

Lync Server 2013 하이브리드 배포의 경우 사용자 계정이 Active Directory 도메인 서비스에서 만들어지도록 Lync Online에서 홈으로 지정할 모든 사용자가 먼저 온-프레미스 배포에서 만들어야 합니다. 이렇게 하면 사용자를 비즈니스용 Skype Online으로 이동 하 여 사용자의 연락처 목록을 이동할 수 있습니다.

Lync 온-프레미스 및 AD FS 및 Dirsync 온라인 배포 간에 사용자 계정을 동기화 하는 경우, 사용자가 온-프레미스 및 온라인 Lync 배포 사이에 조직의 모든 Lync 사용자에 대 한 광고 계정을 동기화 해야 합니다. Lync Online으로 이동 되지 않습니다. 모든 사용자를 동기화 하지 않으면 조직에서 온-프레미스 및 온라인 사용자 간의 통신이 예상 대로 작동 하지 않을 수 있습니다.

<div>


> [!IMPORTANT]  
> 사용자가 Office 365 용 온라인 포털을 사용 하 여 만들어진 경우 사용자 계정이 온-프레미스 Active Directory와 동기화 되지 않으며 사용자는 온-프레미스 Active Directory에 존재 하지 않습니다. Lync Online에서 사용자를 이미 만들었고 온-프레미스 Lync Server를 사용 하 여 하이브리드를 구성 하려는 경우 lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">server 2013에서 Lync Online에서 lync 온-프레미스로 사용자 이동을</A>참조 하세요.



</div>

또한 하이브리드 배포를 계획할 때 다음과 같은 사용자 관련 문제를 고려해 야 합니다.

  - **사용자 연락처**   Lync Online 사용자에 대 한 연락처 제한은 250입니다. 계정이 Lync Online으로 이동 되 면 해당 번호를 초과 하는 모든 연락처가 사용자의 연락처 목록에서 제거 됩니다.

  - **인스턴트 메시지 및 현재 상태**   사용자 연락처 목록, 그룹, acl (액세스 제어 목록)이 사용자 계정으로 마이그레이션됩니다.

  - **회의 데이터, 모임 콘텐츠, 예약 된 모임**   이 콘텐츠는 사용자 계정으로 마이그레이션되지 않습니다. 사용자는 계정이 Lync Online으로 마이그레이션될 때 모임 일정을 재조정 해야 합니다.

</div>

<div>

## <a name="user-policies-and-features"></a>사용자 정책 및 기능

  - Lync Server 2013 하이브리드 환경에서는 온-프레미스 또는 온라인 중 하나에서 인스턴트 메시지, 음성 및 모임에 대 한 사용을 가능 하 게 할 수 있습니다.

  - **Lync 클라이언트**     일부 사용자는 lync Online으로 이동할 때 새 클라이언트 버전이 필요할 수 있습니다. Office Communications Server 2007 R2의 경우 Lync Online으로 마이그레이션하기 전에 사용자를 Lync Server 2013 풀로 이동 해야 합니다.
    
    클라이언트 지원에 대 한 자세한 내용은 Lync Online 및 [지원 되는 lync 클라이언트 및 네트워크 포트 구성](http://go.microsoft.com/fwlink/p/?linkid=281901) [에 대 한 클라이언트](http://go.microsoft.com/fwlink/p/?linkid=281902) 를 참조 하세요.

  - **온-프레미스 정책 및 구성 (비 사용자)**   온라인 및 온-프레미스 정책은 별도의 구성이 필요 합니다. 둘 다에 적용 되는 전역 정책은 설정할 수 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

