---
title: Lync Server 2013 용량 계획 계산기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 385127f1686c2a4fa5beaf33f02d2eec6ba19500
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="3ade7-102">Lync Server 2013에 대 한 용량 계획 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="3ade7-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ade7-103">_**마지막으로 수정한 주제:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="3ade7-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="3ade7-104">Microsoft® Lync™ 서버 2013 용량 계획 계산기를 다운로드할 수 있습니다 <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span><span class="sxs-lookup"><span data-stu-id="3ade7-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="3ade7-105">조직에서 사용 하도록 설정 된 사용자 수 및 통신 형식을에 따라 서버 요구 사항을 결정 하는 데 도움이 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="3ade7-106">조직의 프로필을 입력 하면 계산기는 토폴로지를 계획 하는 데 도움이 되는 권장 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="3ade7-107">계산기가 만든 권장 사항은 계획 목적 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="3ade7-108">Lync Server 2013을 적절 하 게 프로 비전 하려면 실제 부하 시뮬레이션이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="3ade7-109">시뮬레이트된 부하에서 스트레스 테스트를 수행 하려면 [Lync Server 2013 스트레스 및 성능 도구](http://go.microsoft.com/fwlink/?linkid=282724)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="3ade7-110">사용자에 게 사용 하도록 설정 하려는 사용자 프로필 및 형식을를 결정 한 후에는 계산기를 사용 하 여 필요한 서버 수, 메모리 및 대역폭을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="3ade7-111">이 버전의 계산기는 디스크 I/o 요구 사항에 대 한 지침을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="3ade7-112">이 계산기는 [Microsoft Lync server](http://go.microsoft.com/fwlink/?linkid=282725) 및 [microsoft lync server](lync-server-2013-planning.md)를 보완 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="3ade7-113">가이드를 검토 하 고 계획 도구를 사용 하 여 권장 토폴로지를 만든 후 계산기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="3ade7-114">특정 사용자 프로필에 대 한 자세한 정보를 정확 하 게 알고 있다면 계산기를 통해 가장 많은 혜택을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="3ade7-115">예를 들어 음성 사용 가능 사용자, 시간 당 평균 통화, 통화 기간, 회의에 대 한 동시 사용자의 백분율 등은 서버 요구 사항에 큰 차이를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="3ade7-116">계산기에 의해 생성 되는 권장 사항의 정확도는 제공 하는 정보의 정확성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="3ade7-117">용량 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="3ade7-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="3ade7-118">계산기는 Microsoft Excel® 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="3ade7-119">주황색 색이 지정 된 셀은 사용자의 입력 용입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="3ade7-120">기본값 (8만 사용자가 12 개의 프런트 엔드 서버를 사용 하는 한 풀에 있음)을 입력 했지만 조직의 요구 사항에 따라 이러한 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="3ade7-121">사용 모델에는 다음 섹션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-121">The usage model contains the following sections.</span></span> <span data-ttu-id="3ade7-122">용량 요구 사항을 계산 하려면 설명 된 대로 데이터를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="3ade7-123">**인스턴트 메시지 및 현재 상태**</span><span class="sxs-lookup"><span data-stu-id="3ade7-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="3ade7-124">사용자 수 아래에 동시에 로그인 할 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="3ade7-125">이 번호는 일반적으로 프로 비전 된 총 사용자 수의 80%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="3ade7-126">대부분의 경우, 동시 사용자의 100%는 IM 및 현재 상태에 대해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="3ade7-127">기본값은 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-127">The default is 80,000.</span></span>

  - <span data-ttu-id="3ade7-128">연락처 목록의 평균 대화 상대 수는 시스템 요구 사항을 확인 하는 데 사용 하는 연락처 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="3ade7-129">이 번호는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-129">This number is not changeable.</span></span>

<span data-ttu-id="3ade7-130">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="3ade7-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="3ade7-131">Enterprise Voice를 사용할 수 있는 사용자의 경우 Enterprise Voice를 사용할 수 있는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3ade7-132">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-132">The default is 60%.</span></span>

  - <span data-ttu-id="3ade7-133">최대 사용자 당 평균 통화 수 (피크)에 최대 부하 시에 평균 사용자가 참여할 것으로 예상 되는 시간 당 통화 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="3ade7-134">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-134">The default is 4.</span></span>

  - <span data-ttu-id="3ade7-135">미디어 바이패스를 사용 하는 통화 백분율 조정 서버를 우회 하는 사용자가 설정한 통화 비율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="3ade7-136">기본값은 65%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-136">The default is 65%.</span></span>

  - <span data-ttu-id="3ade7-137">UC-PSTN 통화와 관련 된 음성 사용자의 백분율에 따라 UC-PSTN 전화 통화 인 조직의 통화 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="3ade7-138">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-138">The default is 60%</span></span>

  - <span data-ttu-id="3ade7-139">Uc와 관련 된 음성 사용자의 백분율-uc 통화에는 uc-UC 통화에만 사용 하도록 설정할 수 있는 Enterprise Voice를 사용 하는 사용자의 백분율이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="3ade7-140">이 번호는 UC-PSTN 통화에 대해 사용 하도록 설정 된 음성 사용자의 백분율에 따라 입력 하는 내용을 기준으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="3ade7-141">**회의**</span><span class="sxs-lookup"><span data-stu-id="3ade7-141">**Conferencing**</span></span>

  - <span data-ttu-id="3ade7-142">동시 회의의 사용자 비율에는 회의에 동시에 참가 하는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="3ade7-143">기본값은 5%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-143">The default is 5%.</span></span>

  - <span data-ttu-id="3ade7-144">그룹 메신저만 (음성 없음)으로 회의가 진행 되는 백분율, 회의에는 메신저 대화에만 해당 되는 회의 백분율을 입력 합니다. 즉, 오디오 구성 요소가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="3ade7-145">기본값은 10%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-145">The default is 10%</span></span>

  - <span data-ttu-id="3ade7-146">전화 접속 회의를 사용 하는 사용자의 백분율에서 전화 접속 회의를 사용 하는 회의에 참여 하는 동시 참가자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="3ade7-147">기본값은 15%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-147">The default is 15%.</span></span>

  - <span data-ttu-id="3ade7-148">음성을 사용 하는 회의 백분율 오디오 구성 요소를 포함할 회의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="3ade7-149">음성 회의 중 20%에도 일반 비디오가 포함 되는 경우 포함 비디오 (다중 보기 없음) 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="3ade7-150">회의 중 20%에도 다중 보기 비디오가 포함 되는 경우 여러 보기 포함 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="3ade7-151">음성 회의의 50%에도 응용 프로그램 공유가 포함 되는 경우 응용 프로그램 공유 포함 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="3ade7-152">음성 회의 중 20%의 경우 Microsoft PowerPoint® 프레젠테이션 등의 데이터 업로드가 포함 되는 경우 웹 회의 포함 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="3ade7-153">**이동성**</span><span class="sxs-lookup"><span data-stu-id="3ade7-153">**Mobility**</span></span>

  - <span data-ttu-id="3ade7-154">이동성을 사용 하도록 설정 된 사용자 백분율 모바일 장치를 사용 하 여 Lync Server에 연결 하는 데 사용할 수 있는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="3ade7-155">기본값은 40%입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-155">The default is 40%.</span></span>

<span data-ttu-id="3ade7-156">필요한 정보를 모두 입력 하면 용량 계산기가 요구 사항을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="3ade7-157">노란색 셀에는 Lync Server 2013 성능 실습에서 수행한 테스트를 기준으로 CPU, 메모리 및 대역폭 요구 사항에 대 한 계산 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="3ade7-158">숫자는 모든 단일 변형이 테스트 및 검증 되지 않고 지침으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="3ade7-159">다음 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-159">The following values are calculated:</span></span>

  - <span data-ttu-id="3ade7-160">프런트 엔드 CPU: Microsoft 테스트에 사용 된 서버와 동일한 사양의 프런트 엔드 서버 하나에서 전체 로드가 처리 되는 경우 CPU 사용 비율이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="3ade7-161">Mbps 단위 네트워크: 해당 작업 부하에 대 한 메가 비트/초 (Mbps)의 대역폭 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="3ade7-162">GB 메모리: 해당 작업 부하에 대해 기가바이트 (GB)의 메모리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="3ade7-163">녹색 셀에는 입력 한 사용 모델에 대 한 권장 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="3ade7-164">총 프런트 엔드 서버: 필요한 실제 서버 수는 듀얼 프로세서, 16 진수-코어를 사용 하는 Lync Server 2013을 실행 하는 전용 서버에 기반 하 여 2260 메가 사이클을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="3ade7-165">하이퍼스레딩을 사용 하는 것이 좋지만 오디오/비디오를 지 원하는 서버의 성능이 개선 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="3ade7-166">Edge 서버: Edge 서버를 통해 통신 하는 모든 동시 사용자의 30%를 기준으로 필요한 Edge 서버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="3ade7-167">이 백분율은 계산기에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="3ade7-168">보관/통화 세부 정보 기록/경력 서비스 품질: 조직에서 사용 하도록 설정 된 경우 기능을 보관 또는 모니터링 하는 데 필요한 스토어의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="3ade7-169">백 엔드 데이터베이스 서버 필요 (풀 필요): 선택한 작업을 지 원하는 데 필요한 백 엔드 데이터베이스 서버의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="3ade7-170">또한 총 프런트 엔드 서버 옆에 있는 행에서 계획 된 모든 작업 부하에 대 한 서버 및 네트워크의 부하에 대 한 자세한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="3ade7-171">평균 CPU 부하: 프런트 엔드 서버 당 평균 CPU 사용량입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="3ade7-172">네트워크 단위 (Mbps): 입력 한 사용 모델을 지원 하기 위해 필요한 대역폭 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="3ade7-173">GB 인 메모리: 각 프런트 엔드 서버에는 메모리 (기가바이트)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="3ade7-174">프로세서에 맞게 조정</span><span class="sxs-lookup"><span data-stu-id="3ade7-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="3ade7-175">스프레드시트의 모든 CPU 사용량은 각 서버에 2.26 GHz의 듀얼 프로세서, 16 진수 코어, 최소 32 GB의 메모리 1만, 최소 72 GB 하드 디스크 드라이브와 함께 사용 가능한 디스크 공간이 모두 하나 이상 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="3ade7-176">서버에 다른 프로세서가 있는 경우 하드웨어에 맞게 수치를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ade7-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

