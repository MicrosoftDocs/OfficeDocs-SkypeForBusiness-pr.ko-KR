---
title: Lync Server 2013 장치 하드웨어 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="5099e-102">Lync Server 2013의 장치 하드웨어 지원</span><span class="sxs-lookup"><span data-stu-id="5099e-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5099e-103">_**마지막으로 수정한 주제:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="5099e-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="5099e-104">IP 전화와 아날로그 장치를 배포 하기 전에 특정 하드웨어 구성을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="5099e-105">Lync Phone Edition을 실행 하는 IP 전화는 링크 계층 검색 프로토콜-LLDP (미디어 끝점 검색) 및 PoE (Power over Ethernet)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="5099e-106">LLDP를 활용 하려면 스위치가 IEEE 802.1 AB 및 ANSI/TIA-1057를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="5099e-107">PoE을 활용 하려면 스위치가 PoE 802.3 AF 또는 802.3을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="5099e-108">LLDP-MED-V를 사용 하도록 설정 하려면 관리자가 콘솔 창을 사용 하 여 LLDP를 사용 하도록 설정 하 고 올바른 음성 VLAN ID로 LLDP 네트워크 정책 설정을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="5099e-109">또한 배포에 아날로그 장치가 포함 되어 있는 경우 Lync Server를 사용 하도록 아날로그 게이트웨이를 구성 해야 하며 게이트웨이가 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="5099e-110">아날로그 전화 어댑터 (ATA)</span><span class="sxs-lookup"><span data-stu-id="5099e-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="5099e-111">PSTN 아날로그 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="5099e-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="5099e-112">PSTN 아날로그 게이트웨이를 포함 하는 Survivable 지사 기기</span><span class="sxs-lookup"><span data-stu-id="5099e-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="5099e-113">ATA와 통신 하는 PSTN 게이트웨이를 포함 하는 Survivable 지사 기기</span><span class="sxs-lookup"><span data-stu-id="5099e-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="5099e-114">아날로그 게이트웨이를 구성 하는 방법을 알아보려면 Lync Server 2010 TechNet 라이브러리 [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) 에서 "아날로그 장치 배포 계획"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5099e-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="5099e-115">(아날로그 장치는 lync server 2010에서와 동일한 방식으로 Lync Server 2013와 동일 하 게 작동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5099e-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5099e-116">스위치가이를 지 원하는 경우 향상 된 9-1-1 (E9-1)에 대 한 스위치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5099e-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

