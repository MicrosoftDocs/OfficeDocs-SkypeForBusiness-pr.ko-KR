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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '요약: 용량 계산기 도구를 사용 하는 방법'
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186837"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="b3197-103">비즈니스용 Skype 서버 용량 계획 계산기</span><span class="sxs-lookup"><span data-stu-id="b3197-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="b3197-104">**요약:** 용량 계산기 도구를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b3197-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="b3197-105">이 문서에서는 비즈니스용 Skype 서버 2015 다운로드를 참조 하지만, 다음과 같은 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="b3197-106">비즈니스용 Skype 서버 2019.</span><span class="sxs-lookup"><span data-stu-id="b3197-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="b3197-107">비즈니스용 Skype 서버 2015.</span><span class="sxs-lookup"><span data-stu-id="b3197-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b3197-108">비즈니스용 skype [서버 2015 용량 계산기](https://www.microsoft.com/en-us/download/details.aspx?id=51196) 및 [비즈니스용 Skype Server 2019 용량 계산기](https://www.microsoft.com/en-us/download/details.aspx?id=57509) 는 비즈니스용 skype [계획 도구](https://www.microsoft.com/en-us/download/details.aspx?id=50357) 및 배포 문서 (비즈니스용[skype 계획)를 보강 합니다. ](../plan-your-deployment/plan-your-deployment.md)각각의 [비즈니스용 Skype server 2019 배포에 대 한](../../SfBServer2019/plan/plan-your-deployment-2019.md) 서버 2015 배포 및 계획</span><span class="sxs-lookup"><span data-stu-id="b3197-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="b3197-109">가이드를 검토 하 고 계획 도구를 사용 하 여 권장 토폴로지를 만든 후 계산기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="b3197-110">비즈니스용 Skype Server Capacity 계산기는 조직에서 사용 하는 사용자 수와 통신 도구에 따라 서버 요구 사항을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="b3197-111">사용자 프로필 및 사용자에 게 사용할 기능을 결정 한 후에는 계산기를 사용 하 여 필요한 서버 수, 메모리 및 대역폭을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="b3197-112">이 버전의 계산기는 디스크 I/o 요구 사항에 대 한 지침을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="b3197-113">특정 사용자 프로필에 대 한 자세한 정보를 정확 하 게 알고 있다면 계산기를 통해 가장 많은 혜택을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="b3197-114">예를 들어 음성 사용 가능 사용자, 시간 당 평균 통화, 통화 기간, 회의에 대 한 동시 사용자의 백분율 등은 서버 요구 사항에 큰 차이를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="b3197-115">계산기에 의해 생성 되는 권장 사항의 정확도는 제공 하는 정보의 정확성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="b3197-116">계획 도구와 용량 계획 계산기를 사용 하는 경우에는 제안 및 계획 된 부하를 시뮬레이트 하 여 비즈니스용 Skype 서버가 적절 하 게 프로 비전 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="b3197-117">시뮬레이트된 부하에서 스트레스 테스트를 수행 하려면 비즈니스용 skype 서버 스트레스 및 성능 [도구](https://technet.microsoft.com/en-us/library/mt631400.aspx)에서 문서화 된 비즈니스용 [skype 서버 스트레스 및 성능 도구](https://www.microsoft.com/en-us/download/details.aspx?id=50367) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="b3197-118">용량 계산기 사용</span><span class="sxs-lookup"><span data-stu-id="b3197-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="b3197-119">계산기는 Microsoft Excel 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="b3197-120">입력 셀에는 주황색 색이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-120">Your input cells are colored orange.</span></span> <span data-ttu-id="b3197-121">기본값은 셀에 입력 되며 (비즈니스용 Skype Server 2015 8만, 두 개의 프런트 엔드 서버를 사용 하는 한 풀의 사용자는 12 대의 비즈니스용 Skype 서버 2019을 사용 하 고, 1 개의 프런트 엔드 서버가 있는 한 풀의 사용자는 106000), 다음 값을 변경 해야 합니다. 조직의 요구 사항에 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="b3197-122">사용 모델에는 다음 섹션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-122">The usage model contains the following sections.</span></span> <span data-ttu-id="b3197-123">용량 요구 사항을 계산 하려면 시트의 맨 위에 시작 하 여 행 단위로 작업 아래에 설명 된 대로 데이터를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="b3197-124">**인스턴트 메시지 및 현재 상태**</span><span class="sxs-lookup"><span data-stu-id="b3197-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="b3197-125">**사용자 수**아래에서 한 번에 로그인 할 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="b3197-126">이 번호는 일반적으로 프로 비전 된 총 사용자 수의 80%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="b3197-127">대부분의 경우, 동시 사용자의 100%는 IM 및 현재 상태에 대해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="b3197-128">기본값은 비즈니스용 Skype Server 2015 및 106000 사용자 용 비즈니스용 Skype 서버 2019의 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="b3197-129">**연락처 목록의 평균 대화 상대 수** 는 시스템 요구 사항을 확인 하는 데 사용 하는 연락처 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="b3197-130">이 번호는 수정 되 고 변경 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="b3197-131">**엔터프라이즈 음성**</span><span class="sxs-lookup"><span data-stu-id="b3197-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="b3197-132">**Enterprise voice를 사용할 수 있는 사용자**의 경우 엔터프라이즈 음성에 대해 사용 하도록 설정 된 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="b3197-133">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="b3197-134">최대 **사용자 당 평균 통화 수 (피크)** 에, 최대 로드 시간 동안 평균 사용자가 참여 하는 데 예상 되는 시간 당 통화 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="b3197-135">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-135">The default is 4.</span></span> 
    
- <span data-ttu-id="b3197-136">**미디어 바이패스를 사용 하는 통화 백분율**조정 서버를 우회 하는 사용자가 설정한 통화 비율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="b3197-137">기본값은 65% 이지만, 지리적으로 분산 되어 있거나 집에서 근무 하는 사용자 수가 많은 경우에는 작을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="b3197-138">**Uc-pstn 통화와 관련 된 음성 사용자의 백분율**에 따라 UC-pstn 전화 통화 인 조직의 통화 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="b3197-139">기본값은 60%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-139">The default is 60%.</span></span>
    
- <span data-ttu-id="b3197-140">**Uc와 관련 된 음성 사용자의 백분율-uc 통화** 에는 UC-uc 통화에만 사용 하도록 설정할 수 있는 Enterprise voice를 사용 하는 사용자의 백분율이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="b3197-141">이 번호는 **UC-PSTN 통화에 대해 사용 하도록 설정 된 음성 사용자의 백분율**에 따라 입력 하는 내용을 기준으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="b3197-142">**회의**</span><span class="sxs-lookup"><span data-stu-id="b3197-142">**Conferencing**</span></span>
  
- <span data-ttu-id="b3197-143">**동시 회의에**참여 하는 사용자의 백분율, 회의에 참가 하는 사용자의 백분율을 한 번에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="b3197-144">기본값은 5%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="b3197-145">**그룹 메신저만 (음성 없음)으로 회의 백분율을 사용**하 여 인스턴트 메시징과 관련 된 회의 백분율을 입력 하 고 오디오를 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b3197-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="b3197-146">기본값은 10%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-146">The default is 10%</span></span>
    
- <span data-ttu-id="b3197-147">**전화 접속 회의를 사용 하는 사용자의 백분율**에서 한 번에 전화 접속 회의를 사용 하는 회의 참가자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="b3197-148">기본값은 15%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-148">The default is 15%.</span></span>
    
- <span data-ttu-id="b3197-149">**음성을 사용 하는 회의 백분율**오디오를 포함할 회의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="b3197-150">음성 회의 중 20%에도 일반 비디오가 포함 되는 경우 **포함 비디오 (다중 보기 없음)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="b3197-151">회의 중 20%에도 다중 보기 비디오가 포함 되는 경우 **여러 보기 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="b3197-152">음성 회의의 50%에도 응용 프로그램 공유가 포함 되는 경우 **응용 프로그램 공유 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="b3197-153">음성 회의 중 20%에 PowerPoint 프레젠테이션 등의 데이터 업로드가 포함 되는 경우 **웹 회의 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="b3197-154">**간의**</span><span class="sxs-lookup"><span data-stu-id="b3197-154">**Mobility**</span></span>
  
- <span data-ttu-id="b3197-155">**이동성을 사용 하도록 설정 된 사용자 백분율**모바일 장치를 사용 하 여 비즈니스용 Skype 서버에 연결 하는 데 사용할 수 있는 사용자의 백분율을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="b3197-156">기본값은 40%입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-156">The default is 40%.</span></span> 
    
<span data-ttu-id="b3197-157">필요한 정보를 모두 입력 하면 용량 계산기가 요구 사항을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="b3197-158">노란색 셀에는 비즈니스용 Skype 서버 성능 실험에서 수행한 테스트에 따라 CPU, 메모리 및 대역폭 요구 사항에 대 한 계산 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="b3197-159">숫자는 모든 단일 변형이 테스트 및 검증 되지 않고 지침으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="b3197-160">다음 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="b3197-161">**프런트 엔드 cpu**: 전체 로드가 테스트에 사용 된 서버와 동일한 사양의 프런트 엔드 서버에서 처리 되는 경우 (이 문서의 끝부분에 있는 설명 참조) cpu 사용 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="b3197-162">**Mbps 단위 네트워크**: 해당 작업 부하에 대 한 메가 비트/초 (mbps)의 대역폭 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="b3197-163">**Gb 메모리**: 해당 작업 부하에 대해 기가바이트 (gb)의 메모리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="b3197-164">녹색 셀에는 입력 한 사용 모델에 대 한 권장 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="b3197-165">**총 프런트 엔드 서버**: 필요한 물리적 서버 수는 듀얼 프로세서, 16 진수 코어, 2260 메가 사이클 또는 인텔 제온 E5-2673 v3, 듀얼코어 기반 2019 비즈니스용 skype 서버 2015을 통해 비즈니스용 skype를 실행 하는 전용 서버를 기준으로 합니다. 프로세서, 16 진수-코어.</span><span class="sxs-lookup"><span data-stu-id="b3197-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="b3197-166">하이퍼스레딩을 사용 하는 것이 좋지만 오디오/비디오를 지 원하는 서버의 성능이 개선 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="b3197-167">**Edge 서버**: edge 서버를 통해 통신 하는 모든 동시 사용자의 30%를 기준으로 필요한 edge 서버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="b3197-168">이 백분율은 계산기에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="b3197-169">**보관/통화 세부 정보 기록/경력 서비스 품질**: 조직에서 사용 하도록 설정 된 경우 기능을 보관 또는 모니터링 하는 데 필요한 스토어의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="b3197-170">**백 엔드 데이터베이스 서버 필요 (풀 필요)**: 선택한 작업을 지 원하는 데 필요한 백 엔드 데이터베이스 서버의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="b3197-171">또한 총 프런트 엔드 서버 옆에 있는 행에서 계획 된 모든 작업 부하에 대 한 서버 및 네트워크의 부하에 대 한 자세한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="b3197-172">**평균 Cpu 부하**: 프런트 엔드 서버 당 평균 cpu 사용량입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="b3197-173">**네트워크**단위 (Mbps): 입력 한 사용 모델을 지원 하기 위해 필요한 대역폭 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="b3197-174">**GB 인 메모리**: 각 프런트 엔드 서버에는 메모리 (기가바이트)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="b3197-175">프로세서에 맞게 조정</span><span class="sxs-lookup"><span data-stu-id="b3197-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="b3197-176">스프레드시트의 모든 CPU 사용량에는 각각의 비즈니스용 Skype Server 2015 서버에 듀얼 프로세서, 2.26 GHz, 최소 32 GB 메모리, 1만 그리고 최소 72 GB의 하드 디스크 드라이브와 최소한 이상의 사용 가능한 디스크 공간이 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="b3197-177">각 비즈니스용 Skype Server 2019 서버에 대해 스프레드시트의 모든 CPU 사용에 대해 각 서버에 듀얼 프로세서, 인텔 제온 년 1 자-2673 v3, 최소 64 GB의 메모리, 이상 1만-RPM 하드 디스크 드라이브 (최소 72 GB)를 사용 하는 디스크에 설치 되어 있다고 가정 합니다. 맞는.</span><span class="sxs-lookup"><span data-stu-id="b3197-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="b3197-178">서버에 다른 프로세서가 있는 경우 하드웨어에 맞게 수치를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3197-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
