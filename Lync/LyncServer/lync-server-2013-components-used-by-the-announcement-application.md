---
title: 'Lync Server 2013: 알림 응용 프로그램에서 사용 되는 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a888ca21e26a21103d1c45e74518c3d224d18a7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013의 알림 응용 프로그램에서 사용 되는 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-13_

Lync Server 2013에서 알림 응용 프로그램은 응답 그룹 응용 프로그램의 구성 요소입니다. Enterprise Voice를 배포 하면 알림 응용 프로그램이 자동으로 설치 되 고 응답 그룹 응용 프로그램과 함께 활성화 됩니다. 이 섹션에서는 알림 응용 프로그램을 지 원하는 구성 요소에 대해 설명 합니다.

<div>

## <a name="announcement-application-components"></a>알림 응용 프로그램 구성 요소

다음 Lync Server 구성 요소는 알림 응용 프로그램을 지원 합니다.

  - **응용 프로그램 서비스**   응용 프로그램 서비스는 통합 커뮤니케이션 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다. 응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.

  - **응답 그룹 응용**   프로그램 응답 그룹 응용 프로그램은 응용 프로그램 서비스에서 호스팅하는 통합 통신 응용 프로그램 중 하나입니다. 지정 되지 않은 전화 번호 범위가 알림에 라우팅되도록 구성 된 경우 응답 그룹 응용 프로그램은 전화 번호에 대 한 통화를 라우팅하는 데 필요 합니다. 모든 범위가 Exchange UM (통합 메시징)으로 라우팅되도록 구성 된 경우에는 응답 그룹 응용 프로그램이 필요 하지 않습니다.

  - **오디오 파일**   오디오 파일은 알림에 사용 됩니다.

  - **파일 저장소**   알림 응용 프로그램은 파일 저장소를 사용 하 여 오디오 파일을 저장 합니다.

  - **Lync server 제어판**   lync server 제어판을 사용 하 여 지정 되지 않은 번호 테이블을 구성할 수 있습니다.

  - **Lync server 관리 셸**   lync server 관리 셸 cmdlet을 사용 하 여 알림 설정 및 할당 되지 않은 번호 테이블을 구성할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

