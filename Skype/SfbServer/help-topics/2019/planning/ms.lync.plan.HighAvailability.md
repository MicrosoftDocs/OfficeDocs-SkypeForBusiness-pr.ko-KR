---
title: 고가용성(계획 도구)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버의 대부분의 서버 역할에 대한 주요 고가용성 스키마는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819798"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="954a6-104">고가용성(계획 도구)</span><span class="sxs-lookup"><span data-stu-id="954a6-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="954a6-105">비즈니스용 Skype 서버의 대부분의 서버 역할에 대한 주요 고가용성 스키마는 풀링을 통한 서버 중복성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="954a6-106">특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="954a6-107">비즈니스용 Skype 서버에는 고가용성을 사용하려면 프런트 엔드 서버가 두 개 이상 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="954a6-108">계획 도구는 다음 조건을 사용하여 고가용성을 지원하기 위해 추가 서버를 추가할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="954a6-109">배포에 둘 이상의 프런트 엔드 서버가 포함되어 있는 경우 계획 도구에서 추가 서버를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="954a6-110">배포에 에지 서버가 포함되어 있는 경우 서버가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="954a6-111">배포에 영구 채팅이 포함되어 있는 경우 계획 도구에서 추가 서버를 추가하지만 풀 수를 늘리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="954a6-112">예를 들어 배포에 이미 4개의 서버가 포함되어 있는 경우 계획 도구에서 서버(총 5대)를 추가하는 것이 되지만 단일 풀을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="954a6-113">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="954a6-114">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="954a6-115">자세한 내용은 [비즈니스용 Skype에서 Microsoft Teams로 업그레이드를 참조하세요.](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="954a6-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="954a6-116">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="954a6-117">또한 계획 도구는 모든 데이터베이스에 SQL 데이터베이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="954a6-118">예를 들어 프런트 엔드 SQL Server 데이터베이스가 있는 경우 계획 도구는 이 데이터베이스의 미러 데이터베이스로 다른 데이터베이스를 추가하고 이름을 "프런트 엔드 미러 서버 SQL 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="954a6-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="954a6-119">고가용성을 위해 환경을 준비하는 데 대한 자세한 내용은 비즈니스용 Skype 서버의 고가용성 및 재해 복구 [계획을 참조하세요.](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="954a6-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

