---
title: 사용자 모델을 사용 하 여 Lync Server 2013 용량 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>사용자 모델을 사용 하 여 Lync Server 2013에 대 한 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-01-14_

이 섹션에서는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에서 설명한 사용에 따라 사이트에 필요한 서버 수 (해당 사이트의 사용자 수)에 대 한 지침을 제공 합니다.

<div>

## <a name="tested-hardware-platform"></a>테스트를 거친 하드웨어 플랫폼

이 섹션의 모든 성능 결과 및 배포 권장 사항은 다음 표에 설명 된 하드웨어를 실행 하는 서버에 대 한 성능 테스트를 기반으로 합니다. 비슷한 하드웨어를 사용 하는 것이 좋습니다. 덜 강력한 하드웨어를 사용 하는 경우 기능에 문제가 있거나 성능이 저하 될 수 있습니다. 이러한 하드웨어 권장 사항은 이전 버전의 Lync Server 보다 더 높습니다.

### <a name="hardware-used-in-performance-testing"></a>성능 테스트에 사용 되는 하드웨어

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>하드웨어 구성 요소</th>
<th>권장</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>%</p></td>
<td><p>64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상</p>
<p>인텔 아이테니엄 프로세서는 Lync Server 서버 역할에 지원 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Memory</p></td>
<td><p>32 기가바이트 (GB)</p></td>
</tr>
<tr class="odd">
<td><p>공간</p></td>
<td><ul>
<li><p>최소 72 GB의 사용 가능한 디스크 공간을 갖춘 8 대 이상의 1만-RPM 하드 디스크 드라이브.</p>
<p>두 개의 디스크에서 RAID 1을 사용 하 고 6 개는 RAID 10을 사용 해야 합니다.</p>
<p>-또는</p></li>
<li><p>8 1만-RPM 기계 디스크 드라이브와 유사한 성능을 제공 하는 Ssd (고체 스테이트 드라이브).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>결과 요약

다음 표에는 이러한 권장 사항이 요약 되어 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>서버 역할</th>
<th>지원 되는 최대 사용자 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>12 개의 프런트 엔드 서버와 1 백 엔드 서버 또는 미러 백 엔드 서버 쌍이 있는 프런트 엔드 풀</p></td>
<td><p>8만 고유 사용자에 게 동시에 로그인 하 고 50%의 여러 지점 (MPOP)이 비 모바일 인스턴스를 표시 하 고, 사용자의 40%가 총 152000 끝점에 대해 이동성을 사용 하도록 설정 했습니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V 회의</p></td>
<td><p>프런트 엔드 풀에서 제공 하는 A/V 회의 서비스는 최대 컨퍼런스 크기인 250 사용자로 간주 되는 풀의 컨퍼런스와 한 번에 실행 되는 이러한 대량 컨퍼런스만 지원 합니다.</p>
<div>

> [!NOTE]  
> 또한, 대형 회의를 호스트할 프런트 엔드 서버 두 대와 별도의 프런트 엔드 풀을 배포 하 여 250와 1000 사용자 간에 대규모 회의를 지원할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013를 사용 하 여 대형 모임 지원을</A>참조 하세요.


</div></td>
</tr>
<tr class="odd">
<td><p>1에 지 서버</p></td>
<td><p>12000 동시 원격 사용자</p></td>
</tr>
<tr class="even">
<td><p>디렉터 1 개</p></td>
<td><p>12000 동시 원격 사용자</p></td>
</tr>
<tr class="odd">
<td><p>모니터링 및 보관</p></td>
<td><p>Lync Server 2013에서는 이제 각 프런트 엔드 서버에서 별도의 서버 역할이 아니라 모니터링 및 보관 프런트 엔드 서비스를 실행 합니다.</p>
<p>각 모니터링 및 보관에는 여전히 자체 데이터베이스 저장소가 필요 합니다. Exchange 2013를 실행 하는 경우 전용 SQL 데이터베이스가 아닌 Exchange에 보관 데이터를 유지할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>하나의 중재 서버</p></td>
<td><p>프런트 엔드 서버를 사용 하는 중재 서버 collocated 풀의 모든 프런트 엔드 서버에서 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다. 독립 실행형 중재 서버의 경우이 항목의 뒷부분에 나오는 "중재 서버" 섹션을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>1 개 표준 버전 서버</p></td>
<td><p>스탠더드 버전 서버를 사용 하 여 사용자를 호스트 하는 경우, <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구 계획</a>의 권장 사항을 사용 하는 두 서버를 항상 사용 하는 것이 좋습니다. 쌍의 각 서버는 최대 2500 사용자를 호스트할 수 있으며, 한 서버가 실패 하는 경우 나머지 서버는 장애 조치 시나리오에서 5000 사용자를 지원할 수 있습니다.</p>
<p>배포에 상당한 양의 오디오 또는 비디오 소통량이 포함 되어 있는 경우 서버에 2500 사용자가 넘는 경우 서버의 성능이 저하 될 수 있습니다. 이 경우에는 표준 버전 서버를 추가 하거나 Lync Server Enterprise Edition으로 이동 하는 것이 좋습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>프런트 엔드 서버

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

프런트 엔드 풀에서 풀의 모든 서버에 대 한 하이퍼 스레드를 사용 하도록 설정 하 고 서버 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 하 여 풀에 있는 모든 6660 사용자에 대해 프런트 엔드 서버를 하나씩 보유 해야 합니다. 풀의 모든 서버에서 하이퍼 스레드를 사용 하는 경우 한 프런트 엔드 풀의 최대 사용자 수는 8만입니다. 사이트에 8만 명 이상의 사용자가 있는 경우 두 개 이상의 프런트 엔드 풀을 배포할 수 있습니다.

프런트 엔드 풀의 사용자 수를 고려 하는 경우이 프론트 엔드 풀과 연결 된 지점에서 Survivable Branch 기기 및 Survivable Branch 서버에 속한 사용자를 포함 합니다.

활성 서버를 사용할 수 없는 경우 해당 연결이 자동으로 풀의 다른 서버로 전송 됩니다. 예를 들어 3만 사용자와 다섯 개의 프런트 엔드 서버가 있는 경우 서버를 사용할 수 없는 경우에는 6000 사용자의 연결을 다른 4 개의 서버로 전송 해야 합니다. 나머지 4 대의 서버에는 각각 7500 사용자가 있으며 권장 보다 더 큽니다.

3만 사용자를 위해 6 개의 프런트 엔드 서버로 시작 하 고 그 이후에 한 번만 사용할 수 있게 되 면 총 5000 사용자가 나머지 5 대 서버로 이동 합니다. 이 다섯 개의 서버는 각각 호스트 6000 사용자 이며 권장 범위에 있습니다.

프런트 엔드 풀의 최대 사용자 수는 8만입니다. 풀의 최대 프런트 엔드 서버 수는 12 개입니다.

8만 사용자가 있는 프런트 엔드 풀의 경우, [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 따르는 일반적인 배포의 12 개의 프런트 엔드 서버는 성능에 충분 합니다. 재해 복구 장애 조치 (failover)를 지원 하도록 설계 된 배포 4만는 두 개의 쌍으로 이루어진 각 프런트 엔드 풀에 호스트 될 수 있으며, 각 풀의 사용자에 게 하나의 풀을 사용할 수 있는 충분 한 프런트 엔드 서버가 있는 것으로 가정 합니다. (으)로 이동할 수 있습니다.

특정 프런트 엔드 풀에의 한 좋은 성능으로 지원 되는 사용자 수는 다음과 같은 이유로 이러한 번호와 다를 수 있습니다.

  - 프런트 엔드 서버용 하드웨어가 [Lync server 2013의 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)에 대 한 권장 사항을 충족 하지 않습니다.

  - 조직의 사용이 훨씬 더 많은 회의 트래픽과 같은 사용자 모델과 크게 다릅니다.

<div>


> [!IMPORTANT]  
> Lync Server 2013에서 현재 상태 데이터베이스는 백 엔드 서버에서 호스트 되는 Lync Server 2010와는 달리 프런트 엔드 서버에서 호스팅됩니다. 이는 프런트 엔드 서버에서 호스트 되는 사용자 수에 관계 없이 프런트 엔드 서버의 디스크 성능 및 용량이이 섹션의 앞부분에 나열 된 권장 사항 및 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013의 서버 하드웨어 플랫폼</A>에서 노출 되지 않아야 함을 의미 합니다.



</div>

다음 표에서는 [Lync Server 2013의 사용자](lync-server-2013-user-models.md)모델에 정의 된 대로 사용자 모델에 따라 IM 및 현재 상태에 대 한 평균 대역폭을 보여 줍니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 당 평균 대역폭</th>
<th>6660 사용자가 있는 프런트 엔드 서버 당 대역폭 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 프런트 엔드 서버에서 배치 된 A/V 회의 및 조정 서버 기능의 미디어 성능을 개선 하려면 프런트 엔드 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>"Windows Server 2008에서 수신측 배율 향상 기능"을 참조 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>회의 최대값

풀의 사용자 5%가 한 번에 회의에 있을 수 있는 사용자 모델의 경우, 8만 사용자 풀은 한 번에 회의에 4000 사용자를 제공할 수 있습니다. 이러한 회의는 미디어 (일부 IM 전용, 오디오가 있는 일부 메신저, 일부 오디오/비디오 등)와 참가자 수를 혼합 하 여 사용 해야 합니다. 실제 회의 수에는 제한이 없으며 실제 사용량에 따라 실제 성능이 결정 됩니다. 예를 들어 조직에 사용자 모델에 포함 된 것 보다 더 많은 혼합 모드 회의가 있는 경우이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버 또는 A/V 회의 서버를 배포 해야 할 수 있습니다. 사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하세요.

사용자를 호스트 하는 일반 Lync Server 2013 프런트 엔드 풀에서 호스트 하는 지원 되는 최대 컨퍼런스 크기 250입니다. 250 사용자 회의가 진행 되는 동안에도 풀 사용자의 총 5%가 동시에 진행 되는 것을 비롯 한 다른 컨퍼런스도 여전히 지원 됩니다. 예를 들어 12 프런트 엔드 서버와 8만 사용자의 풀에서 250 사용자 회의가 발생 하는 동안에는 Lync Server가 소규모 회의에 참여 하는 3750 다른 사용자를 지원 합니다.

Lync Server는 프런트 엔드 풀 또는 Standard Edition server에 속한 사용자 수와 관계 없이 250-사용자 회의를 호스트 하는 동일한 풀이나 서버에서 작은 회의에 참여 하는 최소 125의 다른 사용자를 지원 합니다.

250와 1000 사용자 간에 회의를 설정 하려면 해당 회의를 호스팅하기 위해 별도의 프런트 엔드 풀을 설정할 수 있습니다. 이 프런트 엔드 풀은 사용자를 호스팅하지 않습니다. 자세한 내용은 [Lync Server 2013를 사용 하 여 대형 모임 지원을](lync-server-2013-supporting-large-meetings.md)참조 하세요.

조직에 사용자 모델에 사용 되는 것 보다 더 많은 혼합 모드 회의가 있는 경우이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버를 배포 해야 할 수 있습니다 (최대 12fes). 사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하세요.

</div>

<div>

## <a name="edge-server"></a>Edge 서버

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

사이트에 동시에 액세스 하는 모든 12000 원격 사용자에 대해 하나의 Edge 서버를 배포 해야 합니다. 최소한 고가용성을 위해 두 개의 Edge 서버를 사용 하는 것이 좋습니다. 이러한 권장 사항은 Edge 서버의 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.

Edge 서버의 사용자 수를 고려 하는 경우이 사이트의 프런트 엔드 풀과 연결 된 지점에서 Survivable Branch 기기 및 Survivable Branch 서버에 속한 사용자를 포함 합니다.

<div>


> [!NOTE]  
> Edge 서버에서 A/V 회의에 대 한 서비스의 성능을 향상 시키려면 Edge 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>"Windows Server 2008에서 수신측 배율 향상 기능"을 참조 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

디렉터 서버 역할을 배포 하는 경우 사이트에 동시에 액세스 하는 모든 12000 원격 사용자에 대해 하나의 디렉터를 배포 하는 것이 좋습니다. 최소한 고가용성을 위해 2 개의 디렉터를 권장 합니다. 이러한 권장 사항은 Edge 서버의 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.

디렉터에 대 한 사용자 수를 고려 하는 경우이 사이트의 프런트 엔드 풀에 연결 된 지점에서 Survivable Branch 기기 및 Survivable Branch 서버에 속한 사용자를 포함 합니다.

</div>

<div>

## <a name="mediation-server"></a>중재 서버

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

프런트 엔드 서버를 사용 하는 중재 서버를 collocate 풀의 모든 프런트 엔드 서버에서 중재 서버가 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다.

독립 실행형 중재 서버 풀을 배포 하는 경우에는 조정 서버에 사용 되는 하드웨어, 보유 한 VoIP 사용자 수, 각 중재 서버 풀에 있는 게이트웨이 피어 수를 비롯 한 다양 한 요인에 따라 배포할 중재 서버 수가 달라 집니다. 해당 게이트웨이를 통해 사용 하는 시간 트래픽 및 중재 서버를 우회 하는 미디어로의 통화 백분율이 표시 됩니다.

다음 표에서는 중재 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 의 요구 사항을 충족 하 고 하이퍼 스레드를 사용 하도록 설정 되어 있다고 가정 하 여 중재 서버가 처리할 수 있는 동시 호출 횟수에 대 한 지침을 제공 합니다. 중재 서버 확장성에 대 한 자세한 내용은 [lync server 2013의 중재 서버에 대 한](lync-server-2013-deployment-guidelines-for-mediation-server.md) [lync Server 2013 및 배포 지침에 대 한 음성 사용량 및 트래픽 예측](lync-server-2013-estimating-voice-usage-and-traffic.md) 을 참조 하세요.

다음 표에는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 요약 된 사용 방법이 들어 있습니다.

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>독립 실행형 중재 서버 용량: 70% 내부 사용자, 우회 되지 않는 외부 사용자 30% (중재 서버에서 수행 하는 미디어 코드 변환)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>서버 하드웨어</th>
<th>최대 통화 수</th>
<th>최대 T1 회선 수</th>
<th>최대 E1 선 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>듀얼 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU (32 GB 메모리와 듀얼 포트 네트워크 어댑터 카드)를 사용 하 여 <strong>하이퍼 스레딩 기능을 사용할 수 없습니다</strong>.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>듀얼 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU, 32 GB 메모리 및 1 개의 듀얼 포트 네트워크 어댑터 카드.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 32 GB의 메모리가 있는 서버는 성능 테스트에 사용 되지만, 16 GB 메모리가 있는 서버는 독립 실행형 중재 서버에 대해 지원 되며이 표에 표시 된 성능을 제공 하기에 충분 합니다.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>서버 용량 조정 (프런트 엔드 서버를 사용 하는 중재 서버 Collocated) 70% 내부 사용자, 30% 외부 사용자, 바이패스 되지 않은 통화 용량 (중재 서버에서 수행 하는 미디어 처리)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>서버 하드웨어</th>
<th>최대 통화 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>32 GB 메모리 및 2 개의 1GB 네트워크 어댑터 카드가 있는 듀얼 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 프런트 엔드 서버는 해당 사용자에 게 있는 6600 사용자에 대 한 다른 기능 및 기능을 처리 해야 하 고 음성 통화에 필요한 코드 변환 외에도이 숫자가 독립 실행형 중재 서버의 숫자 보다 훨씬 작습니다.



</div>

<div>


> [!NOTE]  
> 중재 서버의 성능을 향상 시키려면 중재 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>"Windows Server 2008에서 수신측 배율 향상 기능"을 참조 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="back-end-server"></a>백 엔드 서버

Lync Server 2013에서 현재 상태 데이터베이스는 백 엔드 서버 대신 프런트 엔드 서버에 있습니다. 이로 인해 프런트 엔드 서버의 하드웨어 요구 사항에 해당 하는 Lync Server 2013의 각 백 엔드 서버에 대 한 요구 사항이 훨씬 더 간단 합니다. 백 엔드 서버가 25 개 디스크를 사용 하 여 훨씬 더 높은 성적 서버 여야 하는 Lync Server 2010와 비교해 보세요. 그러나 백 엔드 서버의 작업 부하는 여전히이 섹션의 앞에 나열 된 하드웨어 권장 사항과 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)에서 수행 하지 않도록 하는 것입니다.

백 엔드 서버의 가용성을 높이기 위해 서버 미러링을 배포 하는 것이 좋습니다. 자세한 내용은 [Lync server 2013에서 백 엔드 서버의](lync-server-2013-back-end-server-high-availability.md)고가용성을 참조 하세요.

</div>

<div>

## <a name="monitoring-and-archiving"></a>모니터링 및 보관

Lync Server 2013에서 모니터링 또는 보관을 배포 하는 경우 이러한 서비스의 프런트 엔드 기능은 별도의 서버 역할 대신 프런트 엔드 서버에서 실행 됩니다. 각 모니터링 및 보관은 백 엔드 저장소와는 별도로 자체 데이터베이스 저장소를 계속 사용 합니다. 또는 Exchange 2013을 배포한 경우 전용 SQL 저장소 대신 Exchange에 인스턴트 메시지 보관 데이터를 저장할 수 있습니다.

다음 표에는 데이터 모니터링 및 아카이빙에 대해 일일 사용자 당 얼마나 많은 데이터베이스 저장소가 필요한가 표시 되어 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (모니터링)</strong></p></td>
<td><p><strong>체감 품질 (모니터링)</strong></p></td>
<td><p><strong>보관</strong></p></td>
</tr>
<tr class="even">
<td><p>일일 사용자 당 필요한 디스크 공간</p></td>
<td><p>49 KB</p></td>
<td><p>28KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft는 성능 테스트 중에 모니터링 및 보관을 위해 데이터베이스 서버에 대해 다음 표의 하드웨어를 사용 했습니다. 테스트는 각각 8만 사용자를 포함 하는 두 개의 프런트 엔드 풀의 데이터를 수집 합니다.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>모니터링 및 보관 성능 테스트에 사용 되는 하드웨어

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>하드웨어 구성 요소</th>
<th>권장</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>%</p></td>
<td><p>64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상</p></td>
</tr>
<tr class="even">
<td><p>Memory</p></td>
<td><p>48 기가바이트 (GB)</p></td>
</tr>
<tr class="odd">
<td><p>공간</p></td>
<td><p>25 1만-RPM 하드 디스크 드라이브, 각 디스크에 300 GB, 다음 구성</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>구동</strong></p></td>
<td><p><strong>RAID 구성</strong></p></td>
<td><p><strong>디스크 수</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR, 체감 품질, 데이터베이스 데이터 파일을 단일 드라이브에 보관</p></td>
<td><p>1 + 0</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>CDR 데이터베이스 로그 파일</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>체감 품질 데이터베이스 로그 파일</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>데이터베이스 로그 파일 보관</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 음성 사용량 및 트래픽 예상](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013의 중재 서버 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

