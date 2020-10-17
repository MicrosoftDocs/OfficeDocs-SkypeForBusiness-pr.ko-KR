---
title: 'Lync Server 2013: 음성 사용량 및 트래픽 예상'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9541619578c69a571d93d8c4960b3ecb33476027
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532005"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Lync Server 2013의 음성 사용량 및 트래픽 예상

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-07_

Microsoft Lync Server 2013, 계획 도구에서는 다음 메트릭을 사용 하 여 각 사이트의 사용자 트래픽과 해당 트래픽을 지 원하는 데 필요한 포트 수를 예측 합니다.

  - <span></span>  
    **경량 트래픽**(매시간 사용자당 PSTN 호출 하나)의 경우 포트당 사용자 15명

  - <span></span>  
    **중간 정도의 트래픽**(매시간 사용자당 PSTN 호출 두 개)의 경우 포트당 사용자 10명

  - <span></span>  
    **높은 트래픽**(매시간 사용자당 PSTN 호출 세 개 이상)의 경우 포트당 사용자 5명

그런 다음 포트 수에 따라 필요한 중재 서버 및 게이트웨이 수가 결정 됩니다. 대부분의 조직에서 배포를 고려하는 PSTN(공중 전화망) 게이트웨이의 크기는 포트 2개에서 포트 960개까지 다양합니다. 훨씬 더 큰 게이트웨이도 있지만 이러한 게이트웨이는 주로 전화 서비스 공급자가 사용합니다.

예를 들어 사용자 수가 1만 명이고 트래픽은 중간 정도인 조직의 경우 1,000개의 포트가 필요합니다. 필요한 게이트웨이 수는 총 게이트웨이 용량에 따라 결정되는 필요한 총 포트 수와 같습니다.

</div>

<span> </span>

</div>

</div>

</div>

