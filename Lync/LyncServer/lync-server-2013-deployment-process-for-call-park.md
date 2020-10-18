---
title: 'Lync Server 2013: 통화 대기에 대 한 배포 프로세스'
description: 'Lync Server 2013: 통화 대기에 대 한 배포 프로세스'
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
ms.openlocfilehash: 149252d39ba3fc0c552900c87e453c60e1651a08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575714"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="8e381-103">Lync Server 2013의 통화 대기 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="8e381-103">Deployment process for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e381-104">_**마지막으로 수정 된 항목:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="8e381-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="8e381-105">이 섹션에서는 통화 대기 응용 프로그램을 배포 하는 과정에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-105">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="8e381-106">통화 대기를 구성 하기 전에 enterprise Edition 또는 Standard Edition을 Enterprise Voice로 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="8e381-107">통화 대기에 필요한 구성 요소는 Enterprise Voice를 배포할 때 설치 및 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-107">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="8e381-108">통화 대기 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="8e381-108">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e381-109">단계</span><span class="sxs-lookup"><span data-stu-id="8e381-109">Phase</span></span></th>
<th><span data-ttu-id="8e381-110">단계</span><span class="sxs-lookup"><span data-stu-id="8e381-110">Steps</span></span></th>
<th><span data-ttu-id="8e381-111">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="8e381-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="8e381-112">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="8e381-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e381-113">파킹된 통화 번호 표에서 통화 대기 파킹된 통화 번호 범위 구성</span><span class="sxs-lookup"><span data-stu-id="8e381-113">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="8e381-114">Lync Server 제어판 또는 <strong>get-cscallparkorbit</strong> cmdlet을 사용 하 여 통화 대기 궤도 테이블에 궤도 범위를 만들고 통화 대기 응용 프로그램을 호스트 하는 응용 프로그램 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-114">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8e381-p102">기존 다이얼 플랜과 원활하게 통합할 수 있도록, 파킹된 통화 번호 범위는 일반적으로 가상 내선 번호 블록으로 구성됩니다. DID(Direct Inward Dialing) 번호를 통화 대기 파킹된 통화 번호 표에서 파킹된 통화 번호로 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="8e381-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e381-117">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8e381-118">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-118">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8e381-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-119">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8e381-120">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-120">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e381-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정</a></span><span class="sxs-lookup"><span data-stu-id="8e381-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e381-122">통화 파킹 설정 구성</span><span class="sxs-lookup"><span data-stu-id="8e381-122">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="8e381-123"><strong>New-cscpsconfiguration</strong> cmdlet을 사용 하 여 통화 대기 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-123">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="8e381-124">최소 대기 통화 시간이 초과 될 때 사용할 대체 대상을 구성 하려면 <strong>Ontimeouturi</strong> 옵션을 구성 하는 것이 좋습니다. 또한 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-124">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e381-125">(선택 사항) <strong>EnableMusicOnHold</strong> - 대기 음악을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-125">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="8e381-126">(선택 사항) <strong>MaxCallPickupAttempts</strong> - 대기된 통화를 대체 URI(Uniform Resource Identifier)로 착신 전환할 때까지 해당 통화가 전화기에서 다시 울리는 횟수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-126">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="8e381-127">(선택 사항) <strong>CallPickupTimeoutThreshold</strong> - 통화가 대기된 후부터 전화를 받은 전화기가 다시 울릴 때까지의 경과 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-127">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e381-128">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e381-128">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8e381-129">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-129">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8e381-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-130">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8e381-131">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-131">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e381-132"><a href="lync-server-2013-configure-call-park-settings.md">Lync Server 2013의 통화 대기 설정 구성</a></span><span class="sxs-lookup"><span data-stu-id="8e381-132"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e381-133">원하는 경우 대기 음악을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-133">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="8e381-134"><strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet을 사용하여 오디오 파일을 사용자 지정하고 업로드합니다(기본 대기 음악을 사용하지 않으려는 경우)</span><span class="sxs-lookup"><span data-stu-id="8e381-134">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="8e381-135">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e381-135">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8e381-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-136">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8e381-137">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-137">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8e381-138">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-138">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e381-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Lync Server 2013에서 통화 대기 음악 사용자 지정</a></span><span class="sxs-lookup"><span data-stu-id="8e381-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e381-140">사용자에 대해 통화 대기를 사용 하도록 음성 정책 구성</span><span class="sxs-lookup"><span data-stu-id="8e381-140">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="8e381-141">음성 정책의 사용자에 대해 통화 대기를 사용 하도록 설정 하려면 Lync Server 제어판 또는 <strong>EnableCallPark</strong> 옵션을 가진 <strong>set-csvoicepolicy</strong> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-141">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8e381-142">기본적으로 모든 사용자에 대해 통화 대기를 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-142">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="8e381-143">음성 정책이 여러 개인 경우에는 기본 정책뿐 아니라 각 음성 정책에 대해 EnableCallPark 속성이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-143">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="8e381-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e381-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8e381-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8e381-146">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-146">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="8e381-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e381-148"><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013의 사용자에 대해 통화 대기를 사용 하도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="8e381-148"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e381-149">통화 파킹에 대한 정규화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="8e381-149">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="8e381-p104">통화 대기 파킹된 통화 번호는 정규화해서는 안 됩니다. 정규화 규칙에 파킹된 통화 번호 범위가 포함되어 있지 않은지 확인하고, 필요한 경우에는 파킹된 통화 번호가 정규화되지 않도록 추가 정규화 규칙을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="8e381-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="8e381-153">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e381-153">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8e381-154">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-154">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8e381-155">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-155">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8e381-156">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e381-156">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e381-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013의 통화 대기에 대 한 정규화 규칙 확인</a></span><span class="sxs-lookup"><span data-stu-id="8e381-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e381-158">통화 대기 배포 확인</span><span class="sxs-lookup"><span data-stu-id="8e381-158">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="8e381-159">파킹 및 통화 검색을 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e381-159">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8e381-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">반드시 Lync Server 2013의 통화 대기 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="8e381-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

