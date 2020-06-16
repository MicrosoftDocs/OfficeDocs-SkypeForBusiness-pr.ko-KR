---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba86de15ea86844b677db1abb0f47f7e1995c7e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="bb79a-102">보관 및 모니터링 서버 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="bb79a-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb79a-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bb79a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bb79a-104">Lync Server 2010 환경에 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 Lync Server 2013 환경에서 이러한 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="bb79a-105">그러나 조직에 중요 한 보관 및 모니터링 기능을 사용 하는 경우에는 마이그레이션 프로세스 중에 기능을 사용할 수 있도록 마이그레이션하기 전에 보관 및 모니터링을 Lync Server 2013 파일럿 풀에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="bb79a-106">마이그레이션 프로세스 중에 보관 및 모니터링 기능을 사용할 수 있으려면 다음과 같은 사항을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb79a-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="bb79a-107">데이터 보관 및 모니터링 데이터가 Lync Server 2013 배포로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="bb79a-108">레거시 환경을 해제하기 전에 백업한 데이터는 Lync Server 2010 환경의 작업 내역이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="bb79a-109">Lync server 2010 버전의 보관 서버 및 모니터링 서버는 Lync Server 2010 프런트 엔드 풀에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="bb79a-110">Lync Server 2013에서 보관 및 모니터링은 더 이상 서버 역할은 아니지만 Lync Server 2013 프런트 엔드 풀로 통합 된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="bb79a-111">레거시 및 Lync Server 2013 배포가 공존 하는 시간 동안 Lync server 2010 버전의 보관 서버 및 모니터링 서버는 Lync Server 2010 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="bb79a-112">보관 및 모니터링 Lync Server 2013 Lync Server 2013 풀에 속한 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bb79a-113">새 Lync Server 2013 파일럿 풀에서 레거시에 지 서버를 계속 사용 하는 경우에는 lync server 2010 버전의 보관 서버가 lync server 2010 풀에 있는 사용자에 대 한 데이터를 계속 수집 하며 lync server 2013의 보관은 lync server 2013 풀에 있는 사용자에 대 한 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79a-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="bb79a-114">타사 보관 및 모니터링 솔루션을 Lync Server 2013의 보관 및 모니터링과 함께 사용 하는 경우 타사 솔루션을 Lync Server 2013과 통합 하는 시기 및 방법에 대 한 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb79a-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

