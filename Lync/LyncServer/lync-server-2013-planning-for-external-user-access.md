---
title: 'Lync Server 2013: 외부 사용자 액세스 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-19_

대부분의 조직의 통신에는 내부 네트워크 내에 있지 않은 서비스 및 사용자가 포함 됩니다. 이러한 서비스 및 사용자에 게는 일시적으로 또는 영구적으로 오프 사이트, 고객 또는 파트너 조직의 직원, 공공 메신저 대화 서비스를 사용 하는 사용자, 초대 받은 잠재 고객, 파트너, 익명 사용자 등이 포함 됩니다. 모임 및 프레젠테이션으로 이동할 수 있습니다. 이 문서에서는 이러한 사람들을 통틀어 *외부 사용자*라고 합니다.

Microsoft Lync Server 2013를 사용 하는 경우 조직의 사용자는 메신저 대화 및 현재 상태를 사용 하 여 외부 사용자와 통신할 수 있으며, 오프 사이트의 직원 및 기타 유형의 외부 사용자와 함께 오디오/비디오 (A/V) 회의 및 웹 회의에 참가할 수 있습니다. 모바일 장치 및 엔터프라이즈 음성을 통해 외부 액세스를 지원할 수도 있습니다. 조직의 구성원이 아닌 외부 사용자는 Lync Server 2013 모임에 참가 하 여 익명 참석자를 허용할 수 있습니다.

조직의 방화벽을 통해 통신을 지원 하려면 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)에 Lync Server 2013 Edge 서버를 배포 합니다. Edge 서버는 방화벽 외부의 사용자가 내부 Lync Server 2013 배포에 연결 될 수 있는 방법을 제어 합니다. 또한 방화벽 내에서 시작 된 외부 사용자와의 통신을 제어 합니다.

요구 사항에 따라 하나 이상의 위치에 하나 이상의 Edge 서버를 배포할 수 있습니다. 이 섹션에서는 Lync Server 2013에서 외부 사용자 액세스 시나리오에 대해 설명 하 고, edge 및 리버스 프록시 토폴로지를 계획 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> 엔터프라이즈 음성 및 외부 사용자 액세스를 지원 하기 위해 Edge 서버가 필요 하지만이 섹션에서는 IM, 현재 상태, A/V 회의, 페더레이션, 웹 회의, Lync Mobile에 대 한 지원을 중점적으로 설명 합니다. Enterprise Voice 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013의 Enterprise Voice 계획</A> 을 참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [에지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013의 외부 사용자 액세스 구성 요소에 대한 시스템 요구 사항](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013의 외부 사용자 액세스 개요](lync-server-2013-overview-of-external-user-access.md)

  - [Lync Server 2013의 자동 검색 이해](lync-server-2013-understanding-autodiscover.md)

  - [Lync Server 2013에서 토폴로지 선택](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013의 데이터 수집](lync-server-2013-data-collection.md)

  - [Lync Server 2013에 대한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Lync Server 2013의 에지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013의 외부 사용자 액세스에 대한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

