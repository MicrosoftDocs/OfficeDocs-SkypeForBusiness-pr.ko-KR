---
title: 'Lync Server 2013: QoE 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 958c67b1b10b25e44805d2582ffe2e9fab575568
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="c0c56-102">Lync Server 2013의 QoE 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0c56-103">_**마지막으로 수정 된 항목:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="c0c56-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="c0c56-104">QoE 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-104">QoE summary/trend reports</span></span>

<span data-ttu-id="c0c56-105">QoE 요약/추세 보고서는 조직의 네트워크 리소스가 충분 한지 확인 하기 위해 하루 중 최고 사용 시간을 찾고 해당 시간 동안 미디어 품질을 확인 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="c0c56-106">조직에서는 보고서에서 사용할 수 있는 다양 한 필터를 사용 하 여 특정 위치, 클라이언트 및 장치 유형, 서버에 대 한 성능 번호를 격리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="c0c56-107">QoE 요약/추세 보고서는 다음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="c0c56-108">UC-UC 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="c0c56-109">PSTN 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="c0c56-110">전화 회의 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="c0c56-111">QoE 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-111">QoE performance reports</span></span>

<span data-ttu-id="c0c56-112">QoE 성능 보고서는 중재 서버, A/V 회의 서버 및 끝점 위치의 QoE 성능에 주력 하는 세 가지 보고서에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="c0c56-113">중재 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-113">Mediation server performance report</span></span>

<span data-ttu-id="c0c56-114">중재 서버 성능 보고서에는 지정 된 기간 동안 하나 이상의 중재에 의해 달성 된 메트릭이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="c0c56-115">UC (통합 통신) 및 각 통화의 중재 서버 간 연결에 대 한 메트릭은 개별적으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="c0c56-116">이 보고서를 사용 하 여 조직의 다양 한 중재 서버에 대 한 볼륨 및 성능을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="c0c56-117">각 중재 서버 (and 각 통화 레그)에 대해 보고서에 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="c0c56-118">통화 수</span><span class="sxs-lookup"><span data-stu-id="c0c56-118">Number of calls</span></span>

  - <span data-ttu-id="c0c56-119">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="c0c56-119">Packet Loss</span></span>

  - <span data-ttu-id="c0c56-120">라운드트립 시간</span><span class="sxs-lookup"><span data-stu-id="c0c56-120">Round Trip Time</span></span>

  - <span data-ttu-id="c0c56-121">지터</span><span class="sxs-lookup"><span data-stu-id="c0c56-121">Jitter</span></span>

  - <span data-ttu-id="c0c56-122">MOS (대화 평균 평가 점수)</span><span class="sxs-lookup"><span data-stu-id="c0c56-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c0c56-123">MOS 보내기</span><span class="sxs-lookup"><span data-stu-id="c0c56-123">Sending MOS</span></span>

  - <span data-ttu-id="c0c56-124">수신 대기 MOS</span><span class="sxs-lookup"><span data-stu-id="c0c56-124">Listening MOS</span></span>

  - <span data-ttu-id="c0c56-125">네트워크 MOS</span><span class="sxs-lookup"><span data-stu-id="c0c56-125">Network MOS</span></span>

  - <span data-ttu-id="c0c56-126">네트워크 MOS 성능 저하</span><span class="sxs-lookup"><span data-stu-id="c0c56-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="c0c56-127">에코 반환</span><span class="sxs-lookup"><span data-stu-id="c0c56-127">Echo Return</span></span>

  - <span data-ttu-id="c0c56-128">신호 수준</span><span class="sxs-lookup"><span data-stu-id="c0c56-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="c0c56-129">A/V 회의 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="c0c56-130">A/V 회의 서버 성능 보고서는 지정 된 기간 동안 하나 이상의 A/V 회의 서버에서 얻은 메트릭 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="c0c56-131">이 보고서는 조직의 다양 한 A/V 회의 서버의 볼륨과 성능을 비교 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="c0c56-132">조직에서는 Lync 클라이언트나 PSTN 클라이언트 같은 특정 클라이언트 유형에 대 한 환경만 표시 하도록 보고서를 격리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="c0c56-133">각 A/V 회의 서버에 대해 보고서에 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="c0c56-134">회의 수</span><span class="sxs-lookup"><span data-stu-id="c0c56-134">Number of conferences</span></span>

  - <span data-ttu-id="c0c56-135">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="c0c56-135">Packet Loss</span></span>

  - <span data-ttu-id="c0c56-136">라운드트립 시간</span><span class="sxs-lookup"><span data-stu-id="c0c56-136">Round Trip Time</span></span>

  - <span data-ttu-id="c0c56-137">지터</span><span class="sxs-lookup"><span data-stu-id="c0c56-137">Jitter</span></span>

  - <span data-ttu-id="c0c56-138">MOS (대화 평균 평가 점수)</span><span class="sxs-lookup"><span data-stu-id="c0c56-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c0c56-139">MOS 보내기</span><span class="sxs-lookup"><span data-stu-id="c0c56-139">Sending MOS</span></span>

  - <span data-ttu-id="c0c56-140">수신 대기 MOS</span><span class="sxs-lookup"><span data-stu-id="c0c56-140">Listening MOS</span></span>

  - <span data-ttu-id="c0c56-141">네트워크 MOS</span><span class="sxs-lookup"><span data-stu-id="c0c56-141">Network MOS</span></span>

  - <span data-ttu-id="c0c56-142">네트워크 MOS 성능 저하</span><span class="sxs-lookup"><span data-stu-id="c0c56-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="c0c56-143">에코 반환</span><span class="sxs-lookup"><span data-stu-id="c0c56-143">Echo Return</span></span>

  - <span data-ttu-id="c0c56-144">신호 수준</span><span class="sxs-lookup"><span data-stu-id="c0c56-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="c0c56-145">위치 기반 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="c0c56-145">Location-based performance report</span></span>

<span data-ttu-id="c0c56-146">위치 기반 성능 보고서는 네트워크 위치 목록을 제공 하 고 각 위치에 대해 미리 결정 된 각 품질 범위의 통화 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="c0c56-147">이 보고서의 목표는 다양 한 위치에 대 한 조직의 전화 통화에 대 한 대량의 정보를 파악 하 여 제대로 수행 되지 않는 위치를 파악 하 고 조직의 다양 한 미디어 품질 등급을 볼 수 있도록 하는 것입니다. 다른 위치</span><span class="sxs-lookup"><span data-stu-id="c0c56-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="c0c56-148">보고서를 표시할 때 각 메트릭이 표시 되 면 조직에서 보고 하기로 결정 한 각 메트릭에 대 한 테이블이 하나씩 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="c0c56-149">이 보고서에 대해 다음 메트릭 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0c56-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="c0c56-150">MOS (대화 평균 평가 점수)</span><span class="sxs-lookup"><span data-stu-id="c0c56-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c0c56-151">네트워크 MOS</span><span class="sxs-lookup"><span data-stu-id="c0c56-151">Network MOS</span></span>

  - <span data-ttu-id="c0c56-152">네트워크 MOS 성능 저하</span><span class="sxs-lookup"><span data-stu-id="c0c56-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="c0c56-153">MOS 보내기</span><span class="sxs-lookup"><span data-stu-id="c0c56-153">Sending MOS</span></span>

  - <span data-ttu-id="c0c56-154">수신 대기 MOS</span><span class="sxs-lookup"><span data-stu-id="c0c56-154">Listening MOS</span></span>

  - <span data-ttu-id="c0c56-155">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="c0c56-155">Packet Loss</span></span>

  - <span data-ttu-id="c0c56-156">지터</span><span class="sxs-lookup"><span data-stu-id="c0c56-156">Jitter</span></span>

  - <span data-ttu-id="c0c56-157">대기 시간</span><span class="sxs-lookup"><span data-stu-id="c0c56-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

