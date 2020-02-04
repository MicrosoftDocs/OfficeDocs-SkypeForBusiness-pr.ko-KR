---
title: 'Lync Server 2013: 비디오 예제 시나리오 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="fa5ec-102">Lync Server 2013에 대 한 비디오 구성 예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="fa5ec-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa5ec-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fa5ec-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fa5ec-104">Lync 2013는 1920 x 1080 full 고화질 (HD) 비디오 및 갤러리 보기 비디오를 지원 하기 위해 새로운 비디오 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="fa5ec-105">고객 데이터를 기반으로 하는 측정값은 일반적인 비디오 대역폭이 Lync 2010에 비해 약간만 증가 했지만 전체 HD 지원으로 인해 최대 비디오 스트림 대역폭이 증가 함 (자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)"미디어 트래픽 네트워크 사용량" 섹션을 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="fa5ec-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="fa5ec-106">따라서 관리자는 특정 사용자 (예: 네트워크 용량이 적은 지점의 사용자)에 대 한 비디오 대역폭을 제한 하 고 다른 사용자에 게 최상의 화질 (예: 임원)을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="fa5ec-107">다음 표에서는 다양 한 네트워크 용량에 대해 비디오를 구성 하기 위한 권장 설정 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="fa5ec-108">이러한 설정은 일부 사용자 시나리오가 더 높은 해상도 동영상을 보내고 받지 못하도록 제한 합니다 (맨 오른쪽 열 참조).</span><span class="sxs-lookup"><span data-stu-id="fa5ec-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="fa5ec-109">최소 설정으로 인해 최대 수신 네트워크 대역폭 때문에 갤러리 비디오를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="fa5ec-110">권장 되는 비디오 설정</span><span class="sxs-lookup"><span data-stu-id="fa5ec-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="fa5ec-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="fa5ec-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="fa5ec-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="fa5ec-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="fa5ec-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="fa5ec-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="fa5ec-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="fa5ec-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="fa5ec-115">우수한 품질의 동영상을 위한 비디오 해상도가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa5ec-116">방법은</span><span class="sxs-lookup"><span data-stu-id="fa5ec-116">Best</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-117">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-117">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-118">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-118">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-119">8000</span><span class="sxs-lookup"><span data-stu-id="fa5ec-119">8000</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-120">8000</span><span class="sxs-lookup"><span data-stu-id="fa5ec-120">8000</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-121">피어 투 피어: 최대 1920 x 1080 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="fa5ec-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="fa5ec-122">갤러리 보기: 최대 2 1920 x 1080 비디오 또는 여러 개의 작은 해상도 비디오</span><span class="sxs-lookup"><span data-stu-id="fa5ec-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa5ec-123">적합</span><span class="sxs-lookup"><span data-stu-id="fa5ec-123">Good</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-124">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-124">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-125">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-125">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-126">2500</span><span class="sxs-lookup"><span data-stu-id="fa5ec-126">2500</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-127">2500</span><span class="sxs-lookup"><span data-stu-id="fa5ec-127">2500</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-128">피어 투 피어: 최대 1280 x 720 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="fa5ec-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="fa5ec-129">갤러리 보기: 최대 5 640 x 360 해상도 비디오</span><span class="sxs-lookup"><span data-stu-id="fa5ec-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa5ec-130">높음이나</span><span class="sxs-lookup"><span data-stu-id="fa5ec-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-131">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-131">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-132">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-132">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-133">1000</span><span class="sxs-lookup"><span data-stu-id="fa5ec-133">1000</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-134">1000</span><span class="sxs-lookup"><span data-stu-id="fa5ec-134">1000</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-135">피어 투 피어: 최대 960 x 540 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="fa5ec-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="fa5ec-136">갤러리 보기: 최대 5 424 x 240 해상도 비디오</span><span class="sxs-lookup"><span data-stu-id="fa5ec-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa5ec-137">솟</span><span class="sxs-lookup"><span data-stu-id="fa5ec-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-138">False</span><span class="sxs-lookup"><span data-stu-id="fa5ec-138">True</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-139">해제</span><span class="sxs-lookup"><span data-stu-id="fa5ec-139">False</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-140">350</span><span class="sxs-lookup"><span data-stu-id="fa5ec-140">350</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-141">350</span><span class="sxs-lookup"><span data-stu-id="fa5ec-141">350</span></span></p></td>
<td><p><span data-ttu-id="fa5ec-142">피어 투 피어: 최대 424 x 240 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="fa5ec-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="fa5ec-143">갤러리 보기: 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="fa5ec-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa5ec-144">위의 표에 나와 있는 정보를 사용 하 여 조직의 일부 사용자에 대 한 새 HD 비디오 및 갤러리 보기 비디오 회의 기능을 배포 하는 동시에 다른 사용자에 대 한 비디오 해상도를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="fa5ec-145">다음 예제에서는 관리자가 최고 화질으로 경영진만 사용할 수 있는 새로운 비디오 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="fa5ec-146">네트워크 용량이 낮은 원격 지점 사무실의 경우에는 앞 테이블의 최소 설정만 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="fa5ec-147">다른 모든 직원의 경우 앞의 표에 나와 있는 "좋은" 설정이 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="fa5ec-148">관리자가 경영진에 게 새 기능을 배포 하기 위해 ExecutiveVideo 이라는 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="fa5ec-149">이 회의 정책에는 다음과 같은 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="fa5ec-150">VideoBitRateKB는 8000 Kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="fa5ec-151">TotalReceiveVideoBitRateKB는 8000 Kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="fa5ec-152">AllowMultiview가 True로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="fa5ec-153">EnableMultiviewJoin가 True로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="fa5ec-154">지사의 직원의 경우 관리자가 BranchOfficeVideo 이라는 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="fa5ec-155">이 회의 정책에는 다음과 같은 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="fa5ec-156">VideoBitRateKB는 350 Kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="fa5ec-157">TotalReceiveVideoBitRateKB는 350 Kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="fa5ec-158">AllowMultiview가 True로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="fa5ec-159">EnableMultiviewJoin가 False로 설정 됨</span><span class="sxs-lookup"><span data-stu-id="fa5ec-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="fa5ec-160">다른 모든 직원의 경우 관리자가 StandardVideo 라는 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="fa5ec-161">이 회의 정책에는 다음과 같은 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="fa5ec-162">VideoBitRateKB는 2500 Kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="fa5ec-163">TotalReceiveVideoBitRateKB는 2500 Kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="fa5ec-164">AllowMultiview가 True로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="fa5ec-165">EnableMultiviewJoin가 True로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="fa5ec-166">관리자가 사용자에 게 다음과 같이 회의 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="fa5ec-167">ExecutiveVideo 회의 정책은 경영진에 게 배정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="fa5ec-168">BranchOfficeVideo 회의 정책은 지사에 있는 모든 직원에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="fa5ec-169">StandardVideo 회의 정책은 다른 모든 직원에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="fa5ec-170">이러한 회의 정책 할당을 통해 다음 사용자 환경이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="fa5ec-171">모든 사용자 지원 갤러리 보기를 사용 하 여 구성 되었지만 지점에 있는 직원이 갤러리 보기를 경험해 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="fa5ec-172">2-파티 또는 단체 회의의 경우, 해당 하드웨어와 네트워크 링크가 지 원하는 경우 1920 x 1080 full HD 비디오를 보낼 수 있으며, 다른 참가자 클라이언트가이를 지 원하는 경우 1920 x 1080 full HD 비디오를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="fa5ec-173">임원을 보유 하 고 있지 않은 직원은 2 자 또는 단체 회의에서 경영진 보다 저렴 한 해상도를 경험할 수 있지만 좋은 해상도를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="fa5ec-174">Lync에서 기본 비디오 창 크기를 표시할 때 지사에 거주 하는 직원이 두 대의 영상 품질을 잘 알 수 있습니다. 그러나 Lync 창이 전체 화면으로 최대화 되어 있으면 비디오 해상도가 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="fa5ec-175">단체 컨퍼런스의 경우 지사에 있는 직원이 하나의 활성 비디오만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

