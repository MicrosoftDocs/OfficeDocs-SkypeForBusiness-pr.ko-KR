---
title: 'Lync Server 2013: 그룹 통화 픽업 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="c6e29-102">Lync Server 2013의 그룹 통화 픽업 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="c6e29-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6e29-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c6e29-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c6e29-104">이 섹션에서는 그룹 통화 픽업 배포와 관련 된 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="c6e29-105">그룹 통화 픽업을 구성 하려면 먼저 enterprise Voice를 사용 하 여 Enterprise Edition 또는 Standard Edition을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="c6e29-106">엔터프라이즈 음성을 구축할 때 그룹 통화 픽업에 필요한 구성 요소를 설치 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="c6e29-107">그룹 통화 픽업 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="c6e29-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6e29-108">단계의</span><span class="sxs-lookup"><span data-stu-id="c6e29-108">Phase</span></span></th>
<th><span data-ttu-id="c6e29-109">방법은</span><span class="sxs-lookup"><span data-stu-id="c6e29-109">Steps</span></span></th>
<th><span data-ttu-id="c6e29-110">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="c6e29-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="c6e29-111">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="c6e29-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6e29-112">토폴로지에서 SEFAUtil 리소스 키트 도구 사용</span><span class="sxs-lookup"><span data-stu-id="c6e29-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c6e29-113"><strong>새 CsTrustedApplicationPool</strong> cmdlet을 사용 하 여 신뢰할 수 있는 새 응용 프로그램 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="c6e29-114"><strong>새 CsTrustedApplication</strong> cmdlet을 사용 하 여 SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="c6e29-115"><strong>Enable-CsTopology</strong> cmdlet을 실행 하 여 토폴로지를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="c6e29-116">1 단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 있는 프런트 엔드 서버에 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="c6e29-117">배포에 있는 사용자의 착신 전환 설정을 표시 하려면 SEFAUtil를 실행 하 여 제대로 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c6e29-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c6e29-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c6e29-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Lync Server 2013에서 SEFAUtil 도구 배포</a></span><span class="sxs-lookup"><span data-stu-id="c6e29-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6e29-120">통화 공원에서 통화 픽업 번호 범위 구성 표</span><span class="sxs-lookup"><span data-stu-id="c6e29-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="c6e29-121"><strong>CSCallParkOrbit</strong> cmdlet을 사용 하 여 통화 공원 표 안에 통화 픽업 번호 범위를 만들고 통화 픽업 범위에 grouppickup 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c6e29-122">Lync Server Management Shell을 사용 하 여 통화 공원 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="c6e29-123">Lync Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="c6e29-124">기존 다이얼 플랜에 대 한 원활한 통합을 위해 숫자 범위가 일반적으로 가상 확장 블록으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="c6e29-125">직접 연결 된 전화 접속 (a) 번호를 통화 공원 궤도 테이블의 범위 번호로 지정 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="c6e29-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c6e29-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c6e29-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6e29-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c6e29-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6e29-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c6e29-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6e29-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c6e29-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013에서 통화 픽업 그룹 번호 구성</a></span><span class="sxs-lookup"><span data-stu-id="c6e29-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6e29-131">사용자에 게 통화 픽업 번호를 할당 하 고 사용자를 위해 그룹 통화 픽업 기능을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c6e29-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="c6e29-132">SEFAUtil resource kit 도구의/enablegrouppickup 매개 변수를 사용 하 여 그룹 통화 픽업 기능을 사용 하도록 설정 하 고 사용자에 게 통화 픽업 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6e29-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013에서 사용자의 그룹 통화 픽업 기능을 사용 하도록 설정 하 고 그룹 번호 지정</a></span><span class="sxs-lookup"><span data-stu-id="c6e29-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6e29-134">사용자에 게 할당 된 통화 픽업 번호와 기타 관심 있는 수에 대해 알림</span><span class="sxs-lookup"><span data-stu-id="c6e29-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="c6e29-135">모든 사용자가 그룹 통화 픽업 사용자에 대 한 통화를 검색할 수 있으므로 사용자는 두 개 이상의 그룹을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6e29-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Lync Server 2013에서 사용자에 게 그룹 통화 픽업 배정 전달</a></span><span class="sxs-lookup"><span data-stu-id="c6e29-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6e29-137">그룹 통화 픽업 배포 확인</span><span class="sxs-lookup"><span data-stu-id="c6e29-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="c6e29-138">호출을 배치 하 고 검색 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e29-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6e29-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">) Lync Server 2013에서 그룹 통화 픽업 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="c6e29-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

