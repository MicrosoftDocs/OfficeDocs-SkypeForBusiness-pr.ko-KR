---
title: 'Lync Server 2013: 중앙 사이트 음성 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Lync Server 2013의 중앙 사이트 음성 복구 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-30_

전세계에 여러 사이트를 사용 하는 기업은 점점 늘어나고 있습니다. 중앙 사이트가 서비스를 사용 하지 않는 경우 긴급 한 비즈니스 작업을 수행 하는 능력, 응급 서비스, 지원 센터에 대 한 액세스를 유지 관리 하 고 엔터프라이즈 음성 복원 솔루션에 필수적입니다. 중앙 사이트를 사용할 수 없게 되 면 다음 조건을 충족 해야 합니다.

  - 음성 장애 조치 (failover)를 제공 해야 합니다.

  - 일반적으로 중앙 사이트의 프런트 엔드 풀을 사용 하 여 등록 하는 사용자는 대체 프런트 엔드 풀을 사용 하 여 등록할 수 있어야 합니다. 각 중앙 사이트의 디렉터 풀 또는 프런트 엔드 풀로 확인 되는 여러 DNS SRV 레코드를 만들어이 작업을 수행할 수 있습니다. 해당 중앙 사이트에서 제공 하는 사용자가 다른 SRV 레코드의 해당 디렉터 및 프런트 엔드 풀을 가져올 수 있도록 SRV 레코드의 우선 순위와 가중치를 조정할 수 있습니다.

  - 다른 사이트에 위치한 사용자와의 통화는 PSTN으로 경로를 전환 해야 합니다.

이 항목에서는 중앙 사이트 음성 복구를 보호 하기 위한 권장 해결 방법에 대해 설명 합니다.

<div>

## <a name="architecture-and-topology"></a>아키텍처 및 토폴로지

중앙 사이트의 음성 복원 계획에는 음성 장애 조치를 사용 하는 Lync Server 2013 등록 기관에서 실행 하는 중앙 역할에 대 한 기본적인 이해가 필요 합니다. Lync Server 등록자는 클라이언트 등록과 인증을 가능 하 게 하 고 라우팅 서비스를 제공 하는 서버 역할을 합니다. 이는 스탠더드 버전 서버, 프런트 엔드 서버, 디렉터 또는 Survivable Branch 기기의 다른 구성 요소와 함께 존재 합니다. 등록자 풀은 프런트 엔드 풀에서 실행 되는 등록자 서비스로 구성 되며 같은 사이트에 있습니다. 프런트 엔드 풀은 부하 분산 되어야 합니다. DNS 부하 분산을 권장 하지만 하드웨어 로드 균형 조정을 허용 합니다. Lync 클라이언트는 다음 검색 메커니즘을 통해 프런트 엔드 풀을 검색 합니다.

1.  DNS SRV 레코드

2.  자동 검색 웹 서비스 (Lync Server 2013의 새로 만들기)

3.  DHCP 옵션 120

Lync 클라이언트가 프런트 엔드 풀에 연결 되 면 부하 분산 장치가 풀의 프런트 엔드 서버 중 하나로 리디렉션됩니다. 그러면 프런트 엔드 서버는 해당 클라이언트를 풀의 기본 등록 기관으로 리디렉션합니다.

Enterprise Voice에 대해 설정 된 각 사용자는 해당 사용자의 기본 등록자 풀이 되는 특정 등록자 풀에 할당 됩니다. 특정 사이트에서 수백 또는 수천 명의 사용자가 일반적으로 단일 기본 등록자 풀을 공유 합니다. 현재 상태, 회의 또는 장애 조치를 위해 중앙 사이트를 사용 하는 지점 사이트 사용자가 중앙 사이트 리소스를 사용할 수 있도록 하려면 사용자가 중앙 사이트에 등록 된 것 처럼 각 지점 사이트 사용자를 고려 하는 것이 좋습니다. 현재 Survivable Branch 기기를 사용 하 여 등록 된 사용자를 포함 하 여 지점 사이트 사용자 수에는 제한이 없습니다.

중앙 사이트 장애가 발생 하는 경우에 음성 복원을 보장 하려면 기본 등록자 풀에는 다른 사이트에 있는 하나의 지정 된 백업 등록자 풀이 있어야 합니다. 토폴로지 작성기 복원 설정을 사용 하 여 백업을 구성할 수 있습니다. 두 사이트 간에 탄력적 WAN 연결이 있는 것으로 가정 하면, 기본 등록자 풀을 더 이상 사용할 수 없는 사용자는 자동으로 백업 등록자 풀로 리디렉션됩니다.

다음 단계에서는 클라이언트 검색 및 등록 프로세스에 대해 설명 합니다.

1.  클라이언트가 DNS SRV 레코드를 통해 Lync Server를 검색 합니다. Lync 서버 2013에서 dns srv 레코드를 DNS SRV 쿼리에 대해 둘 이상의 FQDN을 반환 하도록 구성할 수 있습니다. 예를 들어 enterprise Contoso에 세 개의 중앙 사이트 (북미, 유럽, 아시아 태평양) 및 각 중앙 사이트의 디렉터 풀이 있는 경우 DNS SRV 레코드는 각각의 세 위치에서 디렉터 풀 Fqdn을 가리킬 수 있습니다. 위치 중 하나에 디렉터 풀을 사용할 수 있는 동안에는 클라이언트가 첫 번째 홉 Lync 서버에 연결할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 디렉터 풀을 사용 하는 것은 선택 사항입니다. 대신 프런트 엔드 풀을 사용할 수 있습니다.

    
    </div>

2.  디렉터 풀은 Lync 클라이언트에 사용자의 기본 등록자 풀 및 백업 등록자 풀에 대해 알립니다.

3.  Lync 클라이언트는 먼저 사용자의 기본 등록자 풀에 연결 하려고 시도 합니다. 기본 등록자 풀을 사용할 수 있는 경우에는 등록 기관에이 등록이 적용 됩니다. 기본 등록자 풀을 사용할 수 없는 경우 Lync 클라이언트는 백업 등록자 풀에 연결을 시도 합니다. 백업 등록자 풀을 사용할 수 있고 사용자의 기본 등록자 풀을 사용할 수 없는 것으로 확인 된 경우 (예를 들어, 지정 된 장애 조치 간격에 하트 비트 부족 한 경우) 백업 등록자 풀이 사용자의 등록을 수락 합니다. 백업 등록자는 기본 등록 기관을 다시 사용할 수 있다는 것을 감지 하면 백업 등록자 풀이 장애 조치 Lync 클라이언트를 기본 풀로 리디렉션합니다.

다음 그림은 중앙 사이트 복구를 보장 하기 위해 권장 되는 토폴로지를 보여줍니다. 두 사이트는 회복성 있는 WAN 링크로 연결 되어 있습니다. 중앙 사이트를 사용할 수 없게 되 면 해당 풀에 할당 된 사용자가 등록을 위해 백업 사이트로 리디렉션됩니다.

**중앙 사이트 음성 복원에 권장 되는 토폴로지**

중앙 사이트의 ![중앙 사이트 음성 resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "토폴로지 음성 resliency") 토폴로지

</div>

<div>

## <a name="requirements-and-recommendations"></a>요구 사항 및 제안

다음은 대부분의 조직에 적합 한 중앙 사이트 음성 복원의 구현에 대 한 다음과 같은 요구 사항과 권장 사항입니다.

  - 기본 및 백업 등록자 풀이 상주 하는 사이트는 회복성 있는 WAN 링크로 연결 되어야 합니다.

  - 각 중앙 사이트에는 하나 이상의 등록 기관으로 구성 된 등록자 풀이 포함 되어 있어야 합니다.

  - 각 등록자 풀은 DNS 부하 분산, 하드웨어 부하 분산 또는 둘 다를 사용 하 여 로드 균형을 유지 해야 합니다. 부하 분산 구성을 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)을 참조 하세요.

  - 각 사용자는 Lync Server Management Shell **집합-CsUser** Cmdlet 또는 Lync server 제어판을 사용 하 여 기본 등록자 풀에 할당 해야 합니다.

  - 기본 등록자 풀에는 다른 중앙 사이트에 있는 단일 백업 등록자 풀이 있어야 합니다.

  - 기본 등록자 풀은 백업 등록자 풀로 장애 조치 (failback)로 구성 되어야 합니다. 기본적으로 기본 등록자는 300 초 간격으로 백업 등록자 풀로 장애 조치 (fail over) 하도록 설정 됩니다. Lync Server 2013 토폴로지 작성기를 사용 하 여이 간격을 변경할 수 있습니다.

  - 계획 설명서의 "[Lync Server 2013에서 장애 조치 (failover) 경로 구성](lync-server-2013-configuring-a-failover-route.md)" 항목에 설명 된 대로 장애 조치 경로를 구성 합니다. 경로를 구성할 때 기본 경로에 지정 된 게이트웨이에서 다른 사이트에 있는 게이트웨이를 지정 합니다.

  - 중앙 사이트에 주 관리 서버와 오랜 시간 동안 사이트를 사용할 수 있는 경우 백업 사이트에 관리 도구를 다시 설치 해야 합니다. 그렇지 않으면 어떠한 관리 설정도 변경할 수 없게 됩니다.

</div>

<div>

## <a name="dependencies"></a>항목

Lync Server는 다음 인프라 및 소프트웨어 구성 요소에 의존 하 여 음성 복원을 보장 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>요소가</strong></p></td>
<td><p><strong>작동</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>서버-서버 및 서버 클라이언트 연결에 대 한 SRV 레코드 및 레코드 확인</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 및 EWS (Exchange Web Services)</p></td>
<td><p>연락처 저장소 일정 데이터</p></td>
</tr>
<tr class="even">
<td><p>Exchange 통합 메시징 및 Exchange 웹 서비스</p></td>
<td><p>통화 기록, 음성 메일 목록, 음성 메일</p></td>
</tr>
<tr class="odd">
<td><p>DHCP 옵션 120</p></td>
<td><p>DNS SRV를 사용할 수 없는 경우 클라이언트는 DHCP 옵션 120을 사용 하 여 등록자를 검색 하려고 시도 합니다. 이 작업을 수행 하려면 DHCP 서버를 구성 하거나 Lync Server 2013 DHCP를 사용 하도록 설정 해야 합니다. 자세한 내용은 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013의 지점 사이트 복원 요구 사항</a> 에 대 한 지점 사이트 복구의 하드웨어 및 소프트웨어 요구 사항 섹션을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Survivable 음성 기능

앞의 요구 사항 및 권장 사항이 구현 된 경우 백업 등록자 풀에서 다음 음성 기능을 제공 합니다.

  - 아웃 바운드 PSTN 통화

  - 전화 통신 서비스 공급자가 백업 사이트에 장애 조치할 수 있는 기능을 지 원하는 경우의 인바운드 PSTN 통화

  - 동일한 사이트와 두 개의 다른 사이트 간 사용자 간 엔터프라이즈 통화

  - 통화 대기, 검색, 전송을 포함 한 기본 통화 처리

  - 동일한 사이트의 사용자 간에 양방향 인스턴트 메시지 및 오디오 및 비디오 공유

  - 착신 통화 전환, 끝점의 동시 연결, 위임, 팀 호출 서비스 등 두 당사자가 위임을 호출할 때만 또는 모든 팀 구성원이 같은 사이트에서 구성 된 경우에만 가능 합니다.

  - 기존 전화 및 클라이언트가 계속 작동 합니다.

  - CDR(통화 정보 기록)

  - 인증 및 권한 부여

구성 방법에 따라, 주요 중앙 사이트의 서비스가 종료 될 때 다음 음성 기능이 작동 하지 않을 수 있습니다.

  - 음성 메일 입금 및 검색
    
    기본 중앙 사이트의 서비스가 종료 될 때 Exchange UM을 사용할 수 있게 하려면 다음 중 하나를 수행 해야 합니다.
    
      - 중앙 사이트의 Exchange UM 서버에서 다른 사이트의 Exchange UM 서버 백업을 가리키도록 DNS SRV 레코드를 변경 합니다.
    
      - 중앙 사이트와 백업 사이트 모두에 Exchange UM 서버를 포함 하도록 각 사용자의 Exchange UM 다이얼 플랜을 구성 하 되, 백업 Exchange UM 서버는 비활성으로 지정 합니다. 기본 사이트를 사용할 수 없게 되 면 Exchange 관리자가 백업 사이트에서 Exchange UM 서버를 사용으로 표시 해야 합니다.
    
    앞에서 설명한 해결 방법을 모두 사용할 수 없는 경우에는 중앙 사이트를 사용할 수 없게 되는 경우 Exchange UM을 사용 하지 못할 수 있습니다.

  - 모든 유형의 회의
    
    백업 사이트로 장애 조치를 수행한 사용자는 해당 풀을 사용할 수 있지만 더 이상 사용할 수 없는 기본 풀에서 전화를 만들거나 호스트할 수 없는 이끌이를 통해 만들어지거나 호스팅되는 회의에 참가할 수 있습니다. 마찬가지로, 다른 사용자는 영향을 받는 사용자의 기본 풀에서 호스트 되는 회의에 참가할 수 없습니다.

기본 중앙 사이트가 서비스를 이용 하지 않는 경우 다음 음성 기능이 작동 하지 않습니다.

  - 컨퍼런스 자동 전화 교환

  - 현재 상태 및 DND 기반 라우팅

  - 착신 전환 설정 업데이트

  - 응답 그룹 서비스 및 통화 공원

  - 새 전화 및 클라이언트 프로 비전

  - 주소록 웹 검색

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

