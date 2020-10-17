---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 도구 및 사용 권한'
description: 'Lync Server 2013: 백업 및 복원 요구 사항: 도구 및 사용 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553474"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="b12bd-103">Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b12bd-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b12bd-104">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="b12bd-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="b12bd-105">이 항목에서는 Lync Server 2013을 백업 및 복원 하는 데 사용할 수 있는 도구, 필요한 권한, 원격 또는 로컬로 명령을 실행할 수 있는지 여부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="b12bd-106">특히이 항목에서는 백업 및 복원을 위해 Lync Server와 함께 제공 되는 도구에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="b12bd-107">백업</span><span class="sxs-lookup"><span data-stu-id="b12bd-107">Backups</span></span>

<span data-ttu-id="b12bd-108">Lync Server를 백업 하려면 다음 표에서 확인 된 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="b12bd-109">Lync Server를 백업 하는 데 필요한 모든 명령을 스크립트로 작성 하 고 원격으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="b12bd-110">Lync Server 백업 도구</span><span class="sxs-lookup"><span data-stu-id="b12bd-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b12bd-111">백업할 항목:</span><span class="sxs-lookup"><span data-stu-id="b12bd-111">To back up this:</span></span></th>
<th><span data-ttu-id="b12bd-112">사용할 도구 또는 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b12bd-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-113">토폴로지 구성 데이터(Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12bd-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-115">위치 정보 서비스(E9-1-1) 데이터(Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12bd-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-117">응답 그룹 구성 데이터(RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12bd-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-119">영구 사용자 데이터 (Rtcxds 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="b12bd-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="b12bd-120">전화 회의 ID</span><span class="sxs-lookup"><span data-stu-id="b12bd-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="b12bd-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b12bd-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="b12bd-122">보관 데이터베이스(LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b12bd-123">통화 정보 기록 모니터링 데이터베이스(LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b12bd-124">QoE 모니터링 데이터베이스(QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b12bd-125">SQL Server 데이터베이스 도구(예: SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b12bd-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-126">영구 채팅 데이터베이스 (Mgc .mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-127">SQL Server 백업 절차 또는 내보내기-Export-cspersistentchatdata.</span><span class="sxs-lookup"><span data-stu-id="b12bd-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="b12bd-128">Export-CsPersistentChatData 영구 채팅 데이터를 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-129">모든 파일 저장소: Lync Server 파일 저장소, 보관 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="b12bd-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b12bd-130">이름이 <STRONG>Meeting.Active</STRONG>인 파일은 백업해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="b12bd-131">이러한 파일은 사용 중이며 모임이 수행되는 동안 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="b12bd-132">표준 파일 시스템 관리 도구 (예: Robocopy)</span><span class="sxs-lookup"><span data-stu-id="b12bd-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="b12bd-133">복구할</span><span class="sxs-lookup"><span data-stu-id="b12bd-133">Restoration</span></span>

<span data-ttu-id="b12bd-134">Lync Server를 복원 하려면 다음 표의 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="b12bd-135">Lync Server를 복원 하는 데 필요한 모든 명령을 스크립팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="b12bd-136">일부는 원격으로 실행할 수 있지만 다음 표에 지정 된 대로 로컬로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="b12bd-137">Lync Server 복원 도구</span><span class="sxs-lookup"><span data-stu-id="b12bd-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b12bd-138">수행할 작업:</span><span class="sxs-lookup"><span data-stu-id="b12bd-138">To do this:</span></span></th>
<th><span data-ttu-id="b12bd-139">사용할 도구 또는 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b12bd-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-140">신규 또는 깨끗한 컴퓨터 구축</span><span class="sxs-lookup"><span data-stu-id="b12bd-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b12bd-141">Windows 운영 체제 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="b12bd-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="b12bd-142">SQL Server 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="b12bd-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="b12bd-143">내보낼 수 있는 개인 키를 사용하여 인증서를 복원할 경우 MMC(Microsoft Management Console) 스냅인 인증</span><span class="sxs-lookup"><span data-stu-id="b12bd-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-144">파일 저장소 데이터 복원</span><span class="sxs-lookup"><span data-stu-id="b12bd-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="b12bd-145">표준 파일 시스템 관리 도구(예: Robocopy)</span><span class="sxs-lookup"><span data-stu-id="b12bd-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-146">빈 데이터베이스를 다시 만들고 다음에 대한 권한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b12bd-147">Central Management store</span><span class="sxs-lookup"><span data-stu-id="b12bd-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="b12bd-148">백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="b12bd-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="b12bd-149">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="b12bd-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="b12bd-150">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="b12bd-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b12bd-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="b12bd-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-152">Active Directory 도메인 서비스 포인터를 중앙 관리 저장소로 복원</span><span class="sxs-lookup"><span data-stu-id="b12bd-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b12bd-153">언제라도 서비스 연결 지점이 손실될 경우 이 cmdlet을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="b12bd-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b12bd-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-155">토폴로지, 정책 및 구성 설정을 중앙 관리 저장소 (Xds)로 가져오기</span><span class="sxs-lookup"><span data-stu-id="b12bd-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12bd-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-157">토폴로지 게시 및 사용</span><span class="sxs-lookup"><span data-stu-id="b12bd-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="b12bd-158">토폴로지 작성기</span><span class="sxs-lookup"><span data-stu-id="b12bd-158">Topology Builder</span></span></p>
<p><span data-ttu-id="b12bd-159">또는</span><span class="sxs-lookup"><span data-stu-id="b12bd-159">-or-</span></span></p>
<p><span data-ttu-id="b12bd-160">Publish-CsTopology 및 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="b12bd-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-161">마지막으로 게시된 토폴로지 사용</span><span class="sxs-lookup"><span data-stu-id="b12bd-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="b12bd-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="b12bd-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-163">Lync Server 구성 요소 다시 설치</span><span class="sxs-lookup"><span data-stu-id="b12bd-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="b12bd-164">Lync Server 설치</span><span class="sxs-lookup"><span data-stu-id="b12bd-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b12bd-165">Lync Server 설치 폴더 또는 \setup\amd64\Setup.exe 미디어에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-166">위치 정보(E9-1-1) 데이터(Lis.mdf) 복원</span><span class="sxs-lookup"><span data-stu-id="b12bd-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12bd-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-168">영구 사용자 데이터 복원 (Rtcxds)</span><span class="sxs-lookup"><span data-stu-id="b12bd-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b12bd-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-170">응답 그룹 구성 데이터 복원(RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12bd-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b12bd-172">데이터베이스에 응답 그룹 데이터가 없는 새로 배포 된 풀에서 구성을 복원 하는 경우 – OverwriteOwner 옵션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="b12bd-173">복원 중인 데이터가 FQDN (정규화 된 도메인 이름)을 가진 풀에 있더라도이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="b12bd-174">그렇지 않으면 연락처 개체가 Active Directory에 이미 있는 응답 그룹으로 인해 가져오기가 완료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b12bd-175">다음 데이터베이스 복원:</span><span class="sxs-lookup"><span data-stu-id="b12bd-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="b12bd-176">보관 데이터베이스(LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b12bd-177">모니터링 데이터베이스: 통화 정보 기록 데이터베이스(LcsCDR.mdf) 및 QoE 데이터베이스(QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b12bd-178">SQL Server 데이터베이스 관리 도구</span><span class="sxs-lookup"><span data-stu-id="b12bd-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b12bd-179">영구 채팅 데이터베이스 (Mgs .mdf)</span><span class="sxs-lookup"><span data-stu-id="b12bd-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b12bd-180">SQL Server 복원 절차 또는 가져오기-Export-cspersistentchatdata.</span><span class="sxs-lookup"><span data-stu-id="b12bd-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="b12bd-181">Export-cspersistentchatdata에서 만든 파일을 사용 하 여 Import-CsPersistentChatData를 사용할 수 있으며 데이터를 영구 채팅 데이터베이스로 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="b12bd-182">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b12bd-182">Required Permissions</span></span>

<span data-ttu-id="b12bd-183">이 항목에서 설명 하는 모든 명령을 수행 하려면 사용자가 **RTCUniversalServerAdmins** 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="b12bd-184">대부분의 백업 및 복원 명령은 RBAC (역할 기반 액세스 제어)를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="b12bd-185">두 가지 예외는 CsPersistentChatAdministrator 그룹의 구성원 인 사용자가 실행 해야 하는 영구 채팅 cmdlet Export-CsPersistentChatData 및 Export-cspersistentchatdata입니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="b12bd-186">Lync Server 배포 마법사를 실행 하려면 사용자가 로컬 관리자 그룹의 구성원 이기도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12bd-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

