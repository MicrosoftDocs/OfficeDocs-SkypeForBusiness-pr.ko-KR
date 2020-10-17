---
title: 'Lync Server 2013: Lync Server 환경에 대 한 모범 사례'
description: 'Lync Server 2013: Lync Server 환경에 대 한 유용한 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552214"
---
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="982de-103">Lync Server 2013 환경에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="982de-103">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="982de-104">_**마지막으로 수정 된 항목:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="982de-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="982de-105">다음과 같은 일반적인 원칙은 시스템의 지속적인 작업에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-105">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="982de-106">MOF 이해 및 **활용**     MOF는 일일 Lync Server 2013 작업과 같은 IT 자산의 관리에 대 한 조직 기술 지침을 제공 하는 모범 사례, 원칙 및 모델 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="982de-106">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="982de-107">다음 MOF 지침을 참조 하 여 Microsoft 제품에 대 한 업무상 중요 한 프로덕션 시스템 안정성, 가용성, 지원 가능성 및 관리 효율성을 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-107">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="982de-108">자세한 내용은 [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="982de-108">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="982de-109">**Lync Server 2013**     의 모범 사례에 대해 자세히 알아보기 Lync Server 2013을 관리 하기 위한 실용적인 및 입증 된 절차를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-109">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="982de-110">테스트를 거친 방법과 작업을 관리 하는 방법을 사용 하면 고유한 메서드를 개발 하는 것 보다 효율적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-110">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="982de-111">**매일, 매주, 월별 프로세스로**     작업을 구분 합니다. 정기적으로 수행 하는 필수 운영 작업을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-111">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="982de-112">작업을 수행 하는 방법을 문서화 하면 새 기술이 배포 되거나 직원 변경이 발생 하는 등의 작업 환경에서 변경 사항이 있을 때 정보가 보존 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-112">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="982de-113">운영 작업은 매일, 매주 및 매월 수행 되는 작업을 관리 가능한 작업으로 구분 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-113">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="982de-114">일상적인 작업은 시스템 작동에 중점을 둔 것 이며, 월별 작업은 시스템의 장기간 상태를 확인 하는 데 집중 됩니다.</span><span class="sxs-lookup"><span data-stu-id="982de-114">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="982de-115">이 문서는 인스턴트 메시징/현재 상태 (IM/P) 구성 요소 또는 Enterprise Voice가 포함 된 IM/P만 배포 하는 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-115">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="982de-116">작업 또는 검사 목록 항목이 Enterprise Voice와 관련 된 경우에는이를 언급 하며 환경에 Enterprise Voice가 포함 되어 있지 않으면 해당 부분을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-116">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="982de-117">**Lync Server 2013**     운영에 필요한 도구 배포 문제를 해결 하 고 작업을 자동화 하며 Lync Server 2013 환경을 모니터링 하 고 유지 관리 하는 데 도움이 되는 다양 한 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-117">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="982de-118">운영 팀에서 수행 하는 작업이 제어 방식으로 정확 하 고 효율적으로 수행 되도록 조직의 표준 도구 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-118">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="982de-119">또한 인시던트 및 주요 구성 변경 사항을 추적 하기 위한 프로세스도 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-119">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="982de-120">참조</span><span class="sxs-lookup"><span data-stu-id="982de-120">Reference</span></span>

<span data-ttu-id="982de-121">일반적으로 서버 관리의 기본 사항에 대해 잘 모르는 독자의 이점은 서버 관리 방법에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-121">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="982de-122">이미 서버 관리에 익숙한 독자는이 섹션을 건너뛰도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-122">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="982de-123">모범 사례는 IT 전문가가 다양 한 환경에서 얻은 지식과 경험을 기반으로 하는 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="982de-123">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="982de-124">Lync Server 관리자가 매일 수행 해야 하는 일반적인 작업에 대 한 표준 절차를 제공 하 고 Lync Server 환경을 관리 하는 데 사용 해야 하는 도구를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-124">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="982de-125">Lync 관리자에 대 한 일반적인 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="982de-125">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="982de-126">**용량 및 가용성 관리**     향후 용량 요구 사항을 예측 하 고 시스템의 용량, 안정성 및 가용성에 대해 보고 하기 위한 방법 및 측정 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-126">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="982de-127">Lync Server를 실행 하는 서버가 시스템의 부하를 처리 하도록 크기를 조정 했으며, 계획 되지 않은 가동 중지 시간이 SLA (서비스 수준 계약)에 정의 된 수준에 유지 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-127">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="982de-128">또한 정의 된 요구 사항을 충족 하기 위해 계속 해 서 하드웨어를 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-128">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="982de-129">**변경 관리 및 구성 관리**     IT 시스템이 변경 되는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-129">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="982de-130">여기에는 테스트, 응용 프로그램 피드백 및 긴급 복구 계획, 모든 변경에 대 한 설명서, 문제가 발생 한 경우의 관리 승인 등이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-130">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="982de-131">소프트웨어 및 하드웨어 자산 및 해당 구성에 대 한 기록을 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-131">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="982de-132">**시스템 관리**     데이터베이스 관리 및 사이트 관리와 같은 관리 작업을 수행 하는 표준 방법에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-132">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="982de-133">**보안 관리**     데이터 기밀성, 데이터 무결성 및 IT 인프라의 데이터를 보호 하는 자세한 정책 및 계획을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-133">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="982de-134">여기에는 IT 보안 인프라를 유지 관리 하 고 조정 하는 작업과 관련 된 일상적인 작업 및 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="982de-134">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="982de-135">**시스템 문제 해결**     나중에 유사한 문제를 방지 하기 위한 단계를 포함 하 여 예기치 않은 문제를 처리 하는 방법을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-135">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="982de-136">**서비스 수준 계약**     IT 시스템의 성능에 대 한 목표 집합을 유지 관리 하 고 이러한 목표 대비 성과를 정기적으로 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-136">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="982de-137">**설명서**     표준 절차 (예: 구성 정보 및 교훈)를 문서화 하 고이를 필요로 하는 교직원 구성원에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-137">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="982de-138">구성이 변경 되 면 그에 따라 설명서를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="982de-138">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="982de-139">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="982de-139">Related Sections</span></span>

<span data-ttu-id="982de-140">계속 하기 전에 시스템 작업과 관련 하 여 다음 항목을 검토 하십시오.</span><span class="sxs-lookup"><span data-stu-id="982de-140">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="982de-141">Lync Server 2013의 용량 및 가용성 관리</span><span class="sxs-lookup"><span data-stu-id="982de-141">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="982de-142">Lync Server 2013의 변경 관리</span><span class="sxs-lookup"><span data-stu-id="982de-142">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="982de-143">Lync Server 2013의 구성 관리</span><span class="sxs-lookup"><span data-stu-id="982de-143">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="982de-144">Lync Server 2013의 시스템 관리</span><span class="sxs-lookup"><span data-stu-id="982de-144">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="982de-145">Lync Server 2013의 서비스 수준 계약</span><span class="sxs-lookup"><span data-stu-id="982de-145">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="982de-146">Lync Server 2013의 설명서</span><span class="sxs-lookup"><span data-stu-id="982de-146">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="982de-147">Lync Server 2013의 표준 절차</span><span class="sxs-lookup"><span data-stu-id="982de-147">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="982de-148">Lync Server 2013의 응급 절차</span><span class="sxs-lookup"><span data-stu-id="982de-148">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="982de-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="982de-149">See Also</span></span>


[<span data-ttu-id="982de-150">Microsoft Operations Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="982de-150">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

