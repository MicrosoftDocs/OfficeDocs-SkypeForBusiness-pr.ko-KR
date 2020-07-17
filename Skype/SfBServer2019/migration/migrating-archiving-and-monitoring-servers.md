---
title: 보관 및 모니터링 서버 마이그레이션
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
description: 레거시 환경에 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 비즈니스용 Skype 서버 2019 환경에서 이러한 서버를 배포할 수 있습니다. 그러나 조직에 중요 한 보관 및 모니터링 기능을 사용 하는 경우 마이그레이션 프로세스 중에 기능을 사용할 수 있도록 마이그레이션하기 전에 비즈니스용 Skype 서버 2019 파일럿 풀에 보관 및 모니터링을 추가 해야 합니다.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752670"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="62d0a-104">보관 및 모니터링 서버 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="62d0a-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="62d0a-105">레거시 환경에 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 비즈니스용 Skype 서버 2019 환경에서 이러한 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="62d0a-106">그러나 조직에 중요 한 보관 및 모니터링 기능을 사용 하는 경우 마이그레이션 프로세스 중에 기능을 사용할 수 있도록 마이그레이션하기 전에 비즈니스용 Skype 서버 2019 파일럿 풀에 보관 및 모니터링을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="62d0a-107">마이그레이션 프로세스 중에 보관 및 모니터링 기능을 사용할 수 있으려면 다음과 같은 사항을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="62d0a-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="62d0a-108">보관 데이터 및 모니터링 데이터가 비즈니스용 Skype 서버 2019 배포로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="62d0a-109">레거시 환경을 해제 하기 전에 백업 하는 데이터는 레거시 환경의 활동에 대 한 기록입니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="62d0a-110">레거시 버전의 보관 서버 및 모니터링 서버는 레거시 프런트 엔드 풀에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="62d0a-111">비즈니스용 Skype 서버 2019에서 보관 및 모니터링은 더 이상 서버 역할은 아니지만 비즈니스용 Skype 서버 2019 프런트 엔드 풀에 통합 된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="62d0a-112">레거시 및 비즈니스용 Skype 서버 2019 배포가 공존 하는 시간 동안 레거시 버전의 보관 서버 및 모니터링 서버가 레거시 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="62d0a-113">비즈니스용 Skype 서버의 보관 및 모니터링 2019 비즈니스용 Skype 서버 2019 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62d0a-114">새 비즈니스용 Skype 서버 2019 파일럿 풀에서 레거시에 지 서버를 계속 사용 하는 경우 이전 버전의 보관 서버는 레거시 풀에 있는 사용자에 대 한 데이터를 계속 수집 하며 비즈니스용 Skype 서버 2019 2019에서 보관 하는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="62d0a-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="62d0a-115">비즈니스용 Skype 서버 2019의 보관 및 모니터링과 함께 타사 보관 및 모니터링 솔루션을 함께 사용 하는 경우에는 공급 업체에 문의 하 여 타사 솔루션을 비즈니스용 Skype 서버 2019와 통합 해야 하는 경우 및 방법에 대 한 의견을 함께 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="62d0a-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

