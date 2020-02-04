---
title: Lync Server 2013 전화 접속 회의 배포 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf496dcb24c021246bfbb6e7a5ef7b3a3a5acc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="f6a28-102">Lync Server 2013 의 전화 접속 회의 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="f6a28-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6a28-103">_**마지막으로 수정한 주제:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="f6a28-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="f6a28-104">전화 접속 회의에 필요한 구성 요소는 회의 작업을 배포할 때 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="f6a28-105">전화 접속 회의를 구성 하려면 먼저 엔터프라이즈 음성 또는 중재 서버와 PSTN (공개 전환 전화 네트워크) 게이트웨이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="f6a28-106">다음 표에 나와 있는 모든 단계는 사용자가 PSTN에서 전화 접속을 하 여 음성/영상 회의에 참가 하기 전에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6a28-107">Office Communications Server 2007 R2에서 마이그레이션하는 경우 전화 접속 회의를 배포 하기 전에 Office Communications Server 2007 R2 환경에 최신 업데이트를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="f6a28-108">전화 접속 회의 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f6a28-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6a28-109">단계의</span><span class="sxs-lookup"><span data-stu-id="f6a28-109">Phase</span></span></th>
<th><span data-ttu-id="f6a28-110">방법은</span><span class="sxs-lookup"><span data-stu-id="f6a28-110">Steps</span></span></th>
<th><span data-ttu-id="f6a28-111">필요한</span><span class="sxs-lookup"><span data-stu-id="f6a28-111">Permissions</span></span></th>
<th><span data-ttu-id="f6a28-112">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="f6a28-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-113"><strong>조정 서버 및 PSTN 게이트웨이를 포함 하 여 회의 작업량을 포함 하는 토폴로지를 만들고 프런트 엔드 풀 또는 Standard Edition 서버를 배포 합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f6a28-114">토폴로지 작성기를 실행 하 여 토폴로지를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="f6a28-115">토폴로지를 구성 하는 동안 전화 접속 회의 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="f6a28-116">토폴로지를 게시 하 고 프런트 엔드 풀 또는 Standard Edition 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="f6a28-117">필요한 경우 독립 실행형 중재 서버를 만들고 PSTN 게이트웨이와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f6a28-118">엔터프라이즈 음성을 배포 하지 않고 엔터프라이즈 EditionFront End Server 또는 Standard Edition Server와 중재 서버를 collocate 하지 않는 경우에만이 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="f6a28-119">엔터프라이즈 음성을 배포 하는 경우 엔터프라이즈 음성 배포의 일부로 중재 서버와 PSTN 게이트웨이를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="f6a28-120">중재 서버를 collocate 경우에는 프런트 엔드 풀 또는 Standard Edition Server 배포의 일부로 중재 서버를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="f6a28-121">도메인 관리자</span><span class="sxs-lookup"><span data-stu-id="f6a28-121">Domain Admins</span></span></p>
<p><span data-ttu-id="f6a28-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-123">관리자</span><span class="sxs-lookup"><span data-stu-id="f6a28-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6a28-124"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 배포</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="f6a28-125">독립 실행형 중재 서버 풀을 만들려면 다음을 수행 합니다. <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync server 2013에서 중재 서버 배포 및 피어 정의</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-126"><strong>다이얼 플랜 구성</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-127">다이얼 플랜은 전화 인증 및 통화 라우팅과 관련 하 여 특정 위치에서 전화를 거는 번호를 단일 표준 (E) 형식으로 변환 하는 일련의 전화 번호 정규화 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="f6a28-128">다른 위치에서 전화를 거는 같은 번호는 각각의 다이얼 플랜을 기준으로 각 위치에 따라 다른 전자 164 번호로 확인 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="f6a28-129">엔터프라이즈 음성을 배포 하는 경우에는 해당 배포의 일부로 다이얼 플랜을 설정 하 고 다이얼 인 회의도 함께 사용할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="f6a28-130">엔터프라이즈 음성을 배포 하지 않는 경우 전화 접속 회의를 위한 다이얼 플랜을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="f6a28-131">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음과 같이 다이얼 플랜을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="f6a28-132">전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 이상의 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="f6a28-133">각 풀에 기본 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-133">Assign a default dial plan to each pool.</span></span> <span data-ttu-id="f6a28-134">전화 접속 <strong>회의 지역을</strong> 다이얼 플랜을 적용할 지리적 위치로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-134">Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies.</span></span> <span data-ttu-id="f6a28-135">지역에서 다이얼 플랜을 전화 접속 액세스 번호와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-135">The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f6a28-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013에서 전화 접속 회의에 대한 다이얼 플랜 구성</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-141"><strong>다이얼 플랜에 영역이 할당 되어 있는지 확인</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-142"><strong>Get-CsDialPlan 플랜</strong> 및 <strong>Set-csdialplan 플랜</strong> cmdlet을 실행 하 여 모든 다이얼 플랜에 지역이 지정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">다이얼 플랜 설정 Lync 서버 2013에 지역이 지정 되어 있어야 합니다.</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-148"><strong>) 사용자 개인 id 번호 (PIN) 요구 사항 확인 또는 수정</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-149">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 회의 <strong>PIN 정책을</strong>보거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="f6a28-150">최소 PIN 길이, 최대 로그온 시도 횟수, PIN 만료, 공통 패턴 허용 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(선택 사항) Lync Server 2013에서 PIN 정책 설정 확인</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-155"><strong>전화 접속 회의를 지원 하도록 회의 정책 구성</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-156">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 <strong>회의 정책</strong> 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="f6a28-157">여부 지정:</span><span class="sxs-lookup"><span data-stu-id="f6a28-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="f6a28-158">PSTN 회의 전화 접속을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="f6a28-159">사용자가 익명 참가자를 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="f6a28-160">인증 되지 않은 사용자는 전화 걸기 phoning를 사용 하 여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-160">Unauthenticated users can join a conference by using dial-out phoning.</span></span> <span data-ttu-id="f6a28-161">전화 걸기 phoning를 사용 하 여 회의 서버는 사용자에 게 전화를 걸고 사용자는 해당 휴대폰에 응답 하 여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-161">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6a28-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013에서 전화 접속에 대한 회의 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-166"><strong>전화 접속 액세스 번호 구성</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-167">Lync Server 2013 제어판 또는 Lync Server Management Shell을 사용 하 여 전화 접속 액세스 번호를 설정 하 여 사용자가 회의에 전화를 걸고 해당 전화 접속 계획에 액세스 번호를 연결 하는 지역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="f6a28-168">이끌이 다이얼 플랜에서 지정한 영역의 처음 세 개 액세스 번호는 회의 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="f6a28-169">모든 액세스 번호는 전화 접속 회의 설정 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f6a28-170">전화 접속 액세스 번호를 만든 후에는 <STRONG>CsDialInConferencingAccessNumber</STRONG> cmdlet을 사용 하 여 Active Directory 연락처 개체의 표시 이름을 수정 하 고 사용자가 올바른 액세스 번호를 더 쉽게 식별할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="f6a28-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013에서 전화 접속 회의 액세스 번호 구성</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-175"><strong>(선택 사항) 전화 접속 회의 설정 확인</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-176"><strong>CsDialinConferencingAccessNumber</strong> cmdlet을 사용 하 여 액세스 번호 및 지역이 지정 되지 않은 액세스 번호에 사용 되지 않는 전화 접속 회의 영역이 있는 다이얼 플랜을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-180">Csviewadministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="f6a28-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="f6a28-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(선택 사항) Lync Server 2013에서 전화 접속 회의 설정 확인</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-183"><strong>) DTMF 명령의 키 매핑 수정</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-184"><strong>CsDialinConferencingDtmfConfiguration</strong> cmdlet을 사용 하 여 참가자가 전화 회의 설정을 제어 하는 데 사용할 수 있는 DTMF (듀얼 톤 multifrequency) 명령에 사용 되는 키를 수정 합니다 (예: 음소거 및 음소거 해제 또는 잠금 및 잠금 해제).</span><span class="sxs-lookup"><span data-stu-id="f6a28-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="f6a28-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(선택 사항) Lync Server 2013에서 DTMF 명령에 대한 키 매핑 수정</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-189"><strong>) 컨퍼런스 참가 및 알림 종료 동작 수정</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-190"><strong>CsDialinConferencingConfiguration</strong> 를 사용 하 여 참가자가 회의에 참가 하 고 나갈 때 알림이 작동 하는 방식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(선택 사항) Lync Server 2013에서 회의 참가/나가기 알림 활성화/비활성화</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-195"><strong>(선택 사항) 전화 접속 회의 확인</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-196"><strong>CsDialInConferencing</strong> cmdlet을 사용 하 여 지정 된 풀에 대 한 액세스 번호가 올바르게 작동 하는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(선택 사항) Lync Server 2013에서 전화 접속 회의 확인</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-201"><strong>Lync 2013용 온라인 모임 추가 기능 배포</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-202">사용자가 전화 접속 회의를 지 원하는 회의 일정을 예약할 수 있도록 Lync 2013에 대 한 온라인 모임 추가 기능을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="f6a28-203">Lync 2013을 설치 하면 Lync 2013의 온라인 모임 추가 기능이 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-204">관리자</span><span class="sxs-lookup"><span data-stu-id="f6a28-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="f6a28-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013용 온라인 모임 추가 기능 배포</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-206"><strong>사용자 계정 설정 구성</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-207">Lync Server 2013 제어판 또는 Lync Server Management Shell을 사용 하 여 전화 통신 <strong>회선 URI</strong> 를 고유한 정규화 된 전화 번호 (예: tel: + 14255550200)로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="f6a28-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f6a28-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="f6a28-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="f6a28-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f6a28-211"><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013에서 사용자 계정 설정 구성</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a28-212">권장 컨퍼런스 디렉터리 구성</span><span class="sxs-lookup"><span data-stu-id="f6a28-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="f6a28-213"><strong>CsConferenceDirectory</strong> cmdlet을 사용 하 여 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f6a28-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013의 전화 접속 회의 요구 사항</a> <a href="recommended-create-conference-directories.md">(권장) 전화 회의 디렉터리 만들기</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a28-216"><strong>) 사용자가 전화 접속 회의를 시작 하 고 초기 PIN 설정</strong></span><span class="sxs-lookup"><span data-stu-id="f6a28-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="f6a28-217"><strong>CsPinSendCAWelcomeMail</strong> 스크립트를 사용 하 여 사용자의 초기 핀을 설정 하 고 초기 PIN 및 전화 접속 회의 설정 페이지로 연결 되는 링크가 포함 된 환영 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a28-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="f6a28-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f6a28-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f6a28-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(선택 사항) Lync Server 2013에서 사용자에게 전화 접속 회의 시작 메시지 보내기</a></span><span class="sxs-lookup"><span data-stu-id="f6a28-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

