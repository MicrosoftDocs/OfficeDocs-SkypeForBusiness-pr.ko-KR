---
title: 'Lync Server 2013: 모니터링 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ceef06ca0078b9a34c9f02e1ed3be91ab9b34aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-17_

통합 데이터 수집 에이전트는 각 프런트 엔드 서버에서 자동으로 설치 되 고 활성화 되지만 Microsoft Lync Server 2013을 설치 하는 동안 모니터링 데이터를 자동으로 수집 하는 것을 의미 하지는 않습니다. 대신 프런트 엔드 서버/프런트 엔드 풀을 모니터링 데이터베이스와 연결 해야 하 고, 전역 범위 및/또는 사이트 범위에서 CDR (통화 정보 기록) 및/또는 QoE (경력 품질) 모니터링을 사용 하도록 설정 해야 합니다.

프런트 엔드 서버 또는 프런트 엔드 풀을 모니터링 데이터베이스에 연결 하는 방법에 대 한 단계별 지침은 배포 가이드의 [Lync Server 2013에서 모니터링 저장소를 프런트 엔드 풀과 연결](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) 하는 항목을 참조 하십시오. 이러한 연결이 만들어진 후 새 Lync Server 토폴로지가 게시 된 후에도 모니터링 데이터는 수집할 수 없습니다. Lync Server 2013을 설치 하면 기본적으로 CDR 및 QoE 데이터 수집이 모두 사용 하지 않도록 설정 되기 때문입니다.

데이터 수집을 시작 하려면 CDR 및/또는 QoE 모니터링을 사용 하도록 설정 해야 합니다. (CDR 및 QoE 모니터링을 모두 사용 하도록 설정할 필요는 없지만 원하는 경우에는 한 가지 유형의 모니터링을 사용 하도록 설정 하 고 다른 형식은 사용 하지 않도록 설정할 수 있습니다.) 전역 범위에서 CDR 모니터링을 사용 하도록 설정 하려면 Lync Server 관리 셸에서 다음 명령을 실행 합니다.

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

또는 Lync Server 2013 제어판에서 CDR 모니터링을 사용 하도록 설정할 수도 있습니다. Lync Server 제어판에서 다음 절차를 완료 합니다.

1.  **모니터링**을 클릭합니다.

2.  **통화 정보 기록** 탭에서 **전역** 설정을 두 번 클릭 합니다.

3.  **CDR (통화 정보 기록) 설정 편집** 창에서 **cdrs의 모니터링 사용** 을 선택 하 고 **커밋을**클릭 합니다.

전역 범위에서 QoE 모니터링을 사용 하도록 설정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

원하는 경우 Lync Server 제어판 내에서 QoE 모니터링을 사용 하도록 설정할 수도 있습니다. 제어판에서 다음 절차를 완료 합니다.

1.  **모니터링**을 클릭합니다.

2.  **경력 수준 데이터** 탭에서 **전역** 설정을 두 번 클릭 합니다.

3.  **QoE (환경 품질) 설정 편집** 창에서 **QoE 데이터 모니터링 사용** 을 선택 하 고 **커밋을**클릭 합니다.

앞서 설명한 것 처럼 위의 예에서는 전역 범위에서 모니터링을 사용 하도록 설정 합니다. 즉, 조직 전체에서 CDR 및 QoE 모니터링을 사용 하도록 설정 합니다. 또는 사이트 범위에서 별도의 CDR 및 QoE 구성 설정을 만든 다음 각 사이트에 대해 모니터링을 선택적으로 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 예를 들어 Redmond 사이트에 대해 CDR 모니터링을 사용 하도록 설정할 수는 있지만,이 경우에는 더블린 사이트에서 CDR 모니터링을 사용 하지 않도록 설정 해야 모니터링 구성 설정을 관리 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)항목을 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

