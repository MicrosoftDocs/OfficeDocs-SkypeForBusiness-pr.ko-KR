---
title: 'Lync Server 2013: 서버 메모리 용량 제한 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45600ed9c822851c89b13cb776bbc58464decde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Lync Server 2013의 서버 메모리 용량 제한 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 용량 계획을 참조 하는이 항목의 정보는 Lync 2010 모바일 클라이언트 및 모바일 서비스 (Mcx)에만 해당 됩니다. Lync 2013 모바일 클라이언트에서 사용 하는 통합 커뮤니케이션 웹 API (WA)에 대 한 용량 계획은 Lync Server 2013, 계획 도구에서 제공 됩니다.



</div>

두 개의 모바일 성능 카운터를 사용 하 여 현재 사용량을 확인 하 고, Lync Server 2013 Mobility Service (Mcx)에 대 한 용량을 계획 하 고, c u c e 2의 메모리 사용량을 모니터링할 수 있습니다. (C)의 경우 카운터 범주는 **LS: WEB – wa**입니다. 모바일 서비스 (Mcx)의 경우 카운터는 category **LS: 웹-모바일 통신 서비스**에 있습니다. 모니터링할 카운터는 다음과 같습니다.

  - 현재 활성 상태인 구독 (활성 현재 **상태 구독이**있음), 활성 현재 상태 구독이 있는 모바일 서비스 (mcx) (always-연결 된 모바일 사용자 수)

  - **현재 활성 세션 수**: (c) 또는 모바일 서비스를 통해 등록 된 현재 끝점 수

활성 현재 상태 구독 및 **현재 활성 세션 수** 와 현재 활성 **상태인 세션 수** 의 차이가 시간에 비해 작으면 대부분의 모바일 장치 사용자에 게 Android 또는 Nokia 모바일 장치와 같은 항상 연결 된 장치 (mcx에만 해당)가 있음을 의미 합니다. (C u c) 항상 연결 된 장치에는 Lync 2013 모바일 클라이언트를 실행 하는 Apple 및 Android 장치가 포함 됩니다. 현재 활성 상태인 **세션 수가** 활성 현재 상태 구독을 사용 하는 현재 **활성 세션 수**를 초과 하는 경우,이는 더 많은 사용자가 Mcx에 Apple IOS 장치 또는 Windows Phone과 같은 백그라운드 끝점 장치를 사용 한다는 것을 나타냅니다. Windows Phone은이를 등록 하는 유일한 Lync 2013 모바일 클라이언트입니다.

현재 **활성 상태인 구독** 및 예상 사용량, 용량 계획 결과 및 모바일 서비스 및 기타 프런트 엔드 서버 카운터의 지속적인 모니터링을 기반으로 하는 활성 세션 **카운트 성능 카운터** 에 대 한 제한을 설정 해야 합니다. 설정한 제한을 사용 하면 서버 용량을 평가 하 고 용량을 초과 하면 경고를 올릴 수 있습니다.

적절 한 제한을 결정 하려면 먼저 모바일 서비스에 대해 프런트 엔드 서버에서 사용할 수 있는 메모리 양을 확인 해야 합니다. 다음 수식에 따라 카운터를 모니터링 하 여 추가 용량을 계획 해야 하는 시기를 결정 합니다.

Mcx Mobility Service에서 사용 되는 총 메모리 (MB) = 164 + (400 + 134)/ \* **1024 현재 활성 세션 수 (활성** 현재 상태 구독 포함) \* + 400/1024 (현재**활성** 세션 수-현재 활성 **상태인 활성 세션 수**)

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 Capacity 계산기는 계획을 사용 하 여 CPU, 메모리, 하드 드라이브 등의 서버에 대 한 요구 사항을 결정 하는 데 사용할 수 있는 모든 수식이 미리 채워진 스프레드시트입니다. 스프레드시트 및 관련 문서는 다음 위치에서 다운로드할 수 있습니다.<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

프런트 엔드 서버에는 장애 조치 (failover) 상황에서 모바일 서비스를 지 원하는 데 충분 한 사용 가능한 메모리가 필요 합니다. **사용 가능한 메모리\\mb** 카운터를 사용 하 여 프런트 엔드 서버의 현재 사용 가능한 메모리를 모니터링 하거나, 앞에서 설명한 수식을 사용 하 여 모바일 서비스에서 사용할 수 있는 메모리 양을 계획할 수 있습니다.

예상 되는 모바일 사용자 수를 계획할 때 프런트 엔드 서버에서 사용할 수 있는 메모리 양이 1500 MB 보다 작으면 모바일 서비스를 지원 하기 위해 하드웨어를 더 추가 해야 합니다. 자세한 내용은 작업 설명서의 [Lync Server 2013에서 성능에 맞게 모바일 기능 모니터링](lync-server-2013-monitoring-mobility-for-performance.md) 을 참조 하십시오.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 성능에 대 한 모바일 기능 모니터링](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

