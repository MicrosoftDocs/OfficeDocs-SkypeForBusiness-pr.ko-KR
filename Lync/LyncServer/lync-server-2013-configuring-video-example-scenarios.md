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
ms.openlocfilehash: 71eb886bb50f503b43eb757cc41310583fc11303
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="8f67f-102">Lync Server 2013에 대 한 비디오 예제 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="8f67f-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f67f-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8f67f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8f67f-104">Lync 2013는 새로운 비디오 기능을 지원 합니다. 1920 x 1080 full HD (고화질) 비디오 및 갤러리 보기 비디오</span><span class="sxs-lookup"><span data-stu-id="8f67f-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="8f67f-105">고객 데이터를 기반으로 하는 측정값은 일반적인 비디오 대역폭이 Lync 2010에 비해 약간 비해 증가 했지만, 전체 HD 지원으로 인해 최대 비디오 스트림 대역폭이 증가 함 (자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)에서 "미디어 트래픽 네트워크 사용" 섹션을 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="8f67f-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="8f67f-106">따라서 관리자는 특정 사용자 (예: 네트워크 용량이 적은 지점의 사용자)에 대해 비디오 대역폭을 제한 하 고, 다른 사용자에 대해 최상의 가능한 비디오 품질을 유지 하는 데 도움을 받을 수 있습니다 (예: 임원).</span><span class="sxs-lookup"><span data-stu-id="8f67f-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="8f67f-p102">다음 표에는 다양한 네트워크 용량에 대한 권장 비디오 구성 설정 목록이 나와 있습니다. 이러한 설정은 일부 사용자 시나리오에 대한 고해상도 비디오 송/수신을 제한합니다(맨 오른쪽 열 참조). 최소 설정으로 인해 최대 수신 네트워크 대역폭이 낮아지므로 갤러리 비디오를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-p102">The following table provides a list of recommended settings for configuring video for different network capacities. These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column). The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="8f67f-110">권장 비디오 설정</span><span class="sxs-lookup"><span data-stu-id="8f67f-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="8f67f-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="8f67f-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="8f67f-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="8f67f-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="8f67f-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="8f67f-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="8f67f-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="8f67f-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="8f67f-115">표준 화질 비디오에 대한 예상 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="8f67f-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f67f-116">방법은</span><span class="sxs-lookup"><span data-stu-id="8f67f-116">Best</span></span></p></td>
<td><p><span data-ttu-id="8f67f-117">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-117">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-118">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-118">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-119">8000</span><span class="sxs-lookup"><span data-stu-id="8f67f-119">8000</span></span></p></td>
<td><p><span data-ttu-id="8f67f-120">8000</span><span class="sxs-lookup"><span data-stu-id="8f67f-120">8000</span></span></p></td>
<td><p><span data-ttu-id="8f67f-121">피어 투 피어: 최대 1920 x 1080 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="8f67f-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="8f67f-122">갤러리 보기: 최대 1920 x 1080 비디오 두 개 또는 이보다 낮은 해상도의 여러 비디오</span><span class="sxs-lookup"><span data-stu-id="8f67f-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f67f-123">좋습니다</span><span class="sxs-lookup"><span data-stu-id="8f67f-123">Good</span></span></p></td>
<td><p><span data-ttu-id="8f67f-124">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-124">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-125">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-125">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-126">2500</span><span class="sxs-lookup"><span data-stu-id="8f67f-126">2500</span></span></p></td>
<td><p><span data-ttu-id="8f67f-127">2500</span><span class="sxs-lookup"><span data-stu-id="8f67f-127">2500</span></span></p></td>
<td><p><span data-ttu-id="8f67f-128">피어 투 피어: 최대 1280 x 720 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="8f67f-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="8f67f-129">갤러리 보기: 최대 640 x 360 해상도 비디오 5개</span><span class="sxs-lookup"><span data-stu-id="8f67f-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f67f-130">보통</span><span class="sxs-lookup"><span data-stu-id="8f67f-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="8f67f-131">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-131">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-132">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-132">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-133">1000</span><span class="sxs-lookup"><span data-stu-id="8f67f-133">1000</span></span></p></td>
<td><p><span data-ttu-id="8f67f-134">1000</span><span class="sxs-lookup"><span data-stu-id="8f67f-134">1000</span></span></p></td>
<td><p><span data-ttu-id="8f67f-135">피어 투 피어: 최대 960 x 540 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="8f67f-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="8f67f-136">갤러리 보기: 최대 424 x 240 해상도 비디오 5개</span><span class="sxs-lookup"><span data-stu-id="8f67f-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f67f-137">적어도</span><span class="sxs-lookup"><span data-stu-id="8f67f-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="8f67f-138">참</span><span class="sxs-lookup"><span data-stu-id="8f67f-138">True</span></span></p></td>
<td><p><span data-ttu-id="8f67f-139">False</span><span class="sxs-lookup"><span data-stu-id="8f67f-139">False</span></span></p></td>
<td><p><span data-ttu-id="8f67f-140">350</span><span class="sxs-lookup"><span data-stu-id="8f67f-140">350</span></span></p></td>
<td><p><span data-ttu-id="8f67f-141">350</span><span class="sxs-lookup"><span data-stu-id="8f67f-141">350</span></span></p></td>
<td><p><span data-ttu-id="8f67f-142">피어 투 피어: 최대 424 x 240 비디오 해상도</span><span class="sxs-lookup"><span data-stu-id="8f67f-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="8f67f-143">갤러리 보기: 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8f67f-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f67f-144">위의 표의 정보를 사용하여 조직 내 일부 사용자를 위한 새 HD 비디오와 갤러리 보기 비디오 회의 기능을 배포하면서 나머지 사용자에게 다양한 비디오 해상도를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="8f67f-p103">다음 예제에서는 관리자가 중역만 사용할 수 있는 최고 비디오 품질의 새 비디오 기능을 공개합니다. 네트워크 용량이 적은 원격 지점 직원의 경우 위의 표에 나오는 최소 설정만 배포됩니다. 그 밖의 모든 직원에게는 위의 표에 나오는 "표준" 설정이 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-p103">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives. For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed. For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="8f67f-p104">중역에게 새 기능을 공개하기 위해 관리자는 ExecutiveVideo라는 회의 정책을 만듭니다. 이 회의 정책의 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-p104">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="8f67f-150">VideoBitRateKB가 8000Kbps로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="8f67f-151">TotalReceiveVideoBitRateKB가 8000Kbps로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="8f67f-152">AllowMultiview가 True로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="8f67f-153">EnableMultiviewJoin이 True로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="8f67f-p105">관리자는 지점 직원을 위해 BranchOfficeVideo라는 회의 정책을 만듭니다. 이 회의 정책의 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-p105">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="8f67f-156">VideoBitRateKB가 350Kbps로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="8f67f-157">TotalReceiveVideoBitRateKB가 350Kbps로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="8f67f-158">AllowMultiview가 True로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="8f67f-159">EnableMultiviewJoin이 False로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="8f67f-p106">관리자는 그 밖의 모든 직원을 위해 StandardVideo라는 회의 정책을 만듭니다. 이 회의 정책의 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-p106">For all other employees, the administrator creates a conferencing policy named StandardVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="8f67f-162">VideoBitRateKB가 2500Kbps로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="8f67f-163">TotalReceiveVideoBitRateKB가 2500Kbps로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="8f67f-164">AllowMultiview가 True로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="8f67f-165">EnableMultiviewJoin이 True로 설정됨</span><span class="sxs-lookup"><span data-stu-id="8f67f-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="8f67f-166">관리자는 다음과 같이 사용자에게 회의 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="8f67f-167">ExecutiveVideo 회의 정책은 중역에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="8f67f-168">BranchOfficeVideo 회의 정책은 지점의 모든 직원에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="8f67f-169">StandardVideo 회의 정책은 그 밖의 모든 직원에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="8f67f-170">이러한 회의 정책 할당에 따라 다음과 같은 사용자 환경이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="8f67f-171">사용자에 의해 구성된 모든 회의에서 갤러리 보기를 지원하지만, 지점의 직원은 갤러리 보기를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="8f67f-172">두 사용자 간 회의 또는 단체 회의에서 중역은 자신의 하드웨어 및 네트워크 링크에서 지원할 경우 1920 x 1080 Full HD 비디오를 전송할 수 있으며, 다른 참여자 클라이언트에서 지원할 경우 1920 x 1080 Full HD 비디오를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="8f67f-173">중역 이외의 직원은 두 사용자 간 회의 또는 단체 회의에서 중역보다 낮은 표준 화질의 해상도를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="8f67f-174">Lync에서 기본 비디오 창 크기를 표시 하는 경우 지사에 거주 하는 직원이 두 명의 사용자에 게 좋은 화질을 얻게 됩니다. 그러나 Lync 창이 전체 화면으로 최대화 되 면 비디오 해상도가 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="8f67f-175">단체 전화 회의의 경우 지사의 직원에 게는 하나의 활성 비디오만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f67f-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

