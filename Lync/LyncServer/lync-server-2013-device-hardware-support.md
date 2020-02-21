---
title: Lync Server 2013 장치 하드웨어 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6786d22d81f6b78d1e551d05f3d908876ca3068
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Lync Server 2013의 장치 하드웨어 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-14_

IP 전화와 아날로그 장치를 배포하려면 특정 하드웨어 구성을 설정해야 합니다.

Lync Phone Edition을 실행 하는 IP 전화는 링크 계층 검색 프로토콜-LLDP (미디어 끝점 검색) 및 PoE (Power over Ethernet)를 지원 합니다.LLDP-MED를 활용하려면 스위치가 IEEE802.1AB 및 ANSI/TIA-1057을 지원해야 합니다. PoE를 활용하려면 스위치가 PoE802.3AF 또는 802.3at를 지원해야 합니다.

LLDP-MED를 사용하도록 설정하려면 관리자가 스위치 콘솔 창을 사용하여 LLDP를 사용하도록 설정하고 올바른 음성 VLAN ID를 사용하여 LLDP-MED 네트워크 정책을 설정해야 합니다.

또한 배포에 아날로그 장치가 포함 된 경우 Lync Server를 사용 하도록 아날로그 게이트웨이를 구성 해야 하며 게이트웨이는 다음 중 하나 여야 합니다.

  - ATA(Analog Telephone Adapter)

  - PSTN 아날로그 게이트웨이

  - PSTN 아날로그 게이트웨이가 포함된 SBA(Survivable Branch Appliance)

  - ATA를 사용하여 통신하는 PSTN 아날로그 게이트웨이가 포함된 SBA(Survivable Branch Appliance)

아날로그 게이트웨이를 구성 하는 방법에 대 한 자세한 내용은 Lync Server 2010 TechNet 라이브러리 [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) 의 "아날로그 장치 배포 계획"을 참조 하십시오. (아날로그 장치는 lync Server 2010에서와 동일한 방식으로 Lync Server 2013에서 동일 하 게 작동 합니다.)

<div>


> [!IMPORTANT]  
> 스위치에서 지원하는 경우 E9-1-1(Enhanced 9-1-1)을 사용하도록 스위치를 구성할 수 있습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

