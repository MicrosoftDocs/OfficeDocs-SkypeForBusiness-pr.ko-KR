---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6234ca4a8a0e7f6edc2069b7bb42f0bae545713b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0d605-102">Lync Server 2013의 영구 채팅 서버에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="0d605-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d605-103">_**마지막으로 수정 된 항목:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="0d605-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="0d605-104">Lync Server 2013, 영구 채팅 서버를 배포 하려면 올바른 순서로 배포 하 고 필요한 모든 배포 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="0d605-105">배포 순서</span><span class="sxs-lookup"><span data-stu-id="0d605-105">Deployment Sequence</span></span>

<span data-ttu-id="0d605-106">하나 이상의 Lync Server 2013, 프런트 엔드 풀 또는 Lync Server 2013, Standard Edition 서버를 포함 하 여 초기 토폴로지를 배포한 후 영구 채팅 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="0d605-107">이 항목에서는 영구 채팅 서버를 기존 배포에 추가 하 여 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="0d605-108">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="0d605-108">Deployment Process</span></span>

<span data-ttu-id="0d605-109">다음 표에는 영구 채팅 서버를 배포 하 고 자세한 내용을 볼 수 있는 링크를 제공 하는 기본 단계가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="0d605-110">영구 채팅 서버 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="0d605-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d605-111">작업</span><span class="sxs-lookup"><span data-stu-id="0d605-111">Task</span></span></th>
<th><span data-ttu-id="0d605-112">단계</span><span class="sxs-lookup"><span data-stu-id="0d605-112">Steps</span></span></th>
<th><span data-ttu-id="0d605-113">필요한 역할 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="0d605-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="0d605-114">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0d605-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d605-115"><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></span><span class="sxs-lookup"><span data-stu-id="0d605-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="0d605-116">시스템 요구 사항을 충족하는 하드웨어에 다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d605-117">영구 채팅 서버 프런트 엔드 서버에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="0d605-118">시스템 요구 사항을 충족 하는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="0d605-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="0d605-119">Lync Server 2013을 실행 하는 컴퓨터에 대 한 소프트웨어 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0d605-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="0d605-120">영구 채팅 서버 데이터베이스를 호스팅할 서버의 SQL Server</span><span class="sxs-lookup"><span data-stu-id="0d605-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="0d605-121">영구 채팅 서버를 준수 해야 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0d605-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d605-122">영구 채팅 서버 준수 데이터베이스를 호스팅할 서버의 SQL Server</span><span class="sxs-lookup"><span data-stu-id="0d605-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0d605-123">로컬 Administrators 그룹의 구성원 인 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="0d605-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="0d605-124">지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a></span><span class="sxs-lookup"><span data-stu-id="0d605-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="0d605-125">지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">서버 소프트웨어 및 인프라 지원 (Lync Server 2013</a> )</span><span class="sxs-lookup"><span data-stu-id="0d605-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="0d605-126"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013에 대 한 시스템 요구 사항 확인</a></span><span class="sxs-lookup"><span data-stu-id="0d605-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0d605-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="0d605-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d605-128"><strong>영구 채팅 서버 및 선택적으로 영구 채팅 준수를 지원 하기 위한 적절 한 내부 토폴로지 만들기</strong></span><span class="sxs-lookup"><span data-stu-id="0d605-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="0d605-129">토폴로지 작성기를 실행 하 여 토폴로지에 영구 채팅 서버 풀을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d605-130">토폴로지에 영구 채팅 서버 구성 요소 추가</span><span class="sxs-lookup"><span data-stu-id="0d605-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="0d605-131">영구 채팅 서버 저장소에 대 한 SQL Server 데이터베이스 만들기 (재해 복구용 백업 SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0d605-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="0d605-132">영구 채팅 서버 파일용으로 새 Lync 파일 저장소를 정의 하거나 기존 Lync 파일 저장소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="0d605-133">요청을 라우팅할 수 있는 Lync Server 2013 풀을이 영구 채팅 서버 풀에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="0d605-134">영구 채팅 준수가 필요한 경우:</span><span class="sxs-lookup"><span data-stu-id="0d605-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d605-135">영구 채팅 준수 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="0d605-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="0d605-136">준수를 사용 하도록 설정 하려면 영구 채팅 서버 풀 정의 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="0d605-137">토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="0d605-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="0d605-138">Standard Edition에 영구 채팅 서버를 설치 하는 경우 영구 채팅 서버 풀의 FQDN (정규화 된 도메인 이름)이 Standard Edition Server와 일치 해야 하며 SQL Server 데이터베이스가 표준의 SQL Server Express 인스턴스에서 배치 된 됩니다. Edition server</span><span class="sxs-lookup"><span data-stu-id="0d605-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="0d605-139">토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="0d605-140">토폴로지를 게시 하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 인 계정인 사용자에 게 영구 채팅 서버 파일용 Lync 파일 저장소에 대 한 모든 권한 (읽기/쓰기/수정)이 있어야 합니다 (토폴로지 작성기에서 필요한 Dacl을 구성할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="0d605-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="0d605-141">배포 설명서의 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013에서 배포에 영구 채팅 서버 추가</a></span><span class="sxs-lookup"><span data-stu-id="0d605-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d605-142"><strong>영구 채팅 서버 배포</strong></span><span class="sxs-lookup"><span data-stu-id="0d605-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="0d605-143">영구 채팅 서버를 실행 하는 모든 컴퓨터에서 Lync Server 설치 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="0d605-144">영구 채팅 서버 설치 프로그램은 다음 지침을 제공 하는 Lync Server 2013 배포 마법사에 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d605-145">로컬 관리 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="0d605-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="0d605-146">영구 채팅 서버 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="0d605-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="0d605-147">인증서 요청 및 할당</span><span class="sxs-lookup"><span data-stu-id="0d605-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="0d605-148">서비스 실행 및 시작</span><span class="sxs-lookup"><span data-stu-id="0d605-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0d605-149">로컬 Administrators 그룹의 구성원 인 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="0d605-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="0d605-150">배포 설명서의 <a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013에서 영구 채팅 서버 배포</a></span><span class="sxs-lookup"><span data-stu-id="0d605-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d605-151"><strong>영구 채팅 관리자 만들기</strong></span><span class="sxs-lookup"><span data-stu-id="0d605-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="0d605-152">CsPersistentChatAdministrator 보안 그룹에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="0d605-153">도메인 관리자의 구성원 인 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="0d605-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="0d605-154">배포 설명서의 <a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013에서 영구 채팅 관리자 추가</a></span><span class="sxs-lookup"><span data-stu-id="0d605-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d605-155"><strong>영구 채팅 서버 구성</strong></span><span class="sxs-lookup"><span data-stu-id="0d605-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="0d605-156">사용자 구성:</span><span class="sxs-lookup"><span data-stu-id="0d605-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d605-157">영구 채팅 서버에 액세스 하려면 사용자가 정책에 따라 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="0d605-158">기본적으로 정책은 모든 사용자에 대해 해제 되며 전역/사이트/풀/사용자 범위에서 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="0d605-159">설정 구성</span><span class="sxs-lookup"><span data-stu-id="0d605-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0d605-160">사용자는 CsPersistentChatAdministrator의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-160">User must be a member of CsPersistentChatAdministrator.</span></span> <span data-ttu-id="0d605-161">정책을 변경 하려면 사용자가 CsUserAdministrator에 최소한 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-161">To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="0d605-162">배포 설명서의 <a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013에서 영구 채팅 서버 구성</a></span><span class="sxs-lookup"><span data-stu-id="0d605-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d605-163">하나 이상의 영구 채팅 서버 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="0d605-164">지정 된 지역에서 생성 된 데이터가 해당 지역에 유지 해야 하는 규정 이유로 여러 영구 채팅 서버 풀을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="0d605-165">예를 들어 시카고에 영구 채팅 서버 풀을 배포 하는 경우, 스위스의 데이터에 대 한 규정을 준수 하기 위해 취리히 정규에서 사용 하는 경우 사용자는 액세스 권한이 있으면 영구 채팅 서버 풀의 대화방에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d605-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

