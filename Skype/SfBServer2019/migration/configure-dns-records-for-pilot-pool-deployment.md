---
title: 파일럿 풀 배포에 대한 DNS 레코드 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 파일럿 풀을 배포하기 전에 파일럿 풀에 대한 DNS 호스트 A 항목을 업데이트해야 합니다. 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754058"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="dc6c5-104">파일럿 풀 배포에 대한 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="dc6c5-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="dc6c5-105">파일럿 풀을 배포하기 전에 파일럿 풀에 대한 DNS 호스트 A 항목을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="dc6c5-106">이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="dc6c5-107">DNS 호스트 A 레코드를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="dc6c5-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="dc6c5-108">DNS(Domain Name System) 서버에서 **시작**, **관리 도구** 를 차례로 클릭한 다음 **DNS** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="dc6c5-109">도메인의 콘솔 트리에서 정방 지원 영역 확장을 확장한 다음 비즈니스용 Skype 서버 2019가 설치될 도메인을 마우스 오른쪽 단추로 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="dc6c5-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="dc6c5-110">**새 호스트(A 또는 AAAA)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="dc6c5-111">이름을 **클릭하고** 비즈니스용 Skype 서버 2019 풀의 호스트 이름을 입력합니다(도메인 이름은 레코드가 정의된 영역으로 가정되어 A 레코드의 일부로 입력할 필요가 없습니다).</span><span class="sxs-lookup"><span data-stu-id="dc6c5-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="dc6c5-112">**IP 주소를 클릭한** 다음 프런트 엔드 풀의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="dc6c5-113">**호스트 추가** 를 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="dc6c5-114">작업을 마쳤으면 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6c5-114">When you are finished, click **Done**.</span></span>
    

