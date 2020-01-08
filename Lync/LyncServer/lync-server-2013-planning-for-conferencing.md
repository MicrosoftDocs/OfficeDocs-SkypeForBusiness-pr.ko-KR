---
title: 'Lync Server 2013: 회의 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-29_

Lync Server 2013는 다양 한 회의 기능을 제공 합니다.

  - 웹 회의-문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유가 포함 됩니다. Lync Server 2013는 Office Web Apps 및 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션 공유 및 렌더링을 처리 합니다. Office Web Apps 서버를 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - 오디오/비디오 (A/V) 회의: 사용자가 Microsoft Live Meeting 서비스나 타사 오디오 브리지와 같은 외부 서비스에 대 한 필요 없이 실시간으로 오디오 또는 비디오 회의를 할 수 있습니다.

  - 전화 접속 회의-사용자가 타사 오디오 회의 공급자 없이 PSTN (공개 교환 전화 네트워크) 전화를 사용 하 여 Lync Server 2013 컨퍼런스의 오디오 부분에 참가할 수 있도록 합니다.

  - IM (인스턴트 메시징) 회의-두 명 이상의 파티가 단일 IM 세션에서 통신 합니다. 메신저 대화 회의에 대 한 자세한 내용은 [Lync Server 2013에서 프런트 엔드 서버, 메신저 대화, 현재 상태에 대 한 계획](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)을 참조 하세요.

Lync Server 2013는 예약 된 회의와 즉석 회의를 모두 지원 합니다.

Lync Server 2013, 프런트 엔드 서버를 배포 하는 경우 웹 회의와 A/V 회의를 배포할지 여부와 전화 접속 회의 기능도 선택할 수 있습니다. IM 회의 기능은 항상 Lync Server 2013 프런트 엔드 서버의 메신저 대화 기능과 함께 자동으로 배포 됩니다.

<div>


> [!NOTE]  
> Office Communicator 2007 R2 클라이언트 (Microsoft Office Outlook 용 Live Meeting console 또는 회의 추가 기능 포함)를 사용 하 여 구성한 모임이 배포에 포함 되어 있는 경우 모임에는 Lync로 마이그레이션한 후 다음과 같은 제한이 적용 됩니다. 서버 2013: 
> <UL>
> <LI>
> <P>모임의 사용자가 문서 공동 작업, 응용 프로그램 공유, 데스크톱 공유 등의 데이터 공동 작업 기능을 사용할 수 없게 됩니다.</P>
> <LI>
> <P>Office Communicator 2007 R2 클라이언트는 Lync Server 2013에서 지원 되지 않으므로 안정성 문제가 발생할 수 있습니다.</P></LI></UL>이러한 문제를 방지 하려면 lync 용 온라인 모임 2010 추가 기능을 사용 하 여 Office Communicator 2007 R2 2013 2010 클라이언트를 사용 하 여 구성 된 모임에 대 한 일정을 조정 하 고 2013 Lync 용 온라인 모임 추가 기능을 사용해 보세요.



</div>

다음 섹션에서는 계획 프로세스, 구성 요소, 하드웨어 및 소프트웨어 요구 사항, 배포 프로세스를 비롯 한 다양 한 유형의 회의 기능을 배포 하는 데 필요한 사항에 대해 설명 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 회의 개요](lync-server-2013-overview-of-conferencing.md)

  - [Lync Server 2013에서 회의 요구 사항 정의](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013의 회의의 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013의 회의에 대한 기술 요구 사항](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013의 회의에 대한 배포 검사 목록](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013의 대규모 모임 지원](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

