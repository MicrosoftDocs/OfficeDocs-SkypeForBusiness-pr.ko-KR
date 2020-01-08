---
title: 'Lync Server 2013: Lync Server 복원 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="c85ce-102">Lync Server 2013 복원 준비</span><span class="sxs-lookup"><span data-stu-id="c85ce-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c85ce-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c85ce-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c85ce-104">오류가 발생 한 후에 서버와 데이터베이스 복원을 시작 하기 전에 다음 사항을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="c85ce-105">복원 해야 할 사항.</span><span class="sxs-lookup"><span data-stu-id="c85ce-105">What needs to be restored.</span></span>

  - <span data-ttu-id="c85ce-106">복원에 필요한 하드웨어, 소프트웨어, 데이터, 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="c85ce-107">복원할 항목 결정</span><span class="sxs-lookup"><span data-stu-id="c85ce-107">Determining What to Restore</span></span>

<span data-ttu-id="c85ce-108">이 항목에서는 서버, 풀 또는 중앙 관리 저장소 수준에서 발생 하는 Lync Server 중단을 복원 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="c85ce-109">중앙 관리 저장소에 오류가 발생 하는 경우 Lync Server 배포는 계속 작동 하지만 구성을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="c85ce-110">백 엔드 서버 또는 Standard Edition 서버에 오류가 발생 하면 사용자 풀이 작동을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="c85ce-111">다른 서버에 오류가 발생 한 경우 서버의 실행 되는 서버 역할 및 서버에서 하나 이상의 데이터베이스를 호스트 하는지 여부에 따라 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="c85ce-112">복원할 항목</span><span class="sxs-lookup"><span data-stu-id="c85ce-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c85ce-113">실패 한 경우</span><span class="sxs-lookup"><span data-stu-id="c85ce-113">If this failed</span></span></th>
<th><span data-ttu-id="c85ce-114">이 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c85ce-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c85ce-115">스탠더드 버전 서버</span><span class="sxs-lookup"><span data-stu-id="c85ce-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c85ce-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Lync Server 2013에서 Standard Edition 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c85ce-117">중앙 관리 저장소</span><span class="sxs-lookup"><span data-stu-id="c85ce-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="c85ce-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Lync Server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c85ce-119">Enterprise Edition 백 엔드</span><span class="sxs-lookup"><span data-stu-id="c85ce-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="c85ce-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c85ce-121">엔터프라이즈 버전의 미러된 백 엔드 기본 서버</span><span class="sxs-lookup"><span data-stu-id="c85ce-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="c85ce-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-기본</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c85ce-123">엔터프라이즈 버전의 미러된 백 엔드 보조 서버</span><span class="sxs-lookup"><span data-stu-id="c85ce-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="c85ce-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-미러</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c85ce-125">프런트 엔드 서버, Edge 서버, 중재 서버, 또는 영구 채팅 서버와 같이 서버 역할을 실행 하는 모든 Enterprise Edition 서버</span><span class="sxs-lookup"><span data-stu-id="c85ce-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="c85ce-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync Server 2013에서 Enterprise Edition 구성원 서버 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c85ce-127">전체 Lync Server 풀</span><span class="sxs-lookup"><span data-stu-id="c85ce-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="c85ce-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Lync Server 2013에서 Lync Server 풀 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c85ce-129">Enterprise Edition 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="c85ce-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="c85ce-130"><a href="lync-server-2013-restoring-a-file-store.md">Lync Server 2013에서 파일 저장소 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c85ce-131">독립 실행형 모니터링 데이터베이스 또는 보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="c85ce-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="c85ce-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Lync Server 2013에서 모니터링 또는 데이터 보관 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c85ce-133">독립형 영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="c85ce-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="c85ce-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Lync Server 2013에서 영구 채팅 데이터 복원</a></span><span class="sxs-lookup"><span data-stu-id="c85ce-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="c85ce-135">하드웨어, 소프트웨어 및 도구 수집</span><span class="sxs-lookup"><span data-stu-id="c85ce-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="c85ce-136">서버를 복원 하는 경우 새 컴퓨터 또는 깨끗 한 컴퓨터로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="c85ce-137">또한 다음 하드웨어 및 소프트웨어를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="c85ce-138">실패 한 서버와 FQDN (정규화 된 도메인 이름)이 동일한 클린 또는 새 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c85ce-139">운영 체제를 설치할 때 Active Directory 도메인 서비스에서 컴퓨터 계정을 삭제 하지 말고 계정에 대 한 그룹 권한이 유지 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="c85ce-140">운영 체제의 설치 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-140">Installation software for the operating system.</span></span> <span data-ttu-id="c85ce-141">운영 체제를 설치 하려면 조직에서 설정한 서버 배포 절차와 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="c85ce-142">이러한 절차와 구성 요구 사항은 서비스를 복원할 때 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="c85ce-143">SQL Server 2012 또는 SQL Server 2008 R2 용 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="c85ce-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="c85ce-144">데이터베이스 서버를 설치 하려면 해당 버전의 SQL Server와 조직에서 설정한 데이터베이스 서버 배포 절차 및 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="c85ce-145">이러한 절차와 구성 요구 사항은 서비스를 복원할 때 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c85ce-146">Lync Server 배포 마법사에서는 sql server 2012 또는 SQL Server 2008 R2가 설치 되어 있지 않은 경우 각 스탠더드 버전 서버와 다른 Lync Server 서버에 로컬 구성 저장소를 설치한 경우 자동으로 SQL Server 2012 Express를 설치 합니다. 서버.</span><span class="sxs-lookup"><span data-stu-id="c85ce-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="c85ce-147">시스템 이미지를 만드는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c85ce-148">운영 체제 및 SQL Server를 설치한 후 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하 여 복원 중 문제가 발생 하는 경우 롤백 시점으로이 이미지를 사용할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="c85ce-149">Lync Server 2013 설치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="c85ce-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="c85ce-150">Lync Server 배포 마법사는 Lync Server 설치 폴더 또는 \\설치\\amd64\\setup.exe의 미디어에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="c85ce-151">복원 하는 동안 다음 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="c85ce-152">Lync Server 관리 셸 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c85ce-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="c85ce-153">가져오기-CsUserData</span><span class="sxs-lookup"><span data-stu-id="c85ce-153">Import-CsUserData</span></span>

  - <span data-ttu-id="c85ce-154">Windows 폴더 복원 도구</span><span class="sxs-lookup"><span data-stu-id="c85ce-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="c85ce-155">토폴로지 작성기</span><span class="sxs-lookup"><span data-stu-id="c85ce-155">Topology Builder</span></span>

  - <span data-ttu-id="c85ce-156">Sql Server Management Studio와 같은 SQL Server 데이터베이스 유틸리티</span><span class="sxs-lookup"><span data-stu-id="c85ce-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="c85ce-157">서버 복원 준비</span><span class="sxs-lookup"><span data-stu-id="c85ce-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="c85ce-158">서버를 복원 하기 전에 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="c85ce-159">운영 체제를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-159">Install the operating system.</span></span>

2.  <span data-ttu-id="c85ce-160">서버가 백 엔드 서버인 경우 SQL Server 2012 또는 SQL Server 2008 R2를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="c85ce-161">인증서를 복원 하거나 reenroll.</span><span class="sxs-lookup"><span data-stu-id="c85ce-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="c85ce-162">인증서에 대 한 자세한 내용은 [Lync Server 2013: data의 백업 및 복원 요구 사항](lync-server-2013-backup-and-restoration-requirements-data.md)에서 "추가 백업 요구 사항"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c85ce-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="c85ce-163">복원 중 문제가 발생 하는 경우 롤백 시점으로 사용할 복원을 시작 하기 전에 시스템 이미지를 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c85ce-164">이 항목의 절차에 설명 된 Lync Server 배포 마법사 및 cmdlet은 필요한 모든 Acl (액세스 제어 목록)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="c85ce-165">복원을 시작 하기 전에 복원 하려는 구성 요소에 필요한 하드웨어 및 소프트웨어를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="c85ce-166">운영 체제 및 SQL Server를 설치한 후에는 다음 복원 절차의 대부분의 단계를 원격으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="c85ce-167">예외는 절차에 명시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="c85ce-168">또한 복원을 시작 하기 전에 조직의 백업 및 복원 계획 및이 문서의 워크시트에 있는 정보 (예: [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)참조) 등의 마지막 백업 정보도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c85ce-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

