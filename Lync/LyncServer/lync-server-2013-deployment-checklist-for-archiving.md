---
title: 'Lync Server 2013: 보관용 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="47faf-102">Lync Server 2013의 보관용 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="47faf-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47faf-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="47faf-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="47faf-104">사용자의 Lync Server 2013 배포에서 각 프런트 엔드 서버에 보관이 자동으로 설치 되지만, 사용 하기 전에이를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="47faf-105">이 섹션에 요약 된 것 처럼 설정 하는 데 필요한 단계는 보관 배포를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="47faf-106">배포 순서</span><span class="sxs-lookup"><span data-stu-id="47faf-106">Deployment Sequence</span></span>

<span data-ttu-id="47faf-107">보관을 설정 하는 방법은 어떤 저장소 옵션을 선택 하느냐에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="47faf-108">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자를 위해 Lync Server 2013 보관 정책을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="47faf-109">대신 exchange 2013에 있는 사용자의 보관을 지원 하도록 Exchange 원본 위치 유지 정책을 구성 하 고 해당 사서함이 원본 위치 유지에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="47faf-110">이러한 정책을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47faf-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="47faf-111">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에는 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 게시 하 고 사용자에 대 한 정책 및 설정을 구성 하 고 나 서, 다음을 수행 해야 합니다. 해당 사용자의 데이터를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="47faf-112">초기 토폴로지를 배포 하거나 적어도 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 배포한 후에는 보관 데이터베이스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="47faf-113">이 문서에서는 보관 데이터베이스를 기존 배포에 추가 하 여 배포 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="47faf-114">프런트 엔드 풀 또는 Standard Edition 서버 중 하나에서 보관을 사용 하도록 설정 하는 경우 배포의 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에 대해이 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="47faf-115">이는 통신을 보관 해야 하는 사용자가 다른 풀에서 호스트 되는 그룹 메신저 대화 또는 모임에 초대 될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="47faf-116">대화 또는 모임이 호스팅되는 풀에서 보관을 사용할 수 없는 경우 전체 세션이 보관 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="47faf-117">이러한 경우에는 보관을 사용 하는 사용자를 포함 한 메신저 대화를 계속 보관할 수 있지만 회의 콘텐츠 파일 및 회의 참가 또는 종료 이벤트는 보관이 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="47faf-118">조직에서 규정 준수를 위해 보관 하는 것이 중요 한 경우에는 보관을 배포 하 고 적절 한 수준에서 정책 및 기타 옵션을 구성한 다음 모든 해당 사용자에 대해 사용 하도록 설정 하 고 해당 사용자를 Lync Server 2013에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="47faf-119">보관 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="47faf-119">Archiving Deployment Process</span></span>

<span data-ttu-id="47faf-120">다음 표에서는 기존 토폴로지에서 보관을 배포 하는 데 필요한 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47faf-121">단계의</span><span class="sxs-lookup"><span data-stu-id="47faf-121">Phase</span></span></th>
<th><span data-ttu-id="47faf-122">방법은</span><span class="sxs-lookup"><span data-stu-id="47faf-122">Steps</span></span></th>
<th><span data-ttu-id="47faf-123">역할 및 그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="47faf-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="47faf-124">설명서</span><span class="sxs-lookup"><span data-stu-id="47faf-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47faf-125"><strong>필수 하드웨어 및 소프트웨어 설치</strong></span><span class="sxs-lookup"><span data-stu-id="47faf-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="47faf-126">Exchange 2013를 사용 하 여 일부 또는 모든 사용자의 저장소를 보관 하는 Microsoft Exchange 통합을 사용 하려면 기존 Exchange 2013 배포가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="47faf-127">SQL Server 데이터베이스를 사용 하 여 별도의 보관 데이터베이스를 사용 하 여 보관 데이터를 저장 하는 서버의 SQL Server 인 일부 또는 모든 사용자에 대해 저장소를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="47faf-128">보관은 엔터프라이즈 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="47faf-129">해당 서버를 설치 하는 데 필요한 사항 외에 추가 하드웨어 또는 소프트웨어 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="47faf-130">로컬 관리자 그룹의 구성원 인 도메인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="47faf-131">지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지원 되는 하드웨어</a></span><span class="sxs-lookup"><span data-stu-id="47faf-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="47faf-132">지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013의 서버 소프트웨어 및 인프라 지원</a> .</span><span class="sxs-lookup"><span data-stu-id="47faf-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="47faf-133">계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에서 보관을 위한 기술 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="47faf-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="47faf-134">배포 설명서의 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013에서 보관 하는 시스템 및 인프라 설정</a></span><span class="sxs-lookup"><span data-stu-id="47faf-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="47faf-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013의 Exchange server 및 SharePoint 통합 지원은</a> 지원 가능성 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47faf-136"><strong>보관을 지원 하기 위해 적절 한 내부 토폴로지 만들기 (배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에만 해당)</strong></span><span class="sxs-lookup"><span data-stu-id="47faf-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="47faf-137">토폴로지 작성기를 실행 하 여 Lync Server 2013 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가한 다음 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="47faf-138">보관 데이터베이스를 통합 하는 토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="47faf-139">토폴로지를 게시 하려면 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 이며 Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있는 계정 (토폴로지 작성기가 필수 Dacl을 구성할 수 있도록)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="47faf-140">배포 설명서의 <a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">기존 Lync Server 2013 배포에 보관 데이터베이스를 추가</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47faf-141"><strong>서버 간 인증 구성 (Microsoft Exchange 통합을 사용 하는 경우에만 해당)</strong></span><span class="sxs-lookup"><span data-stu-id="47faf-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="47faf-142">서버를 구성 하 여 Lync Server 2013와 Exchange 2013 간에 인증을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="47faf-143">보관을 사용 하도록 설정 하기 전에 <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – 폴더 Dumpster</strong> 를 실행 하 여 Exchange 보관 저장소 연결을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="47faf-144">서버에서 인증서를 관리 하기 위한 적절 한 사용 권한이 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="47faf-145">배포 설명서 또는 운영 설명서의 <a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리</a></span><span class="sxs-lookup"><span data-stu-id="47faf-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47faf-146"><strong>보관 정책 및 구성 구성</strong></span><span class="sxs-lookup"><span data-stu-id="47faf-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="47faf-147">Microsoft Exchange 통합, 전역 정책, 모든 사이트 및 사용자 정책 (모든 데이터 저장소에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우), 특정 보관 옵션 (예: 중요 모드 및 데이터)을 포함 하 여 보관을 구성 합니다. 내보내기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="47faf-148">Microsoft Exchange 통합을 사용 하는 경우 Exchange 원본 위치 유지 정책을 적절 하 게 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="47faf-149">RTCUniversalServerAdmins 그룹 (Windows PowerShell에만 해당) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="47faf-150">배포 설명서의 <a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013에서 보관에 대 한 지원을 구성</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="47faf-151">Exchange 제품 설명서 (Microsoft Exchange 통합을 사용 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="47faf-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="47faf-152">다른 포리스트에 Lync 서버 및 Microsoft Exchange 배포</span><span class="sxs-lookup"><span data-stu-id="47faf-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="47faf-153">Microsoft Exchange Server가 Lync Server와 같은 포리스트에 배포 되지 않은 경우 다음 Exchange Active Directory 특성이 Lync Server를 배포 하는 포리스트와 동기화 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="47faf-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="47faf-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="47faf-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="47faf-155">proxyAddresses</span></span>

<span data-ttu-id="47faf-156">이것은 다중 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-156">This is a multi-value attribute.</span></span> <span data-ttu-id="47faf-157">이 특성을 동기화 할 때 기존 값이 손실 되지 않도록 값을 바꾸지 않고 병합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47faf-157">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

