---
title: 'Lync Server 2013: 외부 사용자 액세스 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e418ee1db146afa1f766aa0fc56842222f7b510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-19_

대부분의 조직에서는 내부 네트워크에 포함 되지 않은 서비스와 사용자가 통신 합니다. 이러한 서비스와 사용자에 게는 일시적 이거나 영구적으로 공유 하는 직원, 고객 또는 파트너 조직의 직원, 공용 IM (인스턴트 메시징) 서비스를 사용 하는 사용자, 초대 하는 잠재 고객, 파트너 및 익명 사용자 등이 있습니다. 모임 및 프레젠테이션으로 이동할 수 있습니다. 이 문서에서는 이러한 사용자를 집합적으로 *외부 사용자*라고 합니다.

Microsoft Lync Server 2013을 사용 하는 경우 조직의 사용자는 IM 및 현재 상태를 통해 외부 사용자와 통신할 수 있으며, 온-V (오디오/비디오) 회의 및 웹 회의에 참가할 수 있습니다 (예를 들어, 오프 사이트 직원과 기타 유형의 외부 사용자). 모바일 장치 및 Enterprise Voice를 통해 외부 액세스를 지원할 수도 있습니다. 조직의 구성원이 아닌 외부 사용자는 Lync Server 2013 모임에 참가할 수 있으며 익명 참석자를 허용 합니다.

조직의 방화벽에서 제공 되는 통신을 지원 하기 위해 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)에 Lync Server 2013에 지 서버를 배포 합니다. 에 지 서버는 방화벽 외부의 사용자가 내부 Lync Server 2013 배포에 연결할 수 있는 방식을 제어 합니다. 또한 방화벽 내에서 시작 된 외부 사용자와의 통신을 제어 합니다.

요구 사항에 따라 하나 이상의 위치에 하나 이상의에 지 서버를 배포할 수 있습니다. 이 섹션에서는 Lync Server 2013의 외부 사용자 액세스 시나리오에 대해 설명 하 고,에 지 및 역방향 프록시 토폴로지를 계획 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> Enterprise Voice 및 외부 사용자 액세스를 지원 하기 위해에 지 서버가 필요 하지만이 섹션에서는 IM, 현재 상태, A/V 회의, 페더레이션, 웹 회의 및 Lync Mobile에 대 한 지원을 중점적으로 설명 합니다. Enterprise Voice 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013에서 Enterprise Voice 계획</A> 을 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [에 지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013의 외부 사용자 액세스 구성 요소에 대 한 시스템 요구 사항](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013의 외부 사용자 액세스 개요](lync-server-2013-overview-of-external-user-access.md)

  - [Lync Server 2013의 자동 검색 이해](lync-server-2013-understanding-autodiscover.md)

  - [Lync Server 2013에서 토폴로지 선택](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013의 데이터 수집](lync-server-2013-data-collection.md)

  - [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Lync Server 2013의에 지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

