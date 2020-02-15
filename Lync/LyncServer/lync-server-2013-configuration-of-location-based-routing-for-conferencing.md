---
title: 'Lync Server 2013: 회의를 위한 위치 기반 라우팅 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a959addbcd98e04d336ba380676399dbff2f586b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 회의를 위한 위치 기반 라우팅 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-09-11_

위치 기반 라우팅 회의 응용 프로그램은 Lync Server 2013 위치 기반 라우팅의 구성을 따릅니다. 기본 구성은 다음과 같습니다.

  - 모임에 참가 하는 참가자의 위치는 해당 네트워크 사이트에 따라 결정 됩니다. 위치 기반 라우팅을 적용 하기 위해서는 네트워크 사이트 및 연결 된 네트워크 서브넷을 Lync Server에서 정의 해야 합니다.

  - 위치 기반 모임 라우팅을 적용 하려면 위치 기반 라우팅을 위해 Lync 참가자를 사용 하도록 설정 해야 합니다.

  - 모임 참가를 위한 PSTN 끝점의 위치 기반 라우팅을 적용 하려면 위치 기반 라우팅을 위해 PSTN 끝점을 연결 하는 데 사용 되는 SIP 트렁크를 구성 해야 합니다.

Lync Server 2013 위치 기반 라우팅 배포 및 구성에 대 한 자세한 내용은 [위치 기반 라우팅](lync-server-2013-configuring-location-based-routing.md)구성를 참조 하세요.

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>위치 기반 라우팅 회의 응용 프로그램 사용

위치 기반 라우팅 회의 응용 프로그램은 기본적으로 사용 하지 않도록 설정 됩니다. 이 응용 프로그램을 사용 하도록 설정 하기 전에 응용 프로그램에 할당할 올바른 우선 순위를 결정 해야 합니다. 이 우선 순위를 확인 하려면 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.

Get-CsServerApplication-Identity Service: 등록자:\<풀 FQDN\>

이 cmdlet에서 \<풀 FQDN\> 은 위치 기반 라우팅 회의 응용 프로그램을 사용 하도록 설정 하는 풀입니다.

이 cmdlet은 Lync Server에서 호스트 되는 응용 프로그램의 목록과 각 작업에 대 한 우선 순위 값을 반환 합니다. 위치 기반 라우팅 회의 응용 프로그램에 "DefaultRouting", "ExumRouting" 및 "OutboundRouting" 응용 프로그램 보다 더 작은 우선 순위 값이 할당 되어야 합니다. 위치 기반 라우팅 회의 응용 프로그램에 "UdcAgent" 응용 프로그램의 우선 순위 값 보다 1 포인트가 더 높은 우선 순위 값을 할당 하는 것이 좋습니다.

예를 들어 "UdcAgent" 응용 프로그램의 우선 순위 값이 "2" 인 경우 "DefaultRouting" 응용 프로그램의 우선 순위 값은 "9"이 고 "ExumRouting" 응용 프로그램의 우선 순위 값은 "10"이 고 "OutboundRouting" 응용 프로그램의 우선 순위 값은 "10" 이면 위치 기반 라우팅 회의 응용 프로그램에 우선 순위 값 "3"을 할당 해야 합니다. 이렇게 하면 응용 프로그램의 우선 순위가 다른 응용 프로그램 (우선 순위: 0 ~ 1), "UdcAgent" (Priority: 2), 위치 기반 라우팅 회의 응용 프로그램 (우선 순위: 3), 기타 응용 프로그램 (우선 순위: 4 ~ 8), " DefaultRouting "(Priority: 9)," ExumRouting "(Priority: 10) 및" OutboundRouting "(Priority: 11)

위치 기반 라우팅 회의 응용 프로그램에 대 한 올바른 우선 순위 값을 찾은 후에 위치 기반 라우팅을 사용 하도록 설정 된 사용자를 가정 하는 각 프런트 엔드 풀 또는 Standard Edition 서버에 대해 다음 cmdlet을 입력 합니다.

새-CsServerApplication-Identity Service: 등록자:\<Pool FQDN\>/LBRouting-Priority \<응용 프로그램\> 우선 순위-사용 $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting

예:

새-CsServerApplication-Identity Service:Registrar:Ls2013-2lbrpool. s t s/LBRouting-Priority 3-사용 $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting

이 cmdlet을 사용한 후에는 풀의 모든 프런트 엔드 서버 또는 위치 기반 라우팅 회의 응용 프로그램을 사용할 수 있는 Standard Edition 서버를 다시 시작 합니다.

<div>


> [!IMPORTANT]  
> 해당 하는 풀 또는 Standard Edition 서버에 있는 모든 프런트 엔드 서버가 다시 시작 될 때 까지는 전화 회의 또는 문의 후 전송에 대 한 위치 기반 라우팅 enforcements 적용 되지 않습니다.



</div>

위치 기반 라우팅 회의 응용 프로그램을 성공적으로 사용 하도록 설정 하 고 해당 하는 모든 Lync 서버를 다시 시작한 후에는 Lync 사용자가 위치 기반 라우팅을 사용 하도록 설정한 모든 회의가 모니터링 되어 PSTN 유료 바이패스를 방지할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

