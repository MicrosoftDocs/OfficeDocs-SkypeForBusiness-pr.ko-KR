---
title: 'Lync Server 2013: 통화 허용 제어 서비스에 대한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="8c894-102">Lync Server 2013의 통화 허용 제어 서비스에 대한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="8c894-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c894-103">_**마지막으로 수정한 주제:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="8c894-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="8c894-104">호출 허용 제어 (CAC)를 효과적으로 계획 하려면 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c894-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="8c894-105">CAC 배포를 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8c894-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="8c894-106">사전 설정 및 구성 결정에 필요한 정보 (배포를 미리 하기 위해 필요 함)</span><span class="sxs-lookup"><span data-stu-id="8c894-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="8c894-107">통화 허용 제어에 대 한 배포 선행 조건</span><span class="sxs-lookup"><span data-stu-id="8c894-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="8c894-108">통화 허용 제어를 배포 하기 전에 먼저 프런트 엔드 풀 또는 Standard Edition 서버를 포함 하 여 Lync Server 2013 내부 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c894-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="8c894-109">통화 허용 제어에 대 한 정보 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="8c894-110">다음 표에는 통화 허용 제어를 배포 하는 데 필요한 정보가 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c894-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="8c894-111">통화 허용 제어 배포에 대 한 정보 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c894-112">방법</span><span class="sxs-lookup"><span data-stu-id="8c894-112">Information</span></span></th>
<th><span data-ttu-id="8c894-113">필요한 정보 요약</span><span class="sxs-lookup"><span data-stu-id="8c894-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="8c894-114">설명서</span><span class="sxs-lookup"><span data-stu-id="8c894-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c894-115">조직에서 필요로 하는 Lync Server 기능</span><span class="sxs-lookup"><span data-stu-id="8c894-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-116">조직에서 지원 되는 기능</span><span class="sxs-lookup"><span data-stu-id="8c894-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="8c894-117">개별 사용자에 대해 사용할 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="8c894-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의</a></span><span class="sxs-lookup"><span data-stu-id="8c894-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c894-119">배포할 토폴로지 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8c894-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-120">CAC 관련 구성 요소는 Lync Server 2013의 일부로 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c894-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의</a></span><span class="sxs-lookup"><span data-stu-id="8c894-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c894-122">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-123">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="8c894-124">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="8c894-125">Collocation 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-126"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013의 시스템 요구 사항 확인</a></span><span class="sxs-lookup"><span data-stu-id="8c894-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c894-127">인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-128">CAC에는 특정 인프라 요구 사항이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c894-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어 서비스에 대한 인프라 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="8c894-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c894-130">네트워크 인터페이스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-131">내부 및 외부 인터페이스 정보</span><span class="sxs-lookup"><span data-stu-id="8c894-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="8c894-132">라우팅 정보 (NextHop 블로그의 정보 포함 <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server 팀의 고객 응답 채널)</span><span class="sxs-lookup"><span data-stu-id="8c894-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-133"><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스 배포</a></span><span class="sxs-lookup"><span data-stu-id="8c894-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c894-134">배포 전략</span><span class="sxs-lookup"><span data-stu-id="8c894-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-135">배포 순서</span><span class="sxs-lookup"><span data-stu-id="8c894-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="8c894-136">작업 그룹 또는 도메인</span><span class="sxs-lookup"><span data-stu-id="8c894-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="8c894-137">보안</span><span class="sxs-lookup"><span data-stu-id="8c894-137">Security</span></span></p></li>
<li><p><span data-ttu-id="8c894-138">모니터링 및 감사</span><span class="sxs-lookup"><span data-stu-id="8c894-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="8c894-139">하드웨어 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어 서비스 모범 사례</a></span><span class="sxs-lookup"><span data-stu-id="8c894-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c894-141">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="8c894-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c894-142">필요 조건</span><span class="sxs-lookup"><span data-stu-id="8c894-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="8c894-143">정보 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c894-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="8c894-144">프로세스 및 절차</span><span class="sxs-lookup"><span data-stu-id="8c894-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c894-145"><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 구성</a></span><span class="sxs-lookup"><span data-stu-id="8c894-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

