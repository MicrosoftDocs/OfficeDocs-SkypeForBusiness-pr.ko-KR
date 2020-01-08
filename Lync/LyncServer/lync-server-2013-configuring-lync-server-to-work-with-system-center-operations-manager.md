---
title: System Center Operations Manager와 작동 하도록 Lync Server 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6f26d4701cf1ed48f0069bcf7994e20ef0b2af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Lync Server 2013에서 System Center Operations Manager와 작동 하도록 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

System Center Operations Manager와 함께 작동 하도록 Microsoft Lync Server 2013 인프라를 구성 하려면 다음 세 가지 작업을 수행 해야 합니다.

  - 기본 System Center Operations Manager 관리 서버를 식별 하 고 구성 합니다. 관리 서버를 구성 하려면 SQL Server를 사용 하 여 백 엔드 데이터베이스를 설정 하는 것은 물론 System Center Operations Manager 2012 또는 System Center Operations Manager 2007 R2를 설치 하는 것이 포함 됩니다. 사용 해야 하는 SQL Server의 실제 버전은 사용 중인 System Center Operations Manager 버전에 따라 다릅니다. 자세한 내용은 [Lync server 2013에서 기본 관리 서버 구성을](lync-server-2013-configuring-the-primary-management-server.md)참조 하세요.

  - 모니터링 하려는 Lync Server 컴퓨터를 식별 하 고 구성 합니다. System Center Operations Manager를 사용 하 여 Lync Server 컴퓨터를 모니터링 하려면 System Center Operations Manager 에이전트 파일을 설치 하 고 각 서버가 프록시로 작동 하도록 구성 해야 합니다.

  - Lync Server *감시자 노드로*작동 시킬 컴퓨터를 식별 하 고 구성 합니다. 감시자 노드는 시스템에 로그온 하는 기능과 같이 키 Lync Server 구성 요소를 확인 하는 Windows PowerShell cmdlet 인 Lync Server 가상 트랜잭션을 정기적으로 실행 하는 컴퓨터 또는 인스턴트 메시지를 교환 하는 기능입니다. 예상 대로 작동 합니다.

이 섹션의 항목에는 이러한 각 작업을 수행 하기 위한 지침이 포함 되어 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 주 관리 서버 구성](lync-server-2013-configuring-the-primary-management-server.md)

  - [Lync Server 2013 관리 팩 설치](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Lync Server 2013에서 모니터링 되는 Lync Server 컴퓨터 구성](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Lync Server 2013에서 감시자 노드 설치 및 구성](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

