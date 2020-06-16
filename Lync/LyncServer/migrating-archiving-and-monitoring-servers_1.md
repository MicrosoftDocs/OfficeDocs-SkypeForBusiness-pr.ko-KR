---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="8c8e5-102">보관 및 모니터링 서버 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8c8e5-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c8e5-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8c8e5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8c8e5-104">Office Communications Server 2007 r 2에 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 Lync Server 2013 환경에서 이러한 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="8c8e5-105">보관 및 모니터링 기능이 조직에 중요한 경우라도 마이그레이션 프로세스 중 기능을 사용할 수 있도록 마이그레이션하기 전에 보관 서버 및 모니터링 서버를 파일럿 풀에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="8c8e5-106">마이그레이션 중에 그리고 동시 사용 단계 중에 보관 및 모니터링 기능을 사용할 수 있으려면 다음과 같은 사항을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="8c8e5-107">데이터 보관 및 모니터링 데이터가 Lync Server 2013 배포로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="8c8e5-108">레거시 환경을 제거 하기 전에 백업 하는 데이터는 Office Communications Server 2007 r 2의 활동 기록이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="8c8e5-109">Office Communications Server 2007 R2 버전의 보관 서버 및 모니터링 서버는 Office Communications Server 2007 R2 프런트 엔드 풀에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="8c8e5-110">Lync Server 2013에서 보관 및 모니터링은 더 이상 서버 역할은 아니지만 Lync Server 2013 프런트 엔드 풀로 통합 된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="8c8e5-111">레거시 및 Lync Server 2013 배포가 공존할 때 Office Communications Server 2007 R2 버전의 보관 서버 및 모니터링 서버는 Office Communications Server 2007 R2 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="8c8e5-112">Lync server 2013 버전의 보관 서버 및 모니터링 서버는 Lync Server 2013 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c8e5-113">새 Lync Server 2013 파일럿 풀에서 레거시에 지 서버를 계속 사용 하는 경우에는 Office Communications Server 2007 R2 버전의 보관 서버가 Office Communications Server 2007 R2 풀에 있는 사용자에 대 한 데이터를 계속 수집 하며 Lync server 2013 버전의 보관 서버는 Lync Server 2013 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="8c8e5-114">보관 서버 및 모니터링 서버와 함께 타사 보관 및 모니터링 솔루션을 사용 하는 경우 타사 솔루션을 Lync Server 2013와 통합 해야 하는 시기 및 방법에 대 한 공급 업체에 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c8e5-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

