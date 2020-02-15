---
title: 'Lync Server 2013: Lync Server 2013 관리 팩 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2324d166ab43153cf37b71500da438e6db6b4b4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Lync Server 2013 관리 팩 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

System Center Operations Manager는 Windows 운영 체제 중 일부만 모니터링 하는 기능도 제공 합니다. 그러나 관리 팩, 즉 System Center Operations Manager에서 모니터링할 수 있는 항목을 결정 하는 소프트웨어, 해당 항목을 모니터링 하는 방법, 경고를 수행 하는 방법을 비롯 하 여 System Center Operations Manager의 기능을 확장할 수 있습니다. 트리거된 후 보고 됩니다. Microsoft Lync Server 2013에는 다음과 같은 기능을 제공 하는 2 개의 System Center Operations Manager 관리 팩이 포함 되어 있습니다.

  - 구성 요소 및 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp (사용자 관리 팩)는 이벤트 로그에 기록 되 고, 성능 카운터에서 등록 되거나, CDR (통화 정보 기록) 또는 경력 품질 (QoE)에 기록 된 Lync Server 문제를 추적 합니다. 데이터베이스. 중요 한 문제의 경우 System Center Operations Manager를 구성 하 여 전자 메일, 인스턴트 메시지 또는 SMS (Short Message Service) 메시징을 통해 관리자에 게 즉시 알릴 수 있습니다. SMS는 모바일 장치 간에 텍스트 메시지를 보내는 데 사용되는 기술입니다.
    
    <div>
    

    > [!NOTE]  
    > Operations Manager 알림을 구성 하는 방법에 대 한 자세한 내용은 TechNet 라이브러리에서 알림 구성 <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>를 참조 하세요.

    
    </div>

  - Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp (액티브 모니터링 팩)는 시스템에 로그온 하 고 인스턴트 메시지를 교환 하거나 공개 전화에 있는 전화기를 호출 하는 등의 주요 Lync Server 구성 요소를 사전에 테스트 합니다. 네트워크 (PSTN). 이러한 테스트는 Lync Server 가상 트랜잭션 cmdlet을 사용 하 여 수행 됩니다. 예를 들어 **Test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간의 인스턴트 메시징 대화를 시뮬레이션하는 데 사용됩니다. 이 시뮬레이션된 메시징 대화가 실패할 경우 알림이 생성됩니다.

Lync Server 2013에 포함 된 두 관리 팩에는 Microsoft Lync Server 2010에서 사용 되는 관리 팩에 대 한 많은 향상 된 기능이 포함 되어 있습니다. 예를 들어 Lync Server 2013 구성 요소 관리 팩은 Lync Server 자체를 모니터링 하는 것으로 제한 되지 않습니다. 구성 요소 관리 팩은 Lync Server에 대 한 이벤트 로그 및 성능 카운터를 모니터링 하는 것 외에도 다음과 같은 중요 한 항목에 대 한 경고의 성능을 추적 하 고 발행할 수 있습니다.

  - ****   인터넷 정보 서비스가 오프 라인 상태가 되 면 IIS (인터넷 정보 서비스) 알림이 실행 됩니다. Lync Server 웹 서비스는 IIS를 사용 하기 때문에이 작업이 중요 합니다.

  - ****   사용 가능한 메모리와 같은 시스템 리소스가 낮은 실행으로 시작 되 면 프로세스 사용 알림이 실행 됩니다. 이 경고는 Lync Server가 높은 시스템 사용에 대 한 책임이 없는 경우에도 발생 합니다.

  - **컴퓨터 오류 이벤트**   경고는 서버의 threatens를 다시 실행 하는 하드웨어 또는 소프트웨어 문제가 발생 하는 경우 발생 합니다. 예를 들어 서버에서 하드 디스크 오류가 발생 하는 경우 Lync Server 관리자에 게이에 대 한 알림이 표시 됩니다.

또한 이러한 새로운 관리 팩은 향상된 보고 기능을 제공합니다. Lync Server 2013에 대 한 새 보고서는 다음과 같습니다.

  - **End to end Scenario availability report**   이 보고서는 등록 또는 현재 상태의 주요 Lync Server 서비스에 대 한 가용성/가동 시간을 자세히 설명 합니다.

  - **용량 보고서**   이 보고서에서는 성능 카운터 정보를 사용 하 여 메모리 가용성 및 프로세서 사용량과 같은 시스템 구성 요소의 추세를 보여 줍니다.

  - **구성 요소 보고서**   이 보고서에는 Lync Server 구성 요소별 그룹화 된 최상위 알림 생성기가 나열 됩니다.

이러한 미리 정의 된 보고서 외에도 Lync Server 2013 관리 팩은 통화 안정성 (통화 정보 기록으로 측정 되는 메트릭) 및 QoE 상태 (경력에 따라 측정 되는 메트릭)에 대 한 경고를 자동으로 보고 합니다. 통화 정보 기록을 사용 하도록 설정한 경우 System Center Operations Manager 콘솔에서 다음 절차를 완료 하 여 통화 안정성 알림을 검토할 수 있습니다.

  - **모니터링**, **Microsoft Lync Server 2013 상태**, **통화 안정성 및 미디어 품질**을 차례로 확장한 후 **통화 안정성**을 클릭합니다.

경험 치 알림의 품질을 보려면 System Center Operations Manager 콘솔에서 다음 절차를 완료 하십시오.

  - **모니터링**, **Microsoft Lync Server 2013 상태**, **통화 안정성 및 미디어 품질**, **미디어 품질**을 차례로 확장합니다.

Lync Server 2013의 관리 팩은 이제 Microsoft Lync Server 2010에서 사용 되는 중앙 검색 메커니즘 대신 컴퓨터 수준 검색을 사용 합니다. 즉, 각 System Center 에이전트는 본질적으로 자체를 검색 하 고 중앙 관리 서버에 해당 사실을 보고 합니다. 컴퓨터 수준 검색을 사용 하면 시스템 센터 인프라를 간편 하 게 관리할 수 있고 lync server 관리 팩의 여러 버전 (예: lync server 2010 및 Lync Server 2013 관리 팩 용 관리 팩)을 사용 하도록 할 수도 있습니다. 존재.

</div>

<span> </span>

</div>

</div>

</div>

