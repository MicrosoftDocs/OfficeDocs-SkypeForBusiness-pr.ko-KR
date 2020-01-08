---
title: 'Lync Server 2013: 일반적인 회의 개념'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 240415ccdf8c0ab9be2eaf10304973b62c302c79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Lync Server 2013의 일반적인 회의 개념

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-19_

여러 개념은 모든 유형의 회의에 공통적입니다. 이러한 기능은 다음 섹션에서 설명 합니다.

<div>

## <a name="policies-and-bandwidth-management"></a>정책 및 대역폭 관리

관리자는 Lync Server 2013를 사용 하 여 사용자가 구성할 수 있는 모임 유형에 대 한 정책을 설정할 수 있습니다. 이는 조직의 정책을 적용 하 고 대역폭 사용량을 제어 하는 데 도움이 됩니다. 다양 한 모임 정책을 정의 하 고 개별 사용자 및 사용자 그룹에 할당할 수 있습니다. 피어 투 피어 대화를 제어 하는 정책을 설정할 수도 있습니다. 회의 정책 설정에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 회의 정책을](lync-server-2013-conferencing-policies.md) 참조 하세요. 대역폭 관리에 대 한 자세한 내용은 lync [server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md) 및 [lync server 2013에서 비디오 대역폭 구성을](lync-server-2013-configuring-video-bandwidth.md)참조 하세요.

</div>

<div>

## <a name="archiving-and-compliance-features"></a>보관 및 규정 준수 기능

Lync Server 2013는 조직이 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공 합니다. 보관 기능을 사용 하 여 모임에 제공 된 콘텐츠를 보관 하 고 인스턴트 메시징 (IM) 대화 및 IM 회의 콘텐츠를 보관할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하세요. 영구 채팅 서버의 규정 준수 기능을 사용 하 여 시간에 따라 유지 되는 단체의 항목 기반 대화를 보관할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하세요.

</div>

<div>

## <a name="monitoring-feature"></a>모니터링 기능

모니터링 서버 기능은 Lync Server 2013를 사용 하는 다른 사용자를 추적 하는 데 사용할 수 있는 CDRs (통화 정보 레코드)를 캡처할 수 있습니다. 모니터링 배포 및 구성에 대 한 자세한 내용은 [Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)를 참조 하세요.

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>회의에서 외부 참여 사용

외부 사용자가 초대 된 경우에도 회의에 참가할 수 있도록 하 여 Lync Server 2013 회의에 대 한 투자 혜택을 대폭 높일 수 있습니다. 외부 사용자는 다음을 포함할 수 있습니다.

  - ****   조직의 사용자에 게 방화벽 외부에서 작업 중 이며 해당 랩톱이 나 다른 Lync Server 2013 장치를 사용 하는 경우 원격 사용자입니다.

  - ****   사용자가 Lync Server 2013을 실행 하는 회사의 페더레이션 사용자가 사용 합니다. 사용자가 이러한 사용자에 게 쉽게 연락할 수 있도록 이러한 회사와의 페더레이션 관계를 만듭니다.

  - **익명 사용자**   특정 회의에 참가 하기 위해 사용자가 특별히 초대 하는 다른 모든 외부 사용자입니다. 회사의 모임 이끌이가 외부 사용자에 게 전화 회의에 대 한 전자 메일 초대를 보낼 수 있습니다. 전자 메일에는 외부 사용자가 클릭 하 여 회의에 참가할 수 있는 링크가 포함 되어 있습니다.

이러한 시나리오 중 일부 또는 모두를 사용 하도록 설정 하려면 Edge 서버를 배포 하 여 Lync Server 2013 배포 및 외부 사용자 간의 보안 통신을 사용할 수 있도록 해야 합니다. Edge 서버를 사용 하는 Lync Server 2013 솔루션은 VPN (가상 사설망)과 같은 다른 솔루션 보다 더 높은 품질의 미디어를 제공 합니다. 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스 계획 수립](lync-server-2013-planning-for-external-user-access.md)을 참조 하세요.

또한 Edge 서버를 배포 하는지 여부에 상관 없이 표준 PSTN 휴대폰에서 사용자 (즉, 조직 내부 또는 외부)에 전화 접속 하 여 온-프레미스 오디오 회의에 참가 하도록 할 수 있습니다. Lync Server 2013 전화 접속 회의를 배포 하 여이 작업을 수행 합니다.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>모임 유형 및 클라이언트 버전 간의 호환성

Lync Server 2013이 이전 버전의 Office Communications Server 및 해당 클라이언트와 상호 운용 되 게 하려면 다음 문제를 알아야 합니다.

  - Lync Server 2013를 사용 하는 사용자는 Live Meeting 컨퍼런스를 예약 하거나이 형식의 모든 마이그레이션된 모임을 수정할 수 없습니다.

  - Office Communications Server 2007 R2를 실행 하는 서버에 호스팅되는 Live Meeting 회의에 참가 해야 하는 Lync Server 2013을 사용 하는 사용자는 이러한 모임에 참석할 수 있도록 컴퓨터에 Live Meeting 클라이언트 (Lync Server 2013 외에는 포함)를 설치 해야 합니다.

  - Live Meeting 회의가 Lync Server 2013로 마이그레이션되면 모임 콘텐츠는 마이그레이션되지 않습니다. 이 내용이 필요한 경우 다시 업로드 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

