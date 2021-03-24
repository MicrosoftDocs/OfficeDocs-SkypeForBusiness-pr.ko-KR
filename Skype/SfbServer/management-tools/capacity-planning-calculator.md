---
title: 비즈니스용 Skype 서버 용량 계획 계산기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '요약: 용량 계산기 도구를 사용하는 방법'
ms.openlocfilehash: cc78e9d5cbf22a9cc194f0a434f246a8560f5382
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098884"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="4029c-103">비즈니스용 Skype 서버 용량 계획 계산기</span><span class="sxs-lookup"><span data-stu-id="4029c-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="4029c-104">**요약:** 용량 계산기 도구를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="4029c-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="4029c-105">이 문서에서는 비즈니스용 Skype 서버 2015 다운로드를 참조하지만 다음에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="4029c-106">비즈니스용 Skype 서버 2019.</span><span class="sxs-lookup"><span data-stu-id="4029c-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="4029c-107">비즈니스용 Skype 서버 2015.</span><span class="sxs-lookup"><span data-stu-id="4029c-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4029c-108">비즈니스용 [Skype 서버 2015](https://www.microsoft.com/download/details.aspx?id=51196) 용량 계산기 및 비즈니스용 [Skype 서버 2019](https://www.microsoft.com/download/details.aspx?id=57509) 용량 계산기는 비즈니스용 [Skype](https://www.microsoft.com/download/details.aspx?id=50357) 계획 도구 및 배포 설명서(각각 비즈니스용 Skype 서버[2015](../plan-your-deployment/plan-your-deployment.md) 배포 계획 및 비즈니스용 Skype [서버 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) 배포 계획)를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="4029c-109">가이드를 검토하고 계획 도구를 사용하여 권장 토폴로지가 만들어진 후 계산기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="4029c-110">비즈니스용 Skype 서버 용량 계산기는 사용자 수 및 조직에서 사용하는 통신 도구에 따라 서버 요구 사항을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="4029c-111">사용자 프로필 및 사용자에 대해 사용하도록 설정할 기능을 확인한 후 계산기를 사용하여 필요한 서버, 메모리 및 대역폭 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="4029c-112">이 버전의 계산기는 디스크 I/O 요구 사항에 대한 지침을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="4029c-113">특정 사용자 프로필에 대한 정확하고 자세한 정보가 있는 경우 계산기를 통해 대부분의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="4029c-114">예를 들어 음성 사용 가능 사용자의 백분율, 사용자당 시간당 평균 통화 수, 통화 시간 및 회의의 동시 사용자 비율이 서버 요구 사항에 큰 차이를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="4029c-115">계산기에서 만든 추천의 정확도는 제공하는 정보의 정확성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="4029c-116">계획 도구 및 용량 계획 계산기를 사용한 후 제안된 부하와 계획된 부하를 시뮬레이트하여 비즈니스용 Skype 서버가 적절하게 프로비전되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="4029c-117">시뮬레이트된 부하에서 스트레스 테스트를 수행하려면 비즈니스용 [Skype](https://www.microsoft.com/download/details.aspx?id=50367) 서버 스트레스 및 성능 도구에 설명된 비즈니스용 [Skype 서버 스트레스 및 성능 도구를 사용합니다.](./stress-and-performance-tool/stress-and-performance-tool.md)</span><span class="sxs-lookup"><span data-stu-id="4029c-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](./stress-and-performance-tool/stress-and-performance-tool.md).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="4029c-118">용량 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="4029c-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="4029c-119">계산기가 Microsoft Excel 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="4029c-120">입력 셀은 주황색입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-120">Your input cells are colored orange.</span></span> <span data-ttu-id="4029c-121">기본값은 셀에 입력됩니다(비즈니스용 Skype 서버 2015의 경우, 프런트 엔드 서버가 12대인 한 풀에 사용자 80,000명, 비즈니스용 Skype 서버 2019의 경우 16개의 프런트 엔드 서버가 있는 풀 하나에 106,000명) 이러한 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="4029c-122">사용 모델에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-122">The usage model contains the following sections.</span></span> <span data-ttu-id="4029c-123">용량 요구 사항을 계산하기 위해 시트 맨 위에 있는 설명에 따라 데이터를 입력하고 행을 기준으로 행을 아래로 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="4029c-124">**인스턴트 메시징 및 현재 상태**</span><span class="sxs-lookup"><span data-stu-id="4029c-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="4029c-125">사용자 **수에** 한 번 로그인할 사용자 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="4029c-126">이 수는 일반적으로 프로비전된 총 사용자 수의 80%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="4029c-127">대부분의 경우 동시 사용자의 100%가 IM 및 현재 상태 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="4029c-128">기본값은 비즈니스용 Skype 서버 2015의 경우 80,000명, 비즈니스용 Skype 서버 2019의 경우 106,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="4029c-129">**연락처 목록의** 평균 연락처 수는 시스템 요구 사항의 유효성을 검사하는 데 사용하는 연락처 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="4029c-130">이 번호는 고정되어 있으며 변경해야 하는 것이 아니라 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="4029c-131">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="4029c-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="4029c-132">사용자에 **Enterprise Voice** 에서 사용자에 대해 사용하도록 설정된 사용자의 백분율을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4029c-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="4029c-133">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="4029c-134">**시간당** 사용자당 평균 통화 수(최대)에서 최대 부하 시간 동안 평균 사용자가 참여할 것으로 예상되는 시간당 통화 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="4029c-135">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-135">The default is 4.</span></span> 
    
- <span data-ttu-id="4029c-136">미디어 **우회를** 사용하는 통화의 백분율에 중재 서버를 우회할 사용자가 걸은 통화의 백분율을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="4029c-137">기본값은 65%이지만, 지리적으로 분산되어 있는 경우나 집에서 일하는 사용자의 비율이 많은 경우 낮을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="4029c-138">**UC-PSTN** 통화에 관련된 음성 사용자의 백분율에 UC-PSTN 전화 통화인 조직의 통화 비율을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="4029c-139">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-139">The default is 60%.</span></span>
    
- <span data-ttu-id="4029c-140">**UC-UC** 통화에 참여한 음성 사용자의 백분율은 UC-UC 통화에만 사용할 Enterprise Voice 사용자 비율을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="4029c-141">이 번호는 **UC-PSTN** 통화에 사용하도록 설정된 음성 사용자의 백분율에 입력한 개수를 기반으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="4029c-142">**회의**</span><span class="sxs-lookup"><span data-stu-id="4029c-142">**Conferencing**</span></span>
  
- <span data-ttu-id="4029c-143">**동시** 회의의 사용자 백분율에 동시에 회의에 참가할 사용자의 백분율을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="4029c-144">기본값은 5%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="4029c-145">그룹 **IM만** 있는 회의의 백분율(음성 없음)에 인스턴트 메시징만 포함할 회의 비율을 입력하고 오디오를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="4029c-146">기본값은 10%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-146">The default is 10%</span></span>
    
- <span data-ttu-id="4029c-147">전화 **접속** 회의를 사용하는 사용자의 백분율에 전화 접속 회의를 사용할 회의 참가자의 비율을 한 번씩 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="4029c-148">기본값은 15%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-148">The default is 15%.</span></span>
    
- <span data-ttu-id="4029c-149">음성을 **사용하는** 회의 비율에 오디오를 포함할 회의의 백분율을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="4029c-150">음성 회의의 20%에 일반 비디오도 포함되어 있는 경우 비디오 **포함(다중** 보기 없음) 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="4029c-151">회의의 20%에 다중 보기 비디오도 포함하려면  다중 보기 포함 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="4029c-152">음성 회의의 50%에 응용 프로그램 공유도 포함하려면 응용 프로그램 공유 포함 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="4029c-153">음성 회의의 20%에 PowerPoint 프레젠테이션과 같은 데이터 업로드가 포함되어 있는 경우 웹 회의 포함 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="4029c-154">**이동성**</span><span class="sxs-lookup"><span data-stu-id="4029c-154">**Mobility**</span></span>
  
- <span data-ttu-id="4029c-155">모바일 **기능을 사용할** 수 있는 사용자의 백분율에 모바일 장치를 사용하여 비즈니스용 Skype 서버에 연결할 수 있는 사용자의 백분율을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="4029c-156">기본값은 40%입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-156">The default is 40%.</span></span> 
    
<span data-ttu-id="4029c-157">필요한 모든 정보를 입력하면 용량 계산기가 요구 사항을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="4029c-158">노란색 셀은 비즈니스용 Skype 서버 성능 랩에서 수행한 테스트를 기반으로 CPU, 메모리 및 대역폭 요구 사항에 대해 계산된 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="4029c-159">이 번호는 모든 단일 변형이 테스트 및 유효성 검사가 아닌 지침으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="4029c-160">계산할 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="4029c-161">프런트 엔드 **CPU:** 테스트에 사용된 서버와 동일한 사양의 한 프런트 엔드 서버에서 전체 부하를 처리하는 경우 CPU 사용량의 백분율입니다(이 문서 끝에 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="4029c-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="4029c-162">**네트워크(Mbps)**: 해당 워크로드에 대한 대역폭 요구 사항(초당 Mbps)입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="4029c-163">**메모리(GB)**: 해당 워크로드에 필요한 메모리(GB)입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="4029c-164">녹색 셀에는 입력한 사용 모델에 대한 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="4029c-165">총 프런트 엔드 **서버:** 필요한 실제 서버 수는 듀얼 프로세서가 있는 비즈니스용 Skype 서버 2015, 16진수 2,260 메가사이클, Intel Xeon E5-2673 v3, 듀얼 프로세서, 16진수 코어가 있는 비즈니스용 Skype Server 2019를 실행하는 전용 서버를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="4029c-166">하이퍼스레드를 사용하도록 설정하는 것이 권장되고 오디오/비디오를 지원하는 서버의 성능을 향상시키는 것으로 입증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="4029c-167">**에지** 서버: 에지 서버를 통해 통신하는 모든 동시 사용자의 30%를 기준으로 필요한 에지 서버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="4029c-168">이 백분율은 계산기에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="4029c-169">**보관/통화 정보 기록/경험** 품질 서비스 저장소: 조직에서 사용하도록 설정된 경우 보관 또는 모니터링 기능에 필요한 저장소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="4029c-170">**백 엔드 데이터베이스 서버 필요(풀 필요)**: 선택한 작업을 지원하는 데 필요한 백 엔드 데이터베이스 서버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="4029c-171">또한 총 프런트 엔드 서버 옆에 있는 행에 계획된 모든 워크로드에 대한 서버 및 네트워크의 부하에 대한 자세한 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="4029c-172">**평균 CPU 부하:** 프런트 엔드 서버당 평균 CPU 사용량입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="4029c-173">**네트워크(Mbps)**: 입력한 사용 모델을 지원하는 데 필요한 대역폭 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="4029c-174">**메모리(GB)**: 각 프런트 엔드 서버에 필요한 메모리(기가바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="4029c-175">프로세서 조정</span><span class="sxs-lookup"><span data-stu-id="4029c-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="4029c-176">스프레드시트의 모든 CPU 사용 현황 수치는 각 비즈니스용 Skype 서버 2015 서버에 2.26GHz의 16진수 코어, 최소 32GB의 메모리 및 72GB 이상의 사용 가능 디스크 공간이 있는 10,000개 이상의 RPM 하드 디스크 드라이브가 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="4029c-177">각 비즈니스용 Skype 서버 2019 서버에 대해 스프레드시트의 모든 CPU 사용 수치는 각 서버에 이중 프로세서, Intel Xeon E5-2673 v3이 있는 16진수 코어, 최소 64GB의 메모리 및 72GB 이상의 사용이 필요한 10,000개 이상의 RPM 하드 디스크 드라이브가 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="4029c-178">서버의 프로세서가 다르면 하드웨어에 맞게 수치도 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4029c-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
