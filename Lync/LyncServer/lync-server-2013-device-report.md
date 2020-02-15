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
ms.openlocfilehash: da9ec08af933f90eaf1e941259628b38ec055d9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="0ff93-102">Lync Server 2013의 장치 보고서</span><span class="sxs-lookup"><span data-stu-id="0ff93-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ff93-103">_**마지막으로 수정 된 항목:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="0ff93-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="0ff93-104">장치 보고서에 마이크 및 스피커 보고서 라는 제목의 제목이 더 적합 합니다. 장치 보고서가 통화에 사용 된 마이크 및 스피커로 그룹화 된 통화 관련 메트릭 (예: 불량 통화 백분율, 에코 및 음성 전환 시간)을 검색 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="0ff93-105">IP 전화에 관심이 있는 경우 (일반적으로 "장치" 라고도 함) [Lync Server 2013에서 Ip 전화 인벤토리 보고서](lync-server-2013-ip-phone-inventory-report.md) 를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="0ff93-p102">장치 보고서는 관리자가 특정 종류의 장치에서 다른 장치보다 더 많은 양의 불량 통화가 발생하는지 여부를 확인하는 데 매우 유용합니다. 따라서 새 장치를 구입해야 하거나 기존 장치를 교체해야 할 시점에 내려야 하는 결정에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="0ff93-p103">기본적으로 장치 보고서에 표시된 정보는 통화에 사용된 마이크(캡처 장치)와 스피커/헤드셋(렌더링 장치)을 기반으로 합니다. 예를 들어 다음과 같은 캡처 장치와 렌더링 장치를 사용하는 여러 사용자가 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="0ff93-111">캡처 장치 -- 마이크(SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="0ff93-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="0ff93-112">렌더링 장치 -- 헤드셋 이어폰(Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="0ff93-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="0ff93-113">이들 사용자가 전화를 건 통화 수가 총 254통이었다면 보고서에는 다음과 같이 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff93-114">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-114">Capture device</span></span></th>
<th><span data-ttu-id="0ff93-115">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-115">Render device</span></span></th>
<th><span data-ttu-id="0ff93-116">통화량</span><span class="sxs-lookup"><span data-stu-id="0ff93-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-117">마이크(SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="0ff93-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-118">헤드셋 이어폰(Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="0ff93-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-119">254</span><span class="sxs-lookup"><span data-stu-id="0ff93-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ff93-p104">이번에는 동일한 캡처 장치와 서로 다른 렌더링 장치를 사용하는 여러 사용자가 있다고 가정해 보겠습니다. 이 경우 보고서에 두 번째 줄에 고유한 캡처 장치 및 렌더링 장치 조합에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff93-122">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-122">Capture device</span></span></th>
<th><span data-ttu-id="0ff93-123">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-123">Render device</span></span></th>
<th><span data-ttu-id="0ff93-124">통화량</span><span class="sxs-lookup"><span data-stu-id="0ff93-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-125">마이크(SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="0ff93-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-126">헤드셋 이어폰(Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="0ff93-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-127">254</span><span class="sxs-lookup"><span data-stu-id="0ff93-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-128">마이크(SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="0ff93-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-129">스피커(SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="0ff93-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-130">319</span><span class="sxs-lookup"><span data-stu-id="0ff93-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ff93-p105">지정된 장치에 대한 총 합계를 볼 경우(예: 사용된 렌더링 장치와 상관없이 SoundMAX 캡처 장치에 대해) 장치 유형 드롭다운 목록에서 해당 옵션(캡처 장치 또는 렌더링 장치)을 선택합니다. 이 예제에서 캡처 장치를 선택할 다음과 같은 출력에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff93-133">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-133">Capture device</span></span></th>
<th><span data-ttu-id="0ff93-134">통화량</span><span class="sxs-lookup"><span data-stu-id="0ff93-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-135">마이크(SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="0ff93-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="0ff93-136">573</span><span class="sxs-lookup"><span data-stu-id="0ff93-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="0ff93-137">장치 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="0ff93-137">Accessing the Device Report</span></span>

<span data-ttu-id="0ff93-138">장치 보고서는 일반적으로 모니터링 보고서 홈 페이지에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0ff93-139">그러나 [Lync Server 2013에서 통화 정보 보고서](lync-server-2013-call-detail-report.md) 를 보고 있는 경우 다음 메트릭 중 하나를 클릭 하 여 특정 장치에 대 한 장치 보고서로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0ff93-140">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-140">Capture Device</span></span>

  - <span data-ttu-id="0ff93-141">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-141">Render Device</span></span>

<span data-ttu-id="0ff93-142">장치 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0ff93-143">통화량</span><span class="sxs-lookup"><span data-stu-id="0ff93-143">Call volume</span></span>

  - <span data-ttu-id="0ff93-144">불량 통화율</span><span class="sxs-lookup"><span data-stu-id="0ff93-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="0ff93-145">장치 보고서의 효과적인 사용</span><span class="sxs-lookup"><span data-stu-id="0ff93-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="0ff93-146">장치 이름에는 장치 보고서에 대한 자세한 설명이 있습니다. 예를 들어 다음 캡처 장치가 있다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="0ff93-147">Aastra 3002 마이크(2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="0ff93-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="0ff93-148">Aastra 3002 마이크(3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="0ff93-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="0ff93-149">Aastra 3002 마이크(Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="0ff93-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="0ff93-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="0ff93-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="0ff93-151">Aastra 6725ip 마이크(10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-152">Aastra 6725ip 마이크(10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="0ff93-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="0ff93-153">Aastra 6725ip 마이크(2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-154">Aastra 6725ip 마이크(3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-155">Aastra 6725ip 마이크(4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-156">Aastra 6725ip 마이크(5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-157">Aastra 6725ip 마이크(6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-158">Aastra 6725ip 마이크(7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-159">Aastra 6725ip 마이크(9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-160">Aastra 6725ip 마이크(9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="0ff93-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="0ff93-161">Aastra 6725ip 마이크(Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="0ff93-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="0ff93-162">Aastra 6725ip 마이크(Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="0ff93-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="0ff93-163">Aastra 6725ip 마이크(USB 오디오 장치)</span><span class="sxs-lookup"><span data-stu-id="0ff93-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="0ff93-164">Aastra 6725ip 마이크(USB 오디오 장치)-V0</span><span class="sxs-lookup"><span data-stu-id="0ff93-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ff93-165">Lync Server 2013의 지역화 된 버전을 실행 중인 경우에는 캡처 장치 이름이 동일 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="0ff93-166">Aastra 6725ip 마이크(Aastra 6725ip)-V0라는 한국어 이름은 프랑스어나 스페인으로는 다른 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="0ff93-167">때로는 이러한 상세 설명이 필요하겠지만, 그 밖의 경우에는 모델 번호와 상관없이 Aastra 마이크를 사용하는 통화 수에만 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="0ff93-168">이 처럼 정보를 가져오는 한 가지 방법으로 장치 보고서 데이터를 Microsoft Excel로 내보낸 다음 해당 데이터를 쉼표로 구분 된 값 파일 (예를 들어 C:\\data\\Devices\_.csv)에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="0ff93-169">그러면 이와 비슷한 명령 집합을 사용하여 .CSV 파일을 Windows PowerShell로 가져오고 Aastra 캡처 장치를 사용하여 전화를 건 총 통화 수를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="0ff93-p109">그러면 Aastra 캡처 장치를 사용하여 전화를 건 총 통화 수를 나타내는 단일 값이 반환됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0ff93-172">필터</span><span class="sxs-lookup"><span data-stu-id="0ff93-172">Filters</span></span>

<span data-ttu-id="0ff93-p110">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 장치 보고서에서는 통화 유형(즉 클라이언트 연결 통화), 전화 회의 또는 PSTN(공중 전화망 통화)와 같은 항목에 대해 필터링을 수행할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 장치는 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0ff93-177">다음 표에서는 장치 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="0ff93-178">장치 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="0ff93-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff93-179">이름</span><span class="sxs-lookup"><span data-stu-id="0ff93-179">Name</span></span></th>
<th><span data-ttu-id="0ff93-180">설명</span><span class="sxs-lookup"><span data-stu-id="0ff93-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p111">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0ff93-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0ff93-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0ff93-p112">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0ff93-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0ff93-187">7/7/2012</span></span></p>
<p><span data-ttu-id="0ff93-188">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0ff93-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0ff93-189">7/3/2012</span></span></p>
<p><span data-ttu-id="0ff93-190">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-191"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p113">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0ff93-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0ff93-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0ff93-p114">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0ff93-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0ff93-197">7/7/2012</span></span></p>
<p><span data-ttu-id="0ff93-198">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0ff93-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0ff93-199">7/3/2012</span></span></p>
<p><span data-ttu-id="0ff93-200">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-201"><strong>음성 스위치 원인</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p115">소리 울림 방지를 위해 반이중 모드로 통화를 설정해야 하는 이유입니다. 반이중 모드에서 통신은 무전기를 이용한 통신에서와 마찬가지로 한 번에 한쪽 방향으로만 전달됩니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-205">모든</span><span class="sxs-lookup"><span data-stu-id="0ff93-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-206">없음</span><span class="sxs-lookup"><span data-stu-id="0ff93-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-207">잘못된 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="0ff93-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-208">에코</span><span class="sxs-lookup"><span data-stu-id="0ff93-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-209">DNLP(dynamic nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="0ff93-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-210">낮은 복잡성</span><span class="sxs-lookup"><span data-stu-id="0ff93-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-211">잘못된 장치 상태</span><span class="sxs-lookup"><span data-stu-id="0ff93-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-212">Post-AEC 에코(음향 반향 취소)</span><span class="sxs-lookup"><span data-stu-id="0ff93-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-213"><strong>에코 원인</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p116">통화에서 적정 수준 이상의 에코가 발견되는 이유입니다. 원격 통신에서 에코는 우물 아래쪽으로 큰 소리를 냈을 때 다시 들려오는 것과 동일한 현상인 소리의 반향을 의미합니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-216">모든</span><span class="sxs-lookup"><span data-stu-id="0ff93-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-217">없음</span><span class="sxs-lookup"><span data-stu-id="0ff93-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-218">잘못된 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="0ff93-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-219">Post-AEC 에코(음향 반향 취소)</span><span class="sxs-lookup"><span data-stu-id="0ff93-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-220">ANLP(adaptive nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="0ff93-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-221">DNLP(dynamic nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="0ff93-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-222">마이크 클리핑</span><span class="sxs-lookup"><span data-stu-id="0ff93-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-223"><strong>통화 유형</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p117">수행된 통화의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-226">모든</span><span class="sxs-lookup"><span data-stu-id="0ff93-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-227">클라이언트 통화</span><span class="sxs-lookup"><span data-stu-id="0ff93-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-228">PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="0ff93-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-229">전화 회의</span><span class="sxs-lookup"><span data-stu-id="0ff93-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-230"><strong>액세스 유형</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p118">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-233">모든</span><span class="sxs-lookup"><span data-stu-id="0ff93-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-234">Internal</span><span class="sxs-lookup"><span data-stu-id="0ff93-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-235">외부:</span><span class="sxs-lookup"><span data-stu-id="0ff93-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-236"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p119">통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-239">모든</span><span class="sxs-lookup"><span data-stu-id="0ff93-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-240">유선</span><span class="sxs-lookup"><span data-stu-id="0ff93-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-241">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="0ff93-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p120">통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-245">모든</span><span class="sxs-lookup"><span data-stu-id="0ff93-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-246">VPN</span><span class="sxs-lookup"><span data-stu-id="0ff93-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-247">비 VPN</span><span class="sxs-lookup"><span data-stu-id="0ff93-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-248"><strong>장치 유형</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p121">장치 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-251">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-252">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="0ff93-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0ff93-253">캡처/렌더링 장치 쌍</span><span class="sxs-lookup"><span data-stu-id="0ff93-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-254"><strong>장치 이름</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-p122">캡처 또는 렌더링 장치의 이름입니다. 전체 장치 이름 또는 장치 이름 중 일부를 입력할 수 있습니다. 예를 들어 마이크 장치(Microsoft LifeCam VX-1000.)를 찾으려면 다음과 같이 전체 장치 이름을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="0ff93-258">Microphone(Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="0ff93-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="0ff93-p123">또는 이름 중 일부만 입력할 수도 있습니다. 예:</span><span class="sxs-lookup"><span data-stu-id="0ff93-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="0ff93-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="0ff93-261">LifeCam</span></span></p>
<p><span data-ttu-id="0ff93-262">위의 필터는 이름에 LifeCam &quot;&quot; 문자열이 포함 된 모든 장치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0ff93-263">선별한</span><span class="sxs-lookup"><span data-stu-id="0ff93-263">Metrics</span></span>

<span data-ttu-id="0ff93-264">다음 표에서는 장치 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="0ff93-265">장치 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="0ff93-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff93-266">이름</span><span class="sxs-lookup"><span data-stu-id="0ff93-266">Name</span></span></th>
<th><span data-ttu-id="0ff93-267">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="0ff93-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0ff93-268">설명</span><span class="sxs-lookup"><span data-stu-id="0ff93-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-269"><strong>캡처 장치</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-270">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-271">오디오 전송에 사용되는 장치(예: 마이크 또는 웹캠)입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-272"><strong>렌더링 장치</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-273">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-274">오디오 수신에 사용되는 장치(예: 헤드셋 또는 스피커)입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-275"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-276">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-277">수행된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-278"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-279">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-280">불량으로 &quot;분류 된 통화의 비율입니다. &quot; 통화 불량은 측정 된 메트릭이 하나 이상 허용 된 값을 초과 하는 모든 통화 (예: 과도 한 지터가 발생 한 통화)입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-281"><strong>고유 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-282">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-p124">장치를 사용한 고유 사용자입니다. 장치를 13회 사용한 사용자나 장치를 한 번만 사용한 사용자 모두 한 명의 고유한 사용자로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-285"><strong>음성 스위치 시간 비율</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-286">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-p125">에코 방지를 위해 반이중 모드로 설정해야 한 통화 비율입니다. 반이중 모드에서 통신은 무전기를 이용한 통신에서와 마찬가지로 한 번에 한쪽 방향으로만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-289"><strong>마이크 작동 안 함 비율</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-290">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-p126">캡처 장치가 적정 수준으로 작동하지 않은 통화 비율입니다. 높은 값은 통화 품질 문제가 주로 올바르게 작동하지 않은 캡처 장치 때문인 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-293"><strong>스피커 작동 안 함 비율</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-294">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-p127">렌더링 장치가 적정 수준으로 작동하지 않은 통화 비율입니다. 높은 값은 통화 품질 문제가 주로 올바르게 작동하지 않은 렌더링 장치 때문인 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-297"><strong>음성 스위치를 사용한 통화(%)</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-298">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-p128">반이중 모드로 설정해야 했던 총 통화 비율입니다. 반이중 모드에서 통신은 무전기를 이용한 통신에서와 마찬가지로 한 번에 한쪽 방향으로만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-301"><strong>마이크 입력 에코(%)</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-302">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-303">마이크 캡처 스트림에서 화면 표시가 감지 되는 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="0ff93-304">일반적으로 헤드셋 이나 송수화기에 대 한 값은 낮고, 스피커 전화 또는 독립 실행형 스피커의 경우에는 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="0ff93-305">온보드 음향 반향 취소를 지 원하는 장치의 경우 높은 값은 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="0ff93-306">다른 장치의 경우에는이 메트릭을 사용 하 여 장치 품질을 평가 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff93-307"><strong>송신 에코(%)</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-308">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-309">다른 사용자에게 전송된 에코 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff93-310"><strong>에코가 있는 통화(%)</strong></span><span class="sxs-lookup"><span data-stu-id="0ff93-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff93-311">예</span><span class="sxs-lookup"><span data-stu-id="0ff93-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff93-312">에코가 적정 수준을 초과한 총 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff93-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

