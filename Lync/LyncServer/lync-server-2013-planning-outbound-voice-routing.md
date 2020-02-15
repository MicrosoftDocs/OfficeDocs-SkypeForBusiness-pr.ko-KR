---
title: 'Lync Server 2013: 아웃 바운드 음성 라우팅 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fbcb976ed4f3d1464b6b956ef60dc1d00bd6907
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Lync Server 2013의 아웃 바운드 음성 라우팅 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

아웃바운드 통화 라우팅은 공중 전화망(PSTN) 게이트웨이, 트렁크 또는 PBX(Private Branch Exchange)로 향하는 통화에 적용됩니다. 사용자가 전화를 걸면 서버는 필요한 경우 전화 번호를 E.164 형식으로 정규화하고 SIP URI에 일치시키려고 합니다. 일치시킬 수 없는 경우 서버는 제공된 다이얼 문자열에 기초하여 아웃바운드 통화 라우팅 논리를 적용합니다. 이 논리는 아래 표에 설명되어 있는 서버 설정을 구성하여 정의합니다.

### <a name="lync-server-outbound-call-routing-settings"></a>Lync Server 아웃바운드 통화 라우팅 설정

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>나타내는</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>다이얼 플랜</p></td>
<td><p>다이얼 플랜은 전화 인증 및 통화 라우팅을 위해 명명된 위치, 개별 사용자 또는 연락처 개체의 전화 번호를 하나의 표준(E.164) 형식으로 변환하는 명명된 정규화 규칙 집합입니다.</p></td>
</tr>
<tr class="even">
<td><p>정규화 규칙</p></td>
<td><p>정규화 규칙은 다양한 형식으로 표현된 전화 번호를 지정된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅하는 방법을 정의합니다. 전화를 건 위치와 전화를 거는 사람 또는 대화 상대 개체에 따라 동일한 전화 걸기 문자열이 다르게 해석되고 변환될 수 있습니다. 특정 위치에 연결된 정규화 규칙 집합이 다이얼 플랜을 구성합니다.</p></td>
</tr>
<tr class="odd">
<td><p>음성 정책</p></td>
<td><p>음성 정책은 하나 이상의 PSTN 사용 레코드를 단일 사용자 또는 사용자 그룹과 연결합니다. 또한 음성 정책은 사용하거나 사용하지 않도록 설정할 수 있는 통화 기능 목록을 제공합니다.</p></td>
</tr>
<tr class="even">
<td><p>PSTN 사용 레코드</p></td>
<td><p>PSTN 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹이 수행할 수 있는 통화 클래스(내부, 시내, 시외 등)를 지정합니다.</p></td>
</tr>
<tr class="odd">
<td><p>통화 경로</p></td>
<td><p>통화 경로는 대상 전화 번호를 특정 트렁크 및 PSTN 사용 레코드와 연결합니다. PSTN 게이트웨이는 트렁크로 간주됩니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

이 섹션에서는 다음의 아웃바운드 통화 라우팅 서버 설정을 구성하는 지침을 제공합니다.

  - <span></span>  
    [Lync Server 2013의 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Lync Server 2013의 음성 정책](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Lync Server 2013의 PSTN 사용 레코드](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 SIP 트렁크](lync-server-2013-sip-trunking.md)  
[Lync Server 2013의 직접 SIP 연결](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

