---
title: 'Lync Server 2013: 통화 대기 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1624042b07bc024d837e55ffac402cb2f158922f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

Lync Server 2013 Call 공원 응용 프로그램을 사용 하면 Enterprise Voice 사용자가 다음 중 하나를 수행할 수 있습니다.

  - 통화를 대기시킨 후에 같은 전화기 또는 다른 전화기에서 통화 재개

  - 통화를 대기시키고 이 통화를 특정 부서나 일반 영역(예: 영업 부서 또는 공통 영역 전화가 있는 창고)으로 전송

  - 통화를 대기시키고 처음에 응답한 전화기에서 다른 통화 수신

사용자가 통화를 파킹 하면 Lync Server는 통화를 검색 하거나 시간이 초과 될 때까지 통화를 대기 하는 *궤도*라고 하는 임시 번호로 호출을 전송 합니다. Lync Server는 통화를 파킹 한 사용자에 게 궤도를 전송 합니다. 대기 통화를 검색 하기 위해 사용자는 궤도 번호로 전화를 걸어 대화 창에서 궤도 링크 또는 단추를 클릭할 수 있습니다.

통화를 대기시킨 사용자는 IM(인스턴트 메시징) 또는 호출 시스템과 같은 외부 메커니즘을 사용하여 파킹된 통화 번호를 전달하는 방식으로 다른 사람에게 통화를 재개하도록 알릴 수 있습니다. 또한 통화를 대기시킨 사용자는 통화가 재개된 경우 알림을 받기 위해 대화 창을 열어 둘 수 있습니다.

궤도 범위는 전역적으로 고유 하므로 라우팅이 적절 하 게 구성 된 경우 Lync Server 사이트 또는 PBX 전화에서 호출을 검색할 수 있습니다. 구성 가능한 시간 내에 아무도 통화를 재개하지 않으면 통화를 대기시킨 사람에게 통화가 다시 연결됩니다. 그런 다음 통화를 대기시킨 사람이 다시 연결된 통화에 응답하지 않으면 통화가 교환원과 같은 대체 대상으로 전송됩니다(이렇게 구성된 경우). 이와 같이 통화가 전송되기 전에 통화가 다시 연결되는 횟수(1회~10회)를 구성할 수 있습니다. 전송된 통화에 아무도 응답하지 않으면 통화 연결이 끊어집니다. 통화가 재개되거나 끊긴 경우에는 파킹된 통화 번호가 비워집니다.

통화 대기를 배포할 때 통화 대기에 사용할 내선 번호(파킹된 통화 번호) 범위를 예약해야 합니다. 이러한 내선 번호는 가상 내선 번호, 즉 할당된 사용자 또는 전화가 없는 내선 번호여야 합니다. 그런 다음 파킹된 통화 번호 범위를 사용하여 통화 대기 파킹된 통화 번호 테이블을 구성하고 각 범위를 처리할 통화 대기 응용 프로그램을 호스팅하는 응용 프로그램 서비스를 지정합니다. 각 프런트 엔드 풀에는 해당 백 엔드 서버에 풀에서 대기 중인 통화를 관리하는 데 사용되는 통화 대기 테이블이 있습니다. 궤도 범위 목록은 중앙 관리 저장소에 저장 되며 대상 풀로 궤도를 라우팅하는 데 사용 됩니다. 통화 대기 응용 프로그램을 배포 하 고 구성 하는 각 Lync Server 풀에는 하나 이상의 궤도 범위가 포함 될 수 있습니다. 궤도 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.

또한 여러분은 시간 초과된 통화가 리디렉션되는 위치 및 통화 대기 중인 사용자에게 음악을 들려줄지 여부와 같은 다른 통화 대기 설정을 구성할 수 있으며, 통화 대기 중인 동안 재생할 음악 파일을 지정할 수도 있습니다.

<div>


> [!NOTE]  
> 통화 대기에 대 한 사용자 지정 음악 보존 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다. 통화 대기를 위해 업로드하는 사용자 지정 대기 음악 파일의 별도 백업 복사본을 항상 유지하십시오.



</div>

통화 대기 응용 프로그램은 Enterprise Voice의 구성 요소입니다. Enterprise Voice를 배포하면 통화 대기 응용 프로그램이 자동으로 설치되고 활성화됩니다. 그러나 통화 대기를 사용하려면 먼저 Enterprise Voice 관리자가 통화 대기를 구성하고 음성 정책을 통해 사용자가 사용할 수 있도록 설정해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

