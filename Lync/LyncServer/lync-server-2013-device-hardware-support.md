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
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Lync Server 2013의 장치 하드웨어 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-14_

IP 전화와 아날로그 장치를 배포 하기 전에 특정 하드웨어 구성을 준비 해야 합니다.

Lync Phone Edition을 실행 하는 IP 전화는 링크 계층 검색 프로토콜-LLDP (미디어 끝점 검색) 및 PoE (Power over Ethernet)를 지원 합니다.LLDP를 활용 하려면 스위치가 IEEE 802.1 AB 및 ANSI/TIA-1057를 지원 해야 합니다. PoE을 활용 하려면 스위치가 PoE 802.3 AF 또는 802.3을 지원 해야 합니다.

LLDP-MED-V를 사용 하도록 설정 하려면 관리자가 콘솔 창을 사용 하 여 LLDP를 사용 하도록 설정 하 고 올바른 음성 VLAN ID로 LLDP 네트워크 정책 설정을 해야 합니다.

또한 배포에 아날로그 장치가 포함 되어 있는 경우 Lync Server를 사용 하도록 아날로그 게이트웨이를 구성 해야 하며 게이트웨이가 다음 중 하나 여야 합니다.

  - 아날로그 전화 어댑터 (ATA)

  - PSTN 아날로그 게이트웨이

  - PSTN 아날로그 게이트웨이를 포함 하는 Survivable 지사 기기

  - ATA와 통신 하는 PSTN 게이트웨이를 포함 하는 Survivable 지사 기기

아날로그 게이트웨이를 구성 하는 방법을 알아보려면 Lync Server 2010 TechNet 라이브러리 [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) 에서 "아날로그 장치 배포 계획"을 참조 하세요. (아날로그 장치는 lync server 2010에서와 동일한 방식으로 Lync Server 2013와 동일 하 게 작동 합니다.)

<div>


> [!IMPORTANT]  
> 스위치가이를 지 원하는 경우 향상 된 9-1-1 (E9-1)에 대 한 스위치를 구성할 수 있습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

