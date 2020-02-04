---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="f4331-102">보관 및 모니터링 서버 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f4331-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4331-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f4331-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f4331-104">Office Communications Server 2007 R2에 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 Lync Server 2013 환경에서 이러한 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="f4331-105">그러나 보관 및 모니터링 기능이 조직에 중요 한 경우 마이그레이션을 수행 하기 전에 보관 및 모니터링을 파일럿 풀에 추가 하 여 마이그레이션 프로세스 동안 해당 기능을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="f4331-106">마이그레이션 및 공존 단계 중에 보관 및 모니터링 기능을 원하는 경우 다음 고려 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="f4331-107">데이터 보관 및 모니터링 데이터는 Lync Server 2013 배포로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="f4331-108">레거시 환경을 서비스 해제 하기 전에 백업 하는 데이터는 Office Communications Server 2007 R2의 활동 기록이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="f4331-109">Office Communications Server 2007 R2 버전의 보관 서버와 모니터링 서버는 Office Communications Server 2007 R2 프런트 엔드 풀에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="f4331-110">Lync Server 2013에서 보관 및 모니터링은 더 이상 서버 역할이 아니지만 Lync Server 2013 프런트 엔드 풀에 통합 된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="f4331-111">레거시 및 Lync Server 2013 배포가 공존할 때 Office Communications Server 2007 R2 버전의 보관 서버 및 모니터링 서버는 Office Communications Server 2007 R2 풀에 속한 사용자의 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="f4331-112">Lync Server 2013 버전의 보관 서버 및 모니터링 서버는 Lync Server 2013 풀에 속한 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4331-113">새로운 Lync Server 2013 파일럿 풀을 사용 하 여 레거시 Edge 서버를 사용 하 고 있는 경우 마이그레이션 단계에서 Office Communications Server 2007 R2 버전의 보관 서버는 Office Communications Server에 속한 사용자의 데이터를 계속 수집 합니다. 2007 R2 풀 및 Lync Server 2013 버전의 보관 서버는 Lync Server 2013 풀에 속한 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4331-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="f4331-114">보관 서버 및 모니터링 서버와 함께 타사 보관 및 모니터링 솔루션을 사용 하는 경우 타사 솔루션을 Lync Server 2013와 통합 해야 하는 시기와 방법에 대 한 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4331-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

