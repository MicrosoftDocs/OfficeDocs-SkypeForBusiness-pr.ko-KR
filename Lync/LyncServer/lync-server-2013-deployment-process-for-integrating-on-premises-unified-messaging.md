---
title: 온-프레미스 통합 메시징을 통합 하기 위한 배포 프로세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>온-프레미스 통합 메시징과 Lync Server 2013의 통합을 위한 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-17_

Exchange UM (통합 메시징)을 Lync Server 2013와 통합 하려면이 항목에서 설명 하는 작업을 수행 해야 합니다. 또한 온 [-프레미스 통합 메시징 및 Lync Server 2013 통합에 대 한 지침](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)에 설명 된 모범 사례 계획 및 배포를 검토 하세요. 이 항목에서는 lync server 2013을 collocated 중재 서버와 함께 배포 했으며 Lync Server 2013에 대해 사용자를 활성화 했으며, 배포 설명서의 [Lync server 2013에서 Enterprise voice를 배포](lync-server-2013-deploying-enterprise-voice.md) 하는 방법에 설명 된 대로 모든 배포 및 구성 단계를 수행 하 여 enterprise voice를 사용 하도록 설정 했다고 가정 합니다.

<div>

## <a name="unified-messaging-integration-process"></a>통합 메시징 통합 프로세스

<div>


> [!IMPORTANT]
> 원활한 성공적인 통합을 위해 각 사용자가 수행할 작업을 확인 하려면 조직의 Exchange 관리자와 협조 하는 것이 중요 합니다.



</div>


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
<th>필수 그룹 및 역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>다음 중 하나를 배포 합니다.</p>
<ul>
<li><p>Microsoft Exchange Server 2007 SP2((서비스 팩 1) 또는 최신 서비스 팩</p></li>
<li><p>Microsoft Exchange Server 2010 또는 최신 서비스 팩</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Microsoft Exchange Server 2013를 사용 하는 경우 Lync Server 2013와 동일한 포리스트나 다른 포리스트에 다음 Exchange Server 역할을 설치 합니다.</p>
<ul>
<li><p>클라이언트 액세스</p></li>
<li><p>사서함당</p></li>
</ul>
<p>Microsoft Exchange Server 2013 및 UM (통합 메시징)이 다른 포리스트에 설치 되어 있는 경우 각 Exchange 포리스트에서 Lync Server 2013 포리스트를 신뢰 하도록 구성 합니다.</p>
<p>Exchange 2010를 사용 하는 경우 Lync Server 2013와 동일한 포리스트나 다른 포리스트에 다음 Exchange Server 역할을 설치 합니다.</p>
<ul>
<li><p>통합 메시징</p></li>
<li><p>허브 전송</p></li>
<li><p>클라이언트 액세스</p></li>
<li><p>사서함당</p></li>
</ul>
<p>Lync Server 2013 및 UM (통합 메시징)이 다른 포리스트에 설치 되어 있는 경우 각 Exchange 포리스트가 Lync Server 2013 포리스트를 신뢰 하도록 구성 합니다.</p></td>
<td><p>엔터프라이즈 관리자 (조직의 첫 번째 Exchange 서버인 경우)</p>
<p>또는</p>
<p>Exchange 조직 관리자 (조직의 첫 번째 Exchange 서버가 아닌 경우)</p></td>
<td><p>현재 버전의 Exchange Server에 대 한 적절 한 설명서를 참조 하세요.</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 배포 설명서를 <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>참조 하세요.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 또는 최신 서비스 팩 배포 설명서를 <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>참조 하세요.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 계획 및 배포 위치 <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>인증서를 설치 합니다.</p></td>
<td><p>신뢰할 수 있는 루트 CA (인증 기관)에서 각 Exchange UM 서버에 대 한 인증서를 다운로드 하 고 설치 합니다. 인증서는 Exchange UM 및 Lync Server 2013를 실행 하는 서버 간의 MTLS (상호 전송 수준 보안)에 필요 합니다.</p></td>
<td><p>관리자</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>새 Exchange UM SIP 다이얼 플랜을 만들고 구성 합니다.</p></td>
<td><p>Exchange UM 서버에서 조직의 특정 배포 요구 사항에 따라 SIP 다이얼 플랜을 만듭니다.</p></td>
<td><p>Exchange 조직 관리자</p></td>
<td><p>Exchange 2007 SP1 또는 최신 서비스 팩의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>는 통합 메시징 SIP URI 다이얼 플랜을 만드는 방법을 참조 하세요.</p>
<p>Exchange 2010 또는 최신 서비스 팩의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>는 UM 다이얼 플랜 만들기를 참조 하세요.</p>
<p>Exchange 2013의 경우 통합 메시징을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>하세요.</p></td>
</tr>
<tr class="even">
<td><p>Exchange UM SIP 다이얼 플랜에 대 한 보안 설정을 구성 합니다.</p></td>
<td><p>엔터프라이즈 음성 트래픽을 암호화 하려면 <strong>sip</strong> 보안 또는 <strong>보안이</strong>설정 된 Exchange UM SIP 다이얼 플랜에서 보안 설정을 구성 합니다. 이는 환경에서 Lync Phone Edition 장치를 배포 하거나 배포 하는 경우 특히 중요 한 단계입니다. Exchange UM 통합을 사용 하는 환경에서 Lync Phone Edition 장치가 작동 하도록 하려면 Lync Server 암호화 설정이 Exchange UM 다이얼 플랜 보안 설정과 일치 해야 합니다. 자세한 내용은 배포 설명서를 참조 하세요.</p></td>
<td><p>Exchange 조직 관리자</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성</a></p>
<p>Exchange 2007 SP1 또는 최신 서비스 팩은 다음을 참조 하세요.</p>
<p>&quot;의 통합 메시징 다이얼 플랜&quot; 에 대 한 보안을 구성 <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>하는 방법을 알아보세요.</p>
<p>Exchange 2010 또는 최신 서비스 팩은 다음을 참조 하세요.</p>
<p>&quot;UM 다이얼 플랜&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>에서 VoIP 보안을 구성 합니다.</p>
<p>Exchange 2013의 경우 통합 메시징을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>하세요.</p></td>
</tr>
<tr class="odd">
<td><p>Exchange UM SIP 다이얼 플랜에 통합 메시징 서버를 추가 합니다.</p></td>
<td><p>새로 설치한 통합 메시징 서버에서 수신 전화에 응답 하 고 처리할 수 있도록 하려면 통합 메시징 서버를 UM 다이얼 플랜에 추가 해야 합니다. 이 경우 Exchange UM SIP 다이얼 플랜에 서버를 추가 합니다.</p></td>
<td><p>관리자</p>
<p>Exchange Server 관리자</p></td>
<td><p>Exchange 2007 SP1 또는 최신 서비스 팩의 경우 다이얼 &quot;플랜&quot; 에 통합 메시징 서버를 추가 하는 방법을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>하세요.</p>
<p>Exchange 2010 또는 최신 서비스 팩의 경우 UM &quot;서버의&quot; 속성 보기 또는 구성을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>하세요.</p>
<p>Exchange 2013의 경우 통합 메시징을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>하세요.</p></td>
</tr>
<tr class="even">
<td><p>SIP 주소를 사용 하 여 사서함을 구성 합니다.</p></td>
<td><p>Exchange UM 기능을 사용 하는 Enterprise Voice 사용자의 사서함에 SIP 주소를 할당 합니다.</p></td>
<td><p>Lync Server 2013 관리자</p>
<p>Exchange 받는 사람 관리자</p></td>
<td><p>Exchange 2007 SP1 또는 최신 서비스 팩의 경우 UM &quot;을 사용할 수 있는 사용자&quot; 의 SIP 주소를 추가, 제거 또는 수정 하는 방법을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>하세요.</p>
<p>Exchange 2010 또는 최신 서비스 팩의 경우 UM &quot;을 사용 하도록 설정 된 사용자&quot; 에 대 한 SIP 주소 <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>수정을 참조 하세요.</p>
<p>Exchange 2013의 경우 통합 메시징을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>하세요.</p></td>
</tr>
<tr class="odd">
<td><p>Exchucutil 스크립트를 실행 합니다.</p></td>
<td><p>Exchange UM 서비스를 실행 하는 서버에서 Exchange 관리 셸을 열고 다음을 수행 하는 exchucutil 스크립트를 실행 합니다.</p>
<ul>
<li><p>이전 작업에서 만든 SIP 다이얼 플랜 인 Exchange UM Active Directory 도메인 서비스 개체를 읽을 수 있는 Lync Server 2013 권한을 부여 합니다.</p></li>
<li><p>Enterprise Voice를 사용 하도록 설정 된 사용자를 호스트 하는 각 Lync Server 2013 Enterprise Edition pool 또는 Standard Edition Server에 대해 Active Directory에 통합 메시징 IP 게이트웨이 개체를 만듭니다.</p></li>
<li><p>각 게이트웨이에 대 한 Exchange UM 헌트 그룹을 만듭니다. 헌트 그룹 조종사 식별자는 해당 게이트웨이와 연결 된 다이얼 플랜의 이름이 됩니다. 다이얼 플랜을 두 개 이상 사용할 경우 1:1이 필요 합니다.</p></li>
</ul></td>
<td><p>Exchange 조직 관리자</p>
<p>Exchange 받는 사람 관리자</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성</a></p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 다이얼 플랜을 구성 합니다.</p></td>
<td><p>Exchange 2007 SP1 또는 최신 서비스 팩 또는 Exchange 2010과 통합 하는 경우 Exchange UM 다이얼 플랜의 FQDN (정규화 된 도메인 이름)과 일치 하는 이름을 사용 하 여 새 Enterprise Voice dial 계획을 만듭니다.</p>



> [!NOTE]
> 각 UM 다이얼 플랜에 대해이 작업을 수행 해야 합니다.


<p>Exchange 2010 SP1과 통합 하는 경우 적절 한 글로벌/사이트 수준 또는 풀 수준의 Enterprise Voice dial 요금제가 구성 되어 있는지 확인 합니다.</p>



> [!NOTE]
> Exchange 2010 SP1과 통합 하는 경우 Lync Server 다이얼 플랜 및 Exchange UM SIP 다이얼 플랜 이름이 일치 하지 않아도 됩니다.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Lync Server 2013에서 다이얼 플랜 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>Exchange UM 통합 도구를 실행 합니다.</p></td>
<td><p>Lync Server 2013에서 다음과 같은 <strong>ocsumutil</strong>을 실행 합니다.</p>
<ul>
<li><p>구독자 액세스 및 자동 전화 교환 연락처 개체를 만듭니다.</p></li>
<li><p>Exchange UM 다이얼 플랜 FQDN과 일치 하는 이름을 사용 하는 Enterprise Voice dial 요금제가 있는지 확인 합니다. Exchange 2010 SP1 이상을 실행 중인 경우 다이얼 플랜 이름이 일치 하지 않아도 되며이에 대 한 도구의 경고는 무시할 수 있습니다.</p></li>
</ul>
<p>이 도구는 Exchange UM 설정에 대 한 Active Directory를 검사 하 고 Lync Server 2013 관리자가 연락처 개체를 보고, 만들고, 편집할 수 있도록 하는 방식으로 작동 합니다.</p></td>
<td><p>RTCUniversalServerAdmins <em>및</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Ocsumutil을 성공적으로 실행 하려면 사용자가 이러한 두 그룹 모두에 속해야 합니다.





> [!NOTE]
> 연락처 개체를 만들려면 ocsumutil을 실행 하는 사용자에 게 새 연락처 개체가 저장 된 Active Directory OU (조직 구성 단위)에 대 한 올바른 권한이 있어야 합니다. 이 권한은 <STRONG>부여-CsOUPermission</STRONG> cmdlet을 실행 하 여 부여할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Microsoft Exchange Server의 통합 메시징과 함께 작동하도록 Lync Server 2013 구성</a></p></td>
</tr>
<tr class="even">
<td><p>필요한 경우 다른 엔터프라이즈 음성 구성 단계를 수행 합니다.</p></td>
<td><p>서버나 사용자에 게 Enterprise Voice 설정을 아직 구성 하지 않은 경우 다음 중 하나 이상을 수행 합니다.</p>
<ul>
<li><p>배포 및 구성</p>
<p>PSTN (공개 교환 전화 네트워크) 게이트웨이 및 중재 서버</p></li>
<li><p>음성 정책, PSTN 사용 레코드 및 아웃 바운드 통화 경로를 정의 합니다.</p></li>
<li><p>엔터프라이즈 음성에 대해 사용자를 사용 하도록 설정 합니다.</p></li>
<li><p>필요에 따라 다이얼 플랜을 사용 하 여 특정 사용자를 구성 합니다.</p></li>
</ul>
<p>사용 하도록 설정 하는 Enterprise 음성 기능에 따라 다른 구성 단계가 필요할 수 있습니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>다음 섹션의 항목을 참조 하세요.</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013에서 엔터프라이즈 음성 배포</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Exchange UM에 대해 Enterprise Voice 사용자를 사용 하도록 설정 합니다.</p></td>
<td><p>Exchange UM 서버에서 통합 메시징 사서함 정책이 만들어졌으며 각 사용자에 게 고유한 내선 번호 할당이 있는지 확인 한 다음 사용자가 통합 메시징을 사용할 수 있도록 설정 합니다.</p></td>
<td><p>Exchange 받는 사람 관리자</p></td>
<td><p>Exchange 2007 SP1 또는 최신 서비스 팩의 경우 사용자 &quot;가에서&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>통합 메시징을 사용 하도록 설정 하는 방법을 참조 하세요.</p>
<p>Exchange 2010 또는 최신 서비스 팩의 경우 사용자 &quot;가에서&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>통합 메시징을 사용할 수 있도록 설정을 참조 하세요.</p>
<p>Exchange 2013의 경우 통합 메시징을 참조 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>하세요.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

