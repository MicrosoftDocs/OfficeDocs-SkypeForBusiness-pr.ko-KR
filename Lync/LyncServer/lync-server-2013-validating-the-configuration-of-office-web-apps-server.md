---
title: 'Lync Server 2013: Office Web Apps 서버 구성 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-22_

Office Web Apps 서버를 토폴로지에 추가 하 고 해당 토폴로지가 게시 된 후에는 Lync Server 이벤트 로그에 새 이벤트 로그 이벤트가 두 개 표시 됩니다. 첫째, LS 데이터 MCU 이벤트 (이벤트 ID 41034)를 추가 해야 합니다. 이 이벤트는 Office Web Apps 서버가 검색 되었음을 보고 합니다.

**웹 회의 서버 Office Web Apps 서버가 검색 되었으며, PowerPoint 콘텐츠를 사용할 수 있습니다.**

이 외에도, Office Web Apps 서버 Url을 보고 하는 다른 LS 데이터 MCU 이벤트 (이벤트 ID 41032)가 표시 되어야 합니다. 예를 들어 다음과 같은 항목이 표시 됩니다.

**웹 회의 서버 Office Web Apps 서버 검색에 성공 했습니다.**

**Office Web Apps Server 내부 발표자 페이지:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps Server 내부 참석자 페이지:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps Server 외부 발표자 페이지:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps Server 내부 참석자 페이지:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

이벤트 ID가 41033 인 LS 데이터 MCU 이벤트가 표시 되는 경우 Office Web Apps 서버 검색에 실패 했음을 의미 합니다. 이 경우 Microsoft Lync Server 2013에서 새로 구성 된 Office Web Apps 서버를 검색 하는 데 필요한 횟수 만큼 시도 합니다. 검색 프로세스가 반복적으로 실행 되지 않는 경우 토폴로지 문서에서 Office Web Apps 서버를 제거 하 고 업데이트 된 토폴로지를 게시 한 다음 연결 문제가 해결 된 후에 Office Web Apps 서버를 토폴로지에 다시 추가 해 보세요.

Office Web Apps 서버가 올바르게 구성 되어 있고 검색 프로세스에서 인식 되는 것으로 표시 되는 경우 Microsoft Lync 2013 클라이언트 쌍 간에 PowerPoint 프레젠테이션을 공유 하 여 Office Web Apps 서버가 예상 대로 작동 하는지 확인할 수 있습니다. 사용자 A가 PowerPoint 프레젠테이션을 로드 하 고 표시할 수 있으며, 사용자 B가 모임에 참가 하 여 해당 프레젠테이션을 볼 수 있으면 Office Web Apps 서버가 작동 하는 것입니다.

Office Web Apps Server가 올바르게 구성 되어 있더라도 PowerPoint 프레젠테이션을 공유 하려고 하면 "서버 연결 문제로 인해 일부 공유 기능을 사용할 수 없습니다." 오류 메시지가 나타날 수 있습니다. 해당 오류 메시지가 나타나면 새 Office Web Apps 서버와 연결 된 프런트 엔드 서버 (또는 서버)를 다시 시작 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

