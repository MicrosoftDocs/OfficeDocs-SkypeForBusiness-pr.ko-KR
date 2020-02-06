---
title: 파일럿 풀 배포를 위한 DNS 레코드 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다. 이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813856"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="9bb6b-104">파일럿 풀 배포를 위한 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="9bb6b-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="9bb6b-105">파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="9bb6b-106">이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="9bb6b-107">DNS 호스트 A 레코드를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="9bb6b-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="9bb6b-108">DNS (도메인 이름 시스템) 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="9bb6b-109">도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 비즈니스용 Skype 서버 2019이 설치 될 도메인을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="9bb6b-110">**새 호스트 (A 또는 AAAA)** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="9bb6b-111">**Name**을 클릭 하 고 비즈니스용 Skype Server 2019 풀의 호스트 이름을 입력 합니다 (해당 레코드가 정의 되어 있고 A 레코드의 일부로 입력할 필요가 없는 영역에서 도메인 이름을 가정).</span><span class="sxs-lookup"><span data-stu-id="9bb6b-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="9bb6b-112">**Ip 주소**를 클릭 한 다음 프런트 엔드 풀의 ip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="9bb6b-113">**호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="9bb6b-114">마쳤으면 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb6b-114">When you are finished, click **Done**.</span></span>
    

