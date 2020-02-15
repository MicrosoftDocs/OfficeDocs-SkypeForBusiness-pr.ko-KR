---
title: 'Lync Server 2013: Microsoft MSPL (SIP Processing Language) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50dea89feb7e72c5076e58a38136d24b1b34499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

MSPL (microsoft SIP Processing Language) 서버 응용 프로그램은 Microsoft Lync 2010 API 대신 MSPL 스크립팅 언어를 사용 하는 스크립트 전용 응용 프로그램입니다. 일부 MSPL 서버 응용 프로그램은 중요로 지정 됩니다. 스크립트가 중요 한 경우 Lync Server 2013을 시작 하기 위해 시스템을 시작 하는 동안 스크립트가 시작 되어야 합니다. Lync Server가 실행 되는 동안 스크립트가 실패 하면 서버가 종료 되지 않지만 스크립트에 트래픽을 보내지 않고 이벤트 로그에 오류를 기록 합니다.

Lync Server 제어판을 사용 하 여 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 중요 하거나 표시 하지 않는 것으로 표시할 수 있습니다.

일부 스크립트에서는 이 옵션이 지원되지 않습니다. 예를 들어 DefaultRouting 스크립트가 중요 스크립트로 표시되었으며, DefaultRouting에 대해 이 옵션을 변경할 수 없습니다.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>MSPL 서버 응용 프로그램을 중요 응용 프로그램으로 표시하거나 표시 해제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **토폴로지**를 클릭한 다음 **서버 응용 프로그램**을 클릭합니다.

4.  **서버 응용 프로그램** 페이지에서 필요한 경우 열 머리글을 클릭하여 응용 프로그램을 정렬한 다음 수정할 서버 응용 프로그램을 클릭합니다.

5.  **동작**을 클릭합니다.

6.  **중요로 표시** 또는 **중요로 선택 해제**를 클릭합니다(즉 스크립트에서 이 옵션이 지원되는 경우).

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Lync Server 2013 토폴로지 관리](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

