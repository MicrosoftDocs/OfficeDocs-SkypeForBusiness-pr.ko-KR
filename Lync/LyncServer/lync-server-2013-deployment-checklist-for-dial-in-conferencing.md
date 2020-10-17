---
title: Lync Server 2013 전화 접속 회의에 대 한 배포 검사 목록
description: Lync Server 2013 전화 접속 회의에 대 한 배포 검사 목록
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
ms.openlocfilehash: 743b5120bf011ab8467679bea9869a46231b0835
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568364"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="46b72-103">Lync Server 2013의 전화 접속 회의에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="46b72-103">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46b72-104">_**마지막으로 수정 된 항목:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="46b72-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="46b72-105">전화 접속 회의에 필요한 구성 요소는 회의 작업을 배포할 때 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-105">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="46b72-106">전화 접속 회의를 구성 하려면 먼저 Enterprise Voice 또는 중재 서버와 PSTN (공중 전화망) 게이트웨이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-106">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="46b72-107">사용자가 PSTN을 통해 오디오/비디오 회의에 참가하려면 다음 표에 설명된 모든 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-107">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46b72-108">Office Communications Server 2007 R2에서 마이그레이션하는 경우 전화 접속 회의를 배포 하기 전에 Office Communications Server 2007 R2 환경에 최신 업데이트를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-108">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="46b72-109">전화 접속 회의 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="46b72-109">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46b72-110">단계</span><span class="sxs-lookup"><span data-stu-id="46b72-110">Phase</span></span></th>
<th><span data-ttu-id="46b72-111">단계</span><span class="sxs-lookup"><span data-stu-id="46b72-111">Steps</span></span></th>
<th><span data-ttu-id="46b72-112">권한</span><span class="sxs-lookup"><span data-stu-id="46b72-112">Permissions</span></span></th>
<th><span data-ttu-id="46b72-113">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="46b72-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46b72-114"><strong>중재 서버 및 PSTN 게이트웨이를 포함 하 여 회의 작업을 포함 하는 토폴로지를 만들고 프런트 엔드 풀 또는 Standard Edition Server를 배포 합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-114"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="46b72-115">토폴로지 작성기를 실행 하 여 토폴로지를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-115">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="46b72-116">토폴로지를 구성할 때 전화 접속 회의 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-116">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="46b72-117">토폴로지를 게시 하 고 프런트 엔드 풀 또는 Standard Edition server를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-117">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="46b72-118">필요한 경우 독립 실행형 중재 서버를 만들어 PSTN 게이트웨이와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-118">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="46b72-119">Enterprise Voice를 배포 하지 않고 엔터프라이즈 EditionFront 엔드 서버 또는 Standard Edition 서버와의 중재 서버를 함께 배치할 하지 않는 경우에만이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-119">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="46b72-120">Enterprise Voice를 배포 하는 경우 Enterprise Voice 배포의 일부로 중재 서버와 PSTN 게이트웨이를 설치 및 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-120">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="46b72-121">중재 서버를 함께 배치할 경우 프런트 엔드 풀 또는 Standard Edition Server 배포의 일부로 중재 서버를 설치 및 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-121">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="46b72-122">DomainAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-122">Domain Admins</span></span></p>
<p><span data-ttu-id="46b72-123">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-123">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-124">관리자</span><span class="sxs-lookup"><span data-stu-id="46b72-124">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="46b72-125"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 배포</a></span><span class="sxs-lookup"><span data-stu-id="46b72-125"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="46b72-126">독립 실행형 중재 서버 풀을 만들려면 다음과 같이 하세요. <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync server 2013에서 중재 서버를 배포 하 고 피어를 정의</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-126">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-127"><strong>다이얼 플랜을 구성합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-127"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-128">다이얼 플랜은 특정 위치에서 걸려 온 전화 번호를 전화 권한 부여 및 통화 라우팅을 위해 단일 표준(E.164) 형식으로 변환하는 전화 번호 정규화 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-128">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="46b72-129">다른 위치에서 전화 건 동일한 전화 번호는 해당 다이얼 플랜에 따라 각 위치에 적절한 다른 E.164 번호로 확인될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-129">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="46b72-130">Enterprise Voice를 배포 하는 경우 해당 배포의 일부로 다이얼 플랜을 설정 하 고 전화 접속 회의도 함께 지원 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-130">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="46b72-131">Enterprise Voice를 배포 하지 않는 경우 전화 접속 회의에 대 한 다이얼 플랜을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-131">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="46b72-132">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 다이얼 플랜을 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-132">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="46b72-133">전화 접속 액세스 번호 라우팅에 대한 하나 이상의 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-133">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="46b72-p105">각 풀에 기본 다이얼 플랜을 할당합니다. <strong>전화 접속 회의 지역</strong>을 다이얼 플랜이 적용되는 지리적 위치로 설정합니다. 이 지역은 다이얼 플랜을 전화 접속 액세스 번호와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="46b72-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="46b72-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성</a></span><span class="sxs-lookup"><span data-stu-id="46b72-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46b72-142"><strong>다이얼 플랜이 할당 된 지역 인지 확인</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-142"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-143"><strong>Get-CsDialPlan 플랜</strong> 및 <strong>Set-csdialplan 플랜</strong> cmdlet을 실행 하 여 모든 다이얼 플랜에 지역이 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-143">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="46b72-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="46b72-146">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-146">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">다이얼 플랜 Lync Server 2013에 지역이 할당 되었는지 확인</a></span><span class="sxs-lookup"><span data-stu-id="46b72-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-149"><strong>(선택 사항) 사용자 PIN(개인 식별 번호) 요구 사항을 확인하거나 수정합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-149"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-150">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 회의 <strong>PIN 정책을</strong>보거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-150">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="46b72-151">최소 PIN 길이, 최대 로그온 시도 횟수, PIN 만료 날짜 및 공통 패턴 허용 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-151">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="46b72-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">반드시 Lync Server 2013에서 PIN 정책 설정 확인</a></span><span class="sxs-lookup"><span data-stu-id="46b72-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46b72-156"><strong>전화 접속 회의를 지원하도록 회의 정책을 구성합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-156"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-157">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 <strong>회의 정책</strong> 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-157">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="46b72-158">다음 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-158">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="46b72-159">PSTN 전화 회의 전화 접속 사용 여부</span><span class="sxs-lookup"><span data-stu-id="46b72-159">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="46b72-160">사용자가 익명 참가자를 초대할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="46b72-160">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="46b72-p108">인증되지 않은 사용자가 전화 접속 전화를 사용하여 전화 회의에 참가할 수 있는지 여부. 전화 접속 전화를 사용하면 전화 회의 서버에서 사용자에게 전화를 걸고 사용자는 이 전화에 응답하여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46b72-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-164">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-164">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-165">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-165">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013에서 전화 접속에 대 한 회의 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="46b72-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-167"><strong>전화 접속 액세스 번호를 구성합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-167"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-168">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 사용자가 전화 회의에 전화를 거는 데 전화 접속 액세스 번호를 설정 하 고 해당 하는 다이얼 플랜과 액세스 번호를 연결 하는 지역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-168">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="46b72-169">이끌이의 다이얼 플랜에 지정된 지역에 대한 처음 세 개의 액세스 번호가 전화 회의 초대에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-169">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="46b72-170">모든 액세스 번호는 전화 접속 회의 설정 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-170">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="46b72-171">전화 접속 액세스 번호를 만든 후에는 <STRONG>get-csdialinconferencingaccessnumber</STRONG> cmdlet을 사용 하 여 Active Directory 연락처 개체의 표시 이름을 수정 하 여 사용자가 올바른 액세스 번호를 보다 쉽게 식별할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-171">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="46b72-172">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-172">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-173">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-173">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-174">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-174">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013에서 전화 접속 회의 액세스 번호 구성</a></span><span class="sxs-lookup"><span data-stu-id="46b72-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46b72-176"><strong>(선택 사항) 전화 접속 회의 설정을 확인합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-176"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-177"><strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet을 사용하여 액세스 번호에 사용되지 않는 전화 접속 회의 지역이 있는 다이얼 플랜 및 할당된 지역이 없는 액세스 번호에 대한 다이얼 플랜을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-177">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="46b72-178">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-178">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-179">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-179">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-180">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-180">CsAdministrator</span></span></p>
<p><span data-ttu-id="46b72-181">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-181">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="46b72-182">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="46b72-182">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="46b72-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">반드시 Lync Server 2013에서 전화 접속 회의 설정 확인</a></span><span class="sxs-lookup"><span data-stu-id="46b72-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-184"><strong>(선택 사항) DTMF 명령의 키 매핑을 수정합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-184"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-185"><strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet을 사용하여 DTMF(Dual-Tone Multifrequency) 명령에 사용되는 키를 수정합니다. 참가자는 이 키를 사용하여 전화 회의 설정(예: 음소거 및 음소거 해제 또는 잠금 및 잠금 해제)을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-185">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="46b72-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-187">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-187">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-188">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-188">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">반드시 Lync Server 2013의 DTMF 명령에 대 한 키 매핑 수정</a></span><span class="sxs-lookup"><span data-stu-id="46b72-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46b72-190"><strong>(선택 사항) 전화 회의 참가 및 나가기 알림 동작을 수정합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-190"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-191"><strong>Set-CsDialinConferencingConfiguration</strong>을 사용하여 참가자가 전화 회의에 참가하고 나갈 때 알림 작동 방식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-191">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="46b72-192">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-192">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-193">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-193">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-194">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-194">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">반드시 Lync Server 2013에서 전화 회의 참가 및 탈퇴 알림 사용 및 사용 안 함</a></span><span class="sxs-lookup"><span data-stu-id="46b72-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-196"><strong>(선택 사항) 전화 접속 회의를 확인합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-196"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-197"><strong>Test-CsDialInConferencing</strong> cmdlet을 사용하여 지정된 풀에 대한 액세스 번호가 올바르게 작동하는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-197">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="46b72-198">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-198">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-199">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-199">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="46b72-200">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-200">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">반드시 Lync Server 2013에서 전화 접속 회의 확인</a></span><span class="sxs-lookup"><span data-stu-id="46b72-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46b72-202"><strong>Lync 2013 용 온라인 모임 추가 기능 배포</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-202"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-203">사용자가 전화 접속 회의를 지 원하는 회의를 예약할 수 있도록 Lync 2013에 대 한 온라인 모임 추가 기능을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-203">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="46b72-204">Lync 2013 2013을 설치 하는 경우에는 sharepoint Online 용 온라인 모임 추가 기능이 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-204">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="46b72-205">관리자</span><span class="sxs-lookup"><span data-stu-id="46b72-205">Administrators</span></span></p></td>
<td><p><span data-ttu-id="46b72-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 용 온라인 모임 추가 기능 배포</a></span><span class="sxs-lookup"><span data-stu-id="46b72-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-207"><strong>사용자 계정 설정을 구성합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-207"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-208">Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 전화 통신 <strong>회선 URI</strong> 를 고유한 정규화 된 전화 번호 (예: tel-+ 14255550200)로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-208">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="46b72-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="46b72-210">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-210">CsAdministrator</span></span></p>
<p><span data-ttu-id="46b72-211">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="46b72-211">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46b72-212"><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013에서 사용자 계정 설정 구성</a></span><span class="sxs-lookup"><span data-stu-id="46b72-212"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46b72-213">는 전화 회의 디렉터리 구성</span><span class="sxs-lookup"><span data-stu-id="46b72-213">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="46b72-214"><strong>Get-csconferencedirectory</strong> cmdlet을 사용 하 여 풀의 999 모든 사용자에 대 한 회의 디렉터리를 하나씩 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-214">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="46b72-215">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-215">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="46b72-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013의 전화 접속 회의 요구 사항</a> <a href="recommended-create-conference-directories.md">(권장) 전화 회의 디렉터리 만들기</a></span><span class="sxs-lookup"><span data-stu-id="46b72-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b72-217"><strong>(선택 사항) 사용자를 전화 접속 회의에 초대하고 초기 PIN을 설정합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="46b72-217"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="46b72-218"><strong>Set-cspinsendcawelcomemail</strong> 스크립트를 사용 하 여 사용자의 초기 핀을 설정 하 고 초기 PIN 및 전화 접속 회의 설정 페이지로 연결 되는 링크가 포함 된 환영 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="46b72-218">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="46b72-219">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="46b72-219">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="46b72-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">반드시 Lync Server 2013에서 사용자에 게 전화 접속 회의 시작</a></span><span class="sxs-lookup"><span data-stu-id="46b72-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

