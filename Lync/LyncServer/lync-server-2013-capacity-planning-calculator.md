---
title: Lync Server 2013 용량 계획 계산기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512825"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="e524a-102">Lync Server 2013에 대 한 용량 계획 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="e524a-102">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e524a-103">_**마지막으로 수정 된 항목:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="e524a-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="e524a-104">Microsoft® Lync™ Server 2013 capacity 계획 계산기는에서 다운로드할 수 있습니다 <https://www.microsoft.com/download/details.aspx?id=36828> .</span><span class="sxs-lookup"><span data-stu-id="e524a-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="e524a-105">이 기능은 조직에서 사용 하도록 설정 된 사용자 수 및 통신 형식에 따라 서버 요구 사항을 결정 하는 데 도움을 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="e524a-106">조직의 프로필을 입력 하면 계산기는 토폴로지를 계획 하는 데 도움이 되는 권장 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="e524a-107">계산기에서 만드는 권장 사항은 계획 목적 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="e524a-108">Lync Server 2013이 제대로 프로 비전 되도록 하려면 실제 부하 시뮬레이션이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="e524a-109">시뮬레이트된 부하에서 스트레스 테스트를 수행 하려면 [Lync Server 2013 스트레스 및 성능 도구](https://go.microsoft.com/fwlink/?linkid=282724)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="e524a-110">사용자에 대해 사용 하도록 설정 하려는 형식를 결정 한 후에는 계산기를 사용 하 여 필요한 서버 수, 메모리 및 대역폭을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="e524a-111">이 버전의 계산기는 디스크 I/o 요구 사항에 대 한 지침을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="e524a-112">이 계산기는 [Microsoft Lync server](https://go.microsoft.com/fwlink/?linkid=282725) 및 [microsoft lync server](lync-server-2013-planning.md)를 보완 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="e524a-113">가이드를 검토 하 고 계획 도구를 사용 하 여 권장 토폴로지를 만든 후에 계산기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="e524a-114">특정 사용자 프로필에 대 한 자세한 정보를 정확 하 게 알고 있는 경우에는 계산기의 장점을 가장 많이 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="e524a-115">예를 들어 음성 사용 가능 사용자, 시간 당 사용자 당 평균 통화, 통화 시간 및 전화 회의에서 동시 사용자의 백분율은 서버 요구 사항에 큰 차이를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="e524a-116">계산기에서 만드는 권장 사항의 정확성은 제공 하는 정보의 정확성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="e524a-117">용량 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="e524a-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="e524a-118">계산기가 Microsoft Excel® 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="e524a-119">주황색 색이 지정 된 셀은 사용자가 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="e524a-120">기본값 입력 (8만 사용자는 12 개의 프런트 엔드 서버를 사용 하는 단일 풀에 있음) 그러나 조직의 요구 사항에 따라 이러한 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="e524a-121">사용 모델에는 다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-121">The usage model contains the following sections.</span></span> <span data-ttu-id="e524a-122">용량 요구 사항을 계산 하려면 설명 된 대로 데이터를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="e524a-123">**인스턴트 메시징 및 현재 상태**</span><span class="sxs-lookup"><span data-stu-id="e524a-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="e524a-124">사용자 수에 동시에 로그인 할 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="e524a-125">이 번호는 일반적으로 프로 비전 된 총 사용자 수의 80%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="e524a-126">대부분의 경우 동시 사용자의 100%는 IM 및 현재 상태에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="e524a-127">기본값은 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-127">The default is 80,000.</span></span>

  - <span data-ttu-id="e524a-128">대화 상대 목록의 평균 대화 상대 수 시스템 요구 사항을 확인 하는 데 사용 하는 연락처의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="e524a-129">이 숫자는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-129">This number is not changeable.</span></span>

<span data-ttu-id="e524a-130">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="e524a-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="e524a-131">Enterprise Voice를 사용할 수 있는 사용자에 게 Enterprise Voice를 사용할 수 있는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="e524a-132">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-132">The default is 60%.</span></span>

  - <span data-ttu-id="e524a-133">시간당 사용자 당 평균 통화 횟수 (최대 사용 수)에는 최대 부하 시간 동안 평균 사용자가 참여 하는 것으로 예상 되는 시간당 호출 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="e524a-134">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-134">The default is 4.</span></span>

  - <span data-ttu-id="e524a-135">미디어 바이패스를 사용 하는 통화 비율에 중재 서버를 무시할 사용자가 건 통화의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="e524a-136">기본값은 65%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-136">The default is 65%.</span></span>

  - <span data-ttu-id="e524a-137">UC-PSTN 통화에 관련 된 음성 사용자의 백분율에 따라 UC-PSTN 전화 통화에 해당 하는 조직의 통화 비율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="e524a-138">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-138">The default is 60%</span></span>

  - <span data-ttu-id="e524a-139">Uc 통화에 포함 된 음성 사용자의 백분율은 UC-UC 통화에만 사용 하도록 설정할 수 있는 Enterprise Voice를 사용할 수 있는 사용자의 비율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="e524a-140">이 번호는 UC PSTN 통화에 사용 하도록 설정 된 음성 사용자의 비율에 따라 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="e524a-141">**회의**</span><span class="sxs-lookup"><span data-stu-id="e524a-141">**Conferencing**</span></span>

  - <span data-ttu-id="e524a-142">동시 회의의 사용자 비율에는 회의에 동시에 참가 하는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="e524a-143">기본값은 5%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-143">The default is 5%.</span></span>

  - <span data-ttu-id="e524a-144">그룹 메신저만 (음성 아님)으로 전화 회의 백분율에 게 인스턴트 메시징과 관련 된 회의 백분율을 입력 합니다. 즉, 오디오 구성 요소를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="e524a-145">기본값은 10%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-145">The default is 10%</span></span>

  - <span data-ttu-id="e524a-146">전화 접속 회의를 사용 하는 사용자의 백분율에 따라 전화 접속 회의를 사용할 회의 참가자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="e524a-147">기본값은 15%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-147">The default is 15%.</span></span>

  - <span data-ttu-id="e524a-148">음성을 사용 하는 회의 백분율에 오디오 구성 요소를 포함할 회의 비율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="e524a-149">음성 회의 중 20%에도 일반 비디오가 포함 되는 경우 포함 비디오 (다중 보기 없음) 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="e524a-150">회의 중 20%에 다중 보기 비디오가 포함 되는 경우에는 여러 보기 포함 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="e524a-151">50%의 음성 회의에서 응용 프로그램 공유도 포함 하려면 응용 프로그램 공유 포함 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="e524a-152">음성 회의 중 20%에 Microsoft PowerPoint® 프레젠테이션과 같은 데이터 업로드를 포함 하는 경우 웹 회의 포함 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="e524a-153">**이동성**</span><span class="sxs-lookup"><span data-stu-id="e524a-153">**Mobility**</span></span>

  - <span data-ttu-id="e524a-154">모바일 장치를 사용 하 여 Lync Server에 연결 하는 데 사용할 수 있는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="e524a-155">기본값은 40%입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-155">The default is 40%.</span></span>

<span data-ttu-id="e524a-156">필요한 정보를 모두 입력 하면 용량 계산기가 요구 사항을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="e524a-157">노란색 셀에는 Lync Server 2013 성능 랩에서 수행한 테스트를 기반으로 CPU, 메모리 및 대역폭 요구 사항에 대 한 계산 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="e524a-158">이 수치는 모든 단일 변형의 테스트 및 유효성 검사를 수행 하는 것이 아니라 지침으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="e524a-159">다음 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-159">The following values are calculated:</span></span>

  - <span data-ttu-id="e524a-160">프런트 엔드 CPU: Microsoft 테스트에서 사용 된 서버와 동일한 사양의 프런트 엔드 서버 하나에서 전체 부하를 처리 하는 경우 CPU 사용 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="e524a-161">Mbps 단위 네트워크: 해당 워크 로드에 대 한 대역폭 요구 사항 (Mbps)입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="e524a-162">메모리 (GB): 해당 작업의 기가바이트 (GB)에 메모리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="e524a-163">녹색 셀에는 입력 한 사용 모델에 대 한 권장 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="e524a-164">총 프런트 엔드 서버: 필요한 실제 서버 수는 이중 프로세서 인 Lync Server 2013을 실행 하는 전용 서버 (2260 메가 사이클)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="e524a-165">하이퍼스레딩을 사용 하는 것이 권장 되며, 오디오/비디오를 지 원하는 서버에 대 한 성능 개선을 위해 입증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="e524a-166">에 지 서버: edge 서버를 통해 통신 하는 모든 동시 사용자의 30%를 기반으로 필요한에 지 서버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="e524a-167">이 비율은 계산기에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="e524a-168">보관/통화 정보 기록/경력 수준 서비스 저장소: 조직에서 사용 하도록 설정 된 경우 보관 또는 모니터링 기능에 필요한 저장소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="e524a-169">백 엔드 데이터베이스 서버 필요 (풀 필요): 선택한 작업을 지 원하는 데 필요한 백 엔드 데이터베이스 서버의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="e524a-170">또한 총 프런트 엔드 서버 옆에 있는 행에서 계획 된 모든 작업 부하에 대 한 서버 및 네트워크 부하에 대 한 자세한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="e524a-171">평균 CPU 부하: 프런트 엔드 서버당 평균 CPU 사용량입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="e524a-172">네트워크 단위 (Mbps): 입력 한 사용 모델을 지원 하기 위한 필요한 대역폭 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="e524a-173">메모리 (GB): 각 프런트 엔드 서버에는 메모리 (기가바이트)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="e524a-174">프로세서 조정</span><span class="sxs-lookup"><span data-stu-id="e524a-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="e524a-175">스프레드시트에 포함 된 모든 CPU 사용량은 각 서버에 이중 프로세서, 2.26 GHz 이상의 메모리 및 최소 32 gb의 사용 가능한 디스크 공간이 72 있는 8 개 이상의 1만-RPM 하드 디스크 드라이브를 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="e524a-176">서버의 프로세서가 서로 다른 경우 하드웨어에 맞게 수치를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524a-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

