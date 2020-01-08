---
title: 'Lync Server 2013: 트렁크 구성 설정의 새 모음 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 새 트렁크 구성 설정 모음 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. 이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.

  - Trunks에서 미디어 바이패스를 사용 해야 하는지 여부

  - RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.

  - 각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부

Microsoft Lync Server 2013을 설치할 때 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.

Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 만들 때 다음 옵션을 사용할 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 설정</th>
<th>PowerShell 매개 변수</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>Identity</p></td>
<td><p>컬렉션의 고유 식별자입니다. 이 속성은 읽기 전용입니다. 트렁크 구성 설정 모음의 Id는 변경할 수 없습니다.</p></td>
</tr>
<tr class="even">
<td><p>설명</p></td>
<td><p>설명</p></td>
<td><p>관리자가 설정에 대 한 추가 정보 (예: 트렁크 구성의 용도)를 저장할 수 있는 방법을 제공 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>지원 되는 최대 빠른 대화 상자</p></td>
<td><p>Maxlya 대화 상자</p></td>
<td><p>서비스 공급자의 PSTN 게이트웨이, IP PBX 또는 SBC가 조정 서버로 전송 된 초대에 받을 수 있는 분기 응답의 최대 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>암호화 지원 수준</p></td>
<td><p>SRTPMode</p></td>
<td><p>서비스 공급자에서 중재 서버와 PSTN 게이트웨이, IP PBX 또는 SBC 간의 미디어 트래픽 보호에 대 한 지원 수준을 나타냅니다. 미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다. 미디어 구성은 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> 및 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> cmdlet을 사용 하 여 설정 합니다.</p>
<p>사용 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>필수: SRTP 암호화를 사용 해야 합니다.</p></li>
<li><p>선택 사항: 게이트웨이에서 지 원하는 경우 SRTP가 사용 됩니다.</p></li>
<li><p>지원 되지 않음: SRTP 암호화가 지원 되지 않으므로 사용 되지 않습니다.</p></li>
</ul>
<p>SRTPMode는 게이트웨이가 TLS (전송 계층 보안)를 사용 하도록 구성 된 경우에만 사용 됩니다. 게이트웨이가 TCP (전송 제어 프로토콜)를 전송으로 구성한 경우에는 SRTPMode가 내부적으로 지원 되지 않는 것으로 설정 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>지원 참조</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>보내기를 사용 하도록 설정 하는 경우 <strong>게이트웨이를 참조</strong>하는 경우 트렁크가 조정 서버의 수신 참조 요청을 지원함을 나타냅니다.</p>
<p>이 기능을 사용 하도록 설정 하면 <strong>타사 통화 제어를 사용</strong>하는 것이 3pcc 프로토콜을 사용 하 여 호스팅된 사이트를 우회 하도록 할 수 있음을 나타냅니다. 3pcc는 타사 컨트롤이 라고도 &quot;&quot; 하며, 타사를 사용 하 여 한 쌍의 호출자를 연결 하는 경우 (예: A 사람에 게 a에 게 전화를 거는 운영자)에 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p>미디어 바이패스 사용</p></td>
<td><p>EnableBypass</p></td>
<td><p>이 트렁크에 미디어 바이패스를 사용 하도록 설정 했는지 여부를 나타냅니다. 미디어 바이패스는 <strong>중앙 집중화 된 미디어 처리</strong> 도 사용할 수 있는 경우에만 사용 가능 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>중앙 집중화 된 미디어 처리</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>잘 알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료의 IP와 동일한 PSTN 게이트웨이가 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>RTP latching 사용</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>SIP 트렁크가 RTP 래치를 지원하는지 여부를 나타냅니다. RTP 래치는 NAT(Network Address Translator) 장치 또는 방화벽을 통한 RTP/RTCP 연결을 설정하는 기술입니다.</p></td>
</tr>
<tr class="odd">
<td><p>착신 통화 기록 사용</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>앞으로 P-어설션된-Id 데이터 사용</p></td>
<td><p>ForwardPAI</p></td>
<td><p>PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>아웃 바운드 라우팅 장애 조치 타이머 사용</p></td>
<td><p>Enablefailovertimer</p></td>
<td><p>게이트웨이에서 응답 하지 않은 아웃 바운드 통화가 10 초 이내에 사용 가능한 다음 트렁크로 라우팅되도록 할지 여부를 표시 합니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다. 느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>연결 된 PSTN 용도</p></td>
<td><p>PSTNUsages</p></td>
<td><p>트렁크에 할당된 PSTN 사용 컬렉션입니다.</p></td>
</tr>
<tr class="odd">
<td><p>테스트를 위해 번역 된 번호</p></td>
<td><p>해당 없음</p></td>
<td><p>트렁크 구성 설정의 임시 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p>연결 된 번역 규칙</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>아웃 바운드 라우팅이 처리 하는 통화에 적용 되는 전화 번호 번역 규칙 (PBX 또는 PSTN 대상으로 라우팅된 통화)을 수집 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>전화 번호 번역 규칙</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>트렁크에 할당된 아웃바운드 호출 번호 변환 규칙 컬렉션입니다.</p></td>
</tr>
<tr class="even">
<td><p>테스트할 전화 번호</p></td>
<td><p>해당 없음</p></td>
<td><p>번역 규칙의 특별 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.</p></td>
</tr>
<tr class="odd">
<td><p>전화 번호</p></td>
<td><p>해당 없음</p></td>
<td><p>테스트 하려는 전화 번호가 발신자의 전화 번호 임을 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>전화 번호</p></td>
<td><p>해당 없음</p></td>
<td><p>전화 번호가 통화 중인 사람의 전화 번호 라는 것을 나타냅니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lync Server Set-cstrunkconfiguration cmdlet은 Lync Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">새 set-cstrunkconfiguration</A> cmdlet에 대 한 도움말 항목을 참조 하세요.



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 새 트렁크 구성 설정을 만들려면

1.  Lync Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.

2.  **트렁크 구성** 탭에서 **새로 만들기**를 클릭 한 다음 **사이트 트렁크** 를 클릭 하 여 사이트 범위에서 새 설정을 만들거나, **풀 트렁크** 에서 서비스 범위에 새 설정을 만듭니다.

3.  **사이트 선택** 또는 **서비스 선택** 대화 상자 (표시 되는 대화 상자는 사이트 범위 또는 서비스 범위 설정을 만들지 여부에 따라 달라 짐) 새 구성 설정의 위치를 선택 하 고 **확인**을 클릭 합니다. 대화 상자가 비어 있으면 새 설정을 만들 수 있는 위치가 없다는 의미입니다. 예를 들어 **사이트 선택** 대화 상자가 비어 있는 경우 모든 사이트에서 이미 트렁크 구성 사이트 모음을 할당 했으며 각 사이트 (및 각 서비스)는 그러한 컬렉션을 하나만 호스트할 수 있습니다. 이러한 경우 기존 컬렉션을 삭제 하 고 새 컬렉션을 만들거나 기존 컬렉션을 수정할 수 있습니다.

4.  **새 트렁크 구성** 대화 상자에서 적절 하 게 선택 하 고 **확인**을 클릭 합니다.

5.  컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다. 변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.

6.  커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.

7.  **Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인을**클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

