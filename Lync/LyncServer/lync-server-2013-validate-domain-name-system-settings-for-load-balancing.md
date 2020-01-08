---
title: 'Lync Server 2013: 부하 분산을 위한 도메인 이름 시스템 설정 유효성 검사'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="ba8ab-102">Lync Server 2013에서 부하 분산에 대 한 도메인 이름 시스템 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ba8ab-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba8ab-103">_**마지막으로 수정한 주제:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="ba8ab-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="ba8ab-104">DNS 부하 분산에 사용 되는 FQDN을 지원 하려면 DNS를 프로 비전 하 여 풀의 모든 서버 (예: 192.168.1.1, 192.168.1.2 등)의 IP 주소에 대 한 풀 FQDN (pool01.contoso.com)을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-104">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="ba8ab-105">현재 배포 된 서버의 IP 주소만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-105">You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="ba8ab-106">또한 Edge 풀에 대해 DNS 부하 분산을 사용 하는 경우 다음 DNS 항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="ba8ab-107">Lync Server 액세스 Edge 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="ba8ab-108">각 항목은 그룹의 Edge 서버 중 하나에서 lync server 액세스 Edge 서비스의 FQDN (예: sip.contoso.com)을 Lync Server 액세스에 지 서비스의 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ba8ab-109">Lync Server 웹 회의 Edge 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="ba8ab-110">각 항목은 Lync Server 웹 회의 경계 서비스의 FQDN (예: webconf.contoso.com)을 풀의 Edge 서버 중 하나에서 Lync Server 웹 회의에 지 서비스의 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ba8ab-111">Lync Server 오디오/비디오에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="ba8ab-112">각 항목은 Lync Server 오디오/비디오 Edge 서비스의 FQDN (예: av.contoso.com)을 풀의 Edge 서버 중 하나에서 Lync Server 오디오/비디오에 지 서비스의 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ba8ab-113">Edge 풀의 내부 인터페이스에서 DNS 부하 분산을 사용 하려는 경우에는 Edge 풀의 내부 FQDN을 풀에 있는 각 서버의 IP 주소로 확인 하는 하나의 DNS 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="ba8ab-114">Dns가 DNS 로드 균형 조정을 위해 올바른 값을 반환 하는지 확인 하려면 nslookup 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="ba8ab-115">Nslookup을 사용 하 여 DNS 레코드의 모든 값을 반환 하려면 다음 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="ba8ab-116">Dns 부하 분산 구성에 사용 되는 모든 FQDN에 대해이 명령을 실행 하 여 DNS 부하 분산의 모든 레코드 집합에서 올바른 항목을 모두 반환 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba8ab-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

