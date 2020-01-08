---
title: 'Lync Server 2013: 아웃바운드 음성 라우팅 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5315b18e83b84980ff6d61e5385626e104a5e1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Lync Server 2013에서 아웃바운드 음성 라우팅 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

아웃 바운드 통화 라우팅은 PSTN (공개 교환 전화 네트워크) 게이트웨이, 트렁크 또는 개인 분기 교환 (PBX)으로 향하는 통화에 적용 됩니다. 사용자가 전화를 걸 때 서버는 필요한 경우에는 휴대폰 번호를 E-164 형식으로 정규화 하 고이를 SIP URI와 일치 시 키 려 고 합니다. 서버에서 일치 하는 항목을 만들 수 없는 경우에는 제공 된 다이얼 문자열을 기반으로 하는 아웃 바운드 호출 라우팅 논리가 적용 됩니다. 다음 표에서 설명 하는 서버 설정을 구성 하 여 해당 논리를 정의 합니다.

### <a name="lync-server-outbound-call-routing-settings"></a>Lync Server 아웃 바운드 통화 라우팅 설정

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>오브젝트가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>다이얼 플랜</p></td>
<td><p>다이얼 플랜은 전화 인증 및 통화 라우팅과 같은 목적으로 명명 된 위치, 개인 사용자 또는 연락처 개체의 전화 번호를 단일 표준 (E) 형식으로 변환 하는 정규화 규칙의 명명 된 집합입니다.</p></td>
</tr>
<tr class="even">
<td><p>정규화 규칙</p></td>
<td><p>정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 지정 된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅되는 방법을 정의 합니다. 전화 거는 위치와 전화를 걸고 있는 사람 또는 연락처 개체에 따라 같은 다이얼 문자열을 다르게 해석 하 고 번역할 수 있습니다. 특정 위치와 관련 된 정규화 규칙 집합은 다이얼 플랜을 구성 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>음성 정책</p></td>
<td><p>음성 정책은 하나 이상의 PSTN 사용 레코드를 한 사용자 또는 사용자 그룹에 연결 합니다. 음성 정책은 또한 사용 하거나 사용 하지 않도록 설정할 수 있는 통화 기능 목록을 제공 합니다.</p></td>
</tr>
<tr class="even">
<td><p>PSTN 사용 레코드</p></td>
<td><p>PSTN 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹에 의해 이루어질 수 있는 호출 클래스 (예: 내부, 지역 또는 시외)를 지정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>통화 경로</p></td>
<td><p>통화 경로는 대상 전화 번호와 특정 trunks 및 PSTN 사용 레코드를 연결 합니다. PSTN 게이트웨이는 트렁크로 간주 됩니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

이 섹션에서는 다음 아웃 바운드 통화 라우팅 서버 설정을 구성 하는 방법에 대 한 지침을 제공 합니다.

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
[Lync Server 2013에서 직접 SIP 연결](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

