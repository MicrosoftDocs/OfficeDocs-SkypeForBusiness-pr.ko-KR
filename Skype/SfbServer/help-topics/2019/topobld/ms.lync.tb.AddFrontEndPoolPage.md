---
title: 프론트 엔드 풀 FQDN 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 만들고 있는 프런트 엔드 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 프런트 엔드 풀을 포함 하는 토폴로지를 게시 한 후에는 풀의 FQDN을 변경할 수 없습니다. 풀의 이름을 변경 해야 하는 경우에는 풀을 삭제 한 다음 새 FQDN을 사용 하 여 새 풀을 추가 해야 합니다.
ms.openlocfilehash: 0d05455a1b57394eaf0b6b11c70d3a6e9d1f84ae
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689327"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="7db3e-105">프론트 엔드 풀 FQDN 추가</span><span class="sxs-lookup"><span data-stu-id="7db3e-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="7db3e-106">만들고 있는 프런트 엔드 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="7db3e-107">프런트 엔드 풀을 포함 하는 토폴로지를 게시 한 후에는 풀의 FQDN을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="7db3e-108">풀의 이름을 변경 해야 하는 경우에는 풀을 삭제 한 다음 새 FQDN을 사용 하 여 새 풀을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="7db3e-109">앞으로 프런트 엔드 풀을 구현 하려는 경우 **여러 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="7db3e-110">풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="7db3e-111">나중에 풀에 컴퓨터를 추가할 준비가 되 면 토폴로지 작성기를 다시 실행 하 여 새 풀 구성원을 정의 하 고 새 토폴로지를 게시 한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 프런트 엔드 풀 구성원을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="7db3e-112">또한 풀의 적절 한 부하 분산 장치, DNS (Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="7db3e-113">대부분의 경우에는 두 로드 균형 조정 시스템이 모두 준비 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="7db3e-114">새 구성원 서버를 둘 다에 추가 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db3e-114">Be sure that you are adding the new member server to both.</span></span> 
  

