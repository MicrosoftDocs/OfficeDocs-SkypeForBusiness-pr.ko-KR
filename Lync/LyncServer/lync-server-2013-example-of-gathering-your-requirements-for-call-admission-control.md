---
title: 통화 허용 제어에 대 한 요구 사항을 수집 하는 예제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345f5d7e41dd9da3e6d68c59ce9656d3052c57b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>예: Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

이 예제에서는 호출 허용 제어 (CAC)를 계획 하 고 구현 하는 방법을 보여 줍니다. 상위 수준에서이는 다음 활동으로 구성 됩니다.

1.  모든 네트워크 허브 및 백본 ( *네트워크 지역*이라고 함)을 식별 합니다.

2.  각 네트워크 지역에 대해 CAC를 관리 하는 Lync Server 중앙 사이트를 식별 합니다.

3.  각 네트워크 영역에 연결 된 *네트워크 사이트* 를 식별 하 고 정의 합니다.

4.  WAN에 연결 된 각 네트워크 사이트에 대 한 대역폭이 제한 되는 경우 WAN 연결의 대역폭 용량과 네트워크 관리자가 Lync Server 미디어 트래픽에 대해 설정한 대역폭 제한에 대해 설명 합니다 (해당 하는 경우). WAN 연결이 대역폭이 제한 되지 않는 사이트는 포함할 필요가 없습니다.

5.  네트워크의 각 서브넷을 네트워크 사이트와 연결 합니다.

6.  네트워크 지역 간 링크를 매핑합니다. 각 링크에 대해 네트워크 관리자가 Lync Server 미디어 트래픽에 설정한 대역폭 용량과 제한 사항에 대해 설명 합니다.

7.  네트워크 지역의 모든 쌍 간의 경로를 정의 합니다.

<div>

## <a name="gather-the-required-information"></a>필요한 정보 수집

통화 허용 제어를 준비 하려면 다음 단계에서 설명 하는 정보를 수집 합니다.

1.  네트워크 지역을 식별 합니다. 네트워크 영역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.
    
    네트워크 백본 또는 네트워크 허브는 여러 네트워크 조각을 상호 관련 시키는 컴퓨터 네트워크 인프라의 일부 이며, 다양 한 Lan 또는 서브넷 간의 정보 교환 경로를 제공 합니다. 백본은 다양 한 네트워크를 소규모 위치에서 넓은 지역으로 묶을 수 있습니다. 일반적으로 백본 용량이 연결 된 네트워크 보다 큽니다.
    
    이 예제 토폴로지에는 북미, EMEA, APAC의 세 가지 네트워크 지역이 있습니다. 네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다. 네트워크 관리자와 협력 하 여 엔터프라이즈의 네트워크 지역을 정의 합니다.

2.  각 네트워크 영역의 연결 된 중앙 사이트를 식별 합니다. 중앙 사이트는 하나 이상의 프런트 엔드 서버를 포함 하며, 네트워크 지역의 WAN 연결을 통해 전달 되는 모든 미디어 트래픽에 대해 CAC를 관리 하는 Lync Server 배포입니다.
    
    **세 개의 네트워크 지역으로 구분 된 엔터프라이즈 네트워크 예제**
    
    ![네트워크 지역이 3개인 네트워크 토폴로지 예제](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "네트워크 지역이 3개인 네트워크 토폴로지 예제")  
    
    <div>
    

    > [!NOTE]
    > MPLS (멀티 프로토콜 레이블 전환) 네트워크는 각 지리적 위치에 해당 하는 네트워크 사이트가 있는 네트워크 영역으로 표시 되어야 합니다. 자세한 내용은 계획 설명서의 "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Lync Server 2013를 사용 하 여 MPLS 네트워크의 허용 제어에 전화 걸기</A>" 항목을 참조 하세요.

    
    </div>
    
    앞의 예제 네트워크 토폴로지에는 세 개의 네트워크 영역이 있으며, 각 영역에는 CAC를 관리 하는 Lync Server 중앙 사이트가 있습니다. 네트워크 지역에 적절 한 중앙 사이트가 지역 주변에서 선택 됩니다. 네트워크 영역 내에서 미디어 소통량이 가장 오래 지속 되므로 지리적 위치에의 한 소유권은 다른 중앙 사이트를 사용할 수 없게 되는 경우에도 계속 작동 합니다.
    
    이 예제에서 시카고 라는 Lync Server 배포는 북미 지역에 대 한 중앙 사이트입니다.
    
    북미 지역에 있는 모든 Lync 사용자는 시카고 배포의 서버에 있습니다. 다음 표에는 세 가지 네트워크 지역 모두에 대 한 중앙 사이트가 나와 있습니다.
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>네트워크 지역 및 연결 된 중앙 사이트
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>네트워크 지역</th>
    <th>중앙 사이트</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>북미</p></td>
    <td><p>시카고</p></td>
    </tr>
    <tr class="even">
    <td><p>슈팅</p></td>
    <td><p>시흥시</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>베이징</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > Lync Server 토폴로지에 따라 동일한 중앙 사이트를 여러 네트워크 지역에 할당할 수 있습니다.

    
    </div>

3.  각 네트워크 지역에 대해 WAN 연결이 대역폭이 제한 되지 않은 모든 네트워크 사이트 (사무실 또는 장소)를 식별 합니다. 이러한 사이트는 대역폭이 제한 되지 않으므로 CAC 대역폭 정책을 적용할 필요가 없습니다.
    
    다음 표에 나와 있는 예제에서 세 개의 네트워크 사이트에는 뉴욕, 시카고, 디트로이트 대역폭 제한 WAN 연결이 없습니다.
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>WAN 대역폭에 의해 제한 되지 않는 네트워크 사이트
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>네트워크 사이트</th>
    <th>네트워크 지역</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>뉴욕</p></td>
    <td><p>북미</p></td>
    </tr>
    <tr class="even">
    <td><p>시카고</p></td>
    <td><p>북미</p></td>
    </tr>
    <tr class="odd">
    <td><p>디트로이트</p></td>
    <td><p>북미</p></td>
    </tr>
    </tbody>
    </table>


4.  각 네트워크 영역에 대해 대역폭 제한 WAN 링크를 통해 네트워크 지역에 연결 하는 모든 네트워크 사이트를 식별 합니다.
    
    오디오 및 비디오 품질을 보장 하기 위해 이러한 대역폭 제한 네트워크 사이트에는 네트워크 지역으로 또는이 지에서 미디어 (음성 또는 비디오) 트래픽을 제한 하는 Wan 모니터링 및 CAC 대역폭 정책이 있는 것이 좋습니다.
    
    다음 표에 표시 된 예제에는 WAN 대역폭 (포틀랜드, Reno 및 Albuquerque에 의해 제한 되는 세 가지 네트워크 사이트가 있습니다.
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>WAN 대역폭에 의해 제한 되는 네트워크 사이트
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>네트워크 사이트</th>
    <th>네트워크 지역</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>북미</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>북미</p></td>
    </tr>
    <tr class="odd">
    <td><p>지사</p></td>
    <td><p>북미</p></td>
    </tr>
    </tbody>
    </table>
    
    **CAC 네트워크 지역 북미, 대역폭 (시카고, 뉴욕, 디트로이트) 및 WAN 대역폭 (포틀랜드, Reno 및 Albuquerque)에 의해 제한 되는 세 개의 네트워크 사이트를 포함 하는 세 개의 네트워크 사이트**
    
    ![WAN 대역폭이 제한된 예제 네트워크 사이트](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN 대역폭이 제한된 예제 네트워크 사이트")  

5.  각 대역폭 제한 WAN 링크에 대해 다음을 결정 합니다.
    
      - 모든 동시 오디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다. 새 오디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.
    
      - 각 개별 오디오 세션에 대해 설정 하려는 대역폭 제한입니다. 기본 CAC 대역폭 제한은 175 kbps 이지만 관리자가 수정할 수 있습니다.
    
      - 모든 동시 비디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다. 새 비디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.
    
      - 각 개별 비디오 세션에 대해 설정 하려는 대역폭 제한 기본 CAC 대역폭 제한은 700 kbps 이지만 관리자가 수정할 수 있습니다.
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>WAN 대역폭 제약 조건 정보가 포함 되는 네트워크 사이트 (대역폭 (kbps))
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>네트워크 사이트</th>
    <th>네트워크 지역</th>
    <th>BW 제한</th>
    <th>오디오 제한</th>
    <th>오디오 세션 제한</th>
    <th>비디오 제한</th>
    <th>비디오 세션 제한</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>북미</p></td>
    <td><p>5,000</p></td>
    <td><p>2000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>북미</p></td>
    <td><p>1만</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>지사</p></td>
    <td><p>북미</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>뉴욕</p></td>
    <td><p>북미</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    </tr>
    <tr class="odd">
    <td><p>시카고</p></td>
    <td><p>북미</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    </tr>
    <tr class="even">
    <td><p>디트로이트</p></td>
    <td><p>북미</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    </tr>
    </tbody>
    </table>


6.  네트워크의 모든 서브넷에 대해 연결 된 네트워크 사이트를 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > 네트워크 사이트에 대역폭이 제한 되어 있지 않은 경우에도 네트워크의 모든 서브넷은 네트워크 사이트와 연결 되어 있어야 합니다. 이것은 call 허용 제어가 서브넷 정보를 사용 하 여 종점이 있는 네트워크 사이트를 결정 하기 때문입니다. 세션에서 두 당사자의 위치가 결정 되 면 통화 허용 제어에서 전화를 걸 충분 한 대역폭이 있는지 확인할 수 있습니다. 대역폭 한도가 없는 링크를 통해 세션이 설정 되 면 경고가 생성 됩니다.<BR>오디오/비디오에 지 서버를 배포 하는 경우 각 Edge 서버의 공용 IP 주소는 Edge 서버가 배포 된 네트워크 사이트와 연결 되어 있어야 합니다. A/V Edge 서버의 각 공용 IP 주소는 서브넷 마스크가 32 인 서브넷으로 네트워크 구성 설정에 추가 되어 있어야 합니다. 예를 들어, 시카고에/V Edge 서버를 배포 하는 경우 해당 서버의 각 외부 IP 주소에 대해 서브넷 마스크가 32 인 서브넷을 만들고 네트워크 사이트 시카고를 해당 서브넷과 연결 합니다. 공용 IP 주소에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">외부 A/V 방화벽 및 Lync Server 2013의 포트 요구 사항 결정</A> 을 참조 하세요.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 네트워크에는 있지만 서브넷에 연결 되지 않았거나 IP 주소가 포함 된 서브넷이 네트워크 사이트와 연결 되어 있지 않은 경우 KHI (키 상태 표시기) 경고가 발생 하는 것입니다. 이 알림은 8 시간 내에 두 번 이상 발생 하지 않습니다. 관련 경고 정보 및 예제는 다음과 같습니다.<BR><STRONG>원본:</STRONG> CS (대역폭 정책 서비스) (Core)<BR><STRONG>이벤트 번호:</STRONG> 36034<BR><STRONG>수준:</STRONG> 2<BR><STRONG>설명:</STRONG> 다음 IP 주소의 서브넷: &lt;ip 주소&gt; 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.<BR><STRONG>원인:</STRONG> 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에 없거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.<BR><STRONG>해결 방법:</STRONG> 앞의 IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.<BR>예를 들어 알림의 IP 주소 목록이 10.121.248.226 및 10.121.249.20를 지정 하는 경우 이러한 IP 주소가 서브넷과 연결 되어 있지 않거나 연결 된 서브넷이 네트워크 사이트에 속하지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당 하는 서브넷 이면 다음과 같이이 문제를 해결할 수 있습니다. 
    > <OL>
    > <LI>
    > <P>IP 주소 10.121.248.226이 10.121.248.0/24 서브넷 및 IP 주소 10.121.249.20와 연결 되어 있는지 확인 하 고 10.121.249.0/24 서브넷과 연결 된 것입니다.</P>
    > <LI>
    > <P>10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결 되어 있는지 확인 합니다.</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>네트워크 사이트 및 관련 서브넷 (kbps (대역폭))
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>네트워크 사이트</th>
    <th>네트워크 지역</th>
    <th>BW 제한</th>
    <th>오디오 제한</th>
    <th>오디오 세션 제한</th>
    <th>비디오 제한</th>
    <th>비디오 세션 제한</th>
    <th>네트</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>북미</p></td>
    <td><p>5,000</p></td>
    <td><p>2000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>북미</p></td>
    <td><p>1만</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>지사</p></td>
    <td><p>북미</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>뉴욕</p></td>
    <td><p>북미</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>시카고</p></td>
    <td><p>북미</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>디트로이트</p></td>
    <td><p>북미</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>(제한 없음)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  Lync Server 호출 허용 제어에서 네트워크 지역 간 연결을 *지역 링크*라고 합니다. 각 지역 링크에 대해 다음을 결정 합니다. 네트워크 사이트의 경우와 동일 합니다.
    
      - 모든 동시 오디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다. 새 오디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.
    
      - 각 개별 오디오 세션에 대해 설정 하려는 대역폭 제한입니다. 기본 CAC 대역폭 제한은 175 kbps 이지만 관리자가 수정할 수 있습니다.
    
      - 모든 동시 비디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다. 새 비디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.
    
      - 각 개별 비디오 세션에 대해 설정 하려는 대역폭 제한 기본 CAC 대역폭 제한은 700 kbps 이지만 관리자가 수정할 수 있습니다.
    
    **연결 된 대역폭 한도가 있는 네트워크 지역 링크**
    
    ![3개 지역 간의 제한 예제](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3개 지역 간의 제한 예제")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>지역 링크 대역폭 정보 (대역폭 (kbps))
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>지역 링크 이름</th>
    <th>첫 번째 지역</th>
    <th>두 번째 지역</th>
    <th>BW 제한</th>
    <th>오디오 제한</th>
    <th>오디오 세션 제한</th>
    <th>비디오 제한</th>
    <th>비디오 세션 제한</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-링크</p></td>
    <td><p>북미</p></td>
    <td><p>슈팅</p></td>
    <td><p>5만</p></td>
    <td><p>2만</p></td>
    <td><p>175</p></td>
    <td><p>14000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-링크</p></td>
    <td><p>슈팅</p></td>
    <td><p>APAC</p></td>
    <td><p>25000</p></td>
    <td><p>1만</p></td>
    <td><p>175</p></td>
    <td><p>7000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  네트워크 지역의 모든 쌍 간의 경로를 정의 합니다.
    
    <div>
    

    > [!NOTE]
    > 북미와 APAC 지역 간의 경로에는 직접 연결 하는 지역 링크가 없기 때문에 두 개의 링크가 필요 합니다.

    
    </div>
    
    ### <a name="region-routes"></a>지역 경로
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>지역 경로 이름</th>
    <th>첫 번째 지역</th>
    <th>두 번째 지역</th>
    <th>지역 링크</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-경로</p></td>
    <td><p>북미</p></td>
    <td><p>슈팅</p></td>
    <td><p>NA-EMEA-링크</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-경로</p></td>
    <td><p>슈팅</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-링크</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-경로</p></td>
    <td><p>북미</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-링크, EMEA-APAC-링크</p></td>
    </tr>
    </tbody>
    </table>


9.  단일 링크 ( *사이트 간* 링크)로 직접 연결 된 모든 네트워크 사이트 쌍에 대해 다음을 결정 합니다.
    
      - 모든 동시 오디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다. 새 오디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.
    
      - 각 개별 오디오 세션에 대해 설정 하려는 대역폭 제한입니다. 기본 CAC 대역폭 제한은 175 kbps 이지만 관리자가 수정할 수 있습니다.
    
      - 모든 동시 비디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다. 새 비디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.
    
      - 각 개별 비디오 세션에 대해 설정 하려는 대역폭 제한 기본 CAC 대역폭 제한은 700 kbps 이지만 관리자가 수정할 수 있습니다.
    
    **CAC 네트워크 지역 북미 Reno와 Albuquerque 사이의 사이트 간 링크에 대 한 대역폭 용량 및 대역폭 한계를 표시 합니다.**
    
    ![WAN 대역폭이 제한된 네트워크 사이트 예제](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN 대역폭이 제한된 네트워크 사이트 예제")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>두 네트워크 사이트 사이의 사이트 간 링크에 대 한 대역폭 정보 (kbps의 대역폭)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>사이트 간 링크 이름</th>
    <th>첫 번째 사이트</th>
    <th>두 번째 사이트</th>
    <th>BW 제한</th>
    <th>오디오 제한</th>
    <th>오디오 세션 제한</th>
    <th>비디오 제한</th>
    <th>비디오 세션 제한</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-사이트 링크</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>2만</p></td>
    <td><p>12000</p></td>
    <td><p>175</p></td>
    <td><p>5,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>다음 단계

필요한 정보를 수집한 후 Lync Server 관리 셸 또는 Lync Server 제어판을 사용 하 여 CAC 배포를 수행할 수 있습니다.

<div>


> [!NOTE]
> Lync Server 제어판을 사용 하 여 대부분의 네트워크 구성 작업을 수행할 수 있지만 서브넷 및 사이트 링크를 만들려면 Lync Server 관리 셸을 사용 해야 합니다. 자세한 내용은 <STRONG>새 CsNetworkSubnet</STRONG> Cmdlet 및 <STRONG>new CsNetworkIntersitePolicy</STRONG> Cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

