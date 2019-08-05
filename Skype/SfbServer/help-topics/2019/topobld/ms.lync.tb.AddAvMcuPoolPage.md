---
title: A/V MCU 풀 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Collocated A/V 회의 서비스를 보유 하 고 있지 않은 중앙 사이트의 모든 Enterprise Edition 프런트 엔드 서버는 동일한 독립 실행형 A/V 회의 풀을 사용할 수 있습니다. 각 A/V 회의 풀에 대해 풀의 FQDN (정규화 된 도메인 이름)을 지정 하 고 단일 A/V 회의 서버 또는 부하 분산 된 여러 A/V 회의 서버를 포함 해야 합니다.
ms.openlocfilehash: dfd1fd056e015ed4d6ed1344384efa485e65f318
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197497"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="5daf2-104">A/V MCU 풀 추가</span><span class="sxs-lookup"><span data-stu-id="5daf2-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="5daf2-105">Collocated A/V 회의 서비스를 보유 하 고 있지 않은 중앙 사이트의 모든 Enterprise Edition 프런트 엔드 서버는 동일한 독립 실행형 A/V 회의 풀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="5daf2-106">각 A/V 회의 풀에 대해 풀의 FQDN (정규화 된 도메인 이름)을 지정 하 고 단일 A/V 회의 서버 또는 부하 분산 된 여러 A/V 회의 서버를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5daf2-107">단일 서버 풀을 다중 서버 풀로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="5daf2-108">나중에 조직에 다중 서버 풀이 필요한 경우 단일 서버 풀을 삭제 한 다음 다중 서버 풀을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="5daf2-109">미래에 A/V 회의 풀을 구현 하려는 경우 **여러 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="5daf2-110">풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="5daf2-111">나중에 풀에 컴퓨터를 추가할 준비가 되 면 토폴로지 작성기를 다시 시작 하 여 새 풀 구성원을 정의 하 고 새 토폴로지를 게시 한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 A/V 회의 풀 구성원을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="5daf2-112">A/V 회의 서버 풀은 풀을 만들 수 있는 부하 분산 장치가 필요 없다는 점에서 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="5daf2-113">A/V 회의 풀은 내부적으로 로드 균형을 유지 하며 추가 하드웨어는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5daf2-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

