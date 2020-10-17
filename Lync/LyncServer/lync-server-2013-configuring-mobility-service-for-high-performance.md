---
title: 'Lync Server 2013: 고성능을 위한 모바일 서비스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d587444dfd1fbe4fae8898438a51bc9cfb2b5ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526955"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Lync Server 2013에서 고성능을 위한 모바일 서비스 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-17_

<div>


> [!IMPORTANT]  
> 이 항목은 Lync server 2013 Mobility Service (Mcx)에만 적용 되며 Lync Server 2013에 대 한 누적 업데이트: 2 월 2013에 제공 되는 통합 커뮤니케이션 웹 API (WA)에는 적용 되지 않습니다.



</div>

IIS (인터넷 정보 서비스) 7.5에 모바일 서비스 (Mcx)를 설치 하면 모바일 서비스 설치 관리자가 프런트 엔드 서버에서 일부 성능 설정을 구성 합니다. 모바일 기능에는 IIS 7.5를 사용하는 것이 좋습니다. 이러한 설정은 최대 동시 사용자 요청 수 및 Mobility Service에 대해 허용되는 최대 스레드 수에 영향을 줍니다.

다음은 성능 설정에 대 한 예제입니다.

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5의 Mcx에 대 한 설정

1.  **maxConcurrentThreadsPerCPU**는 영(0)으로 설정됩니다.

2.  **maxConcurrentRequestsPerCPU**는 영(0)으로 설정됩니다.

3.  ASP.NET 프로세스 모델은 AutoConfig로 설정됩니다(IIS 7.5에만 해당).

4.  HTTP.sys 큐 제한은 기본적으로 1,000으로 설정됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

