---
title: 'Lync Server 2013: 워크시트 백업 및 복원'
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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="cf353-102">Lync Server 2013의 워크시트 백업 및 복원</span><span class="sxs-lookup"><span data-stu-id="cf353-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf353-103">_**마지막으로 수정한 주제:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="cf353-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="cf353-104">조직의 백업 및 복원 계획에는 데이터 및 설정 백업 방법 및 시기에 대 한 세부 정보가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="cf353-105">여기에 표시 된 워크시트를 사용 하 여 특정 배포에 대 한 정보를 문서화 하 고 조직의 백업 및 복원 요구 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="cf353-106">다음 워크시트를 사용 하 여 Lync Server 풀 또는 Standard Edition Server의 데이터베이스, 파일 저장소 및 설정 정보를 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="cf353-107">이러한 워크시트의 복사본 하나 이상을 안전한 위치에 보관 하 여 Lync Server를 복원 해야 하는 경우 쉽게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf353-108">이 섹션의 워크시트는 Lync Server 데이터베이스 및 서버의 데이터 및 설정을 복원 하는 데 필요한 정보만 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="cf353-109">운영 체제 및 기타 소프트웨어를 다시 설치 하기 위한 정보와 같은 다른 복원 정보를 문서화 해야 하는 경우 조직의 배포 계획 및 백업 및 복원 계획을 사용 하 여 이러한 요구 사항을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="cf353-110">데이터베이스 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="cf353-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="cf353-111">다음 표를 사용 하 여 Lync Server 데이터베이스를 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="cf353-112">백업 및 복원에 대 한 데이터베이스 정보</span><span class="sxs-lookup"><span data-stu-id="cf353-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="cf353-113">데이터</span><span class="sxs-lookup"><span data-stu-id="cf353-113">Database</span></span></th>
<th><span data-ttu-id="cf353-114">서버 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cf353-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="cf353-115">백업 일정</span><span class="sxs-lookup"><span data-stu-id="cf353-115">Backup schedule</span></span></th>
<th><span data-ttu-id="cf353-116">데이터베이스 백업 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-116">Database backup tool</span></span></th>
<th><span data-ttu-id="cf353-117">백업 집합</span><span class="sxs-lookup"><span data-stu-id="cf353-117">Backup set</span></span></th>
<th><span data-ttu-id="cf353-118">백업 대상</span><span class="sxs-lookup"><span data-stu-id="cf353-118">Backup destination</span></span></th>
<th><span data-ttu-id="cf353-119">상속자</span><span class="sxs-lookup"><span data-stu-id="cf353-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf353-120">백 엔드 서버의 사용자 데이터에 대 한 Rtc 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="cf353-121"><strong>Export-CsUserData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf353-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="cf353-122">성을</span><span class="sxs-lookup"><span data-stu-id="cf353-122">Name:</span></span></p>
<p><span data-ttu-id="cf353-123">기간이</span><span class="sxs-lookup"><span data-stu-id="cf353-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf353-124">보관 데이터베이스 서버의 LcsLog (기본 이름) 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cf353-125">SQL Server 관리 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="cf353-126">성을</span><span class="sxs-lookup"><span data-stu-id="cf353-126">Name:</span></span></p>
<p><span data-ttu-id="cf353-127">기간이</span><span class="sxs-lookup"><span data-stu-id="cf353-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf353-128">CDRs (호출 정보 레코드)에 대 한 모니터링 데이터베이스 서버의 LcsCdr 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cf353-129">SQL Server 관리 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="cf353-130">성을</span><span class="sxs-lookup"><span data-stu-id="cf353-130">Name:</span></span></p>
<p><span data-ttu-id="cf353-131">기간이</span><span class="sxs-lookup"><span data-stu-id="cf353-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf353-132">환경 품질 (체감 품질) 데이터를 모니터링 하는 데이터베이스 서버의 QoEMetrics 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cf353-133">SQL Server 관리 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="cf353-134">성을</span><span class="sxs-lookup"><span data-stu-id="cf353-134">Name:</span></span></p>
<p><span data-ttu-id="cf353-135">기간이</span><span class="sxs-lookup"><span data-stu-id="cf353-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf353-136">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="cf353-137">SQL Server 관리 도구 또는 <strong>Export-CsPersistentChatData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf353-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="cf353-138">성을</span><span class="sxs-lookup"><span data-stu-id="cf353-138">Name:</span></span></p>
<p><span data-ttu-id="cf353-139">기간이</span><span class="sxs-lookup"><span data-stu-id="cf353-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf353-140">백업 또는 복원에는 다음 데이터베이스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="cf353-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="cf353-141">Rtcdyn.</span></span> <span data-ttu-id="cf353-142">이 데이터베이스의 임시 사용자 데이터는 서비스 복원에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="cf353-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="cf353-143">Rtcab.</span></span> <span data-ttu-id="cf353-144">주소록 데이터베이스는 Active Directory 도메인 서비스의 GAL (전체 주소 목록)에서 자동으로 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="cf353-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="cf353-145">Rgsdyn.</span></span> <span data-ttu-id="cf353-146">이 데이터베이스의 임시 응답 그룹 서비스 데이터는 서비스 복원에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="cf353-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="cf353-147">Cpsdyn.</span></span> <span data-ttu-id="cf353-148">통화 공원 응용 프로그램에 대 한 동적 정보는 서비스 복원에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="cf353-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="cf353-149">MgcComp.</span></span> <span data-ttu-id="cf353-150">서비스 복원에는 영구 채팅에 대 한 규정 준수 데이터베이스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="cf353-151">파일 저장소 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="cf353-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="cf353-152">다음 표를 사용 하 여 파일 저장소를 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="cf353-153">파일 저장소에는 모임 콘텐츠 메타 데이터, 모임 준수 로그, 장치 업데이트에 대 한 업데이트 로그, 응답 그룹, 통화 공원, 알림 응용 프로그램에 대 한 오디오 파일 등의 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="cf353-154">백업 및 복원에 대 한 파일 저장소 정보</span><span class="sxs-lookup"><span data-stu-id="cf353-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="cf353-155">콘텐트가</span><span class="sxs-lookup"><span data-stu-id="cf353-155">Content</span></span></th>
<th><span data-ttu-id="cf353-156">서버 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cf353-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="cf353-157">백업 일정</span><span class="sxs-lookup"><span data-stu-id="cf353-157">Backup schedule</span></span></th>
<th><span data-ttu-id="cf353-158">파일 시스템 백업 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-158">File system backup tool</span></span></th>
<th><span data-ttu-id="cf353-159">백업할 파일 공유 \*</span><span class="sxs-lookup"><span data-stu-id="cf353-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="cf353-160">백업 대상</span><span class="sxs-lookup"><span data-stu-id="cf353-160">Backup destination</span></span></th>
<th><span data-ttu-id="cf353-161">상속자</span><span class="sxs-lookup"><span data-stu-id="cf353-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf353-162">Lync Server 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="cf353-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="cf353-163">Robocopy와 같은 표준 백업 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="cf353-164">Enterprise Edition 용 파일 서버.</span><span class="sxs-lookup"><span data-stu-id="cf353-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="cf353-165">스탠더드 버전 배포의 경우 Standard Edition에서 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="cf353-166">일반적으로 사이트당 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cf353-167">이름이 <strong>Meeting</strong> 인 파일은 백업 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="cf353-168">이러한 파일은 사용 중 이며 모임이 진행 되는 동안 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="cf353-169">설정 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="cf353-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="cf353-170">다음 표를 사용 하 여 설정을 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf353-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="cf353-171">백업 및 복원에 대 한 설정 정보</span><span class="sxs-lookup"><span data-stu-id="cf353-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="cf353-172">데이터</span><span class="sxs-lookup"><span data-stu-id="cf353-172">Database</span></span></th>
<th><span data-ttu-id="cf353-173">서버 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cf353-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="cf353-174">백업 일정</span><span class="sxs-lookup"><span data-stu-id="cf353-174">Backup schedule</span></span></th>
<th><span data-ttu-id="cf353-175">백업 도구</span><span class="sxs-lookup"><span data-stu-id="cf353-175">Backup tool</span></span></th>
<th><span data-ttu-id="cf353-176">구성 파일 (.xml) 이름</span><span class="sxs-lookup"><span data-stu-id="cf353-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="cf353-177">백업 위치</span><span class="sxs-lookup"><span data-stu-id="cf353-177">Backup location</span></span></th>
<th><span data-ttu-id="cf353-178">상속자</span><span class="sxs-lookup"><span data-stu-id="cf353-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf353-179">토폴로지 구성 (전역) 용 중앙 관리 저장소의 Xds 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="cf353-180"><strong>Export-CsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf353-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf353-181">E9 용 중앙 관리 저장소의 Lis 데이터베이스-1-1 위치 정보 (전역)</span><span class="sxs-lookup"><span data-stu-id="cf353-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cf353-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf353-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf353-183">RgsConfig에서 응답 그룹 구성 (풀)에 대 한 백 엔드 서버의 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cf353-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cf353-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf353-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

