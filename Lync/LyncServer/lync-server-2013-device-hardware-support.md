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
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="8d529-102">Lync Server 2013의 장치 하드웨어 지원</span><span class="sxs-lookup"><span data-stu-id="8d529-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d529-103">_**마지막으로 수정 된 항목:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="8d529-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="8d529-104">IP 전화와 아날로그 장치를 배포하려면 특정 하드웨어 구성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="8d529-105">Lync Phone Edition을 실행 하는 IP 전화는 링크 계층 검색 프로토콜-LLDP (미디어 끝점 검색) 및 PoE (Power over Ethernet)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="8d529-106">LLDP-MED를 활용하려면 스위치가 IEEE802.1AB 및 ANSI/TIA-1057을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="8d529-107">PoE를 활용하려면 스위치가 PoE802.3AF 또는 802.3at를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="8d529-108">LLDP-MED를 사용하도록 설정하려면 관리자가 스위치 콘솔 창을 사용하여 LLDP를 사용하도록 설정하고 올바른 음성 VLAN ID를 사용하여 LLDP-MED 네트워크 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="8d529-109">또한 배포에 아날로그 장치가 포함 된 경우 Lync Server를 사용 하도록 아날로그 게이트웨이를 구성 해야 하며 게이트웨이는 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="8d529-110">ATA(Analog Telephone Adapter)</span><span class="sxs-lookup"><span data-stu-id="8d529-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="8d529-111">PSTN 아날로그 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="8d529-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="8d529-112">PSTN 아날로그 게이트웨이가 포함된 SBA(Survivable Branch Appliance)</span><span class="sxs-lookup"><span data-stu-id="8d529-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="8d529-113">ATA를 사용하여 통신하는 PSTN 아날로그 게이트웨이가 포함된 SBA(Survivable Branch Appliance)</span><span class="sxs-lookup"><span data-stu-id="8d529-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="8d529-114">아날로그 게이트웨이를 구성 하는 방법에 대 한 자세한 내용은 Lync Server 2010 TechNet 라이브러리 [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) 의 "아날로그 장치 배포 계획"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d529-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="8d529-115">(아날로그 장치는 lync Server 2010에서와 동일한 방식으로 Lync Server 2013에서 동일 하 게 작동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="8d529-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8d529-116">스위치에서 지원하는 경우 E9-1-1(Enhanced 9-1-1)을 사용하도록 스위치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d529-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

