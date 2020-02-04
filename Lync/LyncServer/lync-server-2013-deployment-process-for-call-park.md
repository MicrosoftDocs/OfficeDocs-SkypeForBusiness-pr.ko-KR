---
title: 'Lync Server 2013: 통화 파킹에 대 한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="b2d48-102">Lync Server 2013의 통화 공원 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="b2d48-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2d48-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="b2d48-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="b2d48-104">이 섹션에서는 통화 공원 응용 프로그램 배포 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="b2d48-105">통화 공원를 구성 하기 전에 엔터프라이즈 음성을 사용 하 여 Enterprise Edition 또는 Standard Edition을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="b2d48-106">통화 공원에 필요한 구성 요소는 엔터프라이즈 음성을 구축할 때 설치 되 고 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="b2d48-107">통화 파킹 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="b2d48-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2d48-108">단계의</span><span class="sxs-lookup"><span data-stu-id="b2d48-108">Phase</span></span></th>
<th><span data-ttu-id="b2d48-109">방법은</span><span class="sxs-lookup"><span data-stu-id="b2d48-109">Steps</span></span></th>
<th><span data-ttu-id="b2d48-110">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="b2d48-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="b2d48-111">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="b2d48-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2d48-112">궤도 테이블에서 통화 공원 궤도 범위 구성</span><span class="sxs-lookup"><span data-stu-id="b2d48-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="b2d48-113">Lync Server 제어판 또는 <strong>CSCallParkOrbit</strong> cmdlet을 사용 하 여 통화 공원에 궤도 범위를 만들고 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b2d48-114">기존 다이얼 플랜을 완벽 하 게 통합 하기 위해 일반적으로 궤도 범위는 가상 확장 블록으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-114">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="b2d48-115">직접 연결 된 전화 접속 (연결) 번호를 통화 공원 궤도 테이블의 궤도 번호로 지정 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="b2d48-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b2d48-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b2d48-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b2d48-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Lync Server 2013에서 통화 공원 궤도 범위 만들기 또는 수정</a></span><span class="sxs-lookup"><span data-stu-id="b2d48-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2d48-121">통화 파킹 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b2d48-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="b2d48-122"><strong>CsCpsConfiguration</strong> cmdlet을 사용 하 여 통화 공원 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="b2d48-123">적어도 파킹 된 통화 시간 초과 시 사용할 대체 대상을 구성 하려면 <strong>Ontimeouturi</strong> 옵션을 구성 하는 것이 좋습니다. 다음 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2d48-124">) <strong>Enablemusiconhold</strong> 대기 음악을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="b2d48-125">) <strong>MaxCallPickupAttempts</strong> 호출을 URI (Fallback Uniform resource Identifier)로 전달 하기 전에 파킹 된 통화가 응답 전화로 다시 연결 하는 횟수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="b2d48-126">) 통화에 응답 한 전화기로 전화를 <strong>CallPickupTimeoutThreshold</strong> 전에 대기 하는 시간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b2d48-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b2d48-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b2d48-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b2d48-131"><a href="lync-server-2013-configure-call-park-settings.md">Lync Server 2013에서 통화 공원 설정 구성</a></span><span class="sxs-lookup"><span data-stu-id="b2d48-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2d48-132">선택적으로 음악을 보류할 때 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b2d48-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="b2d48-133">기본 음악을 누르고 싶지 않은 경우 <strong>CsCallParkServiceMusicOnHoldFile</strong> cmdlet을 사용 하 여 오디오 파일을 사용자 지정 하 고 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="b2d48-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b2d48-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b2d48-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b2d48-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Lync Server 2013에서 통화 공원 음악을 보류할 때 사용자 지정</a></span><span class="sxs-lookup"><span data-stu-id="b2d48-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2d48-139">사용자에 게 전화를 걸 수 있도록 음성 정책 구성</span><span class="sxs-lookup"><span data-stu-id="b2d48-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="b2d48-140">Lync Server 제어판 또는 <strong>EnableCallPark</strong> 옵션과 함께 <strong>CSVoicePolicy</strong> cmdlet을 사용 하 여 음성 정책 사용자에 대 한 통화 대기를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b2d48-141">기본적으로 모든 사용자에 대해 통화 대기를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="b2d48-142">여러 음성 정책을 사용 하는 경우 기본 정책만이 아니라 각 음성 정책에 대해 EnableCallPark 속성이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="b2d48-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b2d48-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b2d48-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b2d48-147"><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013에서 사용자 용 통화 공원 사용</a></span><span class="sxs-lookup"><span data-stu-id="b2d48-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2d48-148">통화 대기에 대한 정규화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="b2d48-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="b2d48-149">통화 공원 orbits는 정규화 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-149">Call park orbits must not be normalized.</span></span> <span data-ttu-id="b2d48-150">정규화 규칙에 궤도 범위 중 어느 것도 포함 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-150">Verify that your normalization rules do not include any of your orbit ranges.</span></span> <span data-ttu-id="b2d48-151">필요한 경우 orbits의 정규화를 방지 하는 추가 정규화 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-151">If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="b2d48-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b2d48-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b2d48-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b2d48-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b2d48-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b2d48-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013에서 통화 공원에 대 한 정규화 규칙 확인</a></span><span class="sxs-lookup"><span data-stu-id="b2d48-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2d48-157">통화 공원 배포 확인</span><span class="sxs-lookup"><span data-stu-id="b2d48-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="b2d48-158">주차장 및 통화 검색을 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d48-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="b2d48-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">) Lync Server 2013에서 통화 공원 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="b2d48-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

