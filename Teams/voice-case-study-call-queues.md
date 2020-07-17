---
title: 팀 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786094"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="bbc72-103">Contoso 사례 연구: 자동 전화 교환 및 통화 대기열</span><span class="sxs-lookup"><span data-stu-id="bbc72-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="bbc72-104">Contoso는 온-프레미스 비즈니스용 Skype 배포의 자동 전화 교환 및 통화 대기열에 익숙합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="bbc72-105">클라우드 자동 전화 교환을 설정 하는 방법에 대 한 자세한 내용은 [클라우드 자동 전화 교환 기능](what-are-phone-system-auto-attendants.md) 을 검토 하는 방법을 이해 하는 데, 그리고 [자동 전화 교환 자습서를 설치 하는 소규모 비즈니스 예-](tutorial-org-aa.yml)</span><span class="sxs-lookup"><span data-stu-id="bbc72-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="bbc72-106">통화 대기열을 설정 하는 데 사용할 수 있는 옵션에 대 한 자세한 내용은 Contoso가 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 검토 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="bbc72-107">사이트 종류에 따라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbc72-107">Requirements depending on site type</span></span>

<span data-ttu-id="bbc72-108">사이트 유형에 따라 Contoso에는 다음과 같은 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="bbc72-109">사이트 종류 A: 기존 레거시 전화 통신 시스템</span><span class="sxs-lookup"><span data-stu-id="bbc72-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="bbc72-110">사이트 receptionist와 연결 된 동일한 전화 번호를 자동 전화 교환 번호로 유지 하는 데 필요한 시간을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="bbc72-111">이러한 각 사이트의 주요 부서에는 팀 구성원에 게 라우팅할 수 있는 고유한 통화 대기열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="bbc72-112">전화 시스템을 사용 하 여 다이렉트 라우팅 및 전화 시스템을 사용한 통화 요금제와 혼합 된 사이트 들이 섞여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="bbc72-113">사이트 종류 B: 비즈니스용 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="bbc72-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="bbc72-114">사이트 유형 B에 팀으로 마이그레이션하는 데 필요한 기존 자동 전화 교환 및 통화 대기열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="bbc72-115">Contoso는 자동 전화 교환에 연결 된 전화 번호를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="bbc72-116">Contoso는 이러한 사이트의 대부분을 전화 시스템으로 통화 요금제로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="bbc72-117">그러나 전화 요금제를 사용할 수 없는 몇 가지 경우에는 Contoso가 이러한 사이트를 직접 라우팅 구성으로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="bbc72-118">사이트 종류 C: 비즈니스용 Skype Enterprise Voice & 기존 레거시 전화 통신 시스템</span><span class="sxs-lookup"><span data-stu-id="bbc72-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="bbc72-119">사이트 유형 C에 기존의 레거시 전화 통신 시스템에 있던 자동 전화 교환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="bbc72-120">이 사이트에 대 한 결정과 구성은 사이트 종류 A와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="bbc72-121">모든 사이트 유형에 대해 Contoso는 다음 질문을 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="bbc72-122">Q: 새로운 숫자나 기존 번호를 사용 합니까?</span><span class="sxs-lookup"><span data-stu-id="bbc72-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="bbc72-123">A: Contoso는 기존 전화 번호를 사용 하 여 자동 전화 교환의 서비스 계정에 할당 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="bbc72-124">Q: 자동 전화 교환은 걸려오는 전화를 수락 하는 데 언제 제공 되나요?</span><span class="sxs-lookup"><span data-stu-id="bbc72-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="bbc72-125">A: Contoso는 업무 시간을 설정 하 고 업무 시간이 "시간 경과 후" 자동 전화 교환으로 리디렉션되는 전화를 받을 수 있도록 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="bbc72-126">Q: 통화 대기열의 구성원에 게 전화를 거는 방법: 전화 교환, 직렬 또는 라운드 로빈 라우팅</span><span class="sxs-lookup"><span data-stu-id="bbc72-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="bbc72-127">A: Contoso는 전화 교환 라우팅을 사용 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="bbc72-128">Q: 사용자가 전화를 받을 수 있는 시간을 결정 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="bbc72-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="bbc72-129">A: Contoso는 통화 처리 옵션을 사용 하 여 에이전트를 사용할 수 있는지 여부를 결정 합니다 (현재 상태 기반 라우팅).</span><span class="sxs-lookup"><span data-stu-id="bbc72-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="bbc72-130">구성</span><span class="sxs-lookup"><span data-stu-id="bbc72-130">Configuration</span></span>

<span data-ttu-id="bbc72-131">자동 전화 교환 및 통화 대기열을 설정 하는 단계에는 [리소스 계정 관리](manage-resource-accounts.md)에 설명 된 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="bbc72-132">서비스 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="bbc72-133">무료 전화 시스템-가상 사용자 라이선스 또는 리소스 계정이 나 전화 시스템 라이선스와 함께 사용 하는 유료 전화 시스템 라이선스를 취득 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbc72-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="bbc72-134">자원 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-134">Create the resource account.</span></span> <span data-ttu-id="bbc72-135">연결 된 리소스 계정이 있는 경우 자동 전화 교환 또는 통화 대기열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="bbc72-136">전화 시스템 또는 전화 시스템-가상 사용자 라이선스를 리소스 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="bbc72-137">자세한 내용은 [Microsoft 365 전화 시스템-가상 사용자 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbc72-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="bbc72-138">라이선스를 할당 한 리소스 계정에 서비스 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="bbc72-139">전화 시스템 통화 대기열 또는 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="bbc72-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="bbc72-140">통화 대기열 또는 자동 전화 교환과 함께 리소스 계정을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="bbc72-141">직접 라우팅이 있는 전화 시스템이 있는 사이트</span><span class="sxs-lookup"><span data-stu-id="bbc72-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="bbc72-142">Contoso는 로컬 통신 업체가 제공 하는 전화 번호를 Office 365의 서비스 번호로 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="bbc72-143">직접 라우팅을 통해 사용할 수 있는 전화 번호를 설정 하려면 Contoso는 [리소스 계정 관리](manage-resource-accounts.md)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="bbc72-144">Office 365이 온-프레미스 전화 번호를 인식 하지 못하기 때문에 Contoso는 PowerShell을 사용 하 여 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="bbc72-145">클라우드 자동 전화 교환을 구성 하기 위해 Contoso는 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="bbc72-146">클라우드 통화 대기열을 설정 하기 위해 Contoso는 [구름 통화 대기열 만들기](create-a-phone-system-call-queue.md)에 명시 된 단계를 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="bbc72-147">전화 시스템이 있는 사이트 (통화 요금제 포함)</span><span class="sxs-lookup"><span data-stu-id="bbc72-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="bbc72-148">Contoso는 비즈니스용 Skype Enterprise Voice 자동 전화 교환에 사용 된 전화 번호를 Office 365 전화 시스템에 이식 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="bbc72-149">이렇게 하면 자동 전화 교환으로 사용할 수 있는 것과 동일한 번호가 서비스 번호로 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="bbc72-150">전화 번호를 이식 하기 위해 Contoso는 [전화 번호를 팀으로 전송](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 하는 지침을 팔 로우 하 고 [조직의 전화 번호 관리에 대 한](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)추가 지침을 얻었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="bbc72-151">클라우드 자동 전화 교환을 구성 하기 위해 Contoso는 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="bbc72-152">클라우드 통화 대기열을 설정 하기 위해 Contoso는 [구름 통화 대기열 만들기](create-a-phone-system-call-queue.md)에 명시 된 단계를 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc72-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 