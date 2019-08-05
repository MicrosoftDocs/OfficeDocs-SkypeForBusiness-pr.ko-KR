---
title: 고가용성 (계획 도구)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: 비즈니스용 Skype Server 2015의 대부분의 서버 역할에 대 한 주요 고가용성 체계는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.
ms.openlocfilehash: 740c12439683fcefccaef11358a8cb65a4fae65a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189132"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="dcae1-104">고가용성 (계획 도구)</span><span class="sxs-lookup"><span data-stu-id="dcae1-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="dcae1-105">비즈니스용 Skype Server 2015의 대부분의 서버 역할에 대 한 주요 고가용성 체계는 풀링을 통한 서버 중복성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="dcae1-106">특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="dcae1-107">가용성을 높이기 위해 비즈니스용 Skype 서버 2015에는 두 대 이상의 프런트 엔드 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="dcae1-108">계획 도구는 다음 조건을 사용 하 여 고가용성을 지원 하기 위해 추가 서버를 추가할 것인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="dcae1-109">배포에 두 개 이상의 프런트 엔드 서버가 포함 된 경우 계획 도구에서 서버를 더 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="dcae1-110">배포에 Edge Server가 포함 되어 있으면 추가 서버가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="dcae1-111">배포에 영구 채팅이 포함 되어 있는 경우 계획 도구는 추가 서버를 추가 하지만 풀 번호는 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="dcae1-112">예를 들어 배포에 이미 4 개의 서버가 있는 경우 계획 도구는 추가 서버 (총 5 개 서버)를 추가 하는 것을 제안 하지만 단일 풀을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="dcae1-113">또한 계획 도구는 모든 데이터베이스에 대 한 미러 SQL 데이터베이스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="dcae1-114">예를 들어 프런트 엔드 SQL Server 데이터베이스가 있는 경우 계획 도구는이 데이터베이스에 대 한 미러 데이터베이스를 추가 하 고 "프런트 엔드 미러 SQL 데이터베이스"로 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dcae1-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="dcae1-115">가용성을 높이기 위해 환경을 준비 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015의 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dcae1-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

