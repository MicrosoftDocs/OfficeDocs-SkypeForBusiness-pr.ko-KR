---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 방화벽 및 포트 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 514c93cff5d3050ae94d1057b57fb703e92696ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5ed13-102">Lync Server 2013에서 외부 사용자 액세스에 대 한 방화벽 및 포트 구성</span><span class="sxs-lookup"><span data-stu-id="5ed13-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ed13-103">_**마지막으로 수정 된 항목:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="5ed13-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="5ed13-104">방화벽 및 포트를 구성하려면 에지 서버, 역방향 프록시 서버 및 하드웨어 부하 분산 장치(DNS 부하 분산을 사용하지 않는 확장된 배포의 경우)에 대해 방화벽과 포트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed13-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="5ed13-105">이 섹션에서는 모든 에지 서버 구성 요소의 방화벽, 포트 요구 사항에 대한 정보 및 에지 서버에 대한 방화벽 포트 구성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed13-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="5ed13-106">역방향 프록시 서버에 대 한 포트를 구성 하는 방법에 대 한 자세한 내용은 [Setting up reverse proxy servers For Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ed13-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="5ed13-107">확장 된에 지 토폴로지를 배포 하 고 DNS 부하 분산 대신 하드웨어 부하 분산을 사용 하는 경우, 하드웨어 부하 분산 장치를 구성 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 하드웨어 부하 분산 장치로 확장 된 통합에 지](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ed13-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5ed13-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ed13-108">See Also</span></span>


[<span data-ttu-id="5ed13-109">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="5ed13-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

