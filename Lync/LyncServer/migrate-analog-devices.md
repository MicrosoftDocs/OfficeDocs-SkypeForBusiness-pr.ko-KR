---
title: 아날로그 장치 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>아날로그 장치 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-16_

Lync Server는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다. Lync Server 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다. Lync Server 2010에서 Lync Server 2013으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다. Lync server Management Shell을 사용 하 여 먼저 Lync Server 2010 아날로그 장치와 연결 된 모든 연락처 개체를 검색 한 다음 해당 개체를 Lync Server 2013 풀로 이동 합니다.

<div>

## <a name="to-migrate-analog-devices"></a>아날로그 장치 마이그레이션

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄에 다음을 입력 합니다.
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  모든 연락처 개체가 Lync Server 2013 풀로 이동 되었는지 확인 합니다. 명령줄에 다음을 입력 합니다.
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  모든 연락처 개체가 Lync Server 2013 풀에 연결 되어 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

