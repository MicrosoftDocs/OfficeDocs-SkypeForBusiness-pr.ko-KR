---
title: 'Lync Server 2013: MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정'
description: 'Lync Server 2013: Microsoft MSPL (SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f919599d6c6a39fea73424f4e287f00636c0982
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544784"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

Lync Server 제어판을 사용 하 여 Lync Server 2013 환경에서 실행 되는 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 이러한 응용 프로그램은 Microsoft Lync 2013 Preview API 대신 스크립트 언어를 사용 하는 스크립트 전용 응용 프로그램입니다.

모든 스크립트를 사용 하거나 사용 하지 않도록 설정할 수는 없습니다. 예를 들어 DefaultRouting 스크립트를 사용할 수 있으며 DefaultRouting에 대해이 옵션을 변경할 수 없습니다.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>MSPL 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **토폴로지**를 클릭한 다음 **서버 응용 프로그램**을 클릭합니다.

4.  **서버 응용 프로그램** 페이지에서 필요한 경우 열 머리글을 클릭하여 응용 프로그램을 정렬한 다음 수정할 서버 응용 프로그램을 클릭합니다.

5.  **동작**을 클릭합니다.

6.  **응용 프로그램 사용** 또는 **응용 프로그램 사용 안 함** (스크립트에서이 옵션을 지 원하는 경우)을 클릭 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Lync Server 2013 토폴로지 관리](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

