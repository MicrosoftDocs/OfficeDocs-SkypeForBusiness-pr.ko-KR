---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 데이터'
description: 'Lync Server 2013: 백업 및 복원 요구 사항: 데이터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563184"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="bc81a-103">Lync Server 2013의 백업 및 복원 요구 사항: 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-103">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc81a-104">_**마지막으로 수정 된 항목:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="bc81a-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="bc81a-105">Lync Server에서는 데이터베이스에 저장 된 설정 및 구성 정보와 데이터베이스 및 파일 저장소에 저장 된 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-105">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="bc81a-106">이 항목에서는 조직에 오류 또는 중단이 발생할 경우 서비스를 복원 하기 위해 백업 해야 하는 데이터에 대해 설명 하 고, Lync Server에서 사용 하는 데이터와 구성 요소를 별도로 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-106">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="bc81a-107">설정 및 구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc81a-107">Settings and Configuration Requirements</span></span>

<span data-ttu-id="bc81a-108">이 항목에서는 Lync Server 서비스의 복구에 필요한 설정 및 구성 정보를 백업 및 복원 하는 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-108">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="bc81a-109">구성 정보는 중앙 관리 저장소나 다른 백 엔드 데이터베이스 또는 Standard Edition server에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-109">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="bc81a-110">다음 표에서는 백업 및 복원 하는 데 필요한 설정 및 구성 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-110">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="bc81a-111">설정 및 구성 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-111">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc81a-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bc81a-112">Type of data</span></span></th>
<th><span data-ttu-id="bc81a-113">저장된 위치</span><span class="sxs-lookup"><span data-stu-id="bc81a-113">Where stored</span></span></th>
<th><span data-ttu-id="bc81a-114">설명/백업할 시기</span><span class="sxs-lookup"><span data-stu-id="bc81a-114">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc81a-115">토폴로지 구성 정보</span><span class="sxs-lookup"><span data-stu-id="bc81a-115">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="bc81a-116">중앙 관리 저장소 (데이터베이스: Xds)</span><span class="sxs-lookup"><span data-stu-id="bc81a-116">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="bc81a-117">토폴로지, 정책 및 구성 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-117">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="bc81a-118">정기 백업과 함께 백업 하 고 Lync Server 제어판 또는 cmdlet을 사용 하 여 구성 또는 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-118">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc81a-119">위치 정보</span><span class="sxs-lookup"><span data-stu-id="bc81a-119">Location information</span></span></p></td>
<td><p><span data-ttu-id="bc81a-120">중앙 관리 저장소 (데이터베이스: Lis)</span><span class="sxs-lookup"><span data-stu-id="bc81a-120">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="bc81a-p103">Enterprise Voice E9-1-1(고급 9-1-1) 구성 정보입니다. 이 정보는 일반적으로 정적입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-p103">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information. This information is generally static.</span></span></p>
<p><span data-ttu-id="bc81a-123">정기 백업 중 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-123">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc81a-124">응답 그룹 구성 정보</span><span class="sxs-lookup"><span data-stu-id="bc81a-124">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="bc81a-125">백 엔드 서버 또는 Standard Edition Server (데이터베이스: RgsConfig)</span><span class="sxs-lookup"><span data-stu-id="bc81a-125">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="bc81a-126">응답 그룹 에이전트 그룹, 큐 및 워크플로</span><span class="sxs-lookup"><span data-stu-id="bc81a-126">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="bc81a-127">정기 백업 중 및 에이전트 그룹, 큐 또는 워크플로를 추가하거나 변경한 후 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-127">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="bc81a-128">데이터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc81a-128">Data Requirements</span></span>

<span data-ttu-id="bc81a-129">다음은 오류가 발생 했을 때 Lync Server 서비스를 복원할 수 있도록 백업 해야 하는 Lync Server 데이터의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-129">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="bc81a-130">일부 데이터 형식은 복구에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-130">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="bc81a-131">이 항목에는 다음을 포함 하 여 이러한 유형의 데이터를 백업 하는 절차는 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-131">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="bc81a-132">끝점과 구독, 활성 회의 서버 및 임시 회의 상태와 같은 임시 사용자 데이터(데이터베이스: RtcDyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="bc81a-132">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="bc81a-133">주소록 데이터 (데이터베이스: Rtcab. .mdf 및 Rtcab1.mdf)</span><span class="sxs-lookup"><span data-stu-id="bc81a-133">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="bc81a-134">주소록 데이터베이스는 Active Directory 도메인 서비스에서 자동으로 다시 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-134">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="bc81a-135">통화 대기 응용 프로그램에 대 한 동적 정보 (데이터베이스: Cpsdyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="bc81a-135">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="bc81a-136">에이전트 로그인 상태 및 통화 대기 정보 (데이터베이스: Rgsdyn.mdf)와 같은 임시 응답 그룹 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-136">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="bc81a-137">영구 채팅에 대 한 준수 데이터베이스 (데이터베이스: MgcComp)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-137">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="bc81a-138">영구 채팅 준수를 사용 하도록 설정한 경우 데이터베이스에서 정보를 읽고 대체 형식으로 변환 하도록 어댑터를 구성한 경우에는 영구 채팅 준수 데이터베이스의 정보가 일시적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-138">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="bc81a-139">따라서 영구 채팅에 대 한 준수 데이터베이스는 일시적으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-139">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="bc81a-140">Lync Server 2013 영구 채팅 서버는 XML 어댑터와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-140">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="bc81a-141">또한이 데이터를 사용 하 여 Exchange Hosted 보관과 같은 다른 원본으로 이동 하는 사용자 지정 어댑터를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-141">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="bc81a-142">다음 표에서는 백업 및 복원 하는 데 필요한 데이터를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-142">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="bc81a-143">데이터베이스에 저장된 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-143">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc81a-144">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bc81a-144">Type of data</span></span></th>
<th><span data-ttu-id="bc81a-145">저장된 위치</span><span class="sxs-lookup"><span data-stu-id="bc81a-145">Where stored</span></span></th>
<th><span data-ttu-id="bc81a-146">설명/백업할 시기</span><span class="sxs-lookup"><span data-stu-id="bc81a-146">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc81a-147">영구 사용자 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-147">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="bc81a-148">백 엔드 서버 또는 Standard Edition Server (데이터베이스: RTCXDS)</span><span class="sxs-lookup"><span data-stu-id="bc81a-148">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="bc81a-149">사용자 권한, 사용자 대화 상대 목록, 서버 또는 풀 데이터, 예약된 회의 등입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-149">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="bc81a-150">이 사용자 데이터에는 회의에 업로드된 콘텐츠가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-150">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="bc81a-151">정기 백업 중 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-151">Back up with your regular backups.</span></span> <span data-ttu-id="bc81a-152">이 정보는 동적 이지만 마지막 일반 백업으로 복원 해야 하는 경우에는 업데이트 손실이 Lync Server에 치명적인 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-152">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="bc81a-153">대화 상대 목록이 조직에 중요한 경우 이 데이터를 보다 자주 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-153">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc81a-154">보관 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-154">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="bc81a-155">보관 데이터베이스(데이터베이스: LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="bc81a-155">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="bc81a-156">이 데이터는 Microsoft Exchange 통합 옵션을 사용 하도록 설정한 경우 Exchange 2013에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-156">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="bc81a-157">그렇지 않으면이 데이터는 Lync Server 보관 데이터베이스에 보관 되며, 다른 Lync Server 데이터베이스와 배치 된 되거나 별도의 데이터베이스 서버에 독립 실행형으로 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-157">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="bc81a-158">IM(인스턴트 메시징) 및 모임 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-158">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="bc81a-159">이 데이터는 Lync Server에 중요 하지 않지만 규정 목적을 위해 조직에서 중요 한 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-159">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="bc81a-160">그에 따라 백업 일정을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc81a-160">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc81a-161">데이터 모니터링</span><span class="sxs-lookup"><span data-stu-id="bc81a-161">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="bc81a-162">모니터링 데이터베이스(LcsCDR.mdf 및 QoeMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="bc81a-162">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="bc81a-163">이러한 데이터베이스는 다른 Lync Server 데이터베이스와 배치 된, 별도의 데이터베이스 서버에서 독립 실행형으로 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-163">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="bc81a-164">통화 정보 기록 (LcsCDR) 및 QoE (환경 품질) 메트릭 (QoeMetrics)</span><span class="sxs-lookup"><span data-stu-id="bc81a-164">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="bc81a-p112">통화 정보 기록은 동적이며 업무에 중요할 수 있습니다. 규제 이유에 따라 이러한 레코드가 필요한지 여부를 고려하여 백업 일정을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc81a-p112">Call detail records are dynamic and may be critical to your business. Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="bc81a-167">체감 품질 정보는 동적입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-167">Quality of experience information is dynamic.</span></span> <span data-ttu-id="bc81a-168">Lync Server 작업에는 QoE 데이터 손실이 중요 하지 않지만 비즈니스에 중요 한 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-168">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="bc81a-169">조직에서 이 정보가 중요한 정도에 따라 백업 일정을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc81a-169">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc81a-170">영구 채팅 데이터</span><span class="sxs-lookup"><span data-stu-id="bc81a-170">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="bc81a-171">영구 채팅 데이터베이스 (관리)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-171">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="bc81a-172">이 데이터베이스는 다른 Lync Server 데이터베이스 또는 별도의 데이터베이스 서버에 독립 실행형으로 배치 된 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-172">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="bc81a-173">영구 채팅 데이터는 대화방에 게시 되는 실제 채팅 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-173">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="bc81a-174">이 데이터는 비즈니스에 중요 한 영향을 주는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-174">This data is often business critical.</span></span></p>
<p><span data-ttu-id="bc81a-175">Lync Server에 제공 된 <strong>export-cspersistentchatdata</strong> cmdlet을 사용 하 여 SQL Server 백업을 사용 하거나 데이터베이스를 내보내도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-175">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="bc81a-176">데이터를 복구 하려면 마지막 전체 백업 시점으로 데이터베이스를 가져오고 복원할 수 있으며,이는 오류 지점으로 데이터베이스를 복원할 수 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-176">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="bc81a-177">파일 저장소 데이터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc81a-177">File Store Data Requirements</span></span>

<span data-ttu-id="bc81a-178">Enterprise Edition 배포에서 Lync Server 파일 저장소는 일반적으로 파일 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-178">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="bc81a-179">Standard Edition 배포에서는 Lync Server 파일 저장소가 Standard Edition 서버에 기본적으로 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-179">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="bc81a-180">일반적으로 사이트에 대해 공유 되는 Lync Server 파일 저장소는 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-180">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="bc81a-181">영구 채팅 파일 저장소는 Lync Server 파일 저장소와 동일한 파일 공유를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-181">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="bc81a-182">파일 저장소 위치는 \\ \\ 서버 \\ 공유 이름으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-182">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="bc81a-183">파일 저장소의 특정 위치를 찾으려면 토폴로지 작성기를 열고 **파일 저장소** 노드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-183">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="bc81a-184">다음 표에서는 백업 및 복원하는 데 필요한 파일 저장소가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-184">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="bc81a-185">파일 저장소</span><span class="sxs-lookup"><span data-stu-id="bc81a-185">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc81a-186">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bc81a-186">Type of data</span></span></th>
<th><span data-ttu-id="bc81a-187">저장된 위치</span><span class="sxs-lookup"><span data-stu-id="bc81a-187">Where stored</span></span></th>
<th><span data-ttu-id="bc81a-188">설명/백업할 시기</span><span class="sxs-lookup"><span data-stu-id="bc81a-188">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc81a-189">Lync Server 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="bc81a-189">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="bc81a-190">일반적으로 파일 서버, 파일 클러스터 또는 Standard Edition 서버에서</span><span class="sxs-lookup"><span data-stu-id="bc81a-190">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="bc81a-191">모임 콘텐츠, 모임 콘텐츠 메타 데이터, 모임 준수 로그, 응용 프로그램 데이터 파일, 장치 업데이트를 위한 업데이트 파일, 응답 그룹, 통화 대기 및 알림 응용 프로그램, 그리고 영구 채팅방에 게시 되는 파일에 대 한 오디오 파일</span><span class="sxs-lookup"><span data-stu-id="bc81a-191">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="bc81a-192">정기 백업 중 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-192">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="bc81a-193">추가 백업 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc81a-193">Additional Backup Requirements</span></span>

<span data-ttu-id="bc81a-194">오류 발생 시 Lync Server 서비스를 복원 하는 기능을 보장 하려면 Lync Server 자체에 포함 되지 않은 필요한 구성 요소를 모두 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-194">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="bc81a-195">다음 구성 요소는이 문서에서 설명 하는 Lync Server 백업 및 복원 프로세스의 일부로 백업 또는 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-195">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="bc81a-196">**Active Directory 도메인 서비스**     Lync Server를 백업 하는 동시에 Active Directory 도구를 사용 하 여 AD DS를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-196">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="bc81a-197">Lync Server에서 AD DS의 대화 상대 개체가 필요한 경우 발생할 수 있는 문제를 방지 하기 위해 AD DS와 Lync Server의 동기화를 유지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-197">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="bc81a-198">AD DS는 Lync Server에서 사용 하는 다음과 같은 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-198">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="bc81a-199">사용자 SIP URI 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="bc81a-199">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="bc81a-200">응답 그룹 및 회의 전화 교환과 같은 응용 프로그램에 대 한 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="bc81a-200">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="bc81a-201">중앙 관리 저장소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-201">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="bc81a-202">Kerberos 인증 계정 (선택적 컴퓨터 개체) 및 Lync Server 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="bc81a-202">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="bc81a-203">Windows Server 2008에서 AD DS를 백업 및 복원 하는 방법에 대 한 자세한 내용은의 "AD DS 백업 및 복구 단계별 가이드"를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .</span><span class="sxs-lookup"><span data-stu-id="bc81a-203">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="bc81a-204">**인증 기관 및 인증서**     CA (인증 기관) 및 인증서를 백업 하는 데 조직의 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-204">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="bc81a-205">내보낼 수 있는 개인 키를 사용 하는 경우에는 인증서와 개인 키를 백업한 다음이 문서의 절차를 사용 하 여 Lync Server를 복원 하는 경우이를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-205">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="bc81a-206">내부 CA를 사용 하는 경우 Lync Server를 복원 해야 하는 경우 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-206">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="bc81a-207">개인 키는 컴퓨터에 문제가 발생했을 때 사용할 수 있도록 안전한 위치에 보관해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-207">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="bc81a-208">**System Center Operations Manager**     Microsoft System Center Operations Manager (이전의 Microsoft Operations Manager)를 사용 하 여 Lync Server 배포를 모니터링 하는 경우에는 Lync Server를 모니터링 하는 동안 생성 되는 데이터를 선택적으로 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-208">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="bc81a-209">표준 SQL Server 백업 프로세스를 사용 하 여 System Center Operations Manager 파일을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-209">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="bc81a-210">복구 중에는 이러한 파일이 복원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-210">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="bc81a-211">**PSTN (공중 전화망) 게이트웨이 구성**     Enterprise Voice 또는 Sba (survivable Branch 기기를 사용 하는 경우 PSTN 게이트웨이 구성을 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-211">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="bc81a-212">PSTN 게이트웨이 구성의 백업 및 복원에 대한 자세한 내용은 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc81a-212">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="bc81a-213">**Lync server 또는 Office Communications server**     버전 동시에 Lync server 2010 배포 2013에 이전 버전의 Office Communications Server가 설치 되어 있는 경우에는이 문서의 절차를 사용 하 여 이전 버전을 백업 하거나 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-213">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="bc81a-214">대신 이전 버전에 대해 설명된 백업 및 복원 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-214">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="bc81a-215">Lync Server 2010의 백업 및 복원에 대 한 자세한 내용은를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span><span class="sxs-lookup"><span data-stu-id="bc81a-215">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="bc81a-216">Microsoft Office Communications Server 2007 R2를 백업 및 복원 하는 방법에 대 한 자세한 내용은를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .</span><span class="sxs-lookup"><span data-stu-id="bc81a-216">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="bc81a-217">**인프라 정보**     방화벽 구성, 부하 분산 구성, IIS (인터넷 정보 서비스) 구성, DNS (Domain Name System) 레코드 및 IP 주소, 동적 호스트 구성 프로토콜 (DHCP) 구성 등 인프라에 대 한 정보를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-217">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="bc81a-218">이러한 구성 요소의 백업에 대한 자세한 내용은 해당 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc81a-218">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="bc81a-219">**Microsoft exchange 및 EXCHANGE UM (통합 메시징)**     Microsoft Exchange 설명서에 설명 된 대로 Microsoft Exchange 및 Exchange UM을 백업 및 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-219">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="bc81a-220">Exchange Server 2013 백업 및 복원에 대 한 자세한 내용은를 참조 하세요 [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) .</span><span class="sxs-lookup"><span data-stu-id="bc81a-220">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="bc81a-221">Exchange Server 2010 백업 및 복원에 대 한 자세한 내용은를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .</span><span class="sxs-lookup"><span data-stu-id="bc81a-221">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="bc81a-222">Lync Server 2013에서는 Exchange 2013에 저장 된 사용자 연락처 목록, 고화질 사용자 사진 및 보관 데이터를 포함 하는 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-222">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="bc81a-223">이러한 유형의 데이터를 백업 하는 방법을 보려면 다음 목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc81a-223">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="bc81a-224">**고화질 사진을** Exchange Server 백업의 일부로 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-224">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="bc81a-225">**통합 연락처 저장소** 는 Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-225">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="bc81a-226">통합 연락처 저장소를 사용 하면 사용자가 Exchange 2013에서 모든 연락처 정보를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-226">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="bc81a-227">사용자 연락처가 통합 연락처 저장소나 Lync 백 엔드 서버에 저장 되는지 여부에 따라 사용자에 대 한 백업이 최신 상태 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-227">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="bc81a-228">다음 시나리오에서는 사용자 연락처를 통합 연락처 저장소로 마이그레이션하는 경우 백업 및 복원 프로세스에 대 한 문제를 발생 시킬 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-228">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="bc81a-229">**시나리오 1:** 사용자 연락처는 통합 연락처 저장소로 마이그레이션되고 사용자 연락처를 마이그레이션하기 전에 수행한 Lync Server 백업에서 복원이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-229">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="bc81a-230">이 시나리오에서 사용자는 Lync Server 마이그레이션 작업이 사용자 연락처를 Exchange로 마이그레이션하기 시작할 때까지 기한이 지난 대화 상대 중 최대 1 일까 집니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-230">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="bc81a-231">사용자 연락처가 이전에 통합 연락처 저장소로 마이그레이션 되었기 때문에 Exchange 연락처 정보가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-231">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="bc81a-232">이 시나리오에서는 관리자 개입이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-232">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="bc81a-233">**시나리오 2:** 사용자 연락처가 이전에 통합 연락처 저장소에 저장 되었지만 롤백 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-233">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="bc81a-234">사용자 연락처가 통합 연락처 저장소에 저장 되었을 때 수행한 Lync Server 백업에서 복원 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-234">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="bc81a-235">이 시나리오에서는 `Error: Incorrect Exchange Version` 클라이언트 또는 Lyss 서버 로그에 있는 오류 메시지에 문제가 있는 것으로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-235">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="bc81a-236">사용자가 Exchange에서 직접 Lync 2013의 대화 상대 목록에 액세스할 수 있지만 클라이언트의 상태는 Lync Server 상태와 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-236">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="bc81a-237">이 문제를 해결 하려면 관리자가 영향을 받는 사용자에 대해 **invoke-csucsrollback** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-237">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="bc81a-238">**보관 데이터** 는 Exchange 2013에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-238">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="bc81a-239">이 데이터는 Lync Server에 중요 하지 않지만 규정 목적을 위해 조직에서 중요 한 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-239">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="bc81a-240">보관 데이터가 Exchange에 저장 되 고 조직에 중요 한 경우 Exchange 백업 및 복원 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-240">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="bc81a-241">Exchange에 저장 된 보관 데이터는 다시 Lync Server로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-241">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="bc81a-242">또한 Lync 보관 데이터베이스에 이미 저장 된 데이터를 Exchange로 이동할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc81a-242">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

