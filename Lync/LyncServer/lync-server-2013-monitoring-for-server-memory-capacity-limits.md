---
title: 'Lync Server 2013: 서버 메모리 용량 한도 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Lync Server 2013의 서버 메모리 용량 한도 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 용량 계획을 지칭 하는이 항목의 정보는 Lync 2010 모바일 클라이언트 및 모바일 서비스 (Mcx)에만 해당 됩니다. Lync 2013 모바일 클라이언트에서 사용 하는 통합 커뮤니케이션 웹 API (c)에 대 한 용량 계획은 Lync Server 2013, 계획 도구에서 제공 합니다.



</div>

두 개의 이동성 성능 카운터를 사용 하 여 현재 사용량을 확인 하 고, Lync (서버 2013 Mobility Services)의 용량을 계획 하는 데 도움이 되 고,이에 대 한 메모리 사용량을 모니터링할 수 있습니다. (A)의 카운터 범주는 **LS: WEB – 웹-의 wa**입니다. 모바일 서비스 (Mcx)의 경우 카운터는 **웹-모바일 통신 서비스**범주 아래에 있습니다. 모니터링할 카운터는 다음과 같습니다.

  - **활성 현재 상태 구독이 포함 된 현재 활성 상태인 세션 수**입니다 .이는 현재 현재 상태 구독이 있는 모바일 서비스 (mcx) 또는 (항상 연결 된 모바일 사용자의 수)입니다.

  - 현재 **활성화 된 세션 수**, 즉,이 수는 인천 Wa 또는 모바일 서비스를 통해 등록 된 현재 종점입니다.

활성 현재 상태 구독이 있고 **현재 활성 세션 수가** **있는 현재 활성 세션 수** 의 차이가 적은 시간에 해당 하는 경우, 대부분의 모바일 장치 사용자는 Android 또는 Nokia 모바일 장치와 같이 항상 연결 된 장치를 사용 하는 것을 의미 합니다 (mcx에만 해당). 연결 된 장치에는 항상 Lync 2013 모바일 클라이언트를 실행 하는 Apple 및 Android 장치가 포함 되어 있습니다. 현재 활성 상태인 **세션 수가** **활성 현재 상태 구독을 사용 하는 현재 활성 세션**수보다 훨씬 높은 경우이는 더 많은 사용자가 Mcx에서 Apple IOS 장치 또는 Windows Phone과 같은 백그라운드 끝점 장치를 사용 하 고 있음을 나타냅니다. (Windows Phone은이를 등록 하는 유일한 Lync 2013 모바일 클라이언트입니다.)

현재 활성 **상태인 세션 수** 에 대 한 제한을 설정 하 고 예상 사용량, 용량 계획 결과, 이동성 서비스 및 기타 프런트 엔드 서버 카운터에 대 한 지속적인 모니터링을 기준으로 현재 활성 세션 **수** 성능 카운터를 지정 해야 합니다. 용량을 초과한 경우 서버 용량을 평가 하 고 경고를 발생 시킬 수 있는 제한을 설정 해야 합니다.

적절 한 제한을 결정 하려면 먼저 모바일 서비스에 대 한 프런트 엔드 서버에서 사용할 수 있는 메모리 크기를 결정 해야 합니다. 카운터를 모니터링 하 여 다음 수식에 따라 추가 용량을 계획 해야 하는 시기를 결정 합니다.

Mcx Mobility Service (MB) = 164 + (400 + 134)/1024 \* **현재 활성 상태인 세션 수에 활성 현재 상태 구독이** 있습니다. + 400/1024 \* (**현재 활성** 상태인 세션 수는 활성 **상태 구독이 있는**활성 세션 수)입니다.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 용량 계산기는 계획자를 사용 하 여 CPU, 메모리, 하드 드라이브 등 서버에 대 한 요구 사항을 결정할 수 있는 모든 수식으로 미리 채워져 있는 스프레드시트입니다. 스프레드시트 및 관련 문서는 다음 위치에서 다운로드할 수 있습니다.<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

프런트 엔드 서버는 장애 조치 상황에서 모바일 서비스를 지원 하기에 충분 한 사용 가능한 메모리가 필요 합니다. **사용 가능한 메모리\\mb** 카운터를 사용 하 여 프런트 엔드 서버에서 현재 사용 가능한 메모리를 모니터링 하거나, 앞에서 설명한 수식을 사용 하 여 모바일 서비스에 사용할 메모리 양을 계획할 수 있습니다.

프런트 엔드 서버에서 사용할 수 있는 메모리 양이 1500 MB 미만이 면 예상 이동성 사용자 수를 계획 하는 경우 모바일 서비스를 지원 하기 위해 더 많은 하드웨어를 추가 해야 합니다. 자세한 내용은 운영 설명서의 [Lync Server 2013에서 성능에 대 한 이동성 모니터링](lync-server-2013-monitoring-mobility-for-performance.md) 을 참조 하세요.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 성능에 대 한 이동성 모니터링](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

