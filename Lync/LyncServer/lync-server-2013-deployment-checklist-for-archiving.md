---
title: 'Lync Server 2013: 보관용 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccec3917e892d1ba6c3e1841773c77e8c2d015d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514531"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="1040d-102">Lync Server 2013의 보관을 위한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="1040d-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1040d-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1040d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1040d-104">보관은 Lync Server 2013 배포의 각 프런트 엔드 서버에 자동으로 설치 되지만 사용 하기 전에 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="1040d-105">이 섹션에 요약된 설정에 필요한 단계에 따라 보관을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="1040d-106">배포 순서</span><span class="sxs-lookup"><span data-stu-id="1040d-106">Deployment Sequence</span></span>

<span data-ttu-id="1040d-107">보관 설정 방법은 선택한 저장소 옵션에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="1040d-108">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자에 대해 Lync Server 2013 보관 정책을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="1040d-109">대신 Exchange 2013에 있는 사용자에 대 한 보관을 지원 하도록 Exchange In-Place 보존 정책을 구성 하 고 해당 사서함을 In-Place 보류에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="1040d-110">이러한 정책을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1040d-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="1040d-111">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에는 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 게시 한 다음 사용자에 대 한 정책 및 설정을 구성 하 여 해당 사용자에 대 한 데이터를 보관 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="1040d-112">보관 데이터베이스는 토폴로지를 처음 배포할 때 함께 배포하거나 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 배포한 후에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="1040d-113">이 문서에서는 기존 배포에 보관 데이터베이스를 추가하여 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="1040d-p104">하나의 프런트 엔드 풀 또는 Standard Edition 서버에서 보관을 사용하도록 설정한 경우 배포에 포함된 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에 대해서도 보관을 사용하도록 설정해야 합니다. 통신을 보관해야 하는 사용자가 다른 풀에서 호스팅되는 그룹 IM 대화 또는 모임에 초대될 수 있기 때문입니다. 대화 또는 모임이 호스팅되는 풀에 보관이 설정되어 있지 않으면 전체 세션이 보관되지 않을 수 있습니다. 이러한 경우 보관이 설정된 사용자의 IM은 보관할 수 있지만 회의 콘텐츠 파일 및 회의 입장 또는 퇴장 이벤트가 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1040d-118">조직에서 규정 준수를 위해 보관이 중요 한 경우에는 보관을 배포 하 고 적절 한 수준에서 정책 및 기타 옵션을 구성 하 고 모든 해당 2013 사용자에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="1040d-119">보관 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="1040d-119">Archiving Deployment Process</span></span>

<span data-ttu-id="1040d-120">다음 표에서는 기존 토폴로지에 보관을 배포하는 데 필요한 단계에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1040d-121">단계</span><span class="sxs-lookup"><span data-stu-id="1040d-121">Phase</span></span></th>
<th><span data-ttu-id="1040d-122">단계</span><span class="sxs-lookup"><span data-stu-id="1040d-122">Steps</span></span></th>
<th><span data-ttu-id="1040d-123">역할 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="1040d-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="1040d-124">설명서</span><span class="sxs-lookup"><span data-stu-id="1040d-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1040d-125"><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></span><span class="sxs-lookup"><span data-stu-id="1040d-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1040d-126">Microsoft Exchange 통합 (일부 또는 모든 사용자에 대 한 보관 저장소의 경우 Exchange 2013 사용)을 사용 하려면 기존 Exchange 2013 배포가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="1040d-127">일부 또는 모든 사용자의 보관 저장소로 별도의 보관 데이터베이스(SQL Server 데이터베이스 사용)를 사용하려는 경우 해당 서버에서 보관 데이터를 저장할 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1040d-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="1040d-p105">보관은 엔터프라이즈 풀의 프런트 엔드 서버 및 Standard Edition 서버에서 실행됩니다. 이러한 서버를 설치하는 데 필요한 것 외에 추가 하드웨어 또는 소프트웨어 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="1040d-130">로컬 Administrators 그룹의 구성원인 도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="1040d-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="1040d-131">지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="1040d-132">지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">서버 소프트웨어 및 인프라 지원 (Lync Server 2013</a> )</span><span class="sxs-lookup"><span data-stu-id="1040d-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="1040d-133">계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에 보관에 대 한 기술 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="1040d-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="1040d-134">배포 설명서의 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013에서 보관용 시스템 및 인프라 설정</a></span><span class="sxs-lookup"><span data-stu-id="1040d-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="1040d-135">지원 가능성 설명서의 <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange server 및 SharePoint 통합 지원은 Lync Server 2013</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1040d-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1040d-136"><strong>보관을 지원 하기 위한 적절 한 내부 토폴로지 만들기 (배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에만)</strong></span><span class="sxs-lookup"><span data-stu-id="1040d-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="1040d-137">토폴로지 작성기를 실행 하 여 Lync Server 2013 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="1040d-138">보관 데이터베이스를 사용하도록 토폴로지를 정의하려는 경우 로컬 Users 그룹의 구성원인 계정</span><span class="sxs-lookup"><span data-stu-id="1040d-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="1040d-139">토폴로지를 게시 하려면 domain admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 인 계정 이며 Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)을 포함 하 고, 토폴로지 작성기에서 필요한 Dacl을 구성할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="1040d-140">배포 설명서의 <a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">기존 Lync Server 2013 배포에 보관 데이터베이스 추가</a></span><span class="sxs-lookup"><span data-stu-id="1040d-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1040d-141"><strong>서버 간 인증 구성 (Microsoft Exchange 통합을 사용 하는 경우에만)</strong></span><span class="sxs-lookup"><span data-stu-id="1040d-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="1040d-142">Lync Server 2013 및 Exchange 2013 간에 인증을 사용 하도록 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="1040d-143">보관을 사용 하도록 설정 하기 전에 <strong>Test-CsExchangeStorageConnectivity testuser_sipUri-Folder 휴지통</strong> 를 실행 하 여 Exchange 보관 저장소 연결을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="1040d-144">서버에서 인증서를 관리하기 위한 적합한 권한이 있는 계정</span><span class="sxs-lookup"><span data-stu-id="1040d-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="1040d-145">배포 설명서 또는 작업 설명서의 <a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리</a></span><span class="sxs-lookup"><span data-stu-id="1040d-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1040d-146"><strong>보관 정책 및 구성 설정</strong></span><span class="sxs-lookup"><span data-stu-id="1040d-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="1040d-147">Microsoft Exchange 통합, 전역 정책 및 모든 사이트 및 사용자 정책 (모든 데이터 저장소에 대해 Microsoft Exchange 통합을 사용 하지 않을 때)을 사용할지 여부와 중요 모드 및 데이터 내보내기 및 제거와 같은 특정 보관 옵션을 포함 하 여 보관을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="1040d-148">Microsoft Exchange 통합을 사용 하는 경우 Exchange In-Place 보존 정책을 적절 하 게 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="1040d-149">RTCUniversalServerAdmins 그룹(Windows PowerShell만) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 지정</span><span class="sxs-lookup"><span data-stu-id="1040d-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="1040d-150">배포 설명서의 <a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013에서 보관에 대 한 지원 구성</a></span><span class="sxs-lookup"><span data-stu-id="1040d-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="1040d-151">Exchange 제품 설명서 (Microsoft Exchange 통합을 사용 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="1040d-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="1040d-152">다른 포리스트에 Lync Server 및 Microsoft Exchange 배포</span><span class="sxs-lookup"><span data-stu-id="1040d-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="1040d-153">Microsoft Exchange Server를 Lync Server와 같은 포리스트에 배포 하지 않은 경우 다음 Exchange Active Directory 특성이 Lync Server를 배포 하는 포리스트와 동기화 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="1040d-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="1040d-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="1040d-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1040d-155">proxyAddresses</span></span>

<span data-ttu-id="1040d-p107">이 특성은 다중 값 특성입니다. 이 특성을 동기화할 때는 기존 값이 손실되지 않도록 값을 대체하지 않고 병합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040d-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

