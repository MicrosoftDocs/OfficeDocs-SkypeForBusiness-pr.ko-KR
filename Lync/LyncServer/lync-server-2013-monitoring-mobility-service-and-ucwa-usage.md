---
title: 'Lync Server 2013: 모바일 서비스 및 기타 WA 사용 현황 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Lync Server 2013에서 모바일 서비스 및이에 대 한 사용 현황 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-14_

지속적으로 Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)에 사용 되는 CPU와 메모리를 모니터링 해야 합니다. 사용 현황을 모니터링 하려면 다음을 사용할 수 있습니다.

**통합 커뮤니케이션 웹 API (c):**

  - IIS (인터넷 정보 서비스) 관리자의 **L C인천** 작업자 프로세스입니다. **작업자 프로세스** 창에서 **CPU%** 및 **전용 바이트 (KB)** 열을 확인 합니다.

  - **CPU** 및 **프로세서** 성능 카운터입니다.

대부분의 배포의 경우 fwa CPU 사용이 평균적으로 15% 미만 이어야 합니다. 메모리 사용은 [Lync server 2013의 서버 메모리 용량 제한에 대 한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 속해야 합니다.

CPU 및 메모리 사용 카운터 외에도 다음 성능 카운터를 사용 하 여 서버에서 요청을 오버 로드할 때이를 확인할 수 있습니다.

  - **LS: 웹 – 제한 및 인증\\웹 –** 서버의 보류 중인 웹 요청 수를 나타내는 총 요청이 처리 중입니다. 이 카운터가 1만에 도달 하면 후속 요청이 실패 하 고 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 나타납니다.

  - **ASP.NET\\요청 대기열** (항상 0 이어야 함).

<div>


> [!NOTE]  
> 이러한 값을 만족 하거나 초과 하는 경우 적절 한 CPU 크기 조정에 대 한 용량 계획을 다시 계산 하 고 웹 서비스를 호스팅하는 컴퓨터에 대 한 코어 및 메모리의 수를 확인 해야 합니다.



</div>

**모바일 서비스 (Mcx)의 경우:**

  - IIS (인터넷 정보 서비스) 관리자의 **Csintmcxapppool** 및 **csextmcxapppool** 작업자 프로세스입니다. **작업자 프로세스** 창에서 **CPU%** 및 **전용 바이트 (KB)** 열을 확인 합니다.

  - **CPU** 및 **프로세서** 성능 카운터입니다.

대부분의 배포의 경우 모바일 서비스 CPU 사용량은 평균적으로 15% 미만 이어야 합니다. 메모리 사용은 [Lync server 2013의 서버 메모리 용량 제한에 대 한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 속해야 합니다.

CPU 및 메모리 사용 카운터 외에도 다음 ASP.NET 성능 카운터를 사용 하 여 서버에서 요청을 오버 로드할 때이를 확인할 수 있습니다.

  - 서버에서 보류 중인 웹 요청 수를 나타내는 **ASP.NET v 2.0.50727\\Requests Current** 이 카운터가 5000에 도달 하면 "503-서비스를 사용할 수 없음" 오류 메시지와 함께 후속 요청이 실패 하 게 됩니다.

  - **ASP.NET\\요청 대기열** (항상 0 이어야 함).

<div>


> [!NOTE]  
> 이러한 값을 만족 하거나 초과 하는 경우 적절 한 CPU 크기 조정, 코어 수, 웹 서비스를 호스팅하는 컴퓨터의 메모리에 대 한 용량 계획을 다시 계산 해야 합니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 서버 메모리 용량 한도 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

