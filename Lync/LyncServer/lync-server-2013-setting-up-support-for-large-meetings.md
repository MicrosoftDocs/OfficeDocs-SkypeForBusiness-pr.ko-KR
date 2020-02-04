---
title: 'Lync Server 2013: 대규모 모임에 대 한 지원 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="e6da9-102">Lync Server 2013에서 대규모 모임에 대 한 지원 설정</span><span class="sxs-lookup"><span data-stu-id="e6da9-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6da9-103">_**마지막으로 수정한 주제:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="e6da9-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="e6da9-104">최대 1000 명의 사용자에 대 한 대규모 모임을 지원 하려면 적절 한 토폴로지, 모임 하드웨어 및 소프트웨어 필수 구성 요소를 만들고 적절 하 게 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="e6da9-105">토폴로지 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6da9-105">Topology Requirements</span></span>

<span data-ttu-id="e6da9-106">단일 대규모 모임에는 하나 이상의 프런트 엔드 서버와 1 백 엔드 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="e6da9-107">그러나 고가용성을 제공 하려면 미러 백 엔드 서버가 있는 2 개의 프런트 엔드 서버 풀을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="e6da9-108">대규모 모임을 호스트 하는 사용자는이 풀에 속한 사용자 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="e6da9-109">그러나이 풀에는 다른 사용자 계정을 호스트 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="e6da9-110">그 대신 대규모 모임에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="e6da9-111">이 풀에는 대규모 모임을 호스트 하는 데만 사용 될 특수 사용자 계정을 만드는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="e6da9-112">대규모 모임 설정은 성능에 최적화 되어 있으므로 일반 사용자로 사용 하면 PSTN 끝점을 사용할 때 P2P 세션을 모임으로 승격할 수 없는 등의 문제가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="e6da9-113">정확히 두 개의 프런트 엔드 서버를 사용 하 여 풀을 관리 하려면 몇 가지 특별 고려 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="e6da9-114">자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="e6da9-115">또한 대규모 모임에 사용 되는 풀에 대해 필요에 따라 재해 복구 백업 및 장애 조치를 제공 하려는 경우에는 다른 데이터 센터에 비슷한 설정 전용 풀을 사용 하 여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="e6da9-116">자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="e6da9-117">![대규모 모임 풀 구성](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "대규모 모임 풀 구성")</span><span class="sxs-lookup"><span data-stu-id="e6da9-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="e6da9-118">토폴로지에 대 한 추가 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="e6da9-119">파일 공유는 모임 콘텐츠를 저장 하는 데 필요 하며 보관 서버를 배포 하 여 사용 하는 경우 보관 파일을 저장 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="e6da9-120">파일 공유는 풀 전용 이거나 풀이 배포 된 사이트의 다른 풀에서 사용 하는 것과 동일한 파일 공유 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="e6da9-121">파일 공유를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 구성을](lync-server-2013-configure-dfs-file-storage.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="e6da9-122">Office Web Apps 서버는 대규모 모임에서 PowerPoint 프레젠테이션 기능을 사용 하도록 설정 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="e6da9-123">Office Web Apps 서버는 대규모 모임 풀 전용 이거나 전용 풀이 배포 된 사이트의 다른 풀에서 사용 하는 동일한 Office Web Apps 서버 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="e6da9-124">프런트 엔드 서버의 부하 분산에는 HTTP 트래픽에 대 한 하드웨어 로드 밸런싱 (예: 모임 콘텐츠 다운로드)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="e6da9-125">DNS 부하 분산은 SIP 트래픽에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="e6da9-126">자세한 내용은 [Lync Server 2013에 대 한 부하 분산 요구 사항을](lync-server-2013-load-balancing-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="e6da9-127">전용 대용량 모임 풀에 모니터링 서버를 사용 하려는 경우에는 Lync Server 배포의 모든 프런트 엔드 서버 풀에서 공유 되는 모니터링 서버와 해당 데이터베이스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="e6da9-128">하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6da9-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="e6da9-129">전용 대용량 모임 풀의 서버에 대 한 하드웨어 요구 사항은 다른 Lync Server 2013 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="e6da9-130">하드웨어 요구 사항에 대 한 자세한 내용은 "[Lync server 용 서버 하드웨어 플랫폼 2013](lync-server-2013-server-hardware-platforms.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e6da9-131">전용 대용량 모임 풀의 서버는 모든 Lync Server 2013 소프트웨어 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="e6da9-132">소프트웨어 요구 사항에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="e6da9-133">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="e6da9-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="e6da9-134">Lync Server 2013의 데이터베이스 소프트웨어 지원</span><span class="sxs-lookup"><span data-stu-id="e6da9-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="e6da9-135">Lync Server 2013에 대한 추가 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6da9-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="e6da9-136">또한 Lync Server 2013와 모든 Lync Server 2013 클라이언트에는 최신 업데이트가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="e6da9-137">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6da9-137">Configuration Requirements</span></span>

<span data-ttu-id="e6da9-138">대규모 모임에 대 한 새로운 회의 정책을 만든 다음 전용 대용량 모임 풀에 속한 사용자에 게 회의 정책을 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="e6da9-139">다음 설정을 사용 하 여 회의 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="e6da9-140">**MaxMeetingSize** 옵션을 **1000**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="e6da9-141">(기본값은 **250**입니다.)</span><span class="sxs-lookup"><span data-stu-id="e6da9-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="e6da9-142">**AllowLargeMeetings** 옵션을 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="e6da9-143">**Enableappdesktopsharing** 옵션을 **없음**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="e6da9-144">**AllowUserToScheduleMeetingsWithAppSharing** 옵션을 **False**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="e6da9-145">**Allowsharednotes** 옵션을 **False**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="e6da9-146">**Allowannotations** 옵션을 **False**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="e6da9-147">**DisablePowerPointAnnotations** 옵션을 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="e6da9-148">**AllowMultiview** 옵션을 **False**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="e6da9-149">**EnableMultiviewJoin** 옵션을 **False**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6da9-150">Lync Server 2013의 1000 사용자 대규모 모임에 대 한 지원에는 모임 스케줄러에 대 한 회의 정책의 <STRONG>AllowLargeMeetings</STRONG> 설정이 true로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="e6da9-151">이 설정을 true로 설정 하면 사용자가 모임에 참가할 때 추가 대규모 모임에 대해 Lync 환경이 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="e6da9-152">특히 대규모 모임에서 Lync는 전체 모임 참가자 목록의 초기 또는 업데이트를 표시 하지 않으며,이는 클라이언트와 Lync 서버 2013 모두에 대 한 성능 병목 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="e6da9-153">대신 Lync에는 사용자 및 모임의 발표자 목록에 대 한 정보만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="e6da9-154">Lync는 대규모 모임에서 사용할 수 있는 참가자의 총 수를 계속 올바르게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="e6da9-155">**최대 모임 크기** 설정을 제외한, 대규모 모임에서 필요 하지 않은 회의 기능을 사용 하지 않도록 설정 하려면 여기에 지정 된 다른 모든 회의 정책 설정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="e6da9-156">또한 풀에 있고 모임 일정 관리를 담당 하는 각 Lync Server 2013 사용자에 게 적절 한 사용 권한이 있도록 전용 대용량 모임 풀을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="e6da9-157">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-157">To do this, do the following:</span></span>

  - <span data-ttu-id="e6da9-158">**발표자로 지정** 옵션을 **없음**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-158">Set the **Designate as presenter** option to **None**.</span></span> <span data-ttu-id="e6da9-159">일반적으로 대규모 모임의 모든 참가자에 대 한 한 명 이상의 사용자가 발표자 인 경우에는 참가자가 발표자로 서 대규모 모임에 자동으로 참여 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-159">Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters.</span></span> <span data-ttu-id="e6da9-160">대신 발표자는 모임 예약 시간에 명시적으로 지정 되거나 대규모 모임 중에 명시적으로 승격 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-160">Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="e6da9-161">**지정 된 컨퍼런스 회의 종류가 기본적으로** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="e6da9-162">이 설정은 모임의 온라인 모임 추가 2013 기능이 이끌이의 지정 된 회의를 사용 하 여 언제 든 지 회의를 예약할 지 여부를 제어 하며,이는 예약 된 모임에 동일한 참가 URL 및 오디오 정보가 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="e6da9-163">소규모 그룹 공동 작업 시나리오에서는 모든 사용자에 게 고유한 회의가 있고, 상수 조인 URL 및 오디오 정보로 인해 모임 참가에 더 빠르게 참가할 수 있으므로 이러한 지정 된 회의 종류가 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="e6da9-164">그러나 대규모 모임 시나리오에서는 대규모 모임 지원 직원이 단일 사용자 자격 증명 집합을 사용 하 여 대규모 모임을 예약 하 고 모임 요청자에 게 참가 Url 및 오디오 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="e6da9-165">이 경우에는 다른 URL을 사용 하 여 각 모임에 참가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="e6da9-166">필요 하지 않은 경우 **익명 사용자의 기본값으로** 허용 확인란이 선택 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="e6da9-167">이 설정은 지정 된 회의를 사용 하지 않을 때 Lync 2013의 온라인 모임 추가 기능에서 예약한 기본 모임 액세스 형식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="e6da9-168">이 설정에 적합 한 옵션은 조직의 요구 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="e6da9-169">조직에 대 한 대부분의 대규모 모임이 내부 모임이 면이 옵션을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e6da9-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="e6da9-170">대부분의 대규모 모임에서 외부 사용자가 참가할 수 있어야 하는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6da9-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

