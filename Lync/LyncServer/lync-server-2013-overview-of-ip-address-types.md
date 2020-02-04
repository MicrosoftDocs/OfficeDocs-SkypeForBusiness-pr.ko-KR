---
title: 'Lync Server 2013: IP 주소 유형의 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013에 대한 IP 주소 유형의 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-29_

Lync Server 2013에서 IP 주소를 구성할 때는 세 가지 옵션이 있습니다. IP 버전 4 (IPv4)만 지원 하도록 Lync 서버 2013을 구성할 수 있으며 (IP 버전 6(Ipv6) 또는 둘 다 ( *이중 스택*이라고 함) 모두의 조합이 가능 합니다. 각 구성 유형에 대해 고려해 야 할 몇 가지 문제가 있습니다.

  - **Ipv4**   는 ipv4 주소를 초과 하지 않기 때문에 IPv6만 만들었습니다. 궁극적으로 IPv6은 전세계에서 완벽 하 게 지원 되지만 이번에는 엔터프라이즈에서 아직 IPv6을 지원 하지 않는 것으로 통신 해야 하는 많은 회사 및 장치를 사용할 수 있습니다. IPv4 전용 구성은 Lync 서버 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.

  - **Ipv6에만**   해당 되는 경우, 전체 ipv6 구현은 지금 많은 기존 장치와의 통신을 제외 합니다.

  - **이중 스택**   듀얼 스택은 IPv4 및 IPv6 주소를 모두 사용할 수 있는 네트워크입니다. 이 구성은 대부분의 경우 전체 IPv4에서 full-IPv6으로 전환 하는 데 몇 년이 소요 되므로 Lync Server 2013에서 지원 됩니다.

다음 섹션에서는 다양 한 Lync Server 기능에 대 한 이러한 세 가지 구성 간의 호환성에 대해 간략하게 설명 합니다.

<div>


> [!NOTE]  
> IPv6을 사용 하는 클라이언트 또는 서버 구성은 랩 또는 유효성 검사 용도로만 지원 됩니다. IPv6 전용 구성은 프로덕션 배포에서 지원 되지 않습니다.



</div>

<div>

## <a name="client-registration"></a>클라이언트 등록


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 끝점 네트워크</th>
<th>서버 네트워크</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Ipv4</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>(Ipv4</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>피어 투 피어 클라이언트

피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유, 파일 전송이 포함 됩니다. 두 클라이언트가 성공적으로 등록 되 면 다음 조합이 지원 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 끝점 1</th>
<th>클라이언트 끝점 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Ipv4</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>(Ipv4</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>회의

회의에는 오디오/비디오, 응용 프로그램 공유, 데이터 공동 작업 (whiteboarding 및 파일 공유)이 포함 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 끝점 네트워크</th>
<th>서버 네트워크</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Ipv4</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>(Ipv4</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>중재 서버/PSTN

Lync Server 2013는 트래픽이 IPv6 인터페이스를 사용 하는 경우에는 PSTN (공개 통신 네트워크) 호출의 미디어 바이패스를 지원 하지 않습니다. 미디어 바이패스가 필요한 경우 PSTN 게이트웨이가 IPv4로 구성 되는 것이 좋습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>기본 인터페이스 *</th>
<th>PSTN 인터페이스 (중재 서버에서)</th>
<th>PSTN 게이트웨이 설정</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Ipv4</p></td>
<td><p>이중 스택</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*기본 인터페이스는 Lync Server 구성 요소와 통신 하는 인터페이스입니다.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>원격 사용자 피어 투 피어 통신

원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시지, 오디오/비디오, 응용 프로그램 공유, 파일 전송 등이 포함 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>원격 사용자 네트워크</th>
<th>Edge 서버 (외부 가장자리)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Ipv4</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="even">
<td><p>이중 스택</p></td>
<td><p>(Ipv4</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>프런트 엔드 풀 및 Edge 풀 구성

다음 표에는 프런트 엔드 서버 풀과 내부 Edge 서버 풀 사이의 지원 행렬이 나와 있습니다.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>프런트 엔드 풀 및 Edge 풀 (내부에 지) 행렬

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
<td><p><strong>Edge 풀: IPv4</strong></p></td>
<td><p><strong>Edge 풀: 이중 스택</strong></p></td>
<td><p><strong>Edge 풀: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>프런트 엔드 풀: IPv4</strong></p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p><strong>프런트 엔드 풀: 이중 스택</strong></p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p><strong>프런트 엔드 풀: IPv6</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>'</p></td>
</tr>
</tbody>
</table>


\*랩 환경 에서만이 조합을 사용 합니다.

다음 표는 내부 및 외부 경계 인터페이스의 지원 되는 조합의 행렬입니다.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Edge 풀 (내부에 지) 및 Edge 풀 (외부 가장자리) 행렬

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
<td><p><strong>Edge 풀 (외부 가장자리): IPv4</strong></p></td>
<td><p><strong>Edge 풀 (외부 가장자리): 이중 스택</strong></p></td>
<td><p><strong>Edge 풀 (외부에 지): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 풀 (내부에 지): IPv4</strong></p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edge 풀 (내부에 지): 이중 스택</strong></p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 풀 (내부에 지): IPv6</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>'</p></td>
</tr>
</tbody>
</table>


\*랩 환경 에서만이 조합을 사용 합니다.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6에 대 한 고급 엔터프라이즈 음성 지원

CAC (호출 허용 제어), 향상 된 9-1-1 (E9-1-1) 또는 미디어 바이패스를 포함 하는 배포는 IPv4 전용 또는 듀얼 누적 구현으로 구성 되어야 합니다.

<div>


> [!NOTE]  
> 듀얼 누적 배포의 경우 Lync 클라이언트가 IPv6을 사용 하 여 Lync Server에 연결 하는 경우에도 Lync는 E9-1-1을 지원 하기 위해 적절 한 IPv4 주소를 매핑하는 것이 좋습니다.



</div>

IPv6 주소를 사용 하는 위치 정보 서비스는 지원 되지 않습니다.

UM (통합 메시징)는 IPv6을 지원 하지 않습니다. Exchange UM의 경우 DNS 확인이 IPv6 주소를 반환 하지 않도록 해야 합니다. 전화를 음성 메일로 보내면 IPv6을 사용 하면 오류를 일으킬 수 있습니다.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>IPv6에 대 한 다른 Lync Server 2013 기능 지원

이전에 언급 한 기능 및 구성 요소 외에도 Lync Server 2013는 다음 기능에 대 한 IPv6을 지원 합니다.

  - **영구 채팅**
    
    토폴로지 작성기를 사용 하 여 영구 채팅을 위해 IPv6을 구성 합니다. 영구 채팅 구성에 대 한 자세한 내용은 영구 채팅 서버 배포 설명서를 참조 하세요.

  - **경력 (체감 품질) 및 통화 정보 기록 (CDR) 보고서**
    
    모니터링 보고서에는 IPv4 또는 IPv6 유형에 관계 없이 모니터링 서버 데이터베이스에 저장 되는 IP 주소가 포함 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

