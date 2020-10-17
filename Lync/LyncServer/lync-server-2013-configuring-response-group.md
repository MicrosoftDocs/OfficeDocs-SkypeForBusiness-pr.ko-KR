---
title: 'Lync Server 2013: 응답 그룹 구성'
description: 'Lync Server 2013: 응답 그룹을 구성 하는 중입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547934"
---
# <a name="configuring-response-group-in-lync-server-2013"></a>Lync Server 2013에서 응답 그룹 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

응답 그룹은 지원 센터 또는 고객 서비스 데스크와 같이 *에이전트*라고 하는 사용자 그룹에 대 한 수신 전화를 라우팅하고 큐에 대기 시키는 Enterprise Voice 기능입니다.

응답 그룹에 필요한 구성 요소는 Enterprise Voice 배포 시 프런트 엔드 서버 또는 Standard Edition Server에 자동으로 설치되어 사용하도록 설정됩니다. 사용자가 응답 그룹을 사용할 수 있도록 하려면 에이전트 그룹을 구성한 다음 큐와 워크플로를 차례로 구성합니다. 또한 응답 그룹 관리자는 기존 워크플로의 구성을 응답 그룹 관리자에 게 위임할 수 있으며, 그러면 해당 워크플로와 연결 된 에이전트 그룹 및 큐를 수정 하 고 다시 구성할 수 있습니다.

이 섹션에서는 Lync Server 2013 응답 그룹의 구성을 안내 합니다. 이 예제에서는 응답 그룹과 관련 된 계획 섹션을 이미 읽고 enterprise Edition 서버 또는 Standard Edition 서버를 Enterprise Voice와 함께 배포 했다고 가정 합니다.

<div>


> [!TIP]  
> 샘플 스크립트를 포함 하 여 Lync Server 관리 셸을 사용 하 여 응답 그룹을 만드는 방법에 대 한 자세한 내용은에서 "Lync Server 관리 셸을 사용 하 여 첫 번째 응답 그룹 만들기"를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> .



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 응답 그룹 구성 권한 및 필수 구성 요소](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013의 응답 그룹 배포 프로세스](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013의 워크플로 생성 시나리오 개요](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [응답 그룹 에이전트 그룹 만들기 Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Lync Server 2013에서 응답 그룹 큐 만들기](lync-server-2013-create-response-group-queues.md)

  - [반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md)

  - [반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Lync Server 2013에서 응답 그룹 워크플로 만들기](lync-server-2013-create-response-group-workflows.md)

  - [반드시 Lync Server 2013에서 응답 그룹 배포 확인](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

