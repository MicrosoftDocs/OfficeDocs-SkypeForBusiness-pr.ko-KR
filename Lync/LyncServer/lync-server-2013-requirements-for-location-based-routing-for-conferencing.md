---
title: 'Lync Server 2013: 회의를 위한 위치 기반 라우팅 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 회의를 위한 위치 기반 라우팅에 대 한 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-19_

다음은 위치 기반 라우팅 회의 응용 프로그램의 설치 및 구성에 필요한 요구 사항입니다.

  - Lync Server 2013 누적 업데이트 2는 토폴로지의 모든 서버 또는 풀에 배포 해야 합니다.

<div>


> [!NOTE]  
> 토폴로지의 Lync server 또는 풀에 Lync Server 2013 누적 업데이트 2 이상이 설치 되어 있지 않은 경우 Lync 모임의 위치 기반 라우팅에 대 한 적용을 보장할 수 없습니다.



</div>

  - Lync Server 2013 위치 기반 라우팅은 위치 기반 라우팅 회의 응용 프로그램에 대 한 사전 필수 요소입니다. Lync Server 2013 위치 기반 라우팅 구성에 대 한 자세한 내용은 [위치 기반 라우팅 구성을](lync-server-2013-configuring-location-based-routing.md)참조 하세요.

  - 위치 기반 라우팅 회의 응용 프로그램의 요구 사항은 Lync Server 2013 위치 기반 라우팅의 요구 사항과 동일 합니다. 자세한 내용은 [위치 기반 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)을 참조 하세요.

<div>

## <a name="supported-servers"></a>지원 되는 서버

위치 기반 라우팅 회의 응용 프로그램을 사용 하려면 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 Lync Server 2013 누적 업데이트 2를 배포 해야 합니다. Lync Server 2013 누적 업데이트 2가 토폴로지의 일부 Lync 서버에 설치 되어 있지 않은 경우에는 Lync 모임 및 consultative 통화 전송에 대해 위치 기반 라우팅 제한을 완전히 적용할 수 없습니다.

다음 표에서는 위치 기반 라우팅을 지 원하는 서버 역할 및 버전의 조합을 식별 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>프런트 엔드 풀 버전</p></td>
<td><p>중재 서버 버전</p></td>
<td><p>지원</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 누적 업데이트 2</p></td>
<td><p>Lync Server 2013 누적 업데이트 2</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 누적 업데이트 2</p></td>
<td><p>Lync Server 2013 누적 업데이트 1</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 누적 업데이트 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 누적 업데이트 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 누적 업데이트 1</p></td>
<td><p>이상</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>이상</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>이상</p></td>
<td><p>아니요</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>지원 되는 클라이언트

Lync 모임에 대 한 위치 기반 라우팅이 지원 되는 Lync 클라이언트는 Lync Server 2013 위치 기반 라우팅을 지 원하는 클라이언트와 동일 합니다. 자세한 내용은 [위치 기반 라우팅에 대 한 클라이언트 및 서버 지원을](lync-server-2013-client-and-server-support-for-location-based-routing.md)참조 하세요.

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Consultative 통화 전송에 대 한 중재 서버 요구 사항 조정

위치 기반 라우팅 회의 응용 프로그램에서는 consultative 통화 전송에 위치 기반 라우팅 제한을 적용 하기 위해 독립 실행형 중재 서버를 배포 해야 합니다.

Consultative call 전송의 위치 기반 라우팅을 적용 하려면 위치 기반 라우팅이 필요한 네트워크 영역에 중재 서버 피어 (예: PBX, SIP 게이트웨이 등)를 하나에만 연결 해야 합니다. 다른 중재 서버 피어가 동일한 네트워크 지역에 배포 되어 있는 경우 중재 서버 피어가 다른 중재 서버와 연결 되어 있어야 합니다. 이 요구 사항은 다음과 같습니다.

  - 여러 consultative 호출 전송이 여러 피어 (예: Pbx 및 게이트웨이)에 여러 개의 SIP trunks 구성한 중재 서버를 통해 조정 서버 피어로 중재 하는 단일 중재 서버 consultative 통화 전송이 일부 SIP trunks를 통해 허용 되지만 다른 SIP trunks를 통해서는 허용 되지 않는 경우 PSTN 부담을 무시할 수 없도록 통화 전송이 차단 됩니다.
    
    예를 들어 PSTN 게이트웨이 조정 서버 피어 및 PBX 중재 서버 피어를 서비스 하는 단일 중재 서버의 경우 다음과 같은 동작이 발생 합니다.
    
      - 지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 consultative 전송을 통해 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 PSTN 끝점을 사용 하 여 통화를 전송 하려고 하면 PSTN 유료 바이패스를 방지 하는 데 통화를 허용 하지 않습니다.
    
      - 지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 consultative 전송을 통해 다른 사이트 (즉, 사이트 2)의 PBX 끝점으로 통화를 전송 하려고 하면 잠재적인 PSTN에서 발생 하지 않는 경우에도 통화가 허용 되지 않습니다 tol l을 건너뜁니다.

  - 중재 서버 피어 당 별도의 중재 서버
    
    Consultative 전송이 중재 서버 피어를 대상으로 하는 경우 중재 서버에서 서비스 하는 단일 중재 서버 피어에 대해 consultative 전송이 평가 됩니다. 이 통화는 사이트의 다른 모든 Mediations 서버 피어가 별도의 중재 서버에서 서비스를 제공 하는 것과 관계 없이 PSTN 유료에서 발생 하는 경우에만 허용 하거나 허용할 수 있습니다.
    
    예를 들어 PSTN 게이트웨이 조정 서버 피어 및 PBX 중재 서버 피어를 서비스 하는 별도의 중재 서버를 사용할 경우 다음과 같은 동작이 발생 합니다.
    
      - 지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 consultative 전송을 통해 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 PSTN 끝점을 사용 하 여 통화를 전송 하려고 하면 PSTN 유료 바이패스를 방지 하는 데 통화를 허용 하지 않습니다.
    
      - 지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 consultative 전송을 통해 다른 사이트 (즉, 사이트 2)의 PBX 끝점을 사용 하 여 통화를 전송 하려고 시도 하는 경우, 해당 통화는 잠재적인 PSTN 유료 바이패스로 인해 발생 하는 것으로 허용 됩니다. ing.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>위치 기반 라우팅 회의 응용 프로그램에서 지원 되지 않는 기능

위치 기반 라우팅 회의 응용 프로그램에서는 다음과 같은 접근 권한 값이 지원 되지 않습니다.

  - 전화 접속 회의. 전화 접속 회의에는 위치 기반 라우팅이 적용 되지 않습니다. 지정 된 회의에 대 한 모든 전화 접속 요청은 모임 이끌이가 위치 기반 회람을 사용 하도록 설정 된 Lync 사용자 인 경우에도 위치 기반 라우팅에 의해 제한 되지 않습니다.

  - 위치 기반 라우팅 제한을 적용 해야 하는 지역에서는 회의 액세스 번호를 제공 하지 않는 것이 좋습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

