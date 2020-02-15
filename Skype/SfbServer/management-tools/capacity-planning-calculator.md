---
title: 비즈니스용 Skype 서버 용량 계획 계산기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 용량 계산기 도구를 사용 하는 방법입니다.'
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031082"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="047cd-103">비즈니스용 Skype 서버 용량 계획 계산기</span><span class="sxs-lookup"><span data-stu-id="047cd-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="047cd-104">**요약:** 용량 계산기 도구를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="047cd-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="047cd-105">이 문서에서는 비즈니스용 Skype 서버 2015 다운로드를 참조 하지만 다음에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="047cd-106">비즈니스용 Skype 서버 2019</span><span class="sxs-lookup"><span data-stu-id="047cd-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="047cd-107">비즈니스용 Skype 서버 2015</span><span class="sxs-lookup"><span data-stu-id="047cd-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="047cd-108">비즈니스용 skype [서버 2015 용량 계산기](https://www.microsoft.com/download/details.aspx?id=51196) 및 [비즈니스용 Skype 서버 2019 용량 계산기](https://www.microsoft.com/download/details.aspx?id=57509) 는 비즈니스용 [skype 계획 도구](https://www.microsoft.com/download/details.aspx?id=50357) 와 배포 설명서 (각각 비즈니스용 Skype[서버 2015 배포](../plan-your-deployment/plan-your-deployment.md) 및 비즈니스용 [skype 서버 2019 배포](../../SfBServer2019/plan/plan-your-deployment-2019.md) 계획)를 확대 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="047cd-109">가이드를 검토 하 고 계획 도구를 사용 하 여 권장 토폴로지를 만든 후에 계산기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="047cd-110">비즈니스용 Skype 서버 용량 계산기는 조직에서 사용 하는 사용자 수 및 통신 도구에 따라 서버 요구 사항을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="047cd-111">사용자 프로필 및 사용자에 대해 사용 하도록 설정할 기능을 결정 한 후에는 계산기를 사용 하 여 필요한 서버 수, 메모리 및 대역폭을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="047cd-112">이 버전의 계산기는 디스크 I/o 요구 사항에 대 한 지침을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="047cd-113">특정 사용자 프로필에 대 한 자세한 정보를 정확 하 게 알고 있는 경우에는 계산기의 장점을 가장 많이 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="047cd-114">예를 들어 음성 사용 가능 사용자, 시간 당 사용자 당 평균 통화, 통화 시간 및 전화 회의에서 동시 사용자의 백분율은 서버 요구 사항에 큰 차이를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="047cd-115">계산기에서 만드는 권장 사항의 정확성은 제공 하는 정보의 정확성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="047cd-116">계획 도구 및 용량 계획 계산기를 사용한 후에는 제안 및 계획 된 부하를 시뮬레이트하여 비즈니스용 Skype 서버가 적절 하 게 구축 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="047cd-117">시뮬레이트된 부하에서 스트레스 테스트를 수행 하려면 비즈니스용 skype 서버 [스트레스 및 성능 도구](https://technet.microsoft.com/library/mt631400.aspx)에서 설명 하는 [비즈니스용 skype 서버 스트레스 및 성능 도구](https://www.microsoft.com/download/details.aspx?id=50367) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="047cd-118">용량 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="047cd-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="047cd-119">계산기가 Microsoft Excel 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="047cd-120">입력 셀의 색이 주황색입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-120">Your input cells are colored orange.</span></span> <span data-ttu-id="047cd-121">기본값은 셀에 입력 되며 (비즈니스용 Skype 서버 2015, 8만 사용자는 12 개의 프런트 엔드 서버를 사용 하는 경우에는 1 대의 비즈니스용 skype 서버 2019에 있지만, 1 개의 프런트 엔드 서버가 있는 한 풀의 사용자는 106000), 이러한 값을 다음으로 변경 해야 합니다. 조직의 요구 사항에 부합 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="047cd-122">사용 모델에는 다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-122">The usage model contains the following sections.</span></span> <span data-ttu-id="047cd-123">용량 요구 사항을 계산 하려면 시트 위쪽에서 시작 하 여 행 단위로 작업을 수행 하 여 설명 된 대로 데이터를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="047cd-124">**인스턴트 메시징 및 현재 상태**</span><span class="sxs-lookup"><span data-stu-id="047cd-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="047cd-125">**사용자 수**에서 한 번에 로그인 할 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="047cd-126">이 번호는 일반적으로 프로 비전 된 총 사용자 수의 80%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="047cd-127">대부분의 경우 동시 사용자의 100%는 IM 및 현재 상태에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="047cd-128">비즈니스용 Skype 서버 2015에 대 한 기본값은 8만이 고 비즈니스용 Skype 서버 2019에는 106000 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="047cd-129">**대화 상대 목록의 평균 대화 상대 수** 시스템 요구 사항을 확인 하는 데 사용 하는 연락처의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="047cd-130">이 번호는 고정 되어 있으며 변경 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="047cd-131">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="047cd-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="047cd-132">**Enterprise voice를 사용할 수 있는 사용자**에 게 enterprise voice에 대해 사용 하도록 설정 된 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="047cd-133">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="047cd-134">**시간당 사용자 당 평균 통화 횟수 (최대 사용 수)** 에는 최대 부하 시간 동안 평균 사용자가 참여 하는 것으로 예상 되는 시간당 호출 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="047cd-135">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-135">The default is 4.</span></span> 
    
- <span data-ttu-id="047cd-136">**미디어 바이패스를 사용 하는 통화 비율**에 중재 서버를 무시할 사용자가 건 통화의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="047cd-137">기본값은 65% 이지만, 지리적으로 분산 되어 있거나 집에서 작업 하는 사용자 수가 많은 경우에는 작을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="047cd-138">**Uc-pstn 통화에 관련 된 음성 사용자의 백분율**에 따라 UC-pstn 전화 통화에 해당 하는 조직의 통화 비율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="047cd-139">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-139">The default is 60%.</span></span>
    
- <span data-ttu-id="047cd-140">Uc **통화에 포함 된 음성 사용자 백분율-** UC-uc 통화에만 사용 하도록 설정할 수 있는 Enterprise voice를 사용할 수 있는 사용자의 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="047cd-141">이 번호는 **UC PSTN 통화에 사용 하도록 설정 된 음성 사용자의 비율**에 따라 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="047cd-142">**전화**</span><span class="sxs-lookup"><span data-stu-id="047cd-142">**Conferencing**</span></span>
  
- <span data-ttu-id="047cd-143">**동시 회의에**참여 하는 사용자의 백분율에 시간을 들 여 회의에 참가 하는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="047cd-144">기본값은 5%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="047cd-145">**그룹 메신저로만 회의 (음성 아님)** 에 대해 인스턴트 메시징과 관련 된 회의 백분율을 입력 하 고 오디오를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="047cd-146">기본값은 10%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-146">The default is 10%</span></span>
    
- <span data-ttu-id="047cd-147">**전화 접속 회의를 사용 하는 사용자의 백분율**에 따라 한 번에 전화 접속 회의를 사용할 회의 참가자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="047cd-148">기본값은 15%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-148">The default is 15%.</span></span>
    
- <span data-ttu-id="047cd-149">**음성을 사용 하는 회의 백분율**에 오디오를 포함할 회의 비율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="047cd-150">음성 회의 중 20%에도 일반 비디오가 포함 되는 경우 **포함 비디오 (다중 보기 없음)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="047cd-151">회의 중 20%에 다중 보기 비디오가 포함 되는 경우에는 **여러 보기 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="047cd-152">50%의 음성 회의에서 응용 프로그램 공유도 포함 하려면 **응용 프로그램 공유 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="047cd-153">음성 회의 중 20%에 PowerPoint 프레젠테이션과 같은 데이터 업로드를 포함 하는 경우 **웹 회의 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="047cd-154">이동성\*\*</span><span class="sxs-lookup"><span data-stu-id="047cd-154">**Mobility**</span></span>
  
- <span data-ttu-id="047cd-155">모바일 **장치를 사용**하 여 비즈니스용 Skype 서버에 연결 하는 데 사용할 수 있는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="047cd-156">기본값은 40%입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-156">The default is 40%.</span></span> 
    
<span data-ttu-id="047cd-157">필요한 정보를 모두 입력 하면 용량 계산기가 요구 사항을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="047cd-158">노란색 셀에는 비즈니스용 Skype 서버 성능 랩에서 수행한 테스트를 기반으로 하는 CPU, 메모리 및 대역폭 요구 사항에 대 한 계산 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="047cd-159">이 수치는 모든 단일 변형의 테스트 및 유효성 검사를 수행 하는 것이 아니라 지침으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="047cd-160">다음 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="047cd-161">**프런트 엔드 CPU**: 테스트에 사용 된 서버와 동일한 사양의 프런트 엔드 서버 하나에서 전체 부하를 처리 하는 경우 (이 문서의 끝부분에 있는 설명 참조) cpu 사용량 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="047cd-162">**Mbps 단위 네트워크**: 해당 워크 로드에 대 한 대역폭 요구 사항 (mbps)입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="047cd-163">**메모리 (gb**): 해당 작업의 기가바이트 (gb)에 메모리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="047cd-164">녹색 셀에는 입력 한 사용 모델에 대 한 권장 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="047cd-165">**총 프런트 엔드 서버**: 필요한 실제 서버 수는 비즈니스용 skype 서버 2015에서 이중 프로세서, 2260 16 메가 사이클, 그리고 인텔 제온 E5-2673 v3, 듀얼 프로세서, 16 진수 코어를 사용 하는 비즈니스용 skype 서버 2019을 실행 하는 전용 서버를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="047cd-166">하이퍼스레딩을 사용 하는 것이 권장 되며, 오디오/비디오를 지 원하는 서버에 대 한 성능 개선을 위해 입증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="047cd-167">에 **지 서버**: edge 서버를 통해 통신 하는 모든 동시 사용자의 30%를 기반으로 필요한에 지 서버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="047cd-168">이 비율은 계산기에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="047cd-169">**보관/통화 정보 기록/경력 수준 서비스 저장소**: 조직에서 사용 하도록 설정 된 경우 보관 또는 모니터링 기능에 필요한 저장소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="047cd-170">**백 엔드 데이터베이스 서버 필요 (풀 필요)**: 선택한 작업을 지 원하는 데 필요한 백 엔드 데이터베이스 서버의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="047cd-171">또한 총 프런트 엔드 서버 옆에 있는 행에서 계획 된 모든 작업 부하에 대 한 서버 및 네트워크 부하에 대 한 자세한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="047cd-172">**평균 Cpu 부하**: 프런트 엔드 서버당 평균 cpu 사용량입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="047cd-173">**네트워크**단위 (Mbps): 입력 한 사용 모델을 지원 하기 위한 필요한 대역폭 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="047cd-174">**메모리 (gb**): 각 프런트 엔드 서버에는 메모리 (기가바이트)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="047cd-175">프로세서 조정</span><span class="sxs-lookup"><span data-stu-id="047cd-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="047cd-176">스프레드시트의 모든 CPU 사용량 그림에서는 각 비즈니스용 Skype 서버 2015 서버에 이중 프로세서, 2.26 g h z, 32 최소, 1만-RPM 하드 디스크 드라이브, 최소 72 GB의 여유 디스크 공간이 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="047cd-177">각 비즈니스용 Skype 서버 2019 서버에 대해 스프레드시트에 있는 모든 CPU 사용에 대해 각 서버에 이중 프로세서, Intel Xeon E5-2673 v3, 최소 64 GB의 메모리, 그리고 최소 72 GB 사용 가능 디스크를 포함 하는 8 개 이상의 1만 RPM 하드 디스크 드라이브를 사용 한다고 가정 합니다. 천천히.</span><span class="sxs-lookup"><span data-stu-id="047cd-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="047cd-178">서버의 프로세서가 서로 다른 경우 하드웨어에 맞게 수치를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047cd-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
