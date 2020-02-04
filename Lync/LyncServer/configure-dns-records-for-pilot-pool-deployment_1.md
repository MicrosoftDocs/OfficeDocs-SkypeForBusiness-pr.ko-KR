---
title: 파일럿 풀 배포를 위한 DNS 레코드 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612857ba1a0ec599b0011ab5779cb7fc4b5a0615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="9f75c-102">파일럿 풀 배포를 위한 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="9f75c-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f75c-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="9f75c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="9f75c-104">Lync Server 2013 파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="9f75c-105">이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="9f75c-106">**DNS 호스트 A 레코드를 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="9f75c-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="9f75c-107">DNS (도메인 이름 시스템) 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="9f75c-108">도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 도메인을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="9f75c-109">**새 호스트 (A 또는 AAAA)** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="9f75c-110">**이름을**클릭 하 고 풀의 호스트 이름을 입력 합니다 (해당 레코드가 정의 되어 있고 A 레코드의 일부로 입력할 필요가 없는 영역에서 도메인 이름을 가정).</span><span class="sxs-lookup"><span data-stu-id="9f75c-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="9f75c-111">**Ip 주소**를 클릭 하 고 프런트 엔드 풀의 ip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="9f75c-112">**호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="9f75c-113">마쳤으면 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

