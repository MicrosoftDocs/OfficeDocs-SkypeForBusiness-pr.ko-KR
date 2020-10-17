---
title: 'Lync Server 2013: 통화 허용 제어에 대 한 요구 사항 정의'
description: 'Lync Server 2013: 통화 허용 제어에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f675ac5811e0c0c1c23dc76ebb8b4525857836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545424"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-28_

CAC(통화 허용 제어) 계획에는 엔터프라이즈 네트워크 토폴로지에 대한 자세한 정보가 필요합니다. 다음 단계에 따라 통화 허용 제어 정책을 보다 쉽게 계획할 수 있습니다.

1.  엔터프라이즈 네트워크 내의 허브/백본(*네트워크 지역*이라고 함) 확인

2.  각 네트워크 지역 내의 사무실 또는 위치(*네트워크 사이트*라고 함) 확인

3.  모든 네트워크 지역 쌍 간의 네트워크 경로 확인

4.  각 WAN 링크에 대한 대역폭 제한 확인
    
    <div>
    

    > [!NOTE]  
    > 대역폭 제한은 WAN 링크에서 엔터프라이즈 음성 및 오디오/비디오 트래픽에 할당 되는 대역폭의 양을 나타냅니다. 따라서 WAN 링크가 "대역폭이 제한된" 것으로 설명된 경우 링크에서 예상되는 최대 트래픽보다 낮은 대역폭 제한이 WAN 링크에 설정되어 있습니다.

    
    </div>

5.  각 네트워크 사이트에 지정된 IP 서브넷 확인

이러한 개념을 설명하기 위해 아래 그림에 표시된 네트워크 토폴로지 예를 사용합니다.

**통화 허용 제어 토폴로지의 예**

![Litware Inc. 네트워크 토폴로지 예](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 네트워크 토폴로지 예")

<div>


> [!NOTE]  
> 모든 네트워크 사이트는 네트워크 지역과 연결됩니다. 예를 들어 포틀랜드, 리노 및 앨버커키는 북미 지역에 포함됩니다. 이 그림에는 CAC 정책이 적용되는 WAN 링크에만 대역폭 제한이 표시되어 있습니다. 시카고, 뉴욕 및 디트로이트의 네트워크 사이트는 대역폭 제한이 없어 CAC 정책이 필요하지 않으므로 북미 지역 타원 안에 표시되어 있습니다.



</div>

이 토폴로지의 예의 구성 요소는 다음 섹션에 설명되어 있습니다. 대역폭 제한을 비롯 하 여이 토폴로지의 계획 방식에 대 한 자세한 내용은 [Example: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)을 참조 하십시오.

<div>

## <a name="identify-network-regions"></a>네트워크 지역 확인

네트워크 지역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.

네트워크 백본 또는 허브는 네트워크의 여러 부분을 상호 연결하는 컴퓨터 네트워크 인프라의 일부로서, 서로 다른 LAN 또는 서브넷 간의 정보 교환 경로를 제공합니다. 백본은 소규모 위치에서 지리적으로 넓은 지역에 이르기까지 다양한 네트워크를 함께 묶을 수 있습니다. 따라서 백본의 용량은 일반적으로 백본에 연결된 네트워크의 용량보다 큽니다.

여기에 설명된 토폴로지에는 북미, EMEA, APAC, 이렇게 세 개의 네트워크 지역이 있습니다. 네트워크 지역은 네트워크 사이트 컬렉션을 포함합니다(이 항목에 뒷 부분에 설명된 네트워크 사이트 정의 참조). 네트워크 운영 팀과 함께 네트워크 지역을 확인하십시오.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>각 네트워크 지역에 중앙 사이트 연결

CAC를 사용 하려면 각 네트워크 지역에 대해 Lync Server 중앙 사이트가 정의 되어 있어야 합니다. 중앙 사이트는 해당 네트워크 지역 내의 다른 모든 사이트에 대해 네트워크 연결 상태가 최상이고 대역폭이 가장 빠른 것으로 선택됩니다. 앞의 네트워크 토폴로지 예에서는 3개의 네트워크 지역이 표시되며, 각 지역에는 CAC 결정을 관리하는 중앙 사이트가 있습니다. 앞의 예에서 적합한 연결은 다음 표에 표시되어 있습니다.

<div>


> [!NOTE]  
> 중앙 사이트가 반드시 네트워크 사이트에 해당 하는 것은 아닙니다. 이 설명서의 예에서는 시카고, London 및 베이징 라는 일부 중앙 사이트는 네트워크 사이트와 같은 이름을 공유 합니다. 그러나 중앙 사이트와 네트워크 사이트에 같은 이름이 공유 되는 경우에도 중앙 사이트는 Lync Server 토폴로지의 요소 이지만, 네트워크 사이트는 Lync Server 토폴로지가 있는 전체 네트워크의 일부입니다.



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>네트워크 지역, 중앙 사이트 및 네트워크 사이트

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>네트워크 지역</th>
<th>중앙 사이트</th>
<th>네트워크 사이트</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>북미</p></td>
<td><p>지사</p></td>
<td><p>지사</p>
<p>뉴욕</p>
<p>디트로이트</p>
<p>포틀랜드</p>
<p>리노</p>
<p>앨버커키</p></td>
</tr>
<tr class="even">
<td><p>슈팅</p></td>
<td><p>인</p></td>
<td><p>인</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>베이징</p></td>
<td><p>베이징</p>
<p>Manila</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>네트워크 사이트 확인

네트워크 사이트는 조직의 실제 장소(예: 사무실, 건물 또는 캠퍼스)가 있는 위치를 나타냅니다. LAN과 다른 사이트에 대한 WAN을 갖고 있는 실제 장소를 네트워크 사이트로 간주합니다. 조직의 모든 사무실을 조사하는 작업부터 시작합니다. 위의 토폴로지 예에서 북미 네트워크 지역은 뉴욕, 시카고, 디트로이트, 포틀랜드, 리노 및 앨버커키 네트워크 사이트로 구성됩니다.

모든 네트워크 사이트를 네트워크 지역과 연결해야 합니다. 네트워크 사이트에 제한된 WAN 링크가 있는지 여부에 따라 대역폭 정책이 네트워크 사이트에 연결됩니다. CAC 정책 및 이러한 정책을 사용하여 할당하는 대역폭에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 "대역폭 정책 정의"를 참조하십시오. CAC를 구성하려면 네트워크 사이트를 네트워크 지역과 연결한 다음 지정된 사이트 또는 지역 간의 대역폭 제한 연결 및 사이트와 지역 간의 WAN 연결에 적용할 대역폭 할당 정책을 만듭니다.

</div>

<div>

## <a name="identify-network-links"></a>네트워크 링크 확인

네트워크 링크는 서로 다른 지역 및 사이트를 연결하는 실제 WAN 연결을 나타냅니다. 위의 토폴로지 예에는 지역 간을 연결하는 두 개의 네트워크 링크, 지역과 사이트를 연결하는 다섯 개의 네트워크 링크 및 두 사이트를 연결하는 하나의 네트워크 링크가 있습니다.

두 개의 지역 링크는 북미와 EMEA, APAC와 EMEA를 연결하며, 각각 NA-EMEA-LINK와 EMEA-APAC-LINK로 표시되어 있습니다.

사이트 링크는 포틀랜드, 리노 및 앨버커키와 북미 지역을 연결하는 선, 마닐라와 APAC 지역을 연결하는 선, 그리고 콜로뉴와 EMEA 지역을 연결하는 선으로 표시되어 있습니다. 리노와 앨버커키 사이의 선은 이 두 사이트 간의 직접 네트워크 링크를 나타냅니다.

</div>

<div>

## <a name="define-bandwidth-policies"></a>대역폭 정책 정의

네트워크 운영 팀과 함께 조직의 WAN 링크를 통해 실시간 오디오 및 비디오 트래픽에 사용할 수 있는 WAN 대역폭을 확인합니다. 대역폭 정책은 일반적으로 대역폭 사용이 제한된 경우, 즉 오디오 및 비디오 형식에 할당될 수 있는 대역폭보다 많은 대역폭이 사용될 것으로 예상되는 경우 WAN 링크에 적용됩니다.

CAC *대역폭 정책*은 실시간 오디오 및 비디오 형식에 대해 예약할 수 있는 최대 대역폭을 정의합니다. CAC는 다른 트래픽의 대역폭을 제한하지 않기 때문에 대규모 파일 전송, 음악 스트리밍 등의 다른 데이터 트래픽이 네트워크 대역폭을 모두 사용하지 못하도록 방지할 수 없습니다.

CAC 대역폭 정책은 다음 중 일부 또는 전부를 정의할 수 있습니다.

  - 오디오에 할당되는 최대 총 대역폭

  - 비디오에 할당되는 최대 총 대역폭

  - 단일 음성 통화(세션)에 할당되는 최대 대역폭

  - 단일 화상 통화(세션)에 할당되는 최대 대역폭

<div>


> [!NOTE]  
> 모든 CAC 대역폭 값은 최대 <EM>단방향</EM> 대역폭 제한을 나타납니다.



</div>

<div>


> [!NOTE]  
> Lync Server 2013 음성 정책 기능을 사용 하면 사용자에 게 제공 되는 발신 전화에 대해 대역폭 정책 검사를 사용자에 게 다시 정의할 수 있습니다. 세션이 설정된 후에는 대역폭 소비가 정확하게 계산됩니다. 이 설정은 가급적 사용하지 않는 것이 좋습니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 만들기 및 Lync server 2013에서 pstn 사용 레코드 구성 및</A> <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync SERVER 2013에서 pstn 사용 레코드 구성</A> 를 참조 하십시오.



</div>

세션별 대역폭 사용량을 최적화하려면 사용할 오디오 및 비디오 코덱의 유형을 고려해야 합니다. 특히, 자주 사용할 것으로 예상되는 코덱에 대한 대역폭을 부족하게 할당하지 않아야 합니다. 반면, 미디어에서 많은 대역폭이 필요한 코덱을 사용하지 않도록 하려면 이러한 코덱을 사용할 수 없을 정도로 낮게 세션별 최대 대역폭을 설정해야 합니다. 오디오의 경우 일부 코덱은 일부 시나리오에 사용할 수 없습니다. 예:

  - Lync 끝점 간의 피어 투 피어 오디오 통화는 코덱의 대역폭과 우선 순위에 영향을 주는 경우 RTAudio (8kHz) 또는 RTAudio (16kHz)를 사용 합니다.

  - Lync 끝점과 A/V 회의 서비스 간의 전화 회의에서는 722 또는 Siren를 사용 합니다.

  - 공중 전화망 (PSTN)에 대 한 통화는 Lync 끝점에서 보내거나 온-g.711 또는 RTAudio (8kHz)를 사용 합니다.

다음 표는 세션별 최대 대역폭 설정을 최적화하는 데 유용합니다.

### <a name="bandwidth-utilization-by-codecs"></a>코덱별 대역폭 사용량

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>코덱</th>
<th>FEC(정방향 오류 정정)가 없는 대역폭 요구 사항</th>
<th>FEC(정방향 오류 정정)가 있는 대역폭 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio(8kHz)</p></td>
<td><p>49.8kbps</p></td>
<td><p>61.6kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio(16kHz)</p></td>
<td><p>67kbps</p></td>
<td><p>96kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57.6kbps</p></td>
<td><p>73.6kbps</p></td>
</tr>
<tr class="even">
<td><p>G.711</p></td>
<td><p>102kbps</p></td>
<td><p>166kbps</p></td>
</tr>
<tr class="odd">
<td><p>722</p></td>
<td><p>105.6kbps</p></td>
<td><p>169.6kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo(CIF 15fps)</p></td>
<td><p>260kbps</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo(VGA 30fps)</p></td>
<td><p>610kbps</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 대역폭 요구 사항에는 Ethernet II, IP, UDP(User Datagram Protocol), RTP(Real-time Transport Protocol) 및 SRTP(실시간 전송 프로토콜)에 대한 오버헤드가 고려되어 있으며, RTCP 오버헤드에 대한 10kbps도 포함되어 있습니다.



</div>

G.722.1 코덱과 Siren 코덱은 유사하지만 비트 전송률이 서로 다릅니다.

Lync Server 회의에 대 한 기본 코덱 인 722은 g.722.1 코덱과 및 Siren 코덱과 완전히 다릅니다.

다음과 같은 경우에는 Siren 코덱이 Lync Server에서 사용 됩니다.

  - 대역폭 정책이 너무 낮게 설정되어 G.722를 사용할 수 없는 경우

  - Communications Server 2007 또는 Communications Server 2007 R2 클라이언트가 Lync Server 회의 서비스에 연결 하는 경우 (해당 클라이언트는 722 코덱을 지원 하지 않음)

### <a name="bandwidth-utilization-by-scenario"></a>시나리오별 대역폭 사용량

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>시나리오</th>
<th>수량에 최적화된 대역폭 요구 사항(kbps)</th>
<th>균형 조정 모드에 적절한 대역폭 요구 사항(kbps)</th>
<th>품질에 최적화된 대역폭 요구 사항(kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>피어 투 피어 음성 통화</p></td>
<td><p>45kbps</p></td>
<td><p>62kbps</p></td>
<td><p>91kbps</p></td>
</tr>
<tr class="even">
<td><p>전화 회의</p></td>
<td><p>53kbps</p></td>
<td><p>101kbps</p></td>
<td><p>165kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 통화 (Lync 2013와 PSTN 게이트웨이 간, 미디어 바이패스 포함)</p></td>
<td><p>97kbps</p></td>
<td><p>97kbps</p></td>
<td><p>161kbps</p></td>
</tr>
<tr class="even">
<td><p>PSTN 통화 (Lync 2013 및 중재 서버 간, 미디어 바이패스 제외)</p></td>
<td><p>45kbps</p></td>
<td><p>97kbps</p></td>
<td><p>161kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 통화 (중재 서버와 PSTN 게이트웨이 간, 미디어 바이패스 제외)</p></td>
<td><p>97kbps</p></td>
<td><p>97kbps</p></td>
<td><p>161kbps</p></td>
</tr>
<tr class="even">
<td><p>Lync-Polycom 통화</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>IP 서브넷 확인

각 네트워크 사이트에 대해 네트워크 관리자와 함께 각 네트워크 사이트에 지정된 IP 서브넷을 확인해야 합니다. 네트워크 관리자가 네트워크 지역 및 네트워크 사이트에 대한 IP 서브넷을 이미 구성한 경우에는 작업이 훨씬 간편합니다.

위의 예에서 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23 및 172.29.81.0/24 IP 서브넷이 지정되어 있습니다. 주로 디트로이트에서 근무하는 Bob이 교육을 받기 위해 뉴욕 사무실에 출장을 왔다고 가정해 보겠습니다. Bob이 컴퓨터를 켜고 네트워크에 연결하면 컴퓨터에서 뉴욕에 예약된 네 개 범위 중 하나의 IP 주소(예: 172.29.80.103)를 가져옵니다.

<div>


> [!WARNING]  
> 서버에서 네트워크를 구성하는 동안 지정된 IP 서브넷을 미디어 바이패스에 사용하려면 IP 서브넷이 클라이언트 컴퓨터에서 제공한 형식과 일치해야 합니다. Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크와 함께 IP 주소를 마스크 합니다. 각 클라이언트에 연결된 바이패스 ID를 확인할 때 등록자는 각 네트워크 사이트에 연결된 IP 서브넷 목록이 클라이언트에서 제공한 서브넷과 정확히 일치하는지 비교합니다. 따라서 서버에서 네트워크를 구성할 때 가상 서브넷 대신 실제 서브넷을 입력해야 합니다. 미디어 바이패스가 아니라 통화 허용 제어를 배포한 경우에는 가상 서브넷을 구성한 경우에도 통화 허용 제어가 제대로 작동합니다.<BR>예를 들어 클라이언트에서 ip 서브넷 마스크가 255.255.255.0 인 172.29.81.57의 IP 주소를 사용 하는 컴퓨터에 로그인 하는 경우 Lync 2013는 서브넷 172.29.81.0와 연결 된 바이패스 ID를 요청 합니다. 서브넷이 172.29.0.0/16으로 정의 된 경우 클라이언트가 가상 서브넷에 속해 있더라도 등록자는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에 해당 등록자는이 일치를 고려 하지 않습니다. 따라서 관리자는 네트워크 구성 중에 서브넷으로 또는 DHCP에 의해 프로 비전 되는 Lync 클라이언트에서 제공 하는 대로 서브넷을 정확히 입력 해야 합니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

