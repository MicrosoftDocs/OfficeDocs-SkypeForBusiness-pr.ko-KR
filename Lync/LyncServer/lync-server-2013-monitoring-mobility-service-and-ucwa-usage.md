---
title: 'Lync Server 2013: Mobility Service 및 c;에 대 한 모니터링 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8fbdd2e411f3613519278f807caed334955810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Lync Server 2013에서 모바일 서비스 및 c u에 대 한 모니터링 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-14_

지속적으로 Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)에서 사용 하는 CPU 및 메모리를 모니터링 해야 합니다. 사용 현황을 모니터링 하려면 다음을 사용할 수 있습니다.

**통합 커뮤니케이션 웹 API (c):**

  - IIS (인터넷 정보 서비스) 관리자의 **Lyncucwa** 작업자 프로세스입니다. **작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.

  - **CPU** 및 **프로세서** 성능 카운터

대부분의 배포의 경우에는 평균적으로 15% 미만 이어야 합니다. 메모리 사용량은 [Lync server 2013의 서버 메모리 용량 제한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 포함 되어야 합니다.

CPU 및 메모리 사용 카운터 외에, 다음 성능 카운터를 사용 하 여 서버가 요청에 따라 오버 로드 되는 시기를 결정할 수 있습니다.

  - **LS: 웹 – 제한 및 인증\\웹 –** 서버의 보류 중인 웹 요청 수를 나타내는 총 요청이 처리 중입니다. 이 카운터가 1만에 도달 하면 후속 요청이 실패 하 고 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 표시 됩니다.

  - **ASP.NET\\요청** (항상 0 이어야 함)

<div>


> [!NOTE]  
> 이러한 값을 충족 하거나 초과 하는 경우에는 웹 서비스를 호스트 하는 컴퓨터에 대 한 올바른 CPU 크기 조정, 코어 수 및 메모리에 대 한 용량 계획을 다시 확인 하 고 계산 해야 합니다.



</div>

**모바일 서비스 (Mcx)에 대해 다음을 수행 합니다.**

  - IIS (인터넷 정보 서비스) 관리자의 **Csintmcxapppool** 및 **csextmcxapppool** 작업자 프로세스 **작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.

  - **CPU** 및 **프로세서** 성능 카운터

대부분의 배포에서 이동성 서비스 CPU 사용량은 평균적으로 15% 미만 이어야 합니다. 메모리 사용량은 [Lync server 2013의 서버 메모리 용량 제한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 포함 되어야 합니다.

CPU 및 메모리 사용량 카운터 외에 다음 ASP.NET 성능 카운터를 사용하여 서버가 너무 많은 요청으로 인해 오버로드되었는지를 확인할 수 있습니다.

  - **ASP.NET v 2.0.50727\\Requests Current**-서버에서 보류 중인 웹 요청 수를 나타냅니다. 이 카운터가 5000에 도달 하면 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 표시 되 고 후속 요청이 실패 합니다.

  - **ASP.NET\\요청** (항상 0 이어야 함)

<div>


> [!NOTE]  
> 이러한 값을 충족 하거나 초과 하는 경우에는 웹 서비스를 호스트 하는 컴퓨터의 정확한 CPU 크기 조정, 코어 수 및 메모리에 대 한 용량 계획을 다시 계산 해야 합니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 서버 메모리 용량 제한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

