---
title: 에지 서버 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 에지 서버 또는 에지 서버 풀을 토폴로지 디자인에 통합하려면 에지 서버 또는 에지 서버 풀을 배포할 서버의 FQDN(정규화된 도메인 이름)을 지정해야 합니다. 에지 서버 또는 에지 서버 풀이 포함된 토폴로지와 비즈니스용 Skype 서버를 설치하기 전에 외부 사용자 액세스 배포를 위한 모든 선행 작업을 완료해야 합니다. 이러한 필요 조건에 대한 자세한 내용은 배포 설명서의 Preparing for Installation of Servers in the Perimeter Network를 참조하십시오.
ms.openlocfilehash: fb5fc4f34531da9bae4585d5a6140fdfe5837735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803598"
---
# <a name="add-edge-server"></a><span data-ttu-id="b620c-105">에지 서버 추가</span><span class="sxs-lookup"><span data-stu-id="b620c-105">Add Edge Server</span></span>

<span data-ttu-id="b620c-106">에지 서버 또는 에지 서버 풀을 토폴로지 디자인에 통합하려면 에지 서버 또는 에지 서버 풀을 배포할 서버의 FQDN(정규화된 도메인 이름)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="b620c-107">에지 서버 또는 에지 서버 풀이 포함된 토폴로지와 비즈니스용 Skype 서버를 설치하기 전에 외부 사용자 액세스 배포를 위한 모든 선행 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="b620c-108">이러한 필수 구성 요소에 대한 자세한 내용은 배포 설명서에서 [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b620c-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b620c-p103">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. 따라서 도메인에 가입되지 않은 에지 서버 또는 에지 서버 풀로 배포할 컴퓨터의 이름에 DNS(Domain Name System) 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-p103">The name you specify must be identical to the computer name configured on the server. By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN. Topology Builder uses FQDNs, not short names. You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span>

> [!TIP]
> <span data-ttu-id="b620c-113">나중에 에지 서버 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="b620c-114">풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="b620c-115">나중에 풀에 컴퓨터를 더 추가할 준비가 된 경우 토폴로지 작성기에서 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 에지 서버 풀 구성원을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="b620c-116">또한 적절한 풀용 부하 분산 장치, DNS 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="b620c-117">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="b620c-118">즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="b620c-119">적절한 부하 분산 장치에 새 구성원 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span>

<span data-ttu-id="b620c-120">초기 토폴로지 배포 시 또는 초기 토폴로지를 배포한 후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-120">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology.</span></span> <span data-ttu-id="b620c-121">기존 토폴로지에 에지 서버 또는 에지 서버 풀을 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b620c-121">For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


