---
title: 'Lync Server 2013: 변경 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39488d423457c01102d6af3c4d5bbfaf6962e2c3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a><span data-ttu-id="3103b-102">Lync Server 2013의 변경 관리</span><span class="sxs-lookup"><span data-stu-id="3103b-102">Change management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3103b-103">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="3103b-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="3103b-104">IT 환경이 변경 되는 것은 피할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-104">Changes to the IT environment are unavoidable.</span></span> <span data-ttu-id="3103b-105">변경 사항에는 새로운 기술, 시스템, 응용 프로그램, 하드웨어, 도구, 프로세스 및 역할 및 책임 변경 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-105">Changes include new technologies, systems, applications, hardware, tools, processes, and changes in roles and responsibilities.</span></span> <span data-ttu-id="3103b-106">효과적인 변경 관리 시스템을 사용 하면 최소한의 서비스 중단으로 인해 IT 환경에 대 한 변경 내용을 빠르게 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-106">An effective change management system lets you introduce changes to the IT environment quickly and with minimal service disruption.</span></span> <span data-ttu-id="3103b-107">변경 관리 시스템은 시스템 변경에 관련 된 팀을 함께 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-107">A change management system brings together the teams involved in changing a system.</span></span> <span data-ttu-id="3103b-108">예를 들어 Office Web Apps를 활용 하기로 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-108">For example, deciding to take advantage of the Office Web Apps.</span></span> <span data-ttu-id="3103b-109">사용자가 브라우저에서 문서를 읽고 편집할 수 있도록 하는 통합 Lync 서비스 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-109">This is an integrated Lync Service application that enables users to read and edit documents in a browser.</span></span> <span data-ttu-id="3103b-110">프로덕션 환경에 참여 한 후에는이 서비스를 구현 하려면 다음과 같은 여러 팀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-110">The implementation of this service, after you have gone into production, requires the involvement of several teams:</span></span>

  - <span data-ttu-id="3103b-111">**테스트 팀**   이 팀은 테스트 서버에서 Office Web Apps를 로드 하 고, 예상 되는 사용 패턴 및 프로덕션 서버의 예상 성능에 대 한 정보를 제공 하는 프로세스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-111">**Test Team**   This team load-tests the Office Web Apps on a test server, in the process providing information about the expected usage patterns and expected performance of the production servers.</span></span>

  - <span data-ttu-id="3103b-112">**Lync 관리자**   이 팀은 배포 전략을 결정 하 고 가능한 설치를 스크립팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-112">**Lync Administrators**   This team determines the deployment strategy and scripts the installation where it was possible.</span></span> <span data-ttu-id="3103b-113">팀은 변경 내용이 프로덕션 환경에 배포 되는지 확인 하 고 이후 관리 작업을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-113">The team is responsible for making sure that the change is deployed on the production environment, and it is responsible for administration afterward.</span></span> <span data-ttu-id="3103b-114">팀에서 변경 사항의 영향을 이해 하 고 변경 내용을 프로덕션 환경에 추가 하기 전에 절차에 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-114">The team must understand the effect of the changes and incorporate them in procedures before the changes are put into production</span></span>

  - <span data-ttu-id="3103b-115">**네트워크 팀**   이 팀은 인터넷에서 내부 Lync 풀 서버로의 액세스를 허용 하는 방화벽 규칙의 변경 사항을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-115">**Network Team**   This team is responsible for changes to firewall rules that allow access from the Internet to the internal Lync pool servers.</span></span> <span data-ttu-id="3103b-116">또한이 팀은 Lync 관리자와 협력 하 여 사용 가능한 대역폭이 추가 부하를 지원할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-116">The team is also responsible in working with the Lync administrators for making sure that the available bandwidth can support the additional load.</span></span>

  - <span data-ttu-id="3103b-117">**보안 팀**   이 팀은 보안을 평가 하 고 위험을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-117">**Security Team**   This team assesses security and minimizes risks.</span></span> <span data-ttu-id="3103b-118">보안 팀은 알려진 취약성을 검토 하 고 보안 위험이 최소화 되도록 하는 데 도움을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-118">The security team must review known vulnerabilities and help ensure that security risks are minimized.</span></span>

  - <span data-ttu-id="3103b-119">**사용자 수용 팀**   이 팀은 시스템을 테스트 하 고 개선을 위해 피드백을 제공할 수 있는 사용자로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-119">**User Acceptance Team**   This team is composed of users who are willing to test the system and offer feedback for improvements.</span></span>

<span data-ttu-id="3103b-120">변경 관리 프로세스에서는 각 팀의 책임을 정의 하 고 수행 해야 하는 작업을 예약 하 고 필요한 위치에 검사 및 테스트를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-120">The change management process defines the responsibilities of each team and schedules the work to be performed, incorporating checks and tests where they are required.</span></span> <span data-ttu-id="3103b-121">변경 컨트롤은 변경의 복잡도와 예상 효과에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-121">Change controls will vary depending on the complexity and expected effect of a change.</span></span> <span data-ttu-id="3103b-122">사소한 변경 사항의 자동 승인에 따라 검토 회의를 변경 하는 것이 전체 프로젝트 수준 검토에 이르기까지 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-122">They can vary from automatic approval of minor changes, to change review meetings, to full project-level reviews.</span></span> <span data-ttu-id="3103b-123">이에 대 한 자세한 내용은이 섹션의 변경 사항 그룹을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-123">To explain this better, the groups of changes are discussed in this section.</span></span>

  - <span data-ttu-id="3103b-124">**주요 변경**   주요 변경 사항은 시스템에 전체적으로 영향을 주는 것으로, 다양 한 팀에서 입력을 받아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-124">**Major Changes**   Major changes have a global effect on the system and may require input from various teams.</span></span> <span data-ttu-id="3103b-125">예를 들어 Lync Server 2013로 업그레이드 하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-125">An example of this is upgrading to Lync Server 2013.</span></span> <span data-ttu-id="3103b-126">주요 변경 내용은 많은 팀과 시스템에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-126">Major changes affect many teams and perhaps different systems.</span></span> <span data-ttu-id="3103b-127">변경 관리 프로세스에는 팀에 게 변경 내용이 나 변경 사항에 영향을 줄 것을 알리기 위한 변경 검토 회의를 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-127">The change management process will probably include one or more change review meetings to inform the teams that will be involved in the change or be affected by the change.</span></span>

  - <span data-ttu-id="3103b-128">**중요**한 변경 사항이 너무 많은 경우 계획, 구축 및 구현에 상당한 리소스가 필요 합니다.   </span><span class="sxs-lookup"><span data-stu-id="3103b-128">**Significant Changes**   Significant changes require significant resources to plan, build, and implement.</span></span> <span data-ttu-id="3103b-129">변경의 영향을 이해 하 고, 배포 절차를 테스트 하 고, 롤백 및 긴급 복구 계획을 준비할 수 있도록 적절 한 변경 컨트롤을 도입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-129">Appropriate change controls should be introduced to help make ensure that the effect of the change is understood, deployment procedures are tested, and the rollback and contingency plans are ready.</span></span> <span data-ttu-id="3103b-130">중요 한 변경의 예로 새 누적 업데이트를 배포 하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-130">An example of a significant change is deploying a new cumulative update.</span></span>

  - <span data-ttu-id="3103b-131">**사소한 변경**   사소한 변경 사항은 Microsoft lync Server 2013 제어판을 통해 특정 Lync 정책을 변경 하는 것과 같이 IT 환경에 큰 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-131">**Minor Changes**   Minor changes do not significantly affect the IT environment, for example, changing certain Lync policies via the Microsoft Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="3103b-132">**표준 변경 사항**   표준 변경 내용은 정기적으로 수행 되며 잘 이해 되며 문서화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-132">**Standard Changes**   Standard changes are performed regularly and are well understood and documented.</span></span> <span data-ttu-id="3103b-133">변경 관리 프로세스는 절차에 대 한 모든 변경 내용을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-133">The change management process should review all changes to the procedures.</span></span> <span data-ttu-id="3103b-134">콘텐츠 데이터베이스를 만들거나 사용자를 추가 하는 것과 같은 루틴 변경에는 필요 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-134">It should not be needed for routine changes like creating a content database or adding a user.</span></span>

<span data-ttu-id="3103b-135">다음 변경 관리 예제에서는 서로 다른 팀의 상호 작용 방법과 새 서비스 팩을 배포할 때 수행 되는 작업을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-135">The following example of change management examines how different teams interact and the actions that are performed when a new service pack is deployed.</span></span> <span data-ttu-id="3103b-136">이러한 작업은 변경 관리 프로세스에 의해 구성 및 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-136">These actions are organized and managed by the change management process.</span></span>

  - <span data-ttu-id="3103b-137">**변경 요청**   발생 보안 팀은 최신 서비스 팩을 평가 하 고 프로덕션 시스템에서 가능한 취약성을 해결 하는지 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-137">**Raise a change request**   The security team has assessed the latest service pack and confirmed that it resolves a possible vulnerability in the production system.</span></span> <span data-ttu-id="3103b-138">이 팀은 Lync Server를 실행 하는 모든 서버에 새 누적 업데이트가 적용 되도록 변경 요청을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-138">The team raises a change request to have the new cumulative update applied to all servers that are running Lync Server.</span></span>

  - <span data-ttu-id="3103b-139">**서비스 팩 릴리스 정보 검토**   Lync 관리자 팀이 서비스 팩 릴리스 정보를 검토 하 여 시스템에 미치는 영향을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-139">**Service pack release notes review**   The Lync administrator team reviews the service pack release notes to identify the effect on the system.</span></span>

  - <span data-ttu-id="3103b-140">**일련의 랩 테스트를 수행**   하는 경우 Lync 관리자 팀은 테스트 환경의 서버에서 테스트 업데이트를 수행 하 여 설치 된 응용 프로그램 및 서버 시스템에 영향을 주지 않고 서비스 팩을 성공적으로 적용할 수 있는지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-140">**A series of lab tests is performed**   The Lync administrator team must perform test updates on a server in a test environment to decide whether the service pack can be applied successfully without affecting any of the installed applications and server systems.</span></span> <span data-ttu-id="3103b-141">프로덕션 환경에서 Lync Server와 상호 작용 하는 타사 또는 내부에 만든 응용 프로그램이 있는 경우에도 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-141">If there are third-party or internally created applications that interface with Lync Server in a production environment, these should be also tested.</span></span> <span data-ttu-id="3103b-142">이러한 테스트를 사용 하 여 업그레이드를 수행 하는 데 필요한 시간을 추정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-142">These tests can also be used to estimate the time that is required to perform the upgrades.</span></span>

  - <span data-ttu-id="3103b-143">**사용자에 게 중단**   에 대 한 알림이 표시 됨 Lync administrator 팀, 통신 팀 또는 사용자 지원 센터에서 계획 된 유지 관리 주기에 대해 영향을 받는 모든 사용자에 게 서비스를 사용할 수 없는 기간을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-143">**Users are informed of the outage**   The Lync administrator team, communications team, or user help desk informs all affected users about the planned maintenance cycle and how long the service will be unavailable.</span></span>

  - <span data-ttu-id="3103b-144">\*\*\*\*   Lync 관리자 팀은 업그레이드 전에 서비스 팩 설치가 실패 하는 경우 원래 시스템 상태로 되돌리는 데 사용할 수 있는 유효한 백업이 있는지 확인 하기 전에 lync의 전체 백업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-144">**A full backup of Lync is performed before the upgrade**   The Lync administrator team must verify that there is a valid backup that can be used to revert to the original system state if the service pack installation fails.</span></span> <span data-ttu-id="3103b-145">문제가 있는 경우이 시스템을 쉽게 사용할 수 있도록 백업을 대기 서버로 복원 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-145">We recommend that the backup be restored to a standby server to have this system readily available if there are issues.</span></span>

  - <span data-ttu-id="3103b-146">**누적 업데이트가 배포**   됨 Lync 관리자 팀이 계획 된 유지 관리 주기 중에 설치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-146">**The cumulative update is deployed**   The Lync administrator team does the installation during the planned maintenance cycle.</span></span>

<div>

## <a name="managing-the-timing-of-changes"></a><span data-ttu-id="3103b-147">변경 시간 관리</span><span class="sxs-lookup"><span data-stu-id="3103b-147">Managing the timing of changes</span></span>

<span data-ttu-id="3103b-148">겹치는 작업 섹션의 중단을 방지 하기 위해 변경 일정을 세우는 절차를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-148">We recommend that you implement a procedure for scheduling changes to avoid disruptions in overlapping sections of your work.</span></span> <span data-ttu-id="3103b-149">예를 들어 두 팀이 모두 시스템에 대 한 사소한 변경을 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-149">For example, two teams may both be planning a minor change to a system.</span></span> <span data-ttu-id="3103b-150">다른 팀에서 레거시 사용자를 해당 풀로 마이그레이션하는 동안 한 팀이 풀에 누적 업데이트를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-150">One team may be applying a cumulative update on a pool while another team is migrating legacy users into that pool.</span></span> <span data-ttu-id="3103b-151">다른 팀에서 계획 하 고 있는 변경 내용의 영향을 받지 않는 팀도 있고, 각 팀이 계획 하 고 있는 변경 사항에 대해 파악 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-151">Neither team is affected by the changes that the other team is planning, and each team may not necessarily know about changes that the other team is planning.</span></span> <span data-ttu-id="3103b-152">두 변경 내용이 동시에 발생 한 경우 변경 사항을 구현 하는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-152">If both changes occurred at the same time, there might be issues implementing the changes.</span></span> <span data-ttu-id="3103b-153">또한 변경 내용이 적용 된 후에 문제가 발생 하는 경우, 예를 들어 사용자 마이그레이션에 실패 한 경우 롤백해야 하는 변경 내용을 결정 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-153">Also, if there are issues after the changes were applied, for example, if the user migration fails, it may be difficult to decide which change should be rolled back.</span></span> <span data-ttu-id="3103b-154">IT와 관리 간에 정기적인 유지 관리 기간이 설정 되어 변경 내용을 테스트 하 고 수락 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3103b-154">There should be regular maintenance periods set up between IT and management to test the changes and accept them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

