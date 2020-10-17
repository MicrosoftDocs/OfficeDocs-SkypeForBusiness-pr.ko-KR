---
title: 'Lync Server 2013: IP 주소 유형에 대 한 개요'
description: 'Lync Server 2013: IP 주소 유형에 대 한 개요입니다.'
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
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559224"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013의 IP 주소 유형 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-29_

Lync Server 2013에서 IP 주소를 구성할 때는 다음과 같은 세 가지 옵션을 사용할 수 있습니다. IP 버전 4 (IPv4), IP 버전 6 (IPv6) 또는 둘 다를 지원 하도록 Lync Server 2013을 구성할 수 있습니다 ( *이중 스택*이라고 함). 구성 유형마다 고려해야 할 몇 가지 사항이 있습니다.

  - **IPv4 전용**     세계에서 IPv4 주소가 부족 하 여 IPv6이 생성 되었습니다. 궁극적으로 IPv6은 전 세계적으로 완벽 하 게 지원 되지만, 이때 엔터프라이즈가 통신 해야 하는 많은 회사 및 장치는 아직 i p v 6을 지원 하지 않을 수도 있습니다. IPv4 전용 구성은 Lync Server 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.

  - **IPv6만**     해당 반대로 현재 전체 IPv6 구현에서는 여러 기존 장치와의 통신을 제외 합니다.

  - **이중 스택**     이중 스택은 IPv4 및 IPv6 주소를 모두 사용 하도록 설정 된 네트워크입니다. 이 구성은 대부분의 경우 전체-IPv4에서 full-IPv6로 전환 하는 데는 몇 년이 소요 되기 때문에 Lync Server 2013에서 지원 됩니다.

다음 섹션에서는 다양 한 Lync Server 기능에 대 한 이러한 세 가지 구성 간의 호환성에 대해 간략하게 설명 합니다.

<div>


> [!NOTE]  
> IPv6를 사용한 클라이언트 또는 서버 구성은 연구 또는 검사 목적으로만 지원됩니다. IPv6 전용 구성은 프로덕션 배포에는 지원되지 않습니다.



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
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>IPv4</p></td>
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

피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다. 두 클라이언트가 성공적으로 등록된 후에는 다음 조합이 지원됩니다.


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
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
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

회의에는 오디오/비디오, 응용 프로그램 공유 및 데이터 공동 작업(화이트보드 및 파일 공유)이 포함됩니다.


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
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>이중 스택</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>IPv4</p></td>
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

Lync Server 2013에서는 트래픽이 IPv6 인터페이스를 통해 수행 되는 경우 공중 전화망 (PSTN) 통화에 대 한 미디어 바이패스를 지원 하지 않습니다. 미디어 바이패스가 필요할 경우 PSTN 게이트웨이를 IPv4로 구성하는 것이 좋습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>기본 인터페이스*</th>
<th>PSTN 인터페이스(중재 서버)</th>
<th>PSTN 게이트웨이 설정</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>이중 스택</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>이중 스택</p></td>
<td><p>이중 스택</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* 기본 인터페이스는 Lync Server 구성 요소와 통신 하는 인터페이스입니다.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>원격 사용자 피어 투 피어 통신

원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시징, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>원격 사용자 네트워크</th>
<th>에지 서버(외부 에지)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>이중 스택</p></td>
<td><p>IPv4</p></td>
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

## <a name="front-end-pool-and-edge-pool-configuration"></a>프런트 엔드 풀과 에지 풀 구성

다음 표에서는 프런트 엔드 서버 풀과 내부에 지 서버 풀 간의 지원 매트릭스를 보여 줍니다.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>프런트 엔드 풀과 에지 풀(내부 에지) 매트릭스

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
<td><p><strong>에지 풀: IPv4</strong></p></td>
<td><p><strong>에지 풀: 이중 스택</strong></p></td>
<td><p><strong>에지 풀: IPv6</strong></p></td>
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
<td><p>예*</p></td>
</tr>
</tbody>
</table>


\* 이 조합은 랩 환경 에서만 사용 해야 합니다.

다음 표는 지원되는 내부 및 외부 에지 인터페이스 조합 매트릭스입니다.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>에지 풀(내부 에지)과 에지 풀(외부 에지) 매트릭스

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
<td><p><strong>에지 풀(외부 에지) : IPv4</strong></p></td>
<td><p><strong>에지 풀(외부 에지): 이중 스택</strong></p></td>
<td><p><strong>에지 풀(외부 에지) : IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>에지 풀(내부 에지) : IPv4</strong></p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p><strong>에지 풀(내부 에지): 이중 스택</strong></p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p><strong>에지 풀(내부 에지) : IPv6</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예*</p></td>
</tr>
</tbody>
</table>


\* 이 조합은 랩 환경 에서만 사용 해야 합니다.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6에 대한 고급 Enterprise Voice 지원

CAC(통화 허용 제어 서비스), E9-1-1(고급 9-1-1) 또는 미디어 바이패스를 포함하는 배포는 IPv4 전용 또는 이중 스택 구현으로 구성해야 합니다.

<div>


> [!NOTE]  
> 이중 스택 배포에서 Lync 클라이언트가 i p v 6을 사용 하 여 Lync Server에 연결 하더라도 Lync에서는 적절 한 IPv4 주소를 E9-1-1을 지원 하도록 매핑하는 것이 좋습니다.



</div>

IPv6 주소를 사용 하는 위치 정보 서비스는 지원 되지 않습니다.

Exchange UM(통합 메시징)에서는 IPv6을 지원하지 않습니다. Exchange UM의 경우 DNS 확인 시 IPv6 주소가 반환되지 않습니다. IPv6을 사용하면 통화가 음성 사서함로 올바르게 전송될 때 실패할 수도 있습니다.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>IPv6에 대 한 기타 Lync Server 2013 기능 지원

앞에서 설명한 기능 및 구성 요소 외에도 Lync Server 2013에서는 다음 기능에 대해 i p v 6을 지원 합니다.

  - **영구 채팅**
    
    토폴로지 작성기를 사용 하 여 영구 채팅을 위해 IPv6을 구성 합니다. 영구 채팅을 구성 하는 방법에 대 한 자세한 내용은 배포 영구 채팅 서버 설명서를 참조 하십시오.

  - **QoE(체감 품질)과 CDR(통화 정보 기록) 보고서**
    
    모니터링 보고서에는 IPv4 형식인지 IPv6 형식인지에 관계 없이 모니터링 서버 데이터베이스에 저장된 IP 주소가 포함됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

