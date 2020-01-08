---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 도구 및 사용 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="b9d9f-102">Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b9d9f-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9d9f-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="b9d9f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="b9d9f-104">이 항목에서는 Lync Server 2013을 백업 하 고 복원 하는 데 사용할 수 있는 도구, 필요한 사용 권한, 명령을 원격으로 실행할 수 있는지 아니면 로컬로 실행할지에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="b9d9f-105">이 항목에서는 백업 및 복원을 위해 Lync Server와 함께 제공 되는 도구에 중점을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="b9d9f-106">해결할</span><span class="sxs-lookup"><span data-stu-id="b9d9f-106">Backups</span></span>

<span data-ttu-id="b9d9f-107">Lync Server를 백업 하려면 다음 표에서 확인 된 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="b9d9f-108">Lync Server를 백업 하는 데 필요한 모든 명령을 스크립팅할 수 있으며 원격으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="b9d9f-109">Lync Server 백업 도구</span><span class="sxs-lookup"><span data-stu-id="b9d9f-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9d9f-110">백업 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-110">To back up this:</span></span></th>
<th><span data-ttu-id="b9d9f-111">이 도구 또는 cmdlet 사용:</span><span class="sxs-lookup"><span data-stu-id="b9d9f-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-112">토폴로지 구성 데이터 (Xds)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-113">수출-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9d9f-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-114">위치 정보 서비스 (E9-1-1) 데이터 (Lis .mdf)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9d9f-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-116">응답 그룹 구성 데이터 (RgsConfig)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9d9f-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-118">영구 사용자 데이터 (Rtcxds 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="b9d9f-119">컨퍼런스 Id</span><span class="sxs-lookup"><span data-stu-id="b9d9f-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b9d9f-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="b9d9f-121">보관 데이터베이스 (LcsLog. .mdf)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-122">통화 정보 기록 데이터베이스 (LcsCDR) 모니터링</span><span class="sxs-lookup"><span data-stu-id="b9d9f-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-123">체감 품질 데이터베이스 모니터링 (QoEMetrics)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b9d9f-124">Sql Server Management Studio와 같은 SQL Server 데이터베이스 도구</span><span class="sxs-lookup"><span data-stu-id="b9d9f-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-125">Mgc .mdf (영구 채팅 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-126">SQL Server 백업 절차 또는 내보내기-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="b9d9f-127">Export-CsPersistentChatData는 영구 채팅 데이터를 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-128">모든 파일 저장소: Lync Server 파일 저장소, 보관 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="b9d9f-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b9d9f-129">이름이 <STRONG>Meeting</STRONG> 인 파일은 백업 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="b9d9f-130">모임이 진행 되는 동안 이러한 파일은 사용 중이거나 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="b9d9f-131">표준 파일 시스템 관리 도구 (예: Robocopy)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="b9d9f-132">복원이</span><span class="sxs-lookup"><span data-stu-id="b9d9f-132">Restoration</span></span>

<span data-ttu-id="b9d9f-133">Lync Server를 복원 하려면 다음 표의 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="b9d9f-134">Lync Server를 복원 하는 데 필요한 모든 명령을 스크립팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="b9d9f-135">일부는 원격으로 실행할 수 있지만, 다음 표에 지정 된 대로 로컬에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="b9d9f-136">Lync Server 복원 도구</span><span class="sxs-lookup"><span data-stu-id="b9d9f-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9d9f-137">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="b9d9f-137">To do this:</span></span></th>
<th><span data-ttu-id="b9d9f-138">이 도구 또는 cmdlet 사용:</span><span class="sxs-lookup"><span data-stu-id="b9d9f-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-139">신규 또는 깨끗 한 컴퓨터 빌드</span><span class="sxs-lookup"><span data-stu-id="b9d9f-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b9d9f-140">Windows 운영 체제 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="b9d9f-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-141">SQL Server 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="b9d9f-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-142">인증서를 내보낼 수 있는 개인 키를 사용 하 여 복원 하는 경우 MMC (Microsoft Management Console) 스냅인</span><span class="sxs-lookup"><span data-stu-id="b9d9f-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-143">파일 저장소 데이터 복원</span><span class="sxs-lookup"><span data-stu-id="b9d9f-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-144">표준 파일 시스템 관리 도구 (예: Robocopy)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-145">빈 데이터베이스를 다시 만들고 다음에 대 한 사용 권한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9d9f-146">중앙 관리 저장소</span><span class="sxs-lookup"><span data-stu-id="b9d9f-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-147">백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="b9d9f-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-148">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="b9d9f-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-149">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="b9d9f-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b9d9f-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="b9d9f-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-151">Active Directory 도메인 서비스 포인터를 중앙 관리 저장소에 복원</span><span class="sxs-lookup"><span data-stu-id="b9d9f-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b9d9f-152">언제 든 지 서비스 연결 지점을 잃어버린 경우이 cmdlet을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="b9d9f-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b9d9f-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-154">토폴로지, 정책 및 구성 설정을 중앙 관리 저장소 (Xds)로 가져오기</span><span class="sxs-lookup"><span data-stu-id="b9d9f-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-155">가져오기-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9d9f-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-156">토폴로지 게시 및 설정</span><span class="sxs-lookup"><span data-stu-id="b9d9f-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-157">토폴로지 작성기</span><span class="sxs-lookup"><span data-stu-id="b9d9f-157">Topology Builder</span></span></p>
<p><span data-ttu-id="b9d9f-158">또는</span><span class="sxs-lookup"><span data-stu-id="b9d9f-158">-or-</span></span></p>
<p><span data-ttu-id="b9d9f-159">게시-CsTopology 및 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="b9d9f-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-160">마지막으로 게시 된 토폴로지 사용</span><span class="sxs-lookup"><span data-stu-id="b9d9f-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="b9d9f-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-162">Lync Server 구성 요소 다시 설치</span><span class="sxs-lookup"><span data-stu-id="b9d9f-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-163">Lync Server 설정</span><span class="sxs-lookup"><span data-stu-id="b9d9f-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b9d9f-164">Lync Server 설치 폴더 또는 \setup\amd64\Setup.exe. 미디어에 위치</span><span class="sxs-lookup"><span data-stu-id="b9d9f-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-165">위치 정보 (E9-1-1) 데이터 (Lis .mdf) 복원</span><span class="sxs-lookup"><span data-stu-id="b9d9f-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-166">가져오기-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9d9f-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-167">영구 사용자 데이터 (Rtcxds) 복원</span><span class="sxs-lookup"><span data-stu-id="b9d9f-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-168">가져오기-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b9d9f-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-169">응답 그룹 구성 데이터 (RgsConfig) 복원</span><span class="sxs-lookup"><span data-stu-id="b9d9f-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-170">가져오기-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9d9f-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b9d9f-171">데이터베이스에 응답 그룹 데이터가 없는 새로 배포 된 풀에서 구성을 복원 하는 경우 – OverwriteOwner 옵션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="b9d9f-172">복원 하려는 데이터가 FQDN (정규화 된 도메인 이름)을 가진 풀에 있는 경우에도이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="b9d9f-173">그렇지 않으면 Active Directory에 이미 존재 하는 응답 그룹에 대 한 contact 개체 때문에 가져오기가 성공 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d9f-174">다음 데이터베이스를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9d9f-175">보관 데이터베이스 (LcsLog. .mdf)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b9d9f-176">데이터베이스 모니터링: 통화 세부 레코드 데이터베이스 (LcsCDR) 및 체감 품질 database (QoEMetrics)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b9d9f-177">SQL Server 데이터베이스 관리 도구</span><span class="sxs-lookup"><span data-stu-id="b9d9f-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d9f-178">Mgs mdf (영구 채팅 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="b9d9f-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b9d9f-179">SQL Server 복원 절차 또는 가져오기-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="b9d9f-180">Export-CsPersistentChatData를 사용 하 여 만든 파일과 함께 CsPersistentChatData를 사용할 수 있으며, 데이터를 영구 채팅 데이터베이스로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="b9d9f-181">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="b9d9f-181">Required Permissions</span></span>

<span data-ttu-id="b9d9f-182">이 항목에 설명 된 모든 명령을 수행 하려면 사용자가 **RTCUniversalServerAdmins** 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="b9d9f-183">대부분의 백업 및 복원 명령은 역할 기반 액세스 제어 (RBAC)를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="b9d9f-184">두 가지 예외는 CsPersistentChatAdministrator 그룹의 구성원 인 사용자가 실행 해야 하는 영구 채팅 cmdlet 내보내기-CsPersistentChatData 및 가져오기-CsPersistentChatData입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="b9d9f-185">Lync Server 배포 마법사를 실행 하려면 사용자도 로컬 관리자 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9d9f-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

