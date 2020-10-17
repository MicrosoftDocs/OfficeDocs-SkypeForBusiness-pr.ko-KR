---
title: 사용자 모델을 사용 하는 Lync Server 2013 용량 계획
description: Lync Server 2013에서는 사용자 모델을 사용 하 여 용량을 계획 합니다.
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
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544414"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>사용자 모델을 사용 하는 Lync Server 2013에 대 한 용량 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-01-14_

이 섹션에서는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 설명 된 사용에 따라 해당 사이트의 사용자 수에 대해 사이트에서 필요한 서버 수에 대 한 지침을 제공 합니다.

<div>

## <a name="tested-hardware-platform"></a>테스트를 거친 하드웨어 플랫폼

이 섹션의 모든 성능 결과 및 배포 권장 사항은 다음 표에 설명 된 하드웨어를 실행 하는 서버에 대 한 성능 테스트를 기반으로 합니다. 비슷한 하드웨어를 사용 하는 것이 좋습니다. 덜 강력한 하드웨어를 사용 하는 경우에는 기능에 문제가 있거나 성능이 저하 될 수 있습니다. 이러한 하드웨어 권장 사항은 이전 버전의 Lync Server 보다 더 높습니다.

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
<td><p>CPU</p></td>
<td><p>64비트 이중 프로세서, 6중 코어, 2.26GHz 이상</p>
<p>Lync Server 서버 역할에는 Intel Itanium 프로세서가 지원 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>메모리</p></td>
<td><p>32GB</p></td>
</tr>
<tr class="odd">
<td><p>공간이</p></td>
<td><ul>
<li><p>72 GB 이상의 사용 가능한 디스크 공간이 있는 1만-RPM 하드 디스크 드라이브 8 개 이상</p>
<p>이 중 두 개는 RAID 1을 사용하고 6개는 RAID 10을 사용합니다.</p>
<p>- 사용자나</p></li>
<li><p>8개의 10,000 RPM 기계식 디스크 드라이브와 유사한 성능을 제공하는 SDD(반도체 드라이브)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1개의 이중 포트 네트워크 어댑터, 1Gbps 이상(2개 권장, 단일 MAC 주소와 단일 IP 주소를 사용하여 팀으로 구성해야 함)</p></li>
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
<td><p>12 개의 프런트 엔드 서버와 하나의 백 엔드 서버 또는 미러링된 백 엔드 서버 쌍의 프런트 엔드 풀</p></td>
<td><p>8만 사용자가 동시에 로그인 하 고 50%에 해당 하는 MPOP (여러 지점)을 포함 40 하 여 모바일이 아닌 인스턴스를 표시 하 고, 총 152000 끝점에 대 한 모바일 기능을 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V 회의</p></td>
<td><p>프런트 엔드 풀에서 제공 하는 A/V 회의 서비스는 최대 회의 크기인 250 명의 사용자만을 지원 하 고 한 번에 실행 되는 이러한 대규모 회의만 있으면 서 풀의 회의를 지원할 수 있습니다.</p>
<div>

> [!NOTE]  
> 또한 대규모 회의를 호스트 하기 위해 두 개의 프런트 엔드 서버를 포함 하는 별도의 프런트 엔드 풀을 배포 하 여 250와 1000 사용자 간의 대규모 회의를 지원할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013을 사용 하 여 대규모 모임 지원</A>를 참조 하세요.


</div></td>
</tr>
<tr class="odd">
<td><p>1 개의에 지 서버</p></td>
<td><p>12000 동시 원격 사용자</p></td>
</tr>
<tr class="even">
<td><p>디렉터 1 개</p></td>
<td><p>12000 동시 원격 사용자</p></td>
</tr>
<tr class="odd">
<td><p>모니터링 및 보관</p></td>
<td><p>Lync Server 2013에서는 모니터링 및 보관 프런트 엔드 서비스가 별도의 서버 역할이 아닌 각 프런트 엔드 서버에서 실행 됩니다.</p>
<p>각 모니터링 및 보관은 여전히 자체 데이터베이스 저장소를 필요로 합니다. Exchange 2013도 실행 하는 경우 전용 SQL 데이터베이스가 아닌 Exchange에 보관 데이터를 유지할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>중재 서버 1 개</p></td>
<td><p>프런트 엔드 서버를 사용 하는 중재 서버 배치 된 풀의 모든 프런트 엔드 서버에서 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다. 독립 실행형 중재 서버에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "중재 서버" 섹션을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>Standard Edition 서버 1 대</p></td>
<td><p>Standard Edition 서버를 사용 하 여 사용자를 호스트 하는 경우 항상 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구 계획</a>의 권장 사항을 사용 하 여 두 서버를 사용 하는 것이 좋습니다. 쌍의 각 서버에서 최대 2500 명의 사용자를 호스팅할 수 있으며, 한 서버가 실패 하면 장애 조치 (failover) 시나리오에서 나머지 서버가 5000 사용자를 지원할 수 있습니다.</p>
<p>배포에 많은 양의 오디오 또는 비디오 트래픽이 포함 되는 경우 서버에 대해 서버 성능에 2500 명 넘게 발생할 수 있습니다. 이 경우 Standard Edition 서버를 더 추가 하거나 Lync Server Enterprise Edition으로 이동 하는 것이 좋습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Front End Server(프런트 엔드 서버)

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

프런트 엔드 풀에서는 풀에 있는 모든 서버에 대해 하이퍼스레딩을 사용 하도록 설정 하 고 서버 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 하 고 풀에 있는 모든 6660 사용자에 대해 프런트 엔드 서버를 하나씩 포함 해야 합니다. 풀의 모든 서버에서 하이퍼스레딩을 사용 하는 경우 한 프런트 엔드 풀의 최대 사용자 수는 8만입니다. 사이트에 사용자가 8만 명 이상인 경우 프런트 엔드 풀을 두 개 이상 배포할 수 있습니다.

프런트 엔드 풀의 사용자 수를 고려해 야 하는 경우이 프런트 엔드 풀과 연결 된 지점에 있는 Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 있는 사용자를 포함 합니다.

활성 서버를 사용할 수 없으면 해당 연결이 풀의 다른 서버로 자동 전송 됩니다. 예를 들어 사용자가 5 명이 고 프런트 엔드 서버가 다섯 대 3만 있는 경우 한 서버를 사용할 수 없는 경우 6000 사용자의 연결을 다른 4 개의 서버로 전송 해야 합니다. 나머지 4 개의 서버에는 각각 7500 명의 사용자가 있으므로 권장 되는 것 보다 더 큰 값이 있습니다.

예를 들어, 3만 사용자에 대해 6 개의 프런트 엔드 서버를 시작한 후 그 중 하나를 사용할 수 없게 되 면 총 5000 명의 사용자가 나머지 5 대 서버로 이동 됩니다. 이러한 5 개의 서버는 각 호스트 6000 사용자를 권장 범위에 있습니다.

프런트 엔드 풀의 최대 사용자 수는 8만입니다. 풀의 최대 프런트 엔드 서버 수는 12입니다.

8만 명의 사용자가 포함 된 프런트 엔드 풀의 경우 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 따르는 일반적인 배포에서 12 개의 프런트 엔드 서버는 성능에 충분 합니다. 재해 복구 장애 조치 (failover)를 지원 하도록 설계 4만 된 배포에서는 각 풀이 두 개의 쌍으로 된 프런트 엔드 풀 각각에 호스트 될 수 있는데,이 경우 각 풀에는 두 풀의 사용자를 둘 다 포함할 프런트 엔드 서버가 충분 한 것으로 가정 합니다.

특정 프런트 엔드 풀에서 양호한 성능을 사용 하 여 지원 되는 사용자 수는 다음과 같은 이유로 인해 발생할 수 있습니다.

  - 프런트 엔드 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 하지 않습니다.

  - 조직의 사용량은 훨씬 더 많은 회의 트래픽 등 사용자 모델과 크게 다릅니다.

<div>


> [!IMPORTANT]  
> Lync Server 2013에서는 현재 상태 데이터베이스가 백 엔드 서버에서 호스트 되는 Lync Server 2010와는 달리 프런트 엔드 서버에 호스트 됩니다. 즉, 프런트 엔드 서버에서 호스팅하는 사용자 수에 관계 없이 프런트 엔드 서버의 디스크 성능 및 용량을이 섹션의 앞부분과 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 용 서버 하드웨어 플랫폼</A>의 권장 사항에 따라 노출 해서는 안 됩니다.



</div>

다음 표에서는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 정의 된 대로 사용자 모델에 따라 IM 및 현재 상태에 대 한 평균 대역폭을 보여 줍니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 당 평균 대역폭</th>
<th>6660 명의 사용자가 있는 프런트 엔드 서버당 대역폭 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 프런트 엔드 서버에서 공동 위치 A/V 회의 및 중재 서버 기능의 미디어 성능을 개선 하려면 프런트 엔드 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은의 "Windows Server 2008에서 수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>회의 최대값

사용자 모델에서 풀 사용자의 5%가 언제 든 지 회의에 참석할 수 있는 경우 한 번에 8만 명의 사용자에 게 4000 명의 사용자가 회의에 참가 하는 것을 겪을 수 있습니다. 이러한 회의는 미디어 (일부 IM 전용, 오디오를 포함 하는 일부 IM, 일부 오디오/비디오 등)와 참가자 수를 혼합 하 여 사용 해야 합니다. 실제로 허용 되는 실제 회의 수에 대 한 제한은 없으며 실제 사용 방법에 따라 실제 성능이 결정 됩니다. 예를 들어 조직에서 사용자 모델에 포함 된 것 보다 많은 혼합 모드를 사용 하는 경우에는이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버 또는 A/V 회의 서버를 배포 해야 할 수 있습니다. 사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하십시오.

사용자가 호스트 하는 일반 Lync Server 2013 프런트 엔드 풀에서 호스트 하는 지원 되는 최대 회의 크기는 250 참가자입니다. 250-사용자 회의가 진행 되는 동안에도 풀은 여전히 다른 회의를 지원 하며,이 경우 풀 사용자의 총 5%가 동시 회의에 참가 하는 것이 좋습니다. 예를 들어 12 프런트 엔드 서버 및 8만 사용자의 그룹에서 250 사용자 회의가 발생 하는 동안 Lync Server에서는 더 작은 회의에 참가 하는 3750을 다른 사용자에 게 지원 합니다.

프런트 엔드 풀 또는 Standard Edition server에 있는 사용자 수에 관계 없이 Lync Server는 250-사용자 회의를 호스트 하는 동일한 풀이나 서버에서 더 작은 회의에 참가 하는 최소 125의 다른 사용자를 지원 합니다.

250과 1000 사용자 간의 전화 회의를 사용 하도록 설정 하려면 이러한 전화 회의를 호스트 하는 경우에만 별도의 프런트 엔드 풀을 설정할 수 있습니다. 이 프런트 엔드 풀은 사용자를 호스팅하지 않습니다. 자세한 내용은 [Lync Server 2013을 사용 하 여 대규모 모임 지원](lync-server-2013-supporting-large-meetings.md)를 참조 하세요.

조직에서 사용자 모델에 사용 되는 것 보다 많은 혼합 모드를 사용 하는 경우에는이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버를 배포 해야 할 수 있습니다 (최대 크기 제한인 12). 사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하십시오.

</div>

<div>

## <a name="edge-server"></a>에지 서버

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

사이트에 동시에 액세스 하는 12000 원격 사용자 마다 하나의에 지 서버를 배포 해야 합니다. 최소한 고가용성을 위해 두 개의에 지 서버를 사용 하는 것이 좋습니다. 이러한 권장 사항은에 지 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.

에 지 서버에 대 한 사용자 수를 고려해 야 하는 경우이 사이트의 프런트 엔드 풀에 연결 된 지점에 있는 Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 홈 사용자를 포함 합니다.

<div>


> [!NOTE]  
> 에 지 서버에서 A/V 회의에 지 서비스의 성능을 향상 시키려면에 지 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은의 "Windows Server 2008에서 수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

디렉터 서버 역할을 배포 하는 경우에는 사이트에 동시에 액세스할 모든 12000 원격 사용자에 대해 하나의 디렉터를 배포 하는 것이 좋습니다. 최소한 고가용성을 위한 두 개의 디렉터를 권장 합니다. 이러한 권장 사항은에 지 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.

디렉터에 대 한 사용자 수를 고려 하는 경우이 사이트의 프런트 엔드 풀에 연결 된 지점에 있는 Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 홈 사용자를 포함 합니다.

</div>

<div>

## <a name="mediation-server"></a>중재 서버

<div>


> [!NOTE]  
> 스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.



</div>

중재 서버와 프런트 엔드 서버를 함께 배치할 경우에는 풀의 모든 프런트 엔드 서버에서 중재 서버가 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다.

독립 실행형 중재 서버 풀을 배포 하는 경우 배포할 중재 서버 수는 중재 서버에 사용 되는 하드웨어, VoIP 사용자 수, 각 중재 서버 풀에서 제어 하는 게이트웨이 피어 수, 이러한 게이트웨이를 통한 통화 시간 트래픽 및 중재 서버를 우회 하는 미디어의 호출 비율을 비롯 한 다양 한 요인에 따라 달라 집니다.

다음 표에는 중재 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 의 요구 사항을 충족 하 고 하이퍼스레딩을 사용 하도록 설정 되어 있다고 가정 하 고 중재 서버가 처리할 수 있는 동시 통화의 수에 대 한 지침을 제공 합니다. 중재 서버 확장성에 대 한 자세한 내용은 lync server [2013의 중재 서버에 대](lync-server-2013-deployment-guidelines-for-mediation-server.md)한 [음성 사용량 및 2013 트래픽 예상](lync-server-2013-estimating-voice-usage-and-traffic.md) 및 배포 지침을 참조 하세요.

다음 표에는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 요약 된 사용 용도가 나와 있습니다.

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>독립 실행형 중재 서버 용량: 70% 내부 사용자, 바이패스 없는 통화 용량을 가진 30%의 외부 사용자 (중재 서버에서 수행 하는 미디어 코드 변환)

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
<th>최대 E1 줄 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이중 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU ( <strong>하이퍼 스레딩 사용 안 함</strong>), 32 GB 메모리 및 이중 포트 네트워크 어댑터 카드 1 개</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>이중 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU (32 GB 메모리 및 1 개의 이중 포트 네트워크 어댑터 카드 포함)</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 메모리가 32 인 서버는 성능 테스트에 사용 되었지만, 16gb 메모리를 가진 서버는 독립 실행형 중재 서버에 대해 지원 되며이 표에 표시 된 성능을 충분히 제공 하기에 충분 합니다.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>중재 서버 용량 (중재 서버 배치 된 with 프런트 엔드 서버) 70% 내부 사용자, 30% 외부 사용자, 바이패스 통화 용량 (중재 서버에서 수행 하는 미디어 처리)

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
<td><p>이중 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU (32 GB 메모리 및 2 개의 1GB 네트워크 어댑터 카드 포함)</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 프런트 엔드 6600 서버는 음성 통화에 필요한 트랜스 코딩 외에도,이 값은 독립 실행형 중재 서버의 숫자 보다 훨씬 더 작습니다 (이 경우에는,).



</div>

<div>


> [!NOTE]  
> 중재 서버의 성능을 향상 시키려면 중재 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은의 "Windows Server 2008에서 수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="back-end-server"></a>백 엔드 서버

Lync Server 2013에서는 현재 상태 데이터베이스가 백 엔드 서버가 아닌 프런트 엔드 서버에 있습니다. 이로 인해 프런트 엔드 서버의 하드웨어 요구 사항에 해당 하는 Lync Server 2013의 각 백 엔드 서버에 대 한 요구 사항이 훨씬 더 간단해졌습니다. 이는 백 엔드 서버가 25 개 디스크를 사용 하는 것 보다 훨씬 높은 등급이 필요한 Lync Server 2010와는 대조적입니다. 그러나 백 엔드 서버의 작업량은 여전히이 섹션의 앞부분과 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)에서 설명한 하드웨어 권장 사항을 충족 시 키 지 않아야 합니다.

백 엔드 서버의 고가용성을 제공 하려면 서버 미러링을 배포 하는 것이 좋습니다. 자세한 내용은 [Lync server 2013에서 백 엔드 서버 고가용성](lync-server-2013-back-end-server-high-availability.md)을 참조 하세요.

</div>

<div>

## <a name="monitoring-and-archiving"></a>모니터링 및 보관

Lync Server 2013에서 모니터링 또는 보관을 배포 하는 경우 이러한 서비스의 프런트 엔드 기능은 별도의 서버 역할이 아닌 프런트 엔드 서버에서 실행 됩니다. 모니터링 및 보관 각 각각은 백 엔드 저장소와는 별도로 자체 데이터베이스 저장소를 그대로 사용 합니다. 또는 Exchange 2013이 배포 된 경우 전용 SQL 저장소가 아닌 Exchange에 인스턴트 메시지 보관 데이터를 저장할 수 있습니다.

다음 표에는 데이터 모니터링 및 보관에 대 한 일별 사용자 당 필요한 데이터베이스 저장소의 양이 대략적으로 나와 있습니다.


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
<td><p><strong>QoE (모니터링)</strong></p></td>
<td><p><strong>보관</strong></p></td>
</tr>
<tr class="even">
<td><p>사용자 당 하루에 필요한 디스크 공간</p></td>
<td><p>49</p></td>
<td><p>28kb(</p></td>
<td><p>57</p></td>
</tr>
</tbody>
</table>


Microsoft는 성능 테스트 중에 모니터링 및 보관을 위해 데이터베이스 서버에 대해 다음 표의 하드웨어를 사용 했습니다. 테스트에서는 각각 8만 사용자를 포함 하는 두 프런트 엔드 풀의 데이터를 수집 합니다.

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
<td><p>CPU</p></td>
<td><p>64비트 이중 프로세서, 6중 코어, 2.26GHz 이상</p></td>
</tr>
<tr class="even">
<td><p>메모리</p></td>
<td><p>48 기가바이트 (GB)</p></td>
</tr>
<tr class="odd">
<td><p>공간이</p></td>
<td><p>25 1만-RPM 다음 구성을 사용 하 여 각 디스크에 300 GB의 하드 디스크 드라이브</p>
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
<td><p><strong>드라이브</strong></p></td>
<td><p><strong>RAID 구성</strong></p></td>
<td><p><strong>디스크 수</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR, QoE 및 보관 데이터베이스 데이터 파일 (단일 드라이브)</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>CDR 데이터베이스 로그 파일</p></td>
<td><p>1 </p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>QoE 데이터베이스 로그 파일</p></td>
<td><p>1 </p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>보관 데이터베이스 로그 파일</p></td>
<td><p>1 </p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1개의 이중 포트 네트워크 어댑터, 1Gbps 이상(2개 권장, 단일 MAC 주소와 단일 IP 주소를 사용하여 팀으로 구성해야 함)</p></li>
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

