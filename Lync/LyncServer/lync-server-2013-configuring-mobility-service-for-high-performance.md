---
title: 'Lync Server 2013: 고성능을 위한 이동성 서비스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Lync Server 2013에서 고성능을 위한 모바일 서비스 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-17_

<div>


> [!IMPORTANT]  
> 이 항목은 Lync Server 2013 Mobility Service (Mcx)에만 적용 되며 Lync Server 2013의 누적 업데이트에서 제공 되는 통합 커뮤니케이션 웹 API (c 2 월 2013)에는 적용 되지 않습니다.



</div>

IIS (인터넷 정보 서비스) 7.5에서 모바일 서비스 (Mcx)를 설치 하면 모바일 서비스 설치 관리자가 프런트 엔드 서버에서 일부 성능 설정을 구성 합니다. 이동성에 IIS 7.5를 사용 하는 것이 좋습니다. 설정은 최대 동시 사용자 요청 수와 모바일 서비스에 허용 되는 최대 스레드 수에 영향을 줍니다.

다음은 성능 설정에 대 한 내용입니다.

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5에서 Mcx에 대 한 설정

1.  **maxConcurrentThreadsPerCPU** 가 0으로 설정 됩니다.

2.  **maxConcurrentRequestsPerCPU** 가 0으로 설정 됩니다.

3.  ASP.NET 프로세스 모델이 AutoConfig로 설정 됩니다 (IIS 7.5에만 해당).

4.  Http.sys 큐 한도가 1000 (기본적으로)으로 설정 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

