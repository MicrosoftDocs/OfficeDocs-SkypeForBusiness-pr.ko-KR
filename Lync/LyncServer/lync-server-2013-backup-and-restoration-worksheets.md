---
title: 'Lync Server 2013: 백업 및 복원 워크시트'
description: 'Lync Server 2013: 백업 및 복원 워크시트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552324"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="70a5d-103">Lync Server 2013의 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="70a5d-103">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70a5d-104">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="70a5d-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="70a5d-105">조직에 대 한 백업 및 복원 계획에는 데이터 및 설정 백업 방법 및 시기에 대 한 세부 정보가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-105">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="70a5d-106">여기에 나와 있는 워크시트를 사용 하 여 특정 배포와 조직의 백업 및 복원 요구 사항에 대 한 정보를 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-106">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="70a5d-107">다음 워크시트를 사용 하 여 Lync Server 풀 또는 Standard Edition Server에 대 한 데이터베이스, 파일 저장소 및 설정 정보를 백업 및 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-107">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="70a5d-108">Lync Server를 복원 해야 하는 경우에도 쉽게 액세스할 수 있도록 이러한 워크시트의 복사본을 하나 이상 안전한 위치에 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-108">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70a5d-109">이 섹션의 워크시트에는 Lync Server 데이터베이스 및 서버의 데이터와 설정을 복원 하는 데 필요한 정보만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-109">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="70a5d-110">운영 체제 및 기타 소프트웨어를 다시 설치 하기 위한 정보와 같은 기타 복원 정보를 문서화 해야 하는 경우 조직의 배포 계획 및 백업 및 복원 계획을 사용 하 여 이러한 요구 사항을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-110">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="70a5d-111">데이터베이스 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="70a5d-111">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="70a5d-112">다음 표를 사용 하 여 Lync Server 데이터베이스를 백업 및 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-112">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="70a5d-113">백업 및 복원에 대 한 데이터베이스 정보</span><span class="sxs-lookup"><span data-stu-id="70a5d-113">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70a5d-114">Database</span><span class="sxs-lookup"><span data-stu-id="70a5d-114">Database</span></span></th>
<th><span data-ttu-id="70a5d-115">서버 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="70a5d-115">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="70a5d-116">백업 일정</span><span class="sxs-lookup"><span data-stu-id="70a5d-116">Backup schedule</span></span></th>
<th><span data-ttu-id="70a5d-117">데이터베이스 백업 도구</span><span class="sxs-lookup"><span data-stu-id="70a5d-117">Database backup tool</span></span></th>
<th><span data-ttu-id="70a5d-118">백업 집합</span><span class="sxs-lookup"><span data-stu-id="70a5d-118">Backup set</span></span></th>
<th><span data-ttu-id="70a5d-119">백업 대상</span><span class="sxs-lookup"><span data-stu-id="70a5d-119">Backup destination</span></span></th>
<th><span data-ttu-id="70a5d-120">참고</span><span class="sxs-lookup"><span data-stu-id="70a5d-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70a5d-121">사용자 데이터에 대 한 백 엔드 서버의 Rtc 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="70a5d-121">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="70a5d-122"><strong>Export-CsUserData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="70a5d-122"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="70a5d-123">Name</span><span class="sxs-lookup"><span data-stu-id="70a5d-123">Name:</span></span></p>
<p><span data-ttu-id="70a5d-124">행사</span><span class="sxs-lookup"><span data-stu-id="70a5d-124">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70a5d-125">보관 데이터베이스 서버의 LcsLog (기본 이름) 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="70a5d-125">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70a5d-126">SQL Server 관리 도구</span><span class="sxs-lookup"><span data-stu-id="70a5d-126">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="70a5d-127">Name</span><span class="sxs-lookup"><span data-stu-id="70a5d-127">Name:</span></span></p>
<p><span data-ttu-id="70a5d-128">행사</span><span class="sxs-lookup"><span data-stu-id="70a5d-128">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70a5d-129">CDRs (통화 정보 레코드)에 대 한 모니터링 데이터베이스 서버의 LcsCdr 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="70a5d-129">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70a5d-130">SQL Server 관리 도구</span><span class="sxs-lookup"><span data-stu-id="70a5d-130">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="70a5d-131">Name</span><span class="sxs-lookup"><span data-stu-id="70a5d-131">Name:</span></span></p>
<p><span data-ttu-id="70a5d-132">행사</span><span class="sxs-lookup"><span data-stu-id="70a5d-132">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70a5d-133">QoE (QoEMetrics Quality) 데이터에 대 한 모니터링 데이터베이스 서버의 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="70a5d-133">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70a5d-134">SQL Server 관리 도구</span><span class="sxs-lookup"><span data-stu-id="70a5d-134">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="70a5d-135">Name</span><span class="sxs-lookup"><span data-stu-id="70a5d-135">Name:</span></span></p>
<p><span data-ttu-id="70a5d-136">행사</span><span class="sxs-lookup"><span data-stu-id="70a5d-136">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70a5d-137">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="70a5d-137">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="70a5d-138">SQL Server 관리 도구 또는 <strong>export-cspersistentchatdata</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="70a5d-138">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="70a5d-139">Name</span><span class="sxs-lookup"><span data-stu-id="70a5d-139">Name:</span></span></p>
<p><span data-ttu-id="70a5d-140">행사</span><span class="sxs-lookup"><span data-stu-id="70a5d-140">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="70a5d-141">다음 데이터베이스에는 백업 또는 복원이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-141">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="70a5d-142">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="70a5d-142">Rtcdyn.</span></span> <span data-ttu-id="70a5d-143">이 데이터베이스의 일시적 사용자 데이터는 서비스 복원에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-143">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="70a5d-144">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="70a5d-144">Rtcab.</span></span> <span data-ttu-id="70a5d-145">주소록 데이터베이스는 Active Directory 도메인 서비스의 GAL (전체 주소 목록)에서 자동으로 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-145">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="70a5d-146">Rgsdyn.mdf.</span><span class="sxs-lookup"><span data-stu-id="70a5d-146">Rgsdyn.</span></span> <span data-ttu-id="70a5d-147">이 데이터베이스의 임시 응답 그룹 서비스 데이터는 서비스 복원에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-147">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="70a5d-148">Cpsdyn.mdf.</span><span class="sxs-lookup"><span data-stu-id="70a5d-148">Cpsdyn.</span></span> <span data-ttu-id="70a5d-149">서비스를 복원 하는 데는 통화 대기 응용 프로그램에 대 한 동적 정보가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-149">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="70a5d-150">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="70a5d-150">MgcComp.</span></span> <span data-ttu-id="70a5d-151">서비스를 복원 하는 데에는 영구적 채팅에 대 한 준수 데이터베이스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-151">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="70a5d-152">파일 저장소 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="70a5d-152">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="70a5d-153">다음 표를 사용 하 여 파일 저장소를 백업 및 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-153">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="70a5d-154">파일 저장소에는 모임 콘텐츠 메타 데이터, 모임 준수 로그, 장치 업데이트의 업데이트 로그, 응답 그룹, 통화 대기 및 알림 응용 프로그램에 대 한 오디오 파일 등의 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-154">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="70a5d-155">백업 및 복원에 대 한 파일 저장소 정보</span><span class="sxs-lookup"><span data-stu-id="70a5d-155">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70a5d-156">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="70a5d-156">Content</span></span></th>
<th><span data-ttu-id="70a5d-157">서버 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="70a5d-157">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="70a5d-158">백업 일정</span><span class="sxs-lookup"><span data-stu-id="70a5d-158">Backup schedule</span></span></th>
<th><span data-ttu-id="70a5d-159">파일 시스템 백업 도구</span><span class="sxs-lookup"><span data-stu-id="70a5d-159">File system backup tool</span></span></th>
<th><span data-ttu-id="70a5d-160">백업할 파일 공유 \*</span><span class="sxs-lookup"><span data-stu-id="70a5d-160">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="70a5d-161">백업 대상</span><span class="sxs-lookup"><span data-stu-id="70a5d-161">Backup destination</span></span></th>
<th><span data-ttu-id="70a5d-162">참고</span><span class="sxs-lookup"><span data-stu-id="70a5d-162">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70a5d-163">Lync Server 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="70a5d-163">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="70a5d-164">표준 백업 도구 (예: Robocopy)</span><span class="sxs-lookup"><span data-stu-id="70a5d-164">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="70a5d-165">Enterprise Edition 용 파일 서버</span><span class="sxs-lookup"><span data-stu-id="70a5d-165">On file server for Enterprise Edition.</span></span> <span data-ttu-id="70a5d-166">Standard edition 배포의 경우 기본적으로 스탠더드 버전을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-166">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="70a5d-167">일반적으로 사이트별로 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-167">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="70a5d-168">이름이 <strong>Meeting.Active</strong>인 파일은 백업해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-168">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="70a5d-169">이 파일은 사용 중 이며 모임이 진행 되는 동안 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-169">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="70a5d-170">설정 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="70a5d-170">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="70a5d-171">다음 표를 사용 하 여 설정을 백업 및 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a5d-171">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="70a5d-172">백업 및 복원에 대 한 설정 정보</span><span class="sxs-lookup"><span data-stu-id="70a5d-172">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70a5d-173">Database</span><span class="sxs-lookup"><span data-stu-id="70a5d-173">Database</span></span></th>
<th><span data-ttu-id="70a5d-174">서버 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="70a5d-174">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="70a5d-175">백업 일정</span><span class="sxs-lookup"><span data-stu-id="70a5d-175">Backup schedule</span></span></th>
<th><span data-ttu-id="70a5d-176">백업 도구</span><span class="sxs-lookup"><span data-stu-id="70a5d-176">Backup tool</span></span></th>
<th><span data-ttu-id="70a5d-177">구성 파일 (.xml) 이름</span><span class="sxs-lookup"><span data-stu-id="70a5d-177">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="70a5d-178">백업 위치</span><span class="sxs-lookup"><span data-stu-id="70a5d-178">Backup location</span></span></th>
<th><span data-ttu-id="70a5d-179">참고</span><span class="sxs-lookup"><span data-stu-id="70a5d-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70a5d-180">토폴로지 구성에 대 한 중앙 관리 저장소의 Xds 데이터베이스 (전역)</span><span class="sxs-lookup"><span data-stu-id="70a5d-180">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="70a5d-181"><strong>Export-CsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="70a5d-181"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70a5d-182">E9-1-1 위치 정보에 대 한 중앙 관리 저장소의 Lis 데이터베이스 (전역)</span><span class="sxs-lookup"><span data-stu-id="70a5d-182">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70a5d-183"><strong>Export-cslisconfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="70a5d-183"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70a5d-184">응답 그룹 구성 (풀)을 위해 백 엔드 서버의 RgsConfig 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="70a5d-184">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70a5d-185"><strong>Export-csrgsconfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="70a5d-185"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

