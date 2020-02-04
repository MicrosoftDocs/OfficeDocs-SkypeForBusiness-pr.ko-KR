---
title: 'Lync Server 2013: 장치 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc453ca1e83d8077e67ef130ef7a83e03c138be2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="142bf-102">Lync Server 2013의 장치 보고서</span><span class="sxs-lookup"><span data-stu-id="142bf-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="142bf-103">_**마지막으로 수정한 주제:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="142bf-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="142bf-104">디바이스 보고서가 마이크와 스피커 보고서 라는 제목의 더 좋을 수 있습니다. 이는 장치 보고서가 통화에 사용 되는 마이크와 스피커로 그룹화 된 통화 관련 메트릭 (불량 통화 백분율, 에코, 음성 전환 시간 등)을 검색 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="142bf-105">IP 전화 ("장치" 라고도 함)에 관심이 있는 경우에는 [Lync Server 2013에서 Ip 전화 인벤토리 보고서](lync-server-2013-ip-phone-inventory-report.md) 를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="142bf-106">장치 보고서는 특정 유형의 장치가 다른 장치 보다 낮은 품질의 통화를 많이 겪고 있는지 확인 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-106">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="142bf-107">이렇게 하면 새 장치를 구입 하거나 기존 장치를 교체할 때 수행 해야 하는 모든 의사 결정에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-107">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="142bf-108">기본적으로 장치 보고서에 표시 되는 정보는 마이크 (캡처 디바이스) 및 통화에 사용 된 스피커/헤드셋 (렌더링 장치)에도 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-108">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="142bf-109">예를 들어 다음과 같은 캡처 장치를 사용 하는 여러 사용자와 다음 렌더링 장치를 가정 합니다. 기본적으로 장치 보고서에 표시 되는 정보는 마이크 (캡처 디바이스) 및 통화에 사용 된 스피커/헤드셋 (렌더링 장치)에도 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-109">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="142bf-110">예를 들어 다음과 같은 캡처 장치 및 렌더링 장치를 사용 하는 여러 사용자가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-110">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="142bf-111">장치 캡처--마이크 (SoundMAX 통합 디지털 HD 오디오)</span><span class="sxs-lookup"><span data-stu-id="142bf-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="142bf-112">장치 렌더링--헤드셋의 휴대 전화 (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="142bf-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="142bf-113">해당 사용자가 총 254 통화를 한 경우 보고서에 다음과 같은 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="142bf-114">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-114">Capture device</span></span></th>
<th><span data-ttu-id="142bf-115">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-115">Render device</span></span></th>
<th><span data-ttu-id="142bf-116">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="142bf-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="142bf-117">마이크 (SoundMAX 통합 디지털 HD 오디오)</span><span class="sxs-lookup"><span data-stu-id="142bf-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="142bf-118">헤드셋의 휴대 전화 (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="142bf-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="142bf-119">254</span><span class="sxs-lookup"><span data-stu-id="142bf-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="142bf-120">이제 동일한 캡처 장치를 사용 하지만 렌더링 장치가 다른 여러 사용자가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-120">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="142bf-121">이 경우 캡처 장치 및 렌더 장치의 고유한 조합에 대 한 두 번째 줄 입력이 보고서에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-121">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="142bf-122">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-122">Capture device</span></span></th>
<th><span data-ttu-id="142bf-123">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-123">Render device</span></span></th>
<th><span data-ttu-id="142bf-124">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="142bf-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="142bf-125">마이크 (SoundMAX 통합 디지털 HD 오디오)</span><span class="sxs-lookup"><span data-stu-id="142bf-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="142bf-126">헤드셋의 휴대 전화 (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="142bf-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="142bf-127">254</span><span class="sxs-lookup"><span data-stu-id="142bf-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-128">마이크 (SoundMAX 통합 디지털 HD 오디오)</span><span class="sxs-lookup"><span data-stu-id="142bf-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="142bf-129">스피커 (SoundMAX 통합 디지털 HD 오디오)</span><span class="sxs-lookup"><span data-stu-id="142bf-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="142bf-130">319</span><span class="sxs-lookup"><span data-stu-id="142bf-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="142bf-131">지정 된 장치에 대해 총 합계가 표시 되는 경우 (예: 사용 하는 렌더링 장치에 상관 없이 SoundMAX 캡처 장치) 장치 유형 드롭다운 목록에서 적절 한 옵션을 선택 합니다 (캡처 장치 또는 렌더 장치).</span><span class="sxs-lookup"><span data-stu-id="142bf-131">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="142bf-132">이 예제에서 장치 캡처를 선택 하면 다음과 유사한 출력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-132">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="142bf-133">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-133">Capture device</span></span></th>
<th><span data-ttu-id="142bf-134">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="142bf-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="142bf-135">마이크 (SoundMAX 통합 디지털 HD 오디오)</span><span class="sxs-lookup"><span data-stu-id="142bf-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="142bf-136">573</span><span class="sxs-lookup"><span data-stu-id="142bf-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="142bf-137">장치 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="142bf-137">Accessing the Device Report</span></span>

<span data-ttu-id="142bf-138">일반적으로 장치 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="142bf-139">그러나 [Lync Server 2013에서 통화 정보 보고서](lync-server-2013-call-detail-report.md) 를 보고 있는 경우 다음 메트릭 중 하나를 클릭 하 여 특정 장치에 대 한 장치 보고서로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="142bf-140">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-140">Capture Device</span></span>

  - <span data-ttu-id="142bf-141">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-141">Render Device</span></span>

<span data-ttu-id="142bf-142">장치 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="142bf-143">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="142bf-143">Call volume</span></span>

  - <span data-ttu-id="142bf-144">통화 불량 백분율</span><span class="sxs-lookup"><span data-stu-id="142bf-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="142bf-145">장치 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="142bf-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="142bf-146">장치 이름에 대 한 자세한 내용은 장치 보고서에 자세히 설명 되어 있습니다. 예를 들어 다음과 같은 캡처 장치가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="142bf-147">Aastra 3002 마이크 (2-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="142bf-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="142bf-148">Aastra 3002 마이크 (3-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="142bf-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="142bf-149">Aastra 3002 마이크 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="142bf-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="142bf-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="142bf-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="142bf-151">Aastra 6725ip 마이크 (10-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-152">Aastra 6725ip 마이크 (10-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="142bf-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="142bf-153">Aastra 6725ip 마이크 (2-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-154">Aastra 6725ip 마이크 (3-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-155">Aastra 6725ip 마이크 (4-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-156">Aastra 6725ip 마이크 (5-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-157">Aastra 6725ip 마이크 (6-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-158">Aastra 6725ip 마이크 (7-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-159">Aastra 6725ip 마이크 (9-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-160">Aastra 6725ip 마이크 (9-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="142bf-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="142bf-161">Aastra 6725ip 마이크 (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="142bf-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="142bf-162">Aastra 6725ip 마이크 (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="142bf-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="142bf-163">Aastra 6725ip 마이크 (USB 오디오 장치)</span><span class="sxs-lookup"><span data-stu-id="142bf-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="142bf-164">Aastra 6725ip 마이크 (USB 오디오 장치)-V0</span><span class="sxs-lookup"><span data-stu-id="142bf-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="142bf-165">Lync Server 2013의 번역 된 버전을 실행 하는 경우 캡처 장치 이름이 동일 하지 않을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="142bf-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="142bf-166">미국 영어에서 Aastra 6725ip 마이크 (Aastra 6725ip)-V0 이라는 장치는 프랑스어 또는 스페인어의 다른 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="142bf-167">해당 수준에 대 한 자세한 정보를 알고 싶은 경우가 있습니다. 그러나 다른 시간에는 모델 번호에 관계 없이 Aastra 마이크를 사용 하는 통화의 수에만 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="142bf-168">이와 같은 정보를 얻으려면 Microsoft Excel로 장치 보고서 데이터를 내보낸 다음 해당 데이터를 쉼표로 구분 된 값 파일 (예: C:\\data\\Devices\_Report. m a m)에 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="142bf-169">그런 다음 다음과 비슷한 명령 집합을 사용 하 여를 가져올 수 있습니다. CSV 파일을 Windows PowerShell에 표시 하 고 Aastra 캡처 장치를 사용 하 여 생성 된 총 통화 수를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="142bf-170">그러면 Aastra 캡처 장치를 사용 하 여 만든 총 통화 수를 나타내는 single 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="142bf-171">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="142bf-172">필터가</span><span class="sxs-lookup"><span data-stu-id="142bf-172">Filters</span></span>

<span data-ttu-id="142bf-173">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="142bf-174">예를 들어 장치 보고서를 사용 하 여 통화 유형 (즉, 클라이언트 전화 통화), 컨퍼런스 통화 또는 PSTN (공공 전환 전화 네트워크) 통화 등의 항목을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="142bf-175">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="142bf-176">이 경우 장치는 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="142bf-177">다음 표에는 장치 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="142bf-178">장치 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="142bf-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="142bf-179">이름</span><span class="sxs-lookup"><span data-stu-id="142bf-179">Name</span></span></th>
<th><span data-ttu-id="142bf-180">설명</span><span class="sxs-lookup"><span data-stu-id="142bf-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="142bf-181"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-182">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-182">Start date/time for the time range.</span></span> <span data-ttu-id="142bf-183">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-183">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="142bf-184">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="142bf-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="142bf-185">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-185">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="142bf-186">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-186">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="142bf-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="142bf-187">7/7/2012</span></span></p>
<p><span data-ttu-id="142bf-188">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="142bf-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="142bf-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="142bf-189">7/3/2012</span></span></p>
<p><span data-ttu-id="142bf-190">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-191"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-192">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-192">End date/time for the time range.</span></span> <span data-ttu-id="142bf-193">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-193">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="142bf-194">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="142bf-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="142bf-195">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-195">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="142bf-196">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-196">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="142bf-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="142bf-197">7/7/2012</span></span></p>
<p><span data-ttu-id="142bf-198">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="142bf-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="142bf-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="142bf-199">7/3/2012</span></span></p>
<p><span data-ttu-id="142bf-200">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-201"><strong>음성 스위치 원인</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-202">에코를 방지 하기 위해 통화를 반이중 모드로 전환 해야 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="142bf-203">반이중 모드에서는 통신을 한 번에 한 방향 으로만 이동할 수 있으며, walkie-talkie와 통신 하는 경우에도 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="142bf-204">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-205">모든</span><span class="sxs-lookup"><span data-stu-id="142bf-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-206">없음</span><span class="sxs-lookup"><span data-stu-id="142bf-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-207">잘못 된 타임 스탬프</span><span class="sxs-lookup"><span data-stu-id="142bf-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-208">O</span><span class="sxs-lookup"><span data-stu-id="142bf-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-209">DNLP (동적 비선형 프로세서)</span><span class="sxs-lookup"><span data-stu-id="142bf-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-210">낮은 복잡도</span><span class="sxs-lookup"><span data-stu-id="142bf-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-211">잘못 된 장치 상태</span><span class="sxs-lookup"><span data-stu-id="142bf-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-212">AEC 이후 에코 (음향 반향 제거)</span><span class="sxs-lookup"><span data-stu-id="142bf-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-213"><strong>에코 원인</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-214">통화 중에 허용 된 수준 위의 반향을 감지 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="142bf-215">(텔레커뮤니케이션에서 echo는 소리를 반사 하는 것으로, 잘 아래쪽으로 yell 때 들릴 수 있는 것과 같은 현상을 말합니다.) 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-216">모든</span><span class="sxs-lookup"><span data-stu-id="142bf-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-217">없음</span><span class="sxs-lookup"><span data-stu-id="142bf-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-218">잘못 된 타임 스탬프</span><span class="sxs-lookup"><span data-stu-id="142bf-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-219">AEC 이후 에코 (음향 반향 제거)</span><span class="sxs-lookup"><span data-stu-id="142bf-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-220">ANLP (적응 비선형 프로세서)</span><span class="sxs-lookup"><span data-stu-id="142bf-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-221">DNLP (동적 비선형 프로세서)</span><span class="sxs-lookup"><span data-stu-id="142bf-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-222">마이크 클리핑</span><span class="sxs-lookup"><span data-stu-id="142bf-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-223"><strong>통화 종류</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-224">발생 한 통화 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="142bf-225">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-226">모든</span><span class="sxs-lookup"><span data-stu-id="142bf-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-227">클라이언트 통화</span><span class="sxs-lookup"><span data-stu-id="142bf-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-228">PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="142bf-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-229">컨퍼런스 통화</span><span class="sxs-lookup"><span data-stu-id="142bf-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-230"><strong>Access 형식</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-231">전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-231">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="142bf-232">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-232">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-233">모든</span><span class="sxs-lookup"><span data-stu-id="142bf-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-234">내부용</span><span class="sxs-lookup"><span data-stu-id="142bf-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-235">내부</span><span class="sxs-lookup"><span data-stu-id="142bf-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-236"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-237">전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-237">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="142bf-238">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-238">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-239">모든</span><span class="sxs-lookup"><span data-stu-id="142bf-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-240">유</span><span class="sxs-lookup"><span data-stu-id="142bf-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-241">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="142bf-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-243">통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-243">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="142bf-244">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-244">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-245">모든</span><span class="sxs-lookup"><span data-stu-id="142bf-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-246">VPN</span><span class="sxs-lookup"><span data-stu-id="142bf-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-247">비 VPN</span><span class="sxs-lookup"><span data-stu-id="142bf-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-248"><strong>장치 유형</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-249">장치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-249">Indicates the type of device.</span></span> <span data-ttu-id="142bf-250">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-251">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-252">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="142bf-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="142bf-253">장치 쌍 캡처/렌더링</span><span class="sxs-lookup"><span data-stu-id="142bf-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-254"><strong>장치 이름</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-255">캡처 또는 렌더링 디바이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-255">Name of the capture or render device.</span></span> <span data-ttu-id="142bf-256">전체 장치 이름 또는 장치 이름의 일부를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="142bf-257">예를 들어 디바이스 마이크 (Microsoft LifeCam VX-1000)를 찾으려면 다음과 같이 전체 장치 이름을 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="142bf-258">마이크 (Microsoft LifeCam VX-1000)</span><span class="sxs-lookup"><span data-stu-id="142bf-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="142bf-259">또는 이름의 일부만 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="142bf-260">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-260">For example:</span></span></p>
<p><span data-ttu-id="142bf-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="142bf-261">LifeCam</span></span></p>
<p><span data-ttu-id="142bf-262">위의 필터는 이름에 LifeCam &quot;&quot; 문자열을 포함 하는 모든 장치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="142bf-263">매트릭스</span><span class="sxs-lookup"><span data-stu-id="142bf-263">Metrics</span></span>

<span data-ttu-id="142bf-264">다음 표에는 장치 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="142bf-265">장치 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="142bf-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="142bf-266">이름</span><span class="sxs-lookup"><span data-stu-id="142bf-266">Name</span></span></th>
<th><span data-ttu-id="142bf-267">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="142bf-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="142bf-268">설명</span><span class="sxs-lookup"><span data-stu-id="142bf-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="142bf-269"><strong>캡처 장치</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-270">예</span><span class="sxs-lookup"><span data-stu-id="142bf-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-271">오디오를 전송 하는 데 사용 되는 장치 (예: 마이크 또는 웹캠)</span><span class="sxs-lookup"><span data-stu-id="142bf-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-272"><strong>렌더링 장치</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-273">예</span><span class="sxs-lookup"><span data-stu-id="142bf-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-274">오디오를 수신 하는 데 사용 되는 장치 (예: 헤드셋 또는 스피커)</span><span class="sxs-lookup"><span data-stu-id="142bf-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-275"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-276">예</span><span class="sxs-lookup"><span data-stu-id="142bf-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-277">총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-278"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-279">예</span><span class="sxs-lookup"><span data-stu-id="142bf-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-280">불량으로 &quot;분류 된 통화의 백분율입니다. &quot; 잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-281"><strong>고유 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-282">예</span><span class="sxs-lookup"><span data-stu-id="142bf-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-283">장치를 사용 하는 고유한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-283">Unique users who used the device.</span></span> <span data-ttu-id="142bf-284">사용자가 장치를 13 번 사용 하는 경우 한 명의 고유 사용자로 서 한 번만 장치를 사용 하는 사용자와 동일 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-285"><strong>음성 전환 시간 비율</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-286">예</span><span class="sxs-lookup"><span data-stu-id="142bf-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-287">에코를 방지 하기 위해 반이중 모드에서 수행 해야 하는 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="142bf-288">반이중 모드에서는 통신을 한 번에 한 방향 으로만 이동할 수 있으며, walkie-talkie와 통신 하는 경우에도 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-289"><strong>마이크 작동 하지 않는 비율</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-290">예</span><span class="sxs-lookup"><span data-stu-id="142bf-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-291">캡처 장치가 허용 되는 수준에서 작동 하지 않는 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="142bf-292">값이 높으면 특히 캡처 장치가 정상적으로 작동 하지 않기 때문에 통화의 품질 문제가 발생 하는 것을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-293"><strong>스피커 작동 하지 않는 비율</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-294">예</span><span class="sxs-lookup"><span data-stu-id="142bf-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-295">렌더링 장치가 허용 되는 수준에서 작동 하지 않는 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="142bf-296">값이 높으면 특히 렌더링 장치가 정상적으로 작동 하지 않기 때문에 통화의 품질 문제가 발생 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-297"><strong>음성 스위치가 있는 통화 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-298">예</span><span class="sxs-lookup"><span data-stu-id="142bf-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-299">반이중 모드에 배치 해야 했던 총 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="142bf-300">반이중 모드에서는 통신을 한 번에 한 방향 으로만 이동할 수 있으며, walkie-talkie와 통신 하는 경우에도 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-301"><strong>(%)에 에코 마이크</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-302">예</span><span class="sxs-lookup"><span data-stu-id="142bf-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-303">마이크 캡처 스트림에 화면 표시가 감지 된 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="142bf-304">일반적으로 헤드셋 이나 송수화기의 경우 값은 낮고 스피커 전화 또는 독립 실행형 스피커는 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="142bf-305">화상 음향 반향 제거를 지 원하는 디바이스의 경우 높은 값은 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="142bf-306">다른 디바이스의 경우이 메트릭은 장치 품질을 평가 하는 데 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142bf-307"><strong>에코 보내기 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-308">예</span><span class="sxs-lookup"><span data-stu-id="142bf-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-309">다른 사용자에 게 전송 되는 에코의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142bf-310"><strong>에코 (%)로 전화 걸기</strong></span><span class="sxs-lookup"><span data-stu-id="142bf-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="142bf-311">예</span><span class="sxs-lookup"><span data-stu-id="142bf-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="142bf-312">에코에 허용 되는 수준을 초과한 총 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="142bf-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

