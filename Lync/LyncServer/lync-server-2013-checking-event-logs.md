---
title: 'Lync Server 2013: 이벤트 로그 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8574681353a6082ce46efb514923871a01c1427d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Lync Server 2013에서 이벤트 로그 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-08-06_

[Windows 이벤트 뷰어](https://go.microsoft.com/fwlink/p/?linkid=314067) 를 사용 하 여 이벤트 로그를 보고, 서비스 오류, AD DS의 복제 오류 및 가상 메모리 및 디스크 공간과 같은 시스템 리소스에 대 한 경고 정보를 가져올 수 있습니다. 이벤트 뷰어는 Windows Server 2008 및 2012에 포함 되어 있습니다.

Lync Server 2013 로깅 도구에서 디버그 세션을 끝낼 때 Snooper 도구를 사용 하 여 로그 파일을 보려면 로그 파일 **분석** 을 클릭 합니다.

이벤트 뷰어는 컴퓨터의 응용 프로그램, 보안 및 시스템 이벤트에 대 한 로그를 유지 관리 합니다. Lync Server 2013 및 Windows에서 경고와 오류 조건을 이벤트 로그에 보고 합니다. 따라서 매일 이벤트 로그를 검토 합니다.

이벤트 뷰어를 사용 하 여 다음을 수행 합니다.

  - 이벤트 로그를 보고 관리 합니다.

  - 해결 해야 하는 하드웨어, 소프트웨어 및 시스템 문제에 대 한 정보를 가져옵니다.

  - 나중에 수행 해야 하는 추세를 파악 합니다.

Windows Server 운영 체제에서 Lync Server를 실행 하는 서버는 다음과 같은 네 가지 유형의 로그에 이벤트를 기록 합니다.

  - **응용 프로그램 로그**   응용 프로그램 로그에는 응용 프로그램이 나 프로그램에서 기록한 이벤트가 포함 됩니다. 개발자는 기록할 이벤트를 결정합니다. 예를 들어 데이터베이스 프로그램은 응용 프로그램 로그에 파일 오류를 기록합니다. 대부분의 Lync Server 2013 관련 이벤트는 응용 프로그램 로그에 표시 됩니다.

  - **보안 로그**   보안 로그는 파일 또는 다른 개체 만들기, 열기 또는 삭제와 같은 리소스 사용과 관련 된 이벤트 외에도 유효 및 유효 하지 않은 로그온 시도와 같은 이벤트를 기록 합니다. 예를 들어 로그온 감사를 사용하는 경우 시스템에 대한 로그온 시도가 보안 로그에 기록됩니다.

  - **시스템 로그**   시스템 로그에는 Windows 시스템 구성 요소에 의해 기록 되는 이벤트가 포함 됩니다. 예를 들어 시작하는 동안 드라이버 또는 기타 시스템 구성요소에 로드하는 데 실패할 경우 시스템 로그에 기록됩니다. 시스템 구성 요소에 의해 기록되는 이벤트 유형은 서버에 의해 미리 결정됩니다.

  - **Lync Server 2013**   로깅 도구는 인증, 연결 및 사용자 작업과 관련 된 중요 한 이벤트를 기록 합니다. 진단 로깅을 사용 하도록 설정한 후에는 이벤트 뷰어에서 로그 항목을 볼 수 있습니다.

<div>


> [!NOTE]  
> Microsoft 고객 지원 서비스에서이 작업을 수행 하는 경우를 제외 하 고는 최대 로깅 설정을 사용 하지 않는 것이 좋습니다. 최대 로깅은 중요 한 리소스를 중단 하 고, 최대 로깅으로만 기록 되 고 실제로 예상 되는 문제를 야기 하는 오류는 매우 많은 "가양성"을 제공할 수 있습니다. 또한 진단 로깅을 영구적으로 사용 하지 않도록 설정 하는 것이 좋습니다. 문제를 해결 해야 하는 경우에만 사용 합니다.



</div>

각 이벤트 뷰어 로그 내에서 Lync Server 2013는 정보, 경고 및 오류 이벤트를 기록 합니다. 이러한 로그를 면밀 하 게 모니터링 하 여 Lync Server 2013 서버에서 수행 되는 트랜잭션의 유형을 추적 합니다. 로그를 주기적으로 보관하거나 자동 롤오버를 사용하여 공간 부족이 발생하지 않도록 해야 합니다. 로그 파일은 일정 한 간격을 차지할 수 있으므로 로그 크기 (예: 50 MB)를 높인 다음 Lync Server 2013 서버가 새 이벤트를 계속 쓸 수 있도록 덮어쓰기로 설정 합니다.

또한 다음과 같은 도구와 기술을 사용 하 여 이벤트 로그 관리를 자동화할 수 있습니다.

  - System Center Operations Manager는 Lync Server 2013 서버의 상태 및 사용을 모니터링 합니다. Lync Server 2013 Operations Manager 용 관리 팩은 Lync Server 2013을 실행 하는 서버에 대 한 특수 한 모니터링을 제공 하 여 Operations Manager를 확장 합니다.

  - Lync Server 2013 Operations Manager 용 관리 팩은 Lync Server 2013 Standard 및 Enterprise Edition을 모니터링 합니다. 이 릴리스에는 이전에는 별도의 관리 팩 이었던 QoE (환경 품질) 관리 팩도 통합 되어 있습니다.

모니터링 되는 유형은 이벤트 로그 항목, 성능 카운터 및 QoE의 상태 모니터링입니다. 이 버전의 관리 팩은 Lync Server 2013 및 2010만 모니터링 하며, Office Communications Server 2007을 모니터링 하는 데 사용할 수 없습니다.

관리 팩은 다음과 같은 기능을 제공 합니다.

  - 서비스에 영향을 주는 이벤트를 나타내는 경고

  - 구성을 나타내는 경고 및 기타 서비스가 영향을 주지 않는 문제

  - Lync Server 서비스의 상태 모니터링

  - 제품 정보: 식별 된 문제의 원인과 해결 방법

Lync Server 2013 관리 팩에 대 한 자세한 내용은 [System Center Operations Manager를 사용 하 여 Lync server 2013 모니터링](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)을 참조 하십시오.

**이벤트 빗질**   이벤트 빗질 도구는 여러 컴퓨터의 이벤트 로그에서 하나의 중앙 위치로 특정 이벤트를 수집 합니다. 이 도구를 사용 하면 이벤트 Id 또는 이벤트 원본이 지정 하는 경우에만 보고할 수 있습니다. 이벤트 빗질에 대 한 자세한 내용은 [계정 잠금 및 관리 도구](https://go.microsoft.com/fwlink/?linkid=35607) 웹 사이트를 참조 하십시오.

****   Windows Server 2012의 이벤트 트리거 관리자가 프로그램을 실행 하거나 전자 메일 메시지를 보내거나 화면 메시지를 표시할 수 있는 windows 이벤트 뷰어 내에서 "이 이벤트에 작업을 연결" 할 수 있습니다. 이 기능에 대 한 자세한 내용은 Windows Server 2008 R2 항목 [지정한 이벤트에 대 한 응답으로 작업 실행](https://technet.microsoft.com/library/cc748900.aspx)을 참조 하십시오. ' Eventtrigger '와 같은 명령줄 도구를 사용 하 여 이벤트 로그를 만들고 쿼리 하 고 로깅된 특정 이벤트에 프로그램을 연결할 수도 있습니다. Eventtriggers .exe를 사용 하 여 특정 이벤트가 발생할 때 프로그램을 실행 하는 이벤트 트리거를 만들 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Windows 이벤트 뷰어](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

