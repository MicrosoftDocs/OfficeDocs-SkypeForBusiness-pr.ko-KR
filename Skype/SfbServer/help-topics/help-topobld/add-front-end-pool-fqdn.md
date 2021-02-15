---
title: 프런트 엔드 풀 FQDN 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 만들 프런트 엔드 풀의 FQDN(정규화된 도메인 이름)을 지정합니다. 프런트 엔드 풀이 포함된 토폴로지를 게시한 후에는 풀의 FQDN을 변경할 수 없습니다. 풀의 이름을 바꿔야 할 경우 풀을 삭제한 다음 새 FQDN으로 새 풀을 추가해야 합니다.
ms.openlocfilehash: 45fa22a6ce69b900fc57618825d299ec0930900a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833358"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="3c97a-105">프런트 엔드 풀 FQDN 추가</span><span class="sxs-lookup"><span data-stu-id="3c97a-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="3c97a-p102">만들 프런트 엔드 풀의 FQDN(정규화된 도메인 이름)을 지정합니다. 프런트 엔드 풀이 포함된 토폴로지를 게시한 후에는 풀의 FQDN을 변경할 수 없습니다. 풀의 이름을 바꿔야 할 경우 풀을 삭제한 다음 새 FQDN으로 새 풀을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="3c97a-109">나중에 프런트 엔드 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="3c97a-110">풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="3c97a-111">나중에 풀에 컴퓨터를 더 추가할 준비가 된 경우 토폴로지 작성기를 다시 실행하여 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 프런트 엔드 풀 구성원을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="3c97a-112">또한 적절한 풀용 부하 분산 장치, DNS(Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="3c97a-113">대부분의 경우 두 부하 분산 시스템이 모두 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="3c97a-114">두 부하 분산 시스템 모두에 새 구성원 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c97a-114">Be sure that you are adding the new member server to both.</span></span> 
  

