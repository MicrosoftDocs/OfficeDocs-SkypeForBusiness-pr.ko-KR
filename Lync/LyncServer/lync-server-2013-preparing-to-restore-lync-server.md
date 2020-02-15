---
title: 'Lync Server 2013: Lync Server 복원 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a011109c985f126c591698f3ea572242498771
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="92971-102">Lync Server 2013 복원 준비</span><span class="sxs-lookup"><span data-stu-id="92971-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92971-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="92971-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="92971-104">오류 발생 후 서버 및 데이터베이스의 복원을 시작하기 전에 다음을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="92971-105">복원 해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="92971-105">What needs to be restored.</span></span>

  - <span data-ttu-id="92971-106">복원에 필요한 하드웨어, 소프트웨어, 데이터 및 도구</span><span class="sxs-lookup"><span data-stu-id="92971-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="92971-107">복원할 대상 확인</span><span class="sxs-lookup"><span data-stu-id="92971-107">Determining What to Restore</span></span>

<span data-ttu-id="92971-108">이 항목에서는 서버, 풀 또는 중앙 관리 저장소 수준에서 발생 하는 Lync Server 중단을 복원 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="92971-109">중앙 관리 저장소에서 오류가 발생 하면 Lync Server 배포가 계속 작동 하지만 구성을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92971-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="92971-110">백 엔드 서버 또는 Standard Edition 서버에 오류가 발생하면 사용자 풀의 작동이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="92971-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="92971-111">다른 서버에 오류가 발생할 경우에는 서버가 실행 중인 서버 역할 및 서버가 하나 이상의 데이터베이스를 호스트하는지 여부에 따라 오류의 영향이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="92971-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="92971-112">복원할 대상</span><span class="sxs-lookup"><span data-stu-id="92971-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92971-113">오류가 발생한 항목</span><span class="sxs-lookup"><span data-stu-id="92971-113">If this failed</span></span></th>
<th><span data-ttu-id="92971-114">다음 섹션 참조:</span><span class="sxs-lookup"><span data-stu-id="92971-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92971-115">Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="92971-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="92971-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Lync Server 2013에서 Standard Edition server 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92971-117">Central Management store</span><span class="sxs-lookup"><span data-stu-id="92971-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="92971-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Lync Server 2013에서 중앙 관리 저장소를 호스트 하는 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92971-119">Enterprise Edition 백 엔드</span><span class="sxs-lookup"><span data-stu-id="92971-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="92971-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92971-121">Enterprise Edition의 미러된 백 엔드 기본 서버</span><span class="sxs-lookup"><span data-stu-id="92971-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="92971-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-기본</a></span><span class="sxs-lookup"><span data-stu-id="92971-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92971-123">Enterprise Edition 미러링된 백 엔드 보조 서버</span><span class="sxs-lookup"><span data-stu-id="92971-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="92971-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-미러</a></span><span class="sxs-lookup"><span data-stu-id="92971-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92971-125">프런트 엔드 서버,에 지 서버, 디렉터, 중재 서버, 또는 영구 채팅 서버와 같은 서버 역할을 실행 하는 모든 Enterprise Edition 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="92971-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="92971-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync Server 2013에서 Enterprise Edition 구성원 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92971-127">전체 Lync Server 풀</span><span class="sxs-lookup"><span data-stu-id="92971-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="92971-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Lync Server 2013에서 Lync Server 풀 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92971-129">Enterprise Edition 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="92971-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="92971-130"><a href="lync-server-2013-restoring-a-file-store.md">Lync Server 2013에서 파일 저장소 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92971-131">독립 실행형 모니터링 데이터베이스 또는 보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="92971-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="92971-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Lync Server 2013에서 모니터링 또는 보관 데이터 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92971-133">독립 실행형 영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="92971-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="92971-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Lync Server 2013에서 영구 채팅 데이터 복원</a></span><span class="sxs-lookup"><span data-stu-id="92971-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="92971-135">하드웨어, 소프트웨어 및 도구 수집</span><span class="sxs-lookup"><span data-stu-id="92971-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="92971-136">서버를 복원할 때는 새 컴퓨터 또는 깨끗한 컴퓨터로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="92971-137">또한 다음 하드웨어 및 소프트웨어를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="92971-138">오류가 발생한 서버와 FQDN(정규화된 도메인 이름)이 동일한 신규 서버 또는 깨끗한 서버.</span><span class="sxs-lookup"><span data-stu-id="92971-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="92971-139">운영 체제를 설치할 때 Active Directory 도메인 서비스에서 컴퓨터 계정을 삭제 하지 말고 계정에 대 한 그룹 권한이 보존 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="92971-140">운영 체제의 설치 소프트웨어.</span><span class="sxs-lookup"><span data-stu-id="92971-140">Installation software for the operating system.</span></span> <span data-ttu-id="92971-141">운영 체제를 설치하려면 조직에서 설정된 서버 배포 절차 및 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="92971-142">서비스를 복원할 때 이러한 절차 및 구성 요구 사항을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="92971-143">SQL Server 2012 또는 SQL Server 2008 r 2 용 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="92971-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="92971-144">데이터베이스 서버를 설치하려면 적합한 버전의 SQL Server 및 조직에서 설정된 데이터베이스 서버 배포 절차와 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="92971-145">서비스를 복원할 때 이러한 절차 및 구성 요구 사항을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92971-146">Lync Server 배포 마법사는 SQL server 2012 또는 SQL Server 2008 r 2를 미리 설치한 경우가 아니면 각 Standard Edition server 및 기타 Lync Server 서버에 SQL Server 2012 Express를 자동으로 설치 합니다. 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="92971-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="92971-147">시스템 이미지 작성을 위한 소프트웨어.</span><span class="sxs-lookup"><span data-stu-id="92971-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="92971-148">복원 중에 문제가 발생 하는 경우이 이미지를 롤백 지점으로 사용할 수 있도록 운영 체제 및 SQL Server를 설치한 후 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92971-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="92971-149">Lync Server 2013 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="92971-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="92971-150">Lync Server 배포 마법사는 \\설치\\Amd64\\setup.exe의 lync server 설치 폴더 또는 미디어에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92971-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="92971-151">복원 중에는 다음 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="92971-152">Lync Server 관리 셸 cmdlet</span><span class="sxs-lookup"><span data-stu-id="92971-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="92971-153">가져오기-CsUserData</span><span class="sxs-lookup"><span data-stu-id="92971-153">Import-CsUserData</span></span>

  - <span data-ttu-id="92971-154">Windows 폴더 복원을 위한 도구</span><span class="sxs-lookup"><span data-stu-id="92971-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="92971-155">토폴로지 작성기</span><span class="sxs-lookup"><span data-stu-id="92971-155">Topology Builder</span></span>

  - <span data-ttu-id="92971-156">SQL Server 데이터베이스 유틸리티(예: SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="92971-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="92971-157">서버 복원 준비</span><span class="sxs-lookup"><span data-stu-id="92971-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="92971-158">서버를 복원 하기 전에 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="92971-159">운영 체제를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-159">Install the operating system.</span></span>

2.  <span data-ttu-id="92971-160">서버가 백 엔드 서버인 경우 SQL Server 2012 또는 SQL Server 2008 R2를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="92971-161">인증서를 복원 하거나 reenroll 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="92971-162">인증서에 대 한 자세한 내용은 [Lync Server 2013: data의 백업 및 복원 요구 사항](lync-server-2013-backup-and-restoration-requirements-data.md)에서 "추가 백업 요구 사항"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92971-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="92971-163">복원 중에 문제가 발생 하는 경우 복원을 시작 하기 전에 시스템 이미지를 사용 하 여 롤백 지점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92971-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92971-164">이 항목의 절차에 설명 된 Lync Server 배포 마법사 및 cmdlet 및 관련 항목에서는 필요한 모든 Acl (액세스 제어 목록)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="92971-165">복원을 시작 하기 전에 복원 하려는 구성 요소에 필요한 하드웨어 및 소프트웨어를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="92971-166">운영 체제 및 SQL Server를 설치한 후 다음 복원 절차의 단계 대부분은 원격으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92971-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="92971-167">다른 부분은 해당 절차에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="92971-168">또한 복원을 시작 하기 전에 조직의 백업 및 복원 계획과 마지막 백업의 정보 (예:이 문서의 워크시트에 포함 된 정보 ( [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)참조)가 사용 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92971-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

