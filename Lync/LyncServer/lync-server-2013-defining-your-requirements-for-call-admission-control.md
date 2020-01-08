---
title: 'Lync Server 2013: 통화 허용 제어 서비스에 대한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-28_

CAC (통화 허용 제어)에 대 한 계획에는 엔터프라이즈 네트워크 토폴로지에 대 한 자세한 정보가 필요 합니다. 통화 허용 제어 정책을 계획 하는 데 도움이 필요 하면 다음 단계를 따르세요.

1.  엔터프라이즈 네트워크 내에서 허브/백본 ( *네트워크 지역*이라고 함)를 식별 합니다.

2.  각 네트워크 지역 내의 사무실 또는 위치 ( *네트워크 사이트*라고 함)를 식별 합니다.

3.  네트워크 지역 모든 쌍 간의 네트워크 경로를 결정 합니다.

4.  각 WAN 링크의 대역폭 제한을 결정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 대역폭 제한은 WAN 링크에서 엔터프라이즈 음성 및 오디오/비디오 트래픽에 할당 되는 대역폭의 양을 나타냅니다. WAN 링크를 "대역폭 제한"으로 설명 하는 경우 WAN 링크에는 링크를 통해 예상 되는 최고 소통량 보다 낮은 대역폭 한도가 있습니다.

    
    </div>

5.  각 네트워크 사이트에 할당 된 IP 서브넷을 식별 합니다.

이러한 개념을 설명 하기 위해 다음 그림에 표시 된 네트워크 토폴로지 예를 사용 합니다.

**통화 허용 제어에 대 한 예제 토폴로지**

![Litware inc. 네트워크 토폴로지 예](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 네트워크 토폴로지 예")

<div>


> [!NOTE]  
> 모든 네트워크 사이트는 네트워크 지역과 연결 되어 있습니다. 예를 들어 포틀랜드, Reno, Albuquerque는 북미 지역에 포함 되어 있습니다. 이 그림에서는 대역폭 제한을 사용 하 여 CAC 정책이 적용 된 WAN 링크만 표시 됩니다. 시카고, 뉴욕 및 디트로이트의 네트워크 사이트는 대역폭이 제한 되지 않으므로 북미 지역 타원형 내에 표시 되므로 CAC 정책은 필요 하지 않습니다.



</div>

이 예제 토폴로지의 구성 요소에 대해서는 다음 섹션에서 설명 합니다. 대역폭 제한을 포함 하 여이 토폴로지가 계획 되는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집 예제](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)를 참조 하세요.

<div>

## <a name="identify-network-regions"></a>네트워크 지역 확인

네트워크 영역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.

네트워크 백본 또는 허브는 네트워크의 여러 부분을 상호 교환 하는 컴퓨터 네트워크 인프라의 일부 이며, 다양 한 Lan 또는 서브넷 간의 정보 교환을 위한 경로를 제공 합니다. 백본은 다양 한 네트워크를 소규모 위치에서 넓은 지역으로 묶을 수 있습니다. 일반적으로 백본 용량은 연결 하는 네트워크 보다 더 큽니다.

이 예제 토폴로지에는 북미, EMEA, APAC의 세 가지 네트워크 지역이 있습니다. 네트워크 지역에는 네트워크 사이트의 컬렉션이 포함 됩니다 (이 항목의 뒷부분에 나오는 네트워크 사이트의 정의 참조). 네트워크 운영 팀과 협력 하 여 네트워크 지역을 식별 합니다.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>각 네트워크 영역에 중앙 사이트 연결

CAC에서는 각 네트워크 지역에 대해 Lync Server 중앙 사이트가 정의 되어 있어야 합니다. 중앙 사이트는 최상의 네트워크 연결을 선택 하 고 해당 네트워크 지역 내의 다른 모든 사이트에 가장 높은 대역폭을 사용 합니다. 앞의 네트워크 토폴로지에 대 한 예는 각각 CAC 결정을 관리 하는 중앙 사이트를 포함 하는 세 개의 네트워크 지역을 표시 합니다. 앞의 예제에서 적절 한 연관은 다음 표에 나와 있습니다.

<div>


> [!NOTE]  
> 중앙 사이트는 네트워크 사이트에 해당 하지 않을 수 있습니다. 이 설명서의 예제에서 일부 중앙 사이트 (시카고, 런던, 베이징)는 네트워크 사이트와 같은 이름을 공유 합니다. 그러나 중앙 사이트와 네트워크 사이트에서 동일한 이름을 공유 하는 경우에도 중앙 사이트는 Lync Server 토폴로지의 요소 이지만, 네트워크 사이트는 Lync Server 토폴로지가 있는 전체 네트워크의 일부입니다.



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>네트워크 지역, 중앙 사이트, 네트워크 사이트

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
<td><p>시카고</p></td>
<td><p>시카고</p>
<p>뉴욕</p>
<p>디트로이트</p>
<p>지사</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>슈팅</p></td>
<td><p>시흥시</p></td>
<td><p>시흥시</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>베이징</p></td>
<td><p>베이징</p>
<p>마닐라</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>네트워크 사이트 확인

네트워크 사이트는 조직에 실제 장소 (예: 사무실, 건물 집합 또는 캠퍼스)가 있는 위치를 나타냅니다. LAN을 사용 하는 물리적인 장소 이며 다른 사이트에 대 한 WAN 연결이 네트워크 사이트로 간주 됩니다. 먼저 모든 조직의 사무실을 인벤토리 합니다. 이 예제 토폴로지에서 북미 네트워크 지역은 뉴욕, 시카고, 디트로이트, 포틀랜드, Reno, Albuquerque 네트워크 사이트로 구성 됩니다.

모든 네트워크 사이트를 네트워크 지역에 연결 해야 합니다. 네트워크 사이트에 제한 된 WAN 링크가 있는지 여부에 따라 대역폭 정책이 네트워크 사이트와 연결 됩니다. CAC 정책 및이를 사용 하 여 할당 하는 대역폭에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "대역폭 정책 정의"를 참조 하세요. CAC를 구성 하려면 네트워크 사이트를 네트워크 영역과 연결 하 고, 해당 사이트 또는 지역과 사이트와 지역 간의 WAN 연결 간에 대역폭 제한 된 연결에 적용 되도록 대역폭 할당 정책을 만듭니다.

</div>

<div>

## <a name="identify-network-links"></a>네트워크 링크 식별

네트워크 링크는 다른 지역과 사이트를 연결 하는 실제 WAN에 대 한 연결을 나타냅니다. 이 예제 토폴로지에서는 두 개의 지역 네트워크 링크, 지역과 사이트 간 다섯 개의 네트워크 연결, 두 사이트 간의 네트워크 링크가 있습니다.

두 지역 링크는 NA-EMEA-링크로 표시 되 고, EMEA-APAC 링크로 표시 되는 APAC와 EMEA 사이에 있는 북미와 EMEA 사이에 있습니다.

사이트 링크는 포틀랜드, Reno, Albuquerque를 북미 지역에 연결 하 고, APAC 지역으로 마닐라 하 고, EMEA 지역으로 Cologne 의해 표시 됩니다. Reno와 Albuquerque 사이의 회선은 두 사이트 간의 직접 네트워크 링크를 보여 줍니다.

</div>

<div>

## <a name="define-bandwidth-policies"></a>대역폭 정책 정의

네트워크 운영 팀과 협력 하 여 조직의 WAN 연결에서 실시간 오디오 및 비디오 트래픽에 사용할 수 있는 WAN 대역폭의 양을 결정 합니다. 대역폭 정책은 대역폭 사용량이 제한 된 경우 일반적으로 WAN 링크에 적용 됩니다. 즉, 오디오 및 비디오 형식을 할당할 수 있는 대역폭 보다 더 많은 것으로 예상 되는 경우

CAC *대역폭 정책은* 실시간 오디오 및 비디오 형식을 예약할 수 있는 최대 대역폭을 정의 합니다. CAC는 다른 트래픽에 대 한 대역폭을 제한 하지 않으므로 모든 네트워크 대역폭을 사용 하 여 대용량 파일 전송, 음악 스트리밍 등의 다른 데이터 트래픽을 방지할 수 없습니다.

CAC 대역폭 정책은 다음 중 일부 또는 모두를 정의할 수 있습니다.

  - 오디오에 대해 할당 된 최대 총 대역폭입니다.

  - 비디오에 대해 할당 된 최대 총 대역폭입니다.

  - 단일 오디오 통화 (세션)에 할당 된 최대 대역폭.

  - 단일 비디오 통화 (세션)에 대해 할당 된 최대 대역폭입니다.

<div>


> [!NOTE]  
> 모든 CAC 대역폭 값은 최대 <EM>단방향</EM> 대역폭 제한을 나타냅니다.



</div>

<div>


> [!NOTE]  
> Lync Server 2013 음성 정책 기능은 사용자에 게 들어오는 호출에 대 한 대역폭 정책 검사를 재정의 하는 기능을 제공 합니다 (사용자가 설정한 발신 통화에는 해당 되지 않음). 세션을 설정한 후에는 대역폭 소비가 정확 하 게 고려 됩니다. 이 설정은 가끔씩만 사용 해야 합니다. 자세한 내용은 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 만들기 및 Lync server 2013에서 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 수정 및 lync SERVER 2013의 pstn 사용 레코드 구성을</A> 참조 하세요.



</div>

세션 별로 대역폭 사용률을 최적화 하려면 사용할 오디오 및 비디오 코덱 유형을 고려해 야 합니다. 특히 자주 사용 하는 것으로 예상 되는 코덱에 충분 한 대역폭을 할당 하지 않도록 합니다. 반대로 더 많은 대역폭이 필요한 코덱을 사용 하 여 미디어를 방지 하려면 세션당 최대 대역폭을 설정 하 여 이러한 사용을 막을 수 있습니다. 오디오의 경우 모든 코덱에 모든 코덱이 제공 되는 것은 아닙니다. 예를 들면 다음과 같습니다.

  - Lync 끝점 간의 피어 투 피어 오디오 통화는 코덱의 대역폭과 우선 순위에 영향을 주는 경우 RTAudio (8kHz) 또는 RTAudio (16kHz)를 사용 합니다.

  - Lync 끝점과 A/V 회의 서비스 간의 컨퍼런스 통화는 722 또는 Siren 중 하나를 사용 합니다.

  - Lync 끝점에서 보내거나 받을 때 PSTN (공개 통신 네트워크)에 대 한 통화는 711 또는 RTAudio (8kHz)를 사용 합니다.

다음 표를 사용 하 여 세션당 최대 대역폭 설정을 최적화 해 보세요.

### <a name="bandwidth-utilization-by-codecs"></a>코덱에의 한 대역폭 이용률

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>코덱이나</th>
<th>FEC (정방향 오류 수정 없음)의 대역폭 요구 사항</th>
<th>FEC (정방향 오류 정정)의 대역폭 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49.8 kbps</p></td>
<td><p>61.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>사이렌</p></td>
<td><p>57.6 kbps</p></td>
<td><p>73.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>722</p></td>
<td><p>105.6 kbps</p></td>
<td><p>169.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 대역폭 요구 사항은 이더넷 II, IP, 사용자 데이터 그램 프로토콜 (UDP), RTP (실시간 전송 프로토콜), SRTP (보안 실시간 전송 프로토콜)에 대 한 계정 오버 헤드를 차지 합니다. 또한 RTCP 오버 헤드에는 10mbps가 포함 되어 있습니다.



</div>

722.1 및 Siren 코덱은 비슷하지만 다양 한 비트 전송률을 제공 합니다.

722는 Lync Server 회의의 기본 코덱으로 722.1 및 Siren 코덱과 완전히 다릅니다.

다음과 같은 경우에는 Lync Server에서 Siren 코덱이 사용 됩니다.

  - 대역폭 정책이 722에 대해 너무 낮게 설정 된 경우 사용 됩니다.

  - 통신 서버 2007 또는 통신 서버 2007 R2 클라이언트가 Lync Server 회의 서비스에 연결 되는 경우 (해당 클라이언트는 722 코덱을 지원 하지 않기 때문)

### <a name="bandwidth-utilization-by-scenario"></a>시나리오에의 한 대역폭 사용률

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
<th>용량에 최적화 된 대역폭 요구 사항 (kbps)</th>
<th>균형 모드 (kbps) 대역폭 요구 사항</th>
<th>음질에 맞게 최적화 된 대역폭 요구 사항 (kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>피어 투 피어 오디오 통화</p></td>
<td><p>45 kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>컨퍼런스 통화</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 통화 (Lync 2013 및 PSTN 게이트웨이 간, 미디어 바이패스 사용)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>PSTN 통화 (Lync 2013 및 중재 서버 간, 미디어 바이패스 없음)</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 통화 (중재 서버와 PSTN 게이트웨이 간의 미디어 바이패스 없음)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
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

각 네트워크 사이트에 대해 네트워크 관리자와 협력 하 여 각 네트워크 사이트에 할당 되는 IP 서브넷을 확인 해야 합니다. 네트워크 관리자가 이미 네트워크 지역 및 네트워크 사이트로 IP 서브넷을 구성한 경우에는 작업이 대폭 간소화 됩니다.

이 예제에서 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24의 IP 서브넷이 지정 됩니다. 일반적으로 디트로이트에서 작동 하는 Bob이 뉴욕 사무실로 이동 하 여 교육을 할 수 있다고 가정 합니다. 컴퓨터를 설정 하 고 네트워크에 연결 하면 컴퓨터는 뉴욕에 대해 예약 된 4 개 범위 (예: 172.29.80.103) 중 하나에서 IP 주소를 가져옵니다.

<div>


> [!WARNING]  
> 서버에서 네트워크 구성 중에 지정 된 IP 서브넷은 미디어 바이패스에 따라 올바르게 사용 되기 위해 클라이언트 컴퓨터에서 제공 하는 형식과 일치 해야 합니다. Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크를 사용 하 여 IP 주소를 마스크 합니다. 각 클라이언트와 연결 된 우회 ID를 결정할 때, 레지스트라는 정확히 일치 하는 클라이언트가 제공 하는 서브넷에 대해 각 네트워크 사이트와 연결 된 IP 서브넷 목록을 비교 합니다. 이러한 이유로, 서버에서 네트워크를 구성 하는 동안 입력 된 서브넷이 가상 서브넷 대신 실제 서브넷이 되는 것이 중요 합니다. (통화 허용 제어를 배포 하지만 미디어 바이패스는 아닌 경우 가상 서브넷을 구성한 경우에도 통화 허용 제어가 올바르게 작동 합니다.)<BR>예를 들어 클라이언트가 ip 서브넷 마스크가 255.255.255.0 인 172.29.81.57의 IP 주소를 사용 하 여 컴퓨터에 로그인 하는 경우 Lync 2013은 서브넷 172.29.81.0와 연결 된 우회 ID를 요청 합니다. 서브넷이 172.29.0.0/16으로 정의 된 경우에는 클라이언트가 가상 서브넷에 속해 있지만, 레지스트라는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에이에 대 한 일치가 고려 되지 않습니다. 따라서 관리자가 Lync 클라이언트에서 제공한 대로 서브넷을 정확히 입력 해야 합니다 (네트워크 구성 중에는 정적 또는 DHCP를 통해 서브넷으로 프로 비전 됨).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

