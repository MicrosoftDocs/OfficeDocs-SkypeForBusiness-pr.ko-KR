---
title: 'Lync Server 2013: 회의를 위한 위치 기반 라우팅 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의에 대 한 위치 기반 라우팅 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-19_

위치 기반 라우팅 회의 응용 프로그램을 설치 하 고 구성 하는 데 필요한 요구 사항은 다음과 같습니다.

  - Lync Server 2013 누적 업데이트 2는 토폴로지의 모든 서버 또는 풀에 배포 해야 합니다.

<div>


> [!NOTE]  
> 토폴로지의 Lync server 또는 풀에 Lync Server 2013 누적 업데이트 2 이상이 설치 되어 있지 않은 경우 Lync 모임의 위치 기반 라우팅에 대 한 적용을 보장할 수 없습니다.



</div>

  - Lync Server 2013 위치 기반 라우팅은 위치 기반 라우팅 회의 응용 프로그램에 대 한 사전 필수 구성 요소입니다. Lync Server 2013 위치 기반 라우팅 구성에 대 한 자세한 내용은 [위치 기반 라우팅 구성](lync-server-2013-configuring-location-based-routing.md)를 참조 하세요.

  - 위치 기반 라우팅 회의 응용 프로그램의 요구 사항은 Lync Server 2013 위치 기반 라우팅에 대 한 요구 사항과 동일 합니다. 자세한 내용은 [위치 기반 라우팅에 대 한 계획](lync-server-2013-planning-for-location-based-routing.md)을 참조 하세요.

<div>

## <a name="supported-servers"></a>지원 되는 서버

위치 기반 라우팅 회의 응용 프로그램을 사용 하려면 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 Lync Server 2013 누적 업데이트 2가 배포 되어 있어야 합니다. Lync Server 2013 누적 업데이트 2가 토폴로지의 일부 Lync 서버에 설치 되어 있지 않으면 Lync meeting 및 문의 후 call 전송에서 위치 기반 라우팅 제한이 완전히 적용 되지 않습니다.

다음 표에는 위치 기반 라우팅을 지 원하는 서버 역할 및 버전 조합이 나와 있습니다.


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
<td><p>모두</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>모두</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>모두</p></td>
<td><p>아니요</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>지원 되는 클라이언트

Lync meeting의 위치 기반 라우팅을 지 원하는 Lync 클라이언트는 Lync Server 2013 위치 기반 라우팅을 지 원하는 것과 동일한 클라이언트입니다. 자세한 내용은 [위치 기반 라우팅을 위한 클라이언트 및 서버 지원을](lync-server-2013-client-and-server-support-for-location-based-routing.md)참조 하세요.

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>문의 후 통화 전송에 대 한 중재 서버 요구 사항

위치 기반 라우팅 회의 응용 프로그램을 사용 하려면 문의 후 call 전송에 대해 위치 기반 라우팅 제한을 적용 하기 위해 독립 실행형 중재 서버를 배포 해야 합니다.

문의 후 통화 전송의 위치 기반 라우팅을 적용 하려면 중재 서버가 위치 기반 라우팅이 필요한 네트워크 지역에서 하나의 중재 서버 피어 (즉, PBX, SIP 게이트웨이 등)에만 연결 되어 있어야 합니다. 추가 중재 서버 피어가 같은 네트워크 지역에 배포 되는 경우 중재 서버 피어는 다른 중재 서버에 연결 되어 있어야 합니다. 이 요구 사항은 다음과 같습니다.

  - 여러 중재 서버 피어에 대 한 단일 중재 서버 문의 후 호출 전송이 여러 피어 트렁크 (예: Pbx 및 게이트웨이)로 구성 된 중재 서버를 통해 중재 서버 피어로 라우팅되는 경우 문의 후 통화 전송은 PSTN 유료 바이패스를 방지 하기 위해 문의 후 통화 전송이 일부 SIP 트렁크를 통해 허용 되지만 다른 SIP 트렁크를 통해서는 허용 되지 않도록 차단 됩니다.
    
    예를 들어 PSTN 게이트웨이 중재 서버 피어 및 PBX 중재 서버 피어를 제공 하는 단일 중재 서버의 경우에는 다음과 같은 동작이 발생 합니다.
    
      - 지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 문의 후 전송을 통해 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 PSTN 끝점을 사용 하 여 통화를 전송 하려고 하면 PSTN 전화 바이패스를 방지할 수 있습니다.
    
      - 지정 된 사이트 (즉, 1)의 Lync 사용자가 같은 사이트 (즉, 사이트 1)에서 PBX 끝점이 있는 통화를 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 문의 후 전송을 통해 전송 하려고 하면 잠재적인 PSTN tol에 문제가 발생 하지 않더라도 통화가 허용 되지 않습니다. l 건너뜀

  - 중재 서버 피어 당 별도의 중재 서버
    
    중재 서버 피어에서 문의 후 전송을 대상으로 하는 경우 문의 후 전송은 중재 서버에서 서비스 되는 단일 중재 서버 피어에 대해 평가 됩니다. 이 통화는 사이트의 다른 모든 Mediations 서버 피어가 별도의 중재 서버에서 서비스를 제공 하는 것과 상관 없이 PSTN 유료 바이패스로 인해 허용 되거나 허용 됩니다.
    
    예를 들어 PSTN 게이트웨이 중재 서버 피어 및 PBX 중재 서버 피어를 제공 하는 별도의 중재 서버가 있는 경우에는 다음과 같은 동작이 발생 합니다.
    
      - 지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 문의 후 전송을 통해 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 PSTN 끝점을 사용 하 여 통화를 전송 하려고 하면 PSTN 전화 바이패스를 방지할 수 있습니다.
    
      - 지정 된 사이트 (즉, 1)의 Lync 사용자가 같은 사이트 (즉, 사이트 1)에서 PBX 끝점이 있는 통화를 다른 사이트 (즉, 사이트 2)의 온-문의 후 transfer를 통해 Lync 사용자에 게 전송 하는 경우 잠재적인 PSTN 무료 바이패스에 문제가 발생 하지 않으므로 통화가 허용 됩니다. 얻지.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>위치 기반 라우팅 회의 응용 프로그램에서 지원 하지 않는 기능

위치 기반 라우팅 회의 응용 프로그램에서는 다음과 같은 기능을 지원 하지 않습니다.

  - 전화 접속 회의 전화 접속 회의에는 위치 기반 라우팅을 적용할 수 없습니다. 전화 회의 이끌이가 위치 기반 라우팅을 사용 하도록 설정 된 Lync 사용자 인 경우에도 지정 된 회의에 대 한 모든 전화 접속 요청이 위치 기반 라우팅으로 제한 되지 않습니다.

  - 위치 기반 라우팅 제한을 적용 해야 하는 지역에서는 회의 액세스 번호를 프로 비전 하지 않는 것이 좋습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

