---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 레거시 환경에서 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 비즈니스용 Skype 서버 2019 환경에서 이러한 서버를 배포할 수 있습니다. 그러나 보관 및 모니터링 기능이 조직에 중요 한 경우 마이그레이션을 시작 하기 전에 비즈니스용 Skype Server 2019 파일럿 풀에 보관 및 모니터링을 추가 하 여 마이그레이션 프로세스 동안 기능을 사용할 수 있도록 해야 합니다.
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196957"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="67a59-104">보관 및 모니터링 서버 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="67a59-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="67a59-105">레거시 환경에서 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 비즈니스용 Skype 서버 2019 환경에서 이러한 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="67a59-106">그러나 보관 및 모니터링 기능이 조직에 중요 한 경우 마이그레이션을 시작 하기 전에 비즈니스용 Skype Server 2019 파일럿 풀에 보관 및 모니터링을 추가 하 여 마이그레이션 프로세스 동안 기능을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="67a59-107">마이그레이션 프로세스 중 보관 및 모니터링 기능을 원하는 경우 다음 고려 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="67a59-108">데이터 보관 및 모니터링 데이터는 비즈니스용 Skype 서버 2019 배포로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="67a59-109">레거시 환경을 서비스 해제 하기 전에 백업 하는 데이터는 레거시 환경의 활동 기록이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="67a59-110">레거시 버전의 보관 서버와 모니터링 서버는 레거시 프런트 엔드 풀에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="67a59-111">비즈니스용 Skype 서버 2019에서 보관 및 모니터링은 더 이상 서버 역할이 아니지만 비즈니스용 Skype Server 2019 프런트 엔드 풀에 통합 된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="67a59-112">레거시 및 비즈니스용 Skype Server 2019 배포가 공존 하는 동안 레거시 버전의 보관 서버 및 모니터링 서버는 레거시 풀에 속한 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="67a59-113">비즈니스용 Skype Server 2019에서 보관 및 모니터링 비즈니스용 Skype Server 2019 풀에 속한 사용자에 게 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="67a59-114">새로운 비즈니스용 Skype Server 2019 파일럿 풀에 레거시 Edge 서버를 사용 하는 경우 이전 버전의 보관 서버는 레거시 풀에 있고 비즈니스용 Skype에서 보관 하는 사용자에 대 한 데이터를 계속 수집 합니다. 서버 2019는 비즈니스용 Skype Server 2019 풀에 속한 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a59-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="67a59-115">비즈니스용 Skype 서버 2019에서 보관 및 모니터링과 함께 타사 보관 및 모니터링 솔루션을 사용 하는 경우, 타사 솔루션을 비즈니스용 Skype Server 2019와 통합 해야 하는 경우와 관련 하 여 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="67a59-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

