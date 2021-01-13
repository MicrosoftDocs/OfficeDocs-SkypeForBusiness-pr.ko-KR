---
title: 디렉터 풀 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 디렉터 풀 FQDN 정의를 수행하려면 부하 분산 풀의 디렉터 두 개 이상으로 구성되는 다중 컴퓨터 풀 또는 단일 컴퓨터 풀을 선택합니다. 또한 Director 풀 또는 단일 감독의 FQDN에 연결하는 데 사용할 FQDN(FQDN)을 입력해야 합니다. 디렉터 컴퓨터 풀의 경우 이 값은 하드웨어 부하 분산 장치의 가상 IP에 대한 DNS(Domain Name System) 입력이나 DNS 부하 분산에 대한 공유 DNS 입력이 됩니다.
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807758"
---
# <a name="add-director-pool"></a><span data-ttu-id="88862-105">디렉터 풀 추가</span><span class="sxs-lookup"><span data-stu-id="88862-105">Add Director Pool</span></span>
 
<span data-ttu-id="88862-106">**디렉터 풀 FQDN 정의** 를 수행하려면 부하 분산 풀의 디렉터 두 개 이상으로 구성되는 **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88862-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="88862-107">또한 Director 풀 또는 단일 감독의 FQDN에 연결하는 데 사용할 FQDN(FQDN)을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88862-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="88862-108">디렉터 컴퓨터 풀의 경우 이 값은 하드웨어 부하 분산 장치의 가상 IP에 대한 DNS(Domain Name System) 입력이나 DNS 부하 분산에 대한 공유 DNS 입력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88862-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="88862-109">나중에 디렉터 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88862-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="88862-110">풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88862-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="88862-111">나중에 풀에 컴퓨터를 더 추가할 준비가 된 경우 토폴로지 작성기를 다시 실행하여 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 Director 풀 구성원을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88862-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="88862-112">또한 적절한 풀용 부하 분산 장치, DNS(Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88862-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="88862-113">대부분의 경우 두 부하 분산 시스템이 모두 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88862-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="88862-114">두 부하 분산 시스템 모두에 새 구성원 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88862-114">Be sure that you are adding the new member server to both.</span></span> 
  

