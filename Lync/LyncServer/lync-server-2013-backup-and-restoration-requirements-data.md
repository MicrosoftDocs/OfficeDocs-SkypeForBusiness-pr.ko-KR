---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 데이터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="40b0d-102">Lync Server 2013의 백업 및 복원 요구 사항: 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b0d-103">_**마지막으로 수정한 주제:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="40b0d-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="40b0d-104">Lync Server는 데이터베이스에 저장 된 설정 및 구성 정보와 데이터베이스 및 파일 저장소에 저장 된 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="40b0d-105">이 항목에서는 조직에 장애가 있거나 중단 되는 경우 서비스를 복원할 수 있도록 백업 해야 하는 데이터에 대해 설명 하 고, Lync Server에서 사용 하는 데이터와 구성 요소를 별도로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="40b0d-106">설정 및 구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="40b0d-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="40b0d-107">이 항목에는 Lync Server 서비스의 복구에 필요한 설정 및 구성 정보를 백업 및 복원 하는 절차가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="40b0d-108">구성 정보는 중앙 관리 저장소나 다른 백 엔드 데이터베이스 또는 Standard Edition server에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="40b0d-109">다음 표에서는 백업 및 복원에 필요한 설정 및 구성 정보를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="40b0d-110">설정 및 구성 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b0d-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="40b0d-111">Type of data</span></span></th>
<th><span data-ttu-id="40b0d-112">저장 위치</span><span class="sxs-lookup"><span data-stu-id="40b0d-112">Where stored</span></span></th>
<th><span data-ttu-id="40b0d-113">설명/백업 시기</span><span class="sxs-lookup"><span data-stu-id="40b0d-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b0d-114">토폴로지 구성 정보</span><span class="sxs-lookup"><span data-stu-id="40b0d-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="40b0d-115">중앙 관리 저장소 (데이터베이스: Xds)</span><span class="sxs-lookup"><span data-stu-id="40b0d-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="40b0d-116">토폴로지, 정책 및 구성 설정</span><span class="sxs-lookup"><span data-stu-id="40b0d-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="40b0d-117">정기 백업으로 백업 하 고 Lync Server 제어판 또는 cmdlet을 사용 하 여 구성 또는 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b0d-118">위치 정보</span><span class="sxs-lookup"><span data-stu-id="40b0d-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="40b0d-119">중앙 관리 저장소 (데이터베이스: Lis)</span><span class="sxs-lookup"><span data-stu-id="40b0d-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="40b0d-120">Enterprise Voice 향상 9-1-1 (E9-1-1) 구성 정보.</span><span class="sxs-lookup"><span data-stu-id="40b0d-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="40b0d-121">이 정보는 일반적으로 정적입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="40b0d-122">정기 백업을 사용 하 여 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b0d-123">응답 그룹 구성 정보</span><span class="sxs-lookup"><span data-stu-id="40b0d-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="40b0d-124">백 엔드 서버 또는 Standard Edition 서버 (데이터베이스: RgsConfig)</span><span class="sxs-lookup"><span data-stu-id="40b0d-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="40b0d-125">응답 그룹 에이전트 그룹, 큐 및 워크플로</span><span class="sxs-lookup"><span data-stu-id="40b0d-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="40b0d-126">정기 백업으로 백업 하 고 에이전트 그룹, 큐 또는 워크플로를 추가 하거나 변경한 후</span><span class="sxs-lookup"><span data-stu-id="40b0d-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="40b0d-127">데이터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="40b0d-127">Data Requirements</span></span>

<span data-ttu-id="40b0d-128">다음은 오류가 발생할 경우 Lync Server 서비스를 복원할 수 있도록 백업 해야 하는 Lync Server 데이터 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="40b0d-129">일부 유형의 데이터는 복구에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="40b0d-130">이 항목에는 다음을 포함 하 여 이러한 유형의 데이터를 백업 하는 절차가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="40b0d-131">끝점, 구독, 활성 회의 서버 및 일시적인 회의 상태 (데이터베이스: RtcDyn)와 같은 임시 사용자 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="40b0d-132">주소록 데이터 (데이터베이스: Rtcab .mdf 및 Rtcab1).</span><span class="sxs-lookup"><span data-stu-id="40b0d-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="40b0d-133">주소록 데이터베이스는 Active Directory 도메인 서비스에서 자동으로 다시 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="40b0d-134">통화 공원 응용 프로그램에 대 한 동적 정보 (데이터베이스: CpsDyn)</span><span class="sxs-lookup"><span data-stu-id="40b0d-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="40b0d-135">에이전트 로그인 상태 및 통화 대기 정보 (데이터베이스: RgsDyn)와 같은 임시 응답 그룹 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="40b0d-136">영구 채팅 (데이터베이스: MgcComp)에 대 한 준수 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="40b0d-137">지속적인 채팅 준수를 사용 하는 경우 데이터베이스에서 정보를 읽고 대체 형식으로 변환 하도록 구성 된 어댑터가 있으면 영구 채팅 준수 데이터베이스의 정보는 일시적입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="40b0d-138">따라서 영구 채팅에 대 한 규정 준수 데이터베이스가 일시적인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="40b0d-139">Lync Server 2013 영구 채팅 서버에는 XML 어댑터가 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="40b0d-140">또한이 데이터를 사용 하는 사용자 지정 어댑터를 설치 하 고 Exchange 호스팅 보관 함과 같은 다른 원본으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="40b0d-141">다음 표에서는 백업 하 고 복원 하는 데 필요한 데이터를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="40b0d-142">데이터베이스에 저장 된 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b0d-143">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="40b0d-143">Type of data</span></span></th>
<th><span data-ttu-id="40b0d-144">저장 위치</span><span class="sxs-lookup"><span data-stu-id="40b0d-144">Where stored</span></span></th>
<th><span data-ttu-id="40b0d-145">설명/백업 시기</span><span class="sxs-lookup"><span data-stu-id="40b0d-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b0d-146">영구 사용자 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="40b0d-147">백 엔드 서버 또는 Standard Edition 서버 (데이터베이스: RTCXDS)</span><span class="sxs-lookup"><span data-stu-id="40b0d-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="40b0d-148">사용자 권한, 사용자 연락처 목록, 서버 또는 풀 데이터, 예약 된 회의 등</span><span class="sxs-lookup"><span data-stu-id="40b0d-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="40b0d-149">이 사용자 데이터에는 회의에 업로드 한 콘텐츠가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="40b0d-150">정기 백업을 사용 하 여 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-150">Back up with your regular backups.</span></span> <span data-ttu-id="40b0d-151">이 정보는 동적 이지만 마지막 정기 백업으로 복원 해야 하는 경우에는 업데이트 손실이 Lync Server에 치명적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="40b0d-152">연락처 목록이 조직에 중요 한 경우에는이 데이터를 더 자주 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b0d-153">데이터 보관</span><span class="sxs-lookup"><span data-stu-id="40b0d-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="40b0d-154">보관 데이터베이스 (데이터베이스: LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="40b0d-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="40b0d-155">Microsoft Exchange 통합 옵션을 사용 하도록 설정한 경우이 데이터는 Exchange 2013에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="40b0d-156">그렇지 않으면이 데이터는 Lync Server 보관 데이터베이스에 보관 되며, 이것은 다른 Lync Server 데이터베이스와 함께 collocated, 별도의 데이터베이스 서버에 독립 실행형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="40b0d-157">인스턴트 메시지 (IM) 및 모임 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="40b0d-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="40b0d-158">이 데이터는 Lync Server에 중요 하지 않지만 규정 목적을 위해 조직에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="40b0d-159">백업 일정을 적절 하 게 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b0d-160">데이터 모니터링</span><span class="sxs-lookup"><span data-stu-id="40b0d-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="40b0d-161">데이터베이스 모니터링 (LcsCDR 및 QoeMetrics)</span><span class="sxs-lookup"><span data-stu-id="40b0d-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="40b0d-162">이러한 데이터베이스는 다른 Lync Server 데이터베이스와 함께 collocated 또는 별도의 데이터베이스 서버에 독립 실행형이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="40b0d-163">통화 정보 레코드 (LcsCDR) 및 환경 품질 (체감 품질) 메트릭 (QoeMetrics).</span><span class="sxs-lookup"><span data-stu-id="40b0d-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="40b0d-164">통화 정보 레코드는 동적인 업무에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="40b0d-165">규정 상의 이유로 이러한 레코드가 필요한 지 여부를 고려 하 여 백업 일정을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="40b0d-166">경력 정보의 품질은 동적입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="40b0d-167">Lync Server의 작동에 대 한 체감 품질 데이터 손실은 중요 하지 않지만 비즈니스에 중요 한 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="40b0d-168">이 정보가 조직에 얼마나 중요 한 지에 따라 백업 일정을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b0d-169">영구 채팅 데이터</span><span class="sxs-lookup"><span data-stu-id="40b0d-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="40b0d-170">영구 채팅 데이터베이스 (mgd).</span><span class="sxs-lookup"><span data-stu-id="40b0d-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="40b0d-171">이 데이터베이스는 다른 Lync Server 데이터베이스와 함께 collocated 또는 별도의 데이터베이스 서버에 독립 실행형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="40b0d-172">영구 채팅 데이터는 채팅방에 게시 되는 실제 채팅 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="40b0d-173">이 데이터는 비즈니스에 중요 한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="40b0d-174">Lync Server에 제공 되는 <strong>export-CsPersistentChatData</strong> cmdlet을 사용 하 여 SQL Server 백업을 사용할지 또는 데이터베이스를 내보낼지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="40b0d-175">데이터 복구의 경우 마지막 전체 백업의 시점으로 데이터베이스를 가져오고 복원할 수 있으며,이는 실패 시점으로 데이터베이스를 복원할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="40b0d-176">파일 저장소 데이터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="40b0d-176">File Store Data Requirements</span></span>

<span data-ttu-id="40b0d-177">Enterprise Edition 배포에서 Lync Server 파일 저장소는 일반적으로 파일 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="40b0d-178">스탠더드 버전 배포의 경우 Lync Server 파일 저장소는 기본적으로 Standard Edition 서버에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="40b0d-179">일반적으로 사이트에 대해 공유 되는 Lync Server 파일 저장소 1 개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="40b0d-180">영구 채팅 파일 저장소는 Lync Server 파일 저장소와 동일한 파일 공유를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="40b0d-181">파일 저장소 위치는 서버 \\ \\\\공유 이름으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="40b0d-182">파일 저장소의 특정 위치를 찾으려면 토폴로지 작성기를 열고 **파일 저장소** 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="40b0d-183">다음 표에서는 백업 하 고 복원 하는 데 필요한 파일 저장소를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="40b0d-184">파일 저장소</span><span class="sxs-lookup"><span data-stu-id="40b0d-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b0d-185">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="40b0d-185">Type of data</span></span></th>
<th><span data-ttu-id="40b0d-186">저장 위치</span><span class="sxs-lookup"><span data-stu-id="40b0d-186">Where stored</span></span></th>
<th><span data-ttu-id="40b0d-187">설명/백업 시기</span><span class="sxs-lookup"><span data-stu-id="40b0d-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b0d-188">Lync Server 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="40b0d-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="40b0d-189">일반적으로 파일 서버, 파일 클러스터 또는 Standard Edition 서버에서</span><span class="sxs-lookup"><span data-stu-id="40b0d-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="40b0d-190">모임 콘텐츠, 모임 콘텐츠 메타 데이터, 모임 준수 로그, 장치 업데이트에 대 한 파일 업데이트, 응답 그룹에 대 한 오디오 파일, 통화 공원, 알림 응용 프로그램, 영구 채팅방에 게시 된 파일</span><span class="sxs-lookup"><span data-stu-id="40b0d-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="40b0d-191">정기 백업을 사용 하 여 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="40b0d-192">추가 백업 요구 사항</span><span class="sxs-lookup"><span data-stu-id="40b0d-192">Additional Backup Requirements</span></span>

<span data-ttu-id="40b0d-193">오류가 발생 했을 때 Lync Server 서비스를 복원할 수 있도록 하려면 Lync Server 자체에 포함 되지 않은 필요한 구성 요소를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="40b0d-194">다음 구성 요소는이 문서에서 설명 하는 Lync Server 백업 및 복원 프로세스의 일부로 서 백업 또는 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="40b0d-195">**Active directory 도메인 서비스**   Lync Server를 백업할 때 active directory 도구를 사용 하 여 AD DS를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="40b0d-196">Lync Server에서 AD DS의 연락처 개체가 필요한 경우 발생할 수 있는 문제를 방지 하기 위해 AD DS와 Lync 서버를 동기화 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="40b0d-197">AD DS는 Lync Server에 사용 되는 다음 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="40b0d-198">사용자 SIP URI 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="40b0d-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="40b0d-199">응답 그룹 및 회의 수행자와 같은 응용 프로그램에 대 한 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="40b0d-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="40b0d-200">중앙 관리 저장소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="40b0d-201">Kerberos 인증 계정 (선택적 컴퓨터 개체) 및 Lync Server 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="40b0d-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="40b0d-202">Windows Server 2008에서 AD DS를 백업 및 복원 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)"Ad ds 백업 및 복구 단계별 가이드"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="40b0d-203">**인증 기관 및 인증서**   는 CA (인증 기관) 및 인증서 백업에 조직의 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="40b0d-204">내보낼 수 있는 개인 키를 사용 하는 경우에는 인증서와 개인 키를 백업한 다음이 문서의 절차를 사용 하 여 Lync Server를 복원 하는 경우 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="40b0d-205">내부 CA를 사용 하는 경우 Lync Server를 복원 해야 하는 경우 다시 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="40b0d-206">컴퓨터에 장애가 발생할 경우 사용할 수 있는 안전한 위치에 개인 키를 유지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="40b0d-207">**System center operations manager**   microsoft system center operations manager (이전의 microsoft Operations manager)를 사용 하 여 lync server 배포를 모니터링 하는 경우 선택적으로 lync server를 모니터링 하는 동안 만든 데이터를 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="40b0d-208">표준 SQL Server 백업 프로세스를 사용 하 여 System Center Operations Manager 파일을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="40b0d-209">이러한 파일은 복구 중에 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="40b0d-210">**Pstn (공개 전환 전화 네트워크) 게이트웨이 구성**   엔터프라이즈 음성 또는 Survivable Branch 기기를 사용 하는 경우 pstn 게이트웨이 구성을 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="40b0d-211">PSTN 게이트웨이 구성 백업 및 복원에 대 한 자세한 내용은 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="40b0d-212">**Lync server 또는 office Communications server**   버전 동시 사용 lync server 2013 배포가 lync server 2010 또는 이전 버전의 Office communications server와 함께 존재 하는 경우이 문서의 절차를 사용 하 여 이전 버전을 백업 하거나 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="40b0d-213">대신 이전 버전에 맞게 문서화 된 백업 및 복원 절차를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="40b0d-214">Lync Server 2010를 백업 및 복원 하는 방법에 대 [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="40b0d-215">Microsoft Office Communications Server 2007 R2를 백업 및 복원 하는 방법에 대 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="40b0d-216">\*\*\*\*   인프라 구성, 부하 분산 구성, IIS (인터넷 정보 서비스) 구성, DNS (Domain Name System) 레코드 및 IP 주소, DHCP (동적 호스트 구성 프로토콜) 구성 등 인프라에 대 한 정보를 백업 하는 데 필요한 인프라 정보</span><span class="sxs-lookup"><span data-stu-id="40b0d-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="40b0d-217">이러한 구성 요소를 백업 하는 방법에 대 한 자세한 내용은 해당 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="40b0d-218">\*\*\*\*   Microsoft exchange 및 exchange um (통합 메시징) 백업 및 microsoft exchange 설명서에 설명 된 대로 microsoft exchange 및 exchange um을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="40b0d-219">Exchange Server 2013 백업 및 복원에 대 한 자세한 내용은을 [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="40b0d-220">Exchange Server 2010 백업 및 복원에 대 한 자세한 내용은을 [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="40b0d-221">Lync Server 2013에는 사용자 연락처 목록, 고화질 사용자 사진, Exchange 2013에 저장 된 데이터 보관 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="40b0d-222">이러한 유형의 데이터를 백업 하는 방법에 대 한 자세한 내용은 다음 목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40b0d-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="40b0d-223">**고해상도 사진은** Exchange Server 백업의 일부로 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="40b0d-224">**통합 된 대화 상대 저장소** 는 Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="40b0d-225">통합 된 대화 상대 저장소를 통해 사용자는 Exchange 2013에서 모든 연락처 정보를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="40b0d-226">사용자 연락처가 통합 된 연락처 저장소나 Lync 백 엔드 서버에 저장 되는지 여부에 따라 백업이 사용자에 게 최신 상태 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="40b0d-227">다음 시나리오는 사용자 연락처를 통합 대화 저장소로 마이그레이션하는 경우 백업 및 복원 프로세스에 문제가 발생할 수 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="40b0d-228">**시나리오 1:** 사용자 연락처는 통합 된 연락처 저장소로 마이그레이션되고 사용자 연락처를 마이그레이션하기 전에 수행한 Lync Server 백업에서 복원이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="40b0d-229">이 시나리오에서는 Lync Server 마이그레이션 작업이 사용자 연락처를 Exchange로 마이그레이션하기 시작 하기까지 최대 1 일 동안 사용자에 게 오래 된 연락처의 상태가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="40b0d-230">(사용자 연락처는 이전에 통합 된 연락처 저장소로 마이그레이션 되었기 때문에 Exchange 연락처 정보가 사용 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="40b0d-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="40b0d-231">이 시나리오에서는 관리자 개입이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="40b0d-232">**시나리오 2:** 사용자 연락처가 이전에 통합 된 연락처 저장소에 저장 되었지만 롤백 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="40b0d-233">사용자 연락처가 통합 대화 상대 저장소에 저장 되었을 때 만든 Lync Server 백업에서 복원이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="40b0d-234">이 시나리오에서는 클라이언트 또는 Lyss 서버 `Error: Incorrect Exchange Version` 로그의 오류 메시지가이에 대 한 문제로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="40b0d-235">사용자가 Exchange에서 직접 Lync 2013의 연락처 목록에 액세스할 수 있지만 클라이언트의 상태는 Lync Server 상태와 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="40b0d-236">이 문제를 해결 하려면 관리자가 영향을 받는 사용자에 대 한 **CsUCSRollback** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="40b0d-237">**데이터 보관** 은 Exchange 2013에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="40b0d-238">이 데이터는 Lync Server에 중요 하지 않지만 규정 목적을 위해 조직에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="40b0d-239">데이터 보관이 Exchange에 저장 되어 있고 조직에 중요 한 경우에는 Exchange 백업 및 복원 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="40b0d-240">Exchange에 저장 된 데이터 보관은 Lync 서버로 다시 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="40b0d-241">또한 Lync 보관 데이터베이스에 이미 저장 된 데이터를 Exchange에 이동할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0d-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

