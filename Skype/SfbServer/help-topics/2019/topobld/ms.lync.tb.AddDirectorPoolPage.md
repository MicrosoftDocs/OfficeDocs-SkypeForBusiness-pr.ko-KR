---
title: 디렉터 풀 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 디렉터 풀 FQDN을 정의 하려면 부하 분산 된 풀 또는 단일 컴퓨터 풀에 두 개 이상의 디렉터로 구성 되는 다중 컴퓨터 풀을 선택 합니다. 또한 디렉터 풀 또는 단일 디렉터의 FQDN에 연결 하는 데 사용 되는 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다. 디렉터 컴퓨터 풀의 경우 하드웨어 로드 균형 조정기의 가상 IP에 대 한 DNS (도메인 이름 시스템) 항목이 나 DNS 부하 분산에 대 한 공유 DNS 항목이 될 수 있습니다.
ms.openlocfilehash: 04fe48423b79a0c5912811b8ce7de67c60594847
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197600"
---
# <a name="add-director-pool"></a><span data-ttu-id="50df5-105">디렉터 풀 추가</span><span class="sxs-lookup"><span data-stu-id="50df5-105">Add Director Pool</span></span>
 
<span data-ttu-id="50df5-106">**디렉터 풀 FQDN을 정의**하려면 부하 분산 된 풀 또는 **단일 컴퓨터 풀**에 두 개 이상의 디렉터로 구성 되는 **다중 컴퓨터 풀** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="50df5-107">또한 디렉터 풀 또는 단일 디렉터의 FQDN에 연결 하는 데 사용 되는 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="50df5-108">디렉터 컴퓨터 풀의 경우 하드웨어 로드 균형 조정기의 가상 IP에 대 한 DNS (도메인 이름 시스템) 항목이 나 DNS 부하 분산에 대 한 공유 DNS 항목이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="50df5-109">나중에 디렉터 풀을 구현 하려는 경우 **여러 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="50df5-110">풀이 부하 분산 되는 두 대 이상의 컴퓨터로 정의 되어 있더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터용 풀 FQDN을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="50df5-111">나중에 풀에 컴퓨터를 추가할 준비가 되 면 토폴로지 작성기를 다시 실행 하 여 새 풀 구성원을 정의 하 고 새 토폴로지를 게시 한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 디렉터 풀 구성원을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="50df5-112">또한 DNS (Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 대해 풀의 적절 한 부하 분산 장치에 새 풀 구성원을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="50df5-113">대부분의 경우에는 두 로드 균형 조정 시스템이 모두 준비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="50df5-114">새 구성원 서버를 둘 다에 추가 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df5-114">Be sure that you are adding the new member server to both.</span></span> 
  

