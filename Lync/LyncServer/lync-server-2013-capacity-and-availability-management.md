---
title: 'Lync Server 2013: 용량 및 가용성 관리'
description: 'Lync Server 2013: 용량 및 가용성 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565154"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="5838c-103">Lync Server 2013의 용량 및 가용성 관리</span><span class="sxs-lookup"><span data-stu-id="5838c-103">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5838c-104">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="5838c-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="5838c-105">용량 관리 및 가용성 관리는 시스템 성능을 측정 하 고 제어 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-105">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="5838c-106">시스템 성능을 측정 하 고 제어할 수 있도록 용량 관리 및 가용성 관리 절차를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-106">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="5838c-107">시스템을 사용할 수 있는지 여부를 확인 하 고, 기준을 설정 하 고 시스템에서 추세를 찾도록 모니터링 하 여 현재와 예상 되는 요구를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-107">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="5838c-108">용량 관리</span><span class="sxs-lookup"><span data-stu-id="5838c-108">Capacity management</span></span>

<span data-ttu-id="5838c-109">용량 관리에는 SLA에 지정 된 최소 성능 수준이 초과 되도록 서비스 용량을 계획, 조정 및 제어 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-109">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="5838c-110">적절 한 용량 관리를 통해 IT 서비스를 적절 한 비용으로 제공 하 고 클라이언트에 Sla에 정의 된 성능 수준을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-110">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="5838c-111">이러한 조건에는 다음이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-111">These criteria can include the following:</span></span>

  - <span data-ttu-id="5838c-112">**시스템 응답 시간**     이 시간은 시스템에서 일반적인 작업을 수행 하는 데 소요 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-112">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="5838c-113">오디오/비디오 서버 역할을 처리 하는 데 필요한 시간, 클라이언트에서 전화 회의를 만들고 참여 하는 데 필요한 시간, 모든 감시자 클라이언트에서 현재 상태를 업데이트 하기 위해 소요 되는 시간 등이 여기에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-113">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="5838c-114">**저장소 용량**     이 용량은 콘텐츠 데이터베이스, 백업 장치 또는 로컬 드라이브 중 하나에 해당 하는 저장소 시스템의 용량입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-114">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="5838c-115">여기에는 사이트별로 제공 되는 최대 저장소 공간 및 덮어쓰기 전에 백업을 저장 해야 하는 시간이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-115">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="5838c-116">용량 조정은 디스크 공간 및 네트워크 대역폭과 같은 충분 한 실제 리소스를 사용할 수 있도록 하는 경우에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-116">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="5838c-117">다음 표에는 용량 관련 문제에 대 한 일반적인 해결 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-117">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="5838c-118">용량 관련 문제에 대 한 일반적인 해결 방법</span><span class="sxs-lookup"><span data-stu-id="5838c-118">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5838c-119">문제</span><span class="sxs-lookup"><span data-stu-id="5838c-119">Issue</span></span></th>
<th><span data-ttu-id="5838c-120">가능한 해결 방법</span><span class="sxs-lookup"><span data-stu-id="5838c-120">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5838c-121">오디오/비디오 성능에 좋지 않은 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="5838c-121">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="5838c-122">WAN 링크에 적절 한 대역폭을 사용할 수 있는지와 QoS가 사용 하도록 설정 되 고 적절 하 게 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-122">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="5838c-123">QoE 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-123">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5838c-124">Lync 환경의 전체 응답 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-124">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="5838c-125">테스트를 실행 하 여 기존 프런트 엔드 서버에서 로드를 처리할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-125">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="5838c-126">필요한 경우 새 프런트 엔드 서버를 도입 합니다. SQL 데이터베이스 응답 시간을 확인 하 고 지연 원인 (예: 디스크 i/o 향상)을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-126">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5838c-127">문제 해결에 대 한 자세한 내용은 Lync Server 네트워킹 가이드에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-127">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="5838c-128">용량은 시스템 구성의 영향을 받으며 네트워크 대역폭과 같은 실제 리소스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-128">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="5838c-129">예를 들어 Lync 환경이 매일 전체 백업을 수행 하도록 구성 된 경우 최종 사용자가 경험 하는 대화형 성능에 미치는 영향을 최소화할 수 있도록 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-129">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="5838c-130">용량 관리는 시스템의 용량을 허용 되는 수준 내에서 유지 하 고 다음과 같은 문제를 해결 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-130">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="5838c-131">**요구 사항**     변경에 대 한 대응 시스템 또는 조직의 변경 사항을 고려 하 여 용량 요구 사항을 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-131">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="5838c-132">예를 들어 환경에서 Enterprise Voice를 구현 하기로 결정 하는 경우 중재 서버 및 PSTN (공중 전화망) 게이트웨이의 수와 배치도 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-132">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="5838c-133">SIP (Session 착수 프로토콜) 트렁크 또는 direct SIP를 수행 하는 경우 최상의 엔터프라이즈 음성 성능을 제공 하기 위해 전체 디자인이 크게 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-133">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="5838c-134">**향후 요구 사항 예측**     시간에 따라 예측 가능한 일부 용량 요구 사항이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-134">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="5838c-135">추세를 추적 하 여 업그레이드를 미리 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-135">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="5838c-136">예를 들어 기준을 만들려면 다양 한 Lync 사이트 간에 사용 가능한 대역폭을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-136">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="5838c-137">이 기준을 사용 하면 이러한 원격 사이트의 사용자 수가 시간에 따라 증가 하므로 이러한 링크에 대 한 대역폭을 더 추가 해야 하는 경우를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-137">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="5838c-138">가용성 관리</span><span class="sxs-lookup"><span data-stu-id="5838c-138">Availability management</span></span>

<span data-ttu-id="5838c-139">가용성 관리는 IT 서비스가 일관 되 고 경제적으로 고객에 게 요구 되는 일관 되 고 신뢰할 수 있는 서비스를 제공 하는지 확인 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-139">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="5838c-140">가용성 관리는 서비스 손실을 최소화 하 고 서비스가 손실 될 경우 적절 한 조치를 취할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-140">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="5838c-141">Lync 환경에서는 Enterprise Voice 서비스를 사용할 수 있는지 여부, 사용자가 예약 된 회의에 참가할 수 있는지 여부 등을 고려해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-141">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="5838c-142">SLA는 허용 되는 빈도와 기간을 정의 하며, 계획 된 유지 관리를 위해 시스템을 사용할 수 없는 특정 기간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-142">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="5838c-143">시스템의 가용성에 대 한 보고서를 관리에 제공 해야 하거나, 누락 된 가용성 목표와 관련 하 여 재정 또는 기타 페널티를 사용 하는 경우에는 가용성 데이터를 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-143">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="5838c-144">이러한 공식적인 요구 사항이 없는 경우에도 최소한 시스템에서 특정 기간 동안 오류가 발생 한 시간을 파악 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-144">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="5838c-145">예를 들어 지난 12 개월 동안의 시스템 가용성과 각 오류에서 복구 하는 데 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-145">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="5838c-146">이 정보는 시스템 오류에 대 한 응답으로 팀의 효율성을 측정 하 고 향상 시키는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-146">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="5838c-147">또한 분쟁에 게 유용한 정보를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-147">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="5838c-148">가용성과 관련 된 측정값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-148">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="5838c-149">**가용성**     이는 일반적으로 시스템 또는 서비스에 액세스할 수 있는 시간을 다운 된 시간과 비교 하 여 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-149">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="5838c-150">일반적으로 백분율로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-150">It is typically expressed as a percentage.</span></span> <span data-ttu-id="5838c-151">"3 개의 9" 또는 "5 개의 9"에 대 한 참조를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-151">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="5838c-152">이는 99.9% 또는 99.999%의 가용성을 의미 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5838c-152">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="5838c-153">**안정성**     이는 시스템 오류 사이의 시간을 측정 한 것으로, 종종 계산 (MTBF) 간격 (평균)으로 표현 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-153">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="5838c-154">**복구 시간**     이 시간은 오류가 발생 한 후에 서비스를 복구 하는 데 소요 되는 시간으로, 대개 평균 수리 시간 (평균값)으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-154">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="5838c-155">가용성, 안정성 및 복구 시간을 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-155">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="5838c-156">**Availability = (mtbf – MTTR)/MTBF**     예를 들어 서버가 6 개월 동안 두 번 실패 하 고 평균 20 분 동안 서버를 사용할 수 없는 경우 MTBF는 3 개월 또는 90 일이 고 MTTR는 20 분이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-156">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="5838c-157">따라서 가용성 = (90 days-20 분)/90 days = 99.985%입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-157">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="5838c-158">가용성 관리는 가용성을 최대화 하 고 Sla에 정의 된 매개 변수 내에 유지 하도록 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-158">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="5838c-159">가용성 관리에는 다음과 같은 프로세스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-159">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="5838c-160">**모니터링**     시간 및 서비스를 사용할 수 없는 시간을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-160">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="5838c-161">**보고**     가용성 수치는 관리, 사용자 및 운영 팀에 게 정기적으로 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-161">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="5838c-162">이러한 보고서에서는 추세를 강조 표시 하 고 주의 해야 하는 영역 및 주의가 필요한 영역을 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-162">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="5838c-163">보고서에서 Sla에 설정 된 대상에 대 한 준수를 요약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-163">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="5838c-164">**개선**     가용성이 Sla에 정의 된 목표를 충족 하지 않는 경우 또는 추세가 감소 하는 추세에 해당 하는 경우 가용성 관리 프로세스에서 예측 가능한 단계를 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-164">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="5838c-165">여기에는 다른 책임 팀과 협력 하 여 중단 이유를 강조 하 고 중단의 반복을 방지 하기 위한 해결 조치 계획을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-165">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="5838c-166">용량 및 가용성 측정값은이 문서의 뒷부분에서 설명 하는 Microsoft System Center Operations Manager (이전 Microsoft Operations Manager)와 같은 자동화 된 도구 및 스크립트에 가장 적합 한 반복적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="5838c-166">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5838c-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5838c-167">See Also</span></span>


[<span data-ttu-id="5838c-168">System Center Operations Manager를 사용 하 여 Lync Server 2013 모니터링</span><span class="sxs-lookup"><span data-stu-id="5838c-168">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

