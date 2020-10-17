---
title: 'Lync Server 2013: 중앙 사이트 음성 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e81f314fd0746b5a3d47f1b17dfa8ab9380678c3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497735"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Lync Server 2013의 중앙 사이트 음성 복구 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-30_

점점 많은 기업에서 전 세계에 여러 사이트를 확산시키고 있습니다. 긴급 서비스 유지 관리, 지원 센터에 대 한 액세스 권한 및 중요 한 비즈니스 작업을 수행 하는 기능 (중앙 사이트의 서비스가 중단 된 경우)은 Enterprise Voice 복구 솔루션에 반드시 필요 합니다. 중앙 사이트가 사용할 수 없게 된 경우 다음 조건을 충족해야 합니다.

  - 음성 장애 조치가 제공되어야 합니다.

  - 일반적으로 중앙 사이트의 프런트 엔드 풀에 등록 하는 사용자는 대체 프런트 엔드 풀을 사용 하 여 등록할 수 있어야 합니다. 이렇게 하려면 각 중앙 사이트에서 디렉터 풀 또는 프런트 엔드 풀로 확인 되는 여러 DNS SRV 레코드를 만듭니다. 해당 중앙 사이트에서 처리 하는 사용자가 다른 SRV 레코드의 해당 디렉터 및 프런트 엔드 풀을 가져올 수 있도록 SRV 레코드의 우선 순위와 가중치를 조정할 수도 있습니다.

  - 다른 사이트에 있는 사용자와의 통화가 PSTN으로 다시 라우팅되어야 합니다.

이 항목에서는 중앙 사이트 음성 복구의 보안을 유지하는 권장 솔루션에 대해 설명합니다.

<div>

## <a name="architecture-and-topology"></a>아키텍처 및 토폴로지

중앙 사이트에서 음성 복구를 계획 하려면 음성 장애 조치 (failover)를 사용 하도록 설정 하는 경우 Lync Server 2013 등록자에서 실행 하는 중앙 역할에 대 한 기본적인 이해가 필요 합니다. Lync Server 등록자는 클라이언트 등록 및 인증을 가능 하 게 하 고 라우팅 서비스를 제공 하는 서버 역할입니다. 이는 Standard Edition server, 프런트 엔드 서버, 디렉터 또는 Sba (survivable Branch 기기의 다른 구성 요소와 함께 존재 합니다. 등록자 풀은 프런트 엔드 풀에서 실행 되며 동일한 사이트에 있는 등록자 서비스로 구성 됩니다. 프런트 엔드 풀의 부하를 분산 해야 합니다. DNS 부하 분산을 권장 하지만 하드웨어 부하 분산을 사용할 수 있습니다. Lync 클라이언트는 다음 검색 메커니즘을 통해 프런트 엔드 풀을 검색 합니다.

1.  DNS SRV 레코드

2.  자동 검색 웹 서비스 (Lync Server 2013의 새로운)

3.  DHCP 옵션 120

Lync 클라이언트가 프런트 엔드 풀에 연결 되 면 부하 분산 장치는 풀의 프런트 엔드 서버 중 하나로 리디렉션됩니다. 그런 다음 프런트 엔드 서버는 풀의 기본 등록 기관으로 클라이언트를 리디렉션합니다.

Enterprise Voice를 사용 하도록 설정 된 각 사용자가 특정 등록자 풀에 할당 되어 해당 사용자의 기본 등록자 풀이 됩니다. 지정된 사이트에서 일반적으로 수백 또는 수천 명의 사용자가 하나의 기본 등록자 풀을 공유합니다. 현재 상태, 회의 또는 장애 조치를 중앙 사이트에 의존하는 분기 사이트 사용자의 중앙 사이트 리소스 사용을 계산하려면 각 분기 사이트 사용자를 중앙 사이트에 등록된 사용자로 간주하는 것이 좋습니다. 현재 Sba (survivable 분기 기기에 등록 된 사용자를 포함 하 여 분기 사이트 사용자 수에 대 한 제한이 없습니다.

중앙 사이트 실패 시 음성 복구를 지원하려면 기본 등록자 풀의 지정된 단일 백업 등록자 풀이 다른 사이트에 있어야 합니다. 토폴로지 작성기 복구 설정을 사용 하 여 백업을 구성할 수 있습니다. 두 사이트 간에 복구 가능한 WAN 링크가 있는 경우 기본 등록자 풀을 더 이상 사용할 수 없는 사용자는 자동으로 백업 등록자 풀에 연결됩니다.

다음 단계에서는 클라이언트 검색 및 등록 프로세스에 대해 설명합니다.

1.  클라이언트에서 DNS SRV 레코드를 통해 Lync Server를 검색 합니다. Lync Server 2013에서는 dns srv 쿼리에 대해 둘 이상의 FQDN을 반환 하도록 DNS SRV 레코드를 구성할 수 있습니다. 예를 들어 Contoso라는 회사에 세 개의 중앙 사이트(북미, 유럽 및 아시아 태평양)가 있고 각 중앙 사이트에 디렉터 풀이 있는 경우 DNS SRV 레코드는 각 위치의 디렉터 풀 FQDN을 가리킬 수 있습니다. 위치 중 하나에 디렉터 풀을 사용할 수 있는 경우 클라이언트는 첫 번째 홉 Lync 서버에 연결할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 디렉터 풀을 사용 하는 것은 선택 사항입니다. 프런트 엔드 풀을 대신 사용할 수 있습니다.

    
    </div>

2.  디렉터 풀은 Lync 클라이언트에 사용자의 기본 등록자 풀 및 백업 등록자 풀에 대 한 정보를 알려 줍니다.

3.  Lync 클라이언트는 먼저 사용자의 기본 등록자 풀에 연결을 시도 합니다. 기본 등록자 풀을 사용할 수 있는 경우 등록자가 등록을 수락합니다. 기본 등록자 풀을 사용할 수 없는 경우 Lync 클라이언트는 백업 등록자 풀에 연결을 시도 합니다. 백업 등록자 풀을 사용할 수 있고 이 풀에서 사용자의 기본 등록자 풀을 사용할 수 없는 것으로 확인(지정된 장애 조치 간격에 대한 하트비트 부족 감지)한 경우 백업 등록자 풀이 사용자의 등록을 수락합니다. 백업 등록자는 기본 등록자를 다시 사용할 수 있는 것으로 감지 하면 백업 등록자 풀은 장애 조치 (failover) Lync 클라이언트를 기본 풀로 리디렉션합니다.

다음 그림에서는 중앙 사이트 복구를 지원하는 권장 토폴로지를 보여 줍니다. 두 사이트는 복구 가능한 WAN 링크로 연결됩니다. 중앙 사이트가 사용할 수 없게 된 경우 해당 풀에 지정된 사용자는 등록을 위해 백업 사이트로 연결됩니다.

**중앙 사이트 음성 복구를 위한 권장 토폴로지**

![중앙 사이트 음성 복구용 토폴로지 토폴로지](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "중앙 사이트 음성 복구용 토폴로지 토폴로지")

</div>

<div>

## <a name="requirements-and-recommendations"></a>요구 사항 및 권장 사항

다음은 대부분의 조직에 적절한 중앙 사이트 음성 복구 구현에 대한 요구 사항 및 권장 사항입니다.

  - 사이트의 기본 및 백업 등록자 풀이 복구 가능한 WAN 링크로 연결되어야 합니다.

  - 각 중앙 사이트에 하나 이상의 등록자로 구성된 등록자 풀이 있어야 합니다.

  - 각 등록자 풀은 DNS 부하 분산, 하드웨어 부하 분산 또는 둘 다를 사용 하 여 로드 균형을 조정 해야 합니다. 부하 분산 구성을 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.

  - 각 사용자는 Lync Server 관리 셸 **설정-CsUser** Cmdlet 또는 Lync server 제어판을 사용 하 여 기본 등록자 풀에 할당 해야 합니다.

  - 기본 등록자 풀의 단일 백업 등록자 풀이 다른 중앙 사이트에 있어야 합니다.

  - 기본 등록자 풀이 백업 등록자 풀로 장애 조치되도록 구성되어야 합니다. 기본적으로 기본 등록자는 300초 간격 후 백업 등록자 풀로 장애 조치되도록 설정됩니다. Lync Server 2013 토폴로지 작성기를 사용 하 여이 간격을 변경할 수 있습니다.

  - 계획 설명서의 "[Lync Server 2013에서 장애 조치 (failover) 경로 구성](lync-server-2013-configuring-a-failover-route.md)" 항목에 설명 된 대로 장애 조치 경로를 구성 합니다. 경로를 구성할 때 기본 경로에 지정된 게이트웨이에서 다른 사이트에 있는 게이트웨이를 지정합니다.

  - 중앙 사이트에 기본 관리 서버가 포함되고 사이트가 연장된 기간 동안 다운될 수 있는 경우 백업 사이트에 관리 도구를 다시 설치해야 합니다. 그러지 않으면 관리 설정을 변경할 수 없게 됩니다.

</div>

<div>

## <a name="dependencies"></a>의존

Lync Server는 다음 인프라 및 소프트웨어 구성 요소에 따라 달라 지 며 음성 복구를 보장 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>구성 요소</strong></p></td>
<td><p><strong>외적인</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>SRV 레코드 및 A 레코드에서 서버 간 연결 및 서버와 클라이언트 간 연결 확인</p></td>
</tr>
<tr class="odd">
<td><p>Exchange와 EWV(Exchange 웹 서비스)</p></td>
<td><p>대화 상대 저장, 일정 데이터</p></td>
</tr>
<tr class="even">
<td><p>Exchange 통합 메시징과 Exchange 웹 서비스</p></td>
<td><p>통화 기록, 음성 메일 목록, 음성 메일</p></td>
</tr>
<tr class="odd">
<td><p>DHCP 옵션 120</p></td>
<td><p>DNS SRV를 사용할 수 없는 경우 클라이언트에서는 DHCP 옵션 120을 사용하여 등록자를 검색합니다. 이 작업을 수행 하려면 DHCP 서버를 구성 해야 하거나, Lync Server 2013 DHCP를 사용 하도록 설정 해야 합니다. 자세한 내용은 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013의 분기 사이트 복구 요구 사항</a> 에서 Branch-Site 복구를 위한 하드웨어 및 소프트웨어 요구 사항 섹션을 참조 하십시오.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>지속 가능한 음성 기능

위의 요구 사항 및 권장 사항이 구현된 경우 백업 등록자 풀에서 다음 음성 기능을 제공합니다.

  - 아웃바운드 PSTN 통화

  - 인바운드 PSTN 통화(전화 통신 서비스 공급자가 백업 사이트로의 장애 조치 기능을 지원하는 경우)

  - 같은 사이트에 있는 사용자 및 서로 다른 두 사이트 간의 엔터프라이즈 통화

  - 통화 보류, 검색 및 전송을 포함한 기본적인 통화 처리

  - 같은 사이트에 있는 사용자 간의 오디오/비디오 공유 및 양자 간 인스턴트 메시징

  - 착신 전환, 동시 끝점 신호 울림, 통화 위임 및 팀 통화 서비스(통화 위임의 두 당사자 또는 모든 팀 구성원이 같은 사이트에 구성된 경우에만)

  - 기존 전화 및 클라이언트는 계속 작동합니다.

  - CDR(통화 정보 기록)

  - 인증 및 권한 부여

다음 음성 기능은 기본 중앙 사이트의 서비스가 중단된 경우 구성 방법에 따라 작동하거나 작동하지 않을 수 있습니다.

  - 음성 메일 보관 및 검색
    
    기본 중앙 사이트의 서비스가 중단된 경우 Exchange UM을 사용하려면 다음 중 하나를 수행해야 합니다.
    
      - 중앙 사이트의 Exchange UM 서버가 다른 사이트에 있는 백업 Exchange UM 서버를 가리키도록 DNS SRV 레코드를 변경합니다.
    
      - 각 사용자의 Exchange UM 다이얼 플랜을 중앙 사이트와 백업 사이트 모두에 포함 하도록 구성 하 되, 백업 Exchange UM 서버를 사용 하지 않도록 지정 합니다. 기본 사이트를 사용할 수 없게 되 면 Exchange 관리자가 백업 사이트에서 Exchange UM 서버를 사용 하도록 표시 해야 합니다.
    
    위의 두 솔루션을 모두 수행할 수 없는 경우에는 중앙 사이트를 사용할 수 없게 되는 경우에 Exchange UM을 사용할 수 없습니다.

  - 모든 유형의 회의
    
    백업 사이트로 장애 조치된 사용자는 풀을 사용할 수 있는 이끌이가 만들거나 호스팅하는 전화 회의에 참가할 수 있지만 더 이상 사용할 수 없는 자신의 기본 풀에서 전화 회의를 만들거나 호스팅할 수는 없습니다. 마찬가지로 다른 사용자는 영향을 받는 사용자의 기본 풀에서 호스팅되는 전화 회의에 참가할 수 없습니다.

다음 음성 기능은 기본 중앙 사이트의 서비스가 중단된 경우 작동하지 않습니다.

  - 회의 자동 길잡이

  - 현재 상태 및 DND 기반 라우팅

  - 착신 전환 설정 업데이트

  - 응답 그룹 서비스 및 통화 대기

  - 새 전화 및 클라이언트 프로비전

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

