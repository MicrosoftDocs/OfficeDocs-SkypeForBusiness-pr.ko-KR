---
title: 'Lync Server 2013: 회의 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0fd8edb6e2939b82711392c53b0e5bef3e7740
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-29_

Lync Server 2013에서는 다음과 같은 다양 한 회의 기능을 제공 합니다.

  - 웹 회의: 문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유가 포함됩니다. Lync Server 2013에서는 Office Web Apps와 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다. Office Web Apps 서버를 설치 및 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - A/V(오디오/비디오) 회의: Microsoft Live Meeting 서비스나 타사 오디오 브리지 등의 외부 서비스 없이 실시간 오디오 또는 비디오 회의를 할 수 있습니다.

  - 전화 접속 회의-사용자가 타사 오디오 회의 공급자 없이도 PSTN (공중 전화망) 전화를 사용 하 여 Lync Server 2013 회의의 오디오 부분에 참가할 수 있도록 합니다.

  - IM(인스턴트 메시징) 회의: 단일 IM 세션에서 두 명 이상의 사람이 통신합니다. IM 회의에 대 한 자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 계획](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)을 참조 하세요.

Lync Server 2013에서는 예약 된 회의와 즉석 회의를 모두 지원 합니다.

Lync Server 2013, 프런트 엔드 서버를 배포할 때는 웹 회의, A/V 회의 및 전화 접속 회의 기능도 함께 배포할지 여부를 선택할 수 있습니다. IM 회의 기능은 Lync Server 2013 프런트 엔드 서버에서 항상 IM 대화 기능과 함께 자동으로 배포 됩니다.

<div>


> [!NOTE]  
> Office Communicator 2007 R2 클라이언트 (Microsoft Office Outlook의 Live Meeting console 또는 회의 추가 기능 포함)를 사용 하 여 구성 된 모임이 배포에 포함 되는 경우에는 Lync로 마이그레이션한 후 모임에 다음과 같은 제한이 적용 됩니다. 서버 2013: 
> <UL>
> <LI>
> <P>모임 사용자는 문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유를 비롯 한 데이터 공동 작업 기능을 사용할 수 없습니다.</P>
> <LI>
> <P>Office Communicator 2007 R2 클라이언트는 Lync Server 2013에서 지원 되지 않으므로 안정성 문제가 발생할 수 있습니다.</P></LI></UL>이러한 문제가 발생 하지 않도록 하려면 Office Communicator 2007 R2 클라이언트를 사용 하 여 구성 된 모든 모임 일정을 Outlook 2010 또는 2013 Lync 용 온라인 모임 추가 기능에 대 한 lync 2010 또는 Outlook 2013을 사용 하 여 오프 라인으로 전환 합니다.



</div>

다음 섹션에서는 계획 프로세스, 구성 요소, 하드웨어와 소프트웨어 요구 사항 및 배포 프로세스를 비롯한 다양한 회의 기능 유형을 배포하는 데 필요한 사항에 대해 설명합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 회의 개요](lync-server-2013-overview-of-conferencing.md)

  - [Lync Server 2013의 회의에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013의 회의에 대 한 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013의 회의에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013의 회의에 대 한 배포 검사 목록](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013의 대규모 모임 지원](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

