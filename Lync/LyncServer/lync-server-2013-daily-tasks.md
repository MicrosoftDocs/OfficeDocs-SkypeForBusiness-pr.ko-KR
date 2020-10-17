---
title: 'Lync Server 2013: 일별 작업'
description: 'Lync Server 2013: 일별 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9e2d62eb29db2bafa23565637bb655ba932c7b6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550184"
---
# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="f05df-103">Lync Server 2013의 일별 작업</span><span class="sxs-lookup"><span data-stu-id="f05df-103">Daily tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f05df-104">_**마지막으로 수정 된 항목:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="f05df-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="f05df-105">Lync Server 2013 배포의 가용성과 안정성을 보장 하기 위해서는 실제 플랫폼, 운영 체제 및 모든 중요 Lync Server 2013 서비스가 포함 된 시스템 작동에 매우 중요 한 일상적인 일상적인 모니터 및 테스트 요소의 일부로 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-105">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="f05df-106">예방적 유지 관리 및 사전 모니터링은 Lync Server 2013 배포에 나쁜 영향을 줄 수 있는 잠재적 오류 및 문제를 파악 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-106">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="f05df-107">모니터링 2013에는 연결, 서비스, 서버 리소스 및 시스템 리소스 관련 문제를 확인 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-107">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="f05df-108">System Center Operations Manager와 함께 Windows Server 운영 체제와 Lync Server를 사용 하 여 Lync Server 조직을 원활 하 게 실행 하는 데 도움이 되는 다양 한 모니터링 도구와 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-108">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="f05df-109">이러한 기술이 함께 구현 되 면 관리자는 문제가 발생할 때 또는 이전에 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-109">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="f05df-110">일일 모니터링의 주요 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-110">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="f05df-111">정의 된 Sla의 성능 및 가용성 요구 사항 충족</span><span class="sxs-lookup"><span data-stu-id="f05df-111">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="f05df-112">매일 백업 작업, 서버 상태 확인과 같은 특정 관리 작업을 성공적으로 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-112">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="f05df-113">서버 성능의 병목 현상 등의 문제를 검색 및 해결 하 고, 생산성에 영향을 주기 전에 추가 리소스에 대 한 요구 사항을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-113">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="f05df-114">일일 유지 관리 작업은 관리 팀이 조직 내의 일반 시스템 작업에 대 한 조건 또는 기준을 정의 하거나 설정 하 고 비정상적인 활동을 검색 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-114">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="f05df-115">관리 팀이 사용 현황 수준, 가능한 성능 병목 현상 및 관리 변경과 같은 Lync Server 2013 인프라에 대 한 데이터를 캡처 및 유지 관리할 수 있도록 이러한 일일 유지 관리 작업을 구현 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-115">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="f05df-116">일별 작업의 성능을 쉽게 구성 하려면 [일별 작업 검사 목록을](lync-server-2013-operations-checklists.md)사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05df-116">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f05df-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f05df-117">See Also</span></span>


[<span data-ttu-id="f05df-118">일별 작업 검사 목록</span><span class="sxs-lookup"><span data-stu-id="f05df-118">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

