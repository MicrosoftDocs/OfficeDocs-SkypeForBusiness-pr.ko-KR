---
title: 'Lync Server 2013: 알림 응용 프로그램 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e711eb408d0819c818157f85fbb0ff81930da7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013의 알림 응용 프로그램 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-13_

알림 응용 프로그램을 배포할 때는 사용자가 지정 되지 않은 번호에 전화를 걸 때 수행할 작업을 결정 하는 할당 되지 않은 번호 테이블을 구성 해야 합니다. 지정 되지 않은 번호 테이블에는 조직에 적합 한 전화 번호 범위가 포함 되며 각 범위를 처리 하는 알림 응용 프로그램을 지정 합니다. 발신자가 조직에 대해 유효한 전화 번호로 전화를 걸 때 모든 사용자에 게 할당 되지 않은 경우 Lync Server는 할당 되지 않은 번호 라우팅 테이블에서 번호를 조회 하 고, 해당 번호의 범위를 식별 하 고, 알림에 대 한 통화 경로를 지정 합니다. 해당 범위에 대해 지정 된 응용 프로그램 알림 응용 프로그램은 통화에 응답 하 고 음성 메시지를 재생 하며 (이를 위해 구성한 경우) 통화의 연결을 끊거나 교환원과 같은 미리 정의 된 대상으로 전송 합니다. Lync Server 관리 셸 cmdlet을 사용 하 여 여러 오디오 메시지를 구성 하거나 대상을 전송할 수 있습니다.

지정되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 더 이상 사용되지 않는 특정 번호가 있는 경우 각 번호별로 지정된 메시지를 재생하려면 지정되지 않은 번호 테이블에 해당 특정 번호를 입력하면 됩니다. 예를 들어 고객 서비스 센터의 번호를 변경한 경우 이전 고객 서비스 번호를 입력하고 새 번호를 제공하는 알림과 연결할 수 있습니다. 지정되지 않은 번호(예: 퇴사한 직원의 번호)로 전화를 건 모든 사람에게 일반 메시지를 재생하려면 조직의 유효한 모든 내선 번호 범위를 입력하면 됩니다. 그러면 발신자가 현재 지정되지 않은 번호로 전화를 걸 때마다 지정되지 않은 번호 테이블이 호출됩니다.

Lync Server 2013에서는 알림 응용 프로그램이 응답 그룹 응용 프로그램과 함께 자동으로 설치 됩니다. 알림 및 응답 그룹 응용 프로그램은 enterprise voice 배포의 표준 구성 요소 이며, Enterprise Voice를 배포할 때 이러한 응용 프로그램은 모두 자동으로 배포 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

