---
title: 'Lync Server 2013: 통화 허용 제어에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d9591ad8dfed90373fedc8adfb3a3c3c44eb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529145"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e4e52-102">Lync Server 2013의 통화 허용 제어에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="e4e52-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4e52-103">_**마지막으로 수정 된 항목:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="e4e52-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="e4e52-104">CAC(통화 허용 제어)를 효과적으로 계획하려면 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e52-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="e4e52-105">CAC 배포를 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e4e52-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="e4e52-106">CAC에 필요한 정보 및 배포 전 결정해야 하는 구성 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="e4e52-107">통화 허용 제어에 대한 배포 필요 조건</span><span class="sxs-lookup"><span data-stu-id="e4e52-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="e4e52-108">통화 허용 제어를 배포 하기 전에 프런트 엔드 풀 또는 Standard Edition 서버를 포함 하 여 Lync Server 2013 내부 서버를 이미 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e52-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="e4e52-109">통화 허용 제어에 대한 정보 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="e4e52-110">다음 표에는 통화 허용 제어 배포에 필요한 정보가 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4e52-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="e4e52-111">통화 허용 제어 배포에 대한 정보 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4e52-112">정보</span><span class="sxs-lookup"><span data-stu-id="e4e52-112">Information</span></span></th>
<th><span data-ttu-id="e4e52-113">필요한 정보 요약</span><span class="sxs-lookup"><span data-stu-id="e4e52-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="e4e52-114">설명서</span><span class="sxs-lookup"><span data-stu-id="e4e52-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4e52-115">조직에 필요한 Lync Server 기능</span><span class="sxs-lookup"><span data-stu-id="e4e52-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-116">조직에서 지원할 기능</span><span class="sxs-lookup"><span data-stu-id="e4e52-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="e4e52-117">개별 사용자에 대해 사용하도록 설정할 기능</span><span class="sxs-lookup"><span data-stu-id="e4e52-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e52-119">배포할 토폴로지 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e4e52-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-120">CAC 관련 구성 요소는 Lync Server 2013의 일부로 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4e52-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4e52-122">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-123">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="e4e52-124">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="e4e52-125">배치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-126"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013에 대 한 시스템 요구 사항 확인</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e52-127">인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-128">CAC에는 특별한 인프라 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4e52-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어에 대 한 인프라 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4e52-130">네트워크 인터페이스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-131">내부 및 외부 인터페이스 정보</span><span class="sxs-lookup"><span data-stu-id="e4e52-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="e4e52-132">라우팅 정보 (다음 홉 블로그의 정보 포함 <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> ) (Microsoft Lync Server 팀의 고객 응답 채널)</span><span class="sxs-lookup"><span data-stu-id="e4e52-132">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-133"><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스 배포</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e52-134">배포 전략</span><span class="sxs-lookup"><span data-stu-id="e4e52-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-135">배포 순서</span><span class="sxs-lookup"><span data-stu-id="e4e52-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="e4e52-136">작업 그룹 또는 도메인</span><span class="sxs-lookup"><span data-stu-id="e4e52-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="e4e52-137">보안</span><span class="sxs-lookup"><span data-stu-id="e4e52-137">Security</span></span></p></li>
<li><p><span data-ttu-id="e4e52-138">모니터링 및 감사</span><span class="sxs-lookup"><span data-stu-id="e4e52-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="e4e52-139">하드웨어 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어에 대 한 모범 사례</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4e52-141">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="e4e52-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4e52-142">필수 조건</span><span class="sxs-lookup"><span data-stu-id="e4e52-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="e4e52-143">정보 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e52-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="e4e52-144">프로세스 및 절차</span><span class="sxs-lookup"><span data-stu-id="e4e52-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4e52-145"><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 구성</a></span><span class="sxs-lookup"><span data-stu-id="e4e52-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

