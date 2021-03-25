---
title: 사용자를 위한 비즈니스용 Skype 2015 클라이언트 환경 계획
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '요약: 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015, Lync Server 2013 또는 Lync Server 2010을 사용 중이든, 새 비즈니스용 Skype 및 사용자에 대해 업데이트 준비를 위해 취할 수 있는 단계에 대해 자세히 알아보십시오.'
ms.openlocfilehash: 4f61876ab9826644fb7ef22db99d54adb2afe403
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112804"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a><span data-ttu-id="80af0-103">사용자를 위한 비즈니스용 Skype 2015 클라이언트 환경 계획</span><span class="sxs-lookup"><span data-stu-id="80af0-103">Plan the Skype for Business 2015 client experience for your users</span></span>
 
<span data-ttu-id="80af0-104">**요약:** 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015, Lync Server 2013 또는 Lync Server 2010을 사용 중이든, 새 비즈니스용 Skype 및 사용자에 대해 업데이트 준비를 위해 취할 수 있는 단계에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="80af0-104">**Summary:** Learn about the new Skype for Business and the steps you can take to prepare your environment and your users for the update, whether you're using Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013, or Lync Server 2010.</span></span>
  
<span data-ttu-id="80af0-105">Lync 2013용 Office 업데이트 2015년 4월 14일에는 새로운 비즈니스용 Skype 사용자 인터페이스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-105">The April 14th, 2015 Office Update for Lync 2013 includes the new Skype for Business user interface.</span></span> <span data-ttu-id="80af0-106">이 업데이트를 통해 관리자는 클라이언트의 모양과 느낌을 제어하고 Lync 2013 클라이언트 환경을 유지할지 또는 향상된 비즈니스용 Skype 클라이언트 환경을 사용할지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-106">This update enables administrators to control the look and feel of the client and choose whether to retain the Lync 2013 client experience or use the improved Skype for Business client experience.</span></span> <span data-ttu-id="80af0-107">비즈니스용 Skype 클라이언트는 Lync 2013 클라이언트를 효과적으로 대체하고 관리자가 기존 Lync 클라이언트 환경과 새로운 비즈니스용 Skype 클라이언트 환경 중 선택할 수 있는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-107">The Skype for Business client effectively replaced the Lync 2013 client, and added the ability for administrators to choose between the existing Lync client experience and the new Skype for Business client experience.</span></span> <span data-ttu-id="80af0-108">이 업데이트에 대한 자세한 내용은 [Lync 2013용 2015년 4월 14일 업데이트(비즈니스용 Skype)(KB2889923)를 참조하세요.](https://support.microsoft.com/kb/2889923/)</span><span class="sxs-lookup"><span data-stu-id="80af0-108">For information about this update, see [April 14, 2015 update for Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).</span></span>
  
<span data-ttu-id="80af0-109">2015년 5월 12일에는 업데이트된 비즈니스용 Skype 클라이언트를 포함하는 Office의 또 다른 월별 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-109">On May 12th, 2015 there will be another monthly update from Office that includes the updated Skype for Business client.</span></span> <span data-ttu-id="80af0-110">4월 업데이트를 적용하지 않은 많은 고객은 Office 2013의 5월 12일 업데이트를 선택하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-110">Many customers that did not apply the April update will pick up the May 12th update for Office 2013.</span></span> <span data-ttu-id="80af0-111">이 항목의 정보는 클라이언트 업데이트를 위해 조직, 환경 및 사용자를 준비하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-111">The information in this topic will help you prepare your organization, your environment, and your users for the client update.</span></span> <span data-ttu-id="80af0-112">사용자 및 지원 팀이 쉽게 전환할 수 있도록 이 항목의 정보를 사용하여 사용자에게 원하는 클라이언트 환경을 결정한 다음 조직에 클라이언트 업데이트를 배포하기 전에 환경을 변경하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-112">To make the transition easy for your users and support teams, use the information in this topic to help you decide which client experience you want for your users and then make the changes to your environment before deploying the client update in your organization.</span></span>
  
- [<span data-ttu-id="80af0-113">사용자에게 어떤 클라이언트 환경을 원하나요?</span><span class="sxs-lookup"><span data-stu-id="80af0-113">What client experience do you want for your users?</span></span>](user-experience.md#clientexperience)
    
- [<span data-ttu-id="80af0-114">비즈니스용 Skype 클라이언트에 대한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="80af0-114">Prepare your environment for the Skype for Business client</span></span>](user-experience.md#usinglync)
    
- [<span data-ttu-id="80af0-115">지원 팀과 최종 사용자가 업데이트를 준비하는 데 도움이 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="80af0-115">Resources to help you prepare your support teams and your end users for the update</span></span>](user-experience.md#support)
    
> [!NOTE]
> <span data-ttu-id="80af0-116">Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대한 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="80af0-117">Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않는지 확인하시기 바랍니다. 예: 16.x.x.x</span><span class="sxs-lookup"><span data-stu-id="80af0-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a><span data-ttu-id="80af0-118">사용자에게 어떤 클라이언트 환경을 원하나요?</span><span class="sxs-lookup"><span data-stu-id="80af0-118">What client experience do you want for your users?</span></span>
<span data-ttu-id="80af0-119"><a name="clientexperience"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-119"><a name="clientexperience"> </a></span></span>

<span data-ttu-id="80af0-120">새 비즈니스용 Skype 클라이언트를 사용하여 Lync 또는 비즈니스용 Skype 중 어떤 클라이언트 환경을 사용할지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-120">With the new Skype for Business client, you can control which client experience your users get, either Lync or Skype for Business.</span></span> <span data-ttu-id="80af0-121">기본 클라이언트 환경은 온-프레미스 또는 온라인에서 Lync 또는 비즈니스용 Skype를 사용하는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-121">The default client experience depends on whether you are using Lync or Skype for Business on-premises or online.</span></span> <span data-ttu-id="80af0-122">현재 비즈니스용 Skype Online(Lync Online)을 엔터프라이즈용 Microsoft 365 앱, Microsoft 365 Business Standard 또는 Office 2013과 함께 사용하는 경우 Skype의 모양과 느낌을 통해 업데이트된 비즈니스용 Skype 클라이언트 환경이 기본 사용자 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-122">If you are using Skype for Business Online (Lync Online) today with Microsoft 365 Apps for enterprise, Microsoft 365 Business Standard or Office 2013, the updated Skype for Business client experience—inspired by the look and feel of Skype—will be the default user experience.</span></span> <span data-ttu-id="80af0-123">현재 온-프레미스에서 Lync Server를 사용하는 경우 Lync 클라이언트 환경이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-123">If you are using Lync Server on-premises today, the Lync client experience will be the default.</span></span>
  
<span data-ttu-id="80af0-124">클라이언트 정책을 사용하여 사용자가 얻을 수 있는 클라이언트 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-124">You can configure which client experience your users get by using client policies.</span></span> <span data-ttu-id="80af0-125">클라이언트 정책은 사용자가 Lync 또는 비즈니스용 Skype에 로그인할 때 적용되는 구성 설정 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-125">A client policy is a set of configuration settings that are applied to users when they login to Lync or Skype for Business.</span></span>
  
### <a name="skype-for-business-client-experience"></a><span data-ttu-id="80af0-126">비즈니스용 Skype 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="80af0-126">Skype for Business client experience</span></span>

<span data-ttu-id="80af0-127">비즈니스용 Skype는 Lync의 모든 기능 외에도 Skype의 간소화된 컨트롤 및 친숙한 아이콘이 있는 새로운 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-127">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons from Skype.</span></span> <span data-ttu-id="80af0-128">비즈니스용 Skype의 일부 새로운 기능은 새 비즈니스용 Skype 클라이언트 환경에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-128">Some new features in Skype for Business are available only with the new Skype for Business client experience.</span></span> <span data-ttu-id="80af0-129">비즈니스용 Skype의 새로운 기능에 대한 자세한 내용은 [비즈니스용 Skype 검색을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=528686)</span><span class="sxs-lookup"><span data-stu-id="80af0-129">To learn more about the new features in Skype for Business, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).</span></span>
  
### <a name="lync-client-experience"></a><span data-ttu-id="80af0-130">Lync 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="80af0-130">Lync client experience</span></span>

<span data-ttu-id="80af0-131">Lync 클라이언트 환경은 사용자가 이미 익숙한 Lync 2013 클라이언트 환경과 매우 유사하지만 사용자에게 알려야 할 몇 가지 변경 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-131">The Lync client experience is very similar to the Lync 2013 client experience that your users are already familiar with, but there are a few changes that you'll want to let your users know about.</span></span> <span data-ttu-id="80af0-132">Lync 클라이언트 환경과 Lync 2013 클라이언트 간의 다른 기능을 보시겠습니까? [Lync를](https://go.microsoft.com/fwlink/p/?LinkId=544712) 사용할 때 비즈니스용 Skype가 표시되는 이유는 무엇일까요? 및 이 항목의 뒤에 있는 추가 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80af0-132">To see what's different between the Lync client experience and the Lync 2013 client, see [Why do I see Skype for Business when I'm using Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) and the additional links later in this topic.</span></span>
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a><span data-ttu-id="80af0-133">비즈니스용 Skype 클라이언트에 대한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="80af0-133">Prepare your environment for the Skype for Business client</span></span>
<span data-ttu-id="80af0-134"><a name="usinglync"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-134"><a name="usinglync"> </a></span></span>

<span data-ttu-id="80af0-135">클라이언트 업데이트에 대한 환경을 준비하기 위해 몇 가지 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-135">There are a few things you'll need to do to get your environment ready for the client update.</span></span> <span data-ttu-id="80af0-136">클라이언트 환경을 구성하기 위해 변경을 시작하기 전에 먼저 클라이언트 정책 설정을 지원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-136">Before you start making any changes to configure the client experience, you first need to make sure that you are using a version of Skype for Business Server or Lync Server that supports the client policy settings.</span></span>
  
<span data-ttu-id="80af0-137">정책 설정을 지원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용하여 클라이언트 환경을 제어하는지 확인한 후 환경에서 정책 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-137">Once you've confirmed that you're using a version of Skype for Business Server or Lync Server that supports the policy settings to control the client experience, you'll need to configure the policy settings in your environment.</span></span> <span data-ttu-id="80af0-138">따라야 하는 특정 단계는 사용중인 비즈니스용 Skype 서버 또는 Lync Server 버전과 사용자가 온-프레미스인지 온라인인지에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-138">The specific steps you need to follow depend on the version of Skype for Business Server or Lync Server that you are using, and whether your users are on-premises or online.</span></span> 
  
<span data-ttu-id="80af0-139">사용자가 비즈니스용 Skype 클라이언트를 처음 시작할 때부터 클라이언트 환경을 제어할 수 있도록 클라이언트 업데이트가 사용자에게 전달되기 전에 이러한 변경을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-139">You'll want to make these changes before the client update is delivered to your users so that you can control the client experience from the first time they start the Skype for Business client.</span></span> <span data-ttu-id="80af0-140">다음 표에서는 사용자에 대해 원하는 클라이언트 환경에 맞게 환경을 구성하기 위해 필요한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-140">The following tables points you to the steps you need to take to configure your environment for the desired client experience for your users.</span></span>
  
|<span data-ttu-id="80af0-141">**배포**</span><span class="sxs-lookup"><span data-stu-id="80af0-141">**Deployment**</span></span>|<span data-ttu-id="80af0-142">**비즈니스용 Skype 클라이언트 환경**</span><span class="sxs-lookup"><span data-stu-id="80af0-142">**Skype for Business client experience**</span></span>|<span data-ttu-id="80af0-143">**Lync 클라이언트 환경**</span><span class="sxs-lookup"><span data-stu-id="80af0-143">**Lync client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80af0-144">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="80af0-144">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="80af0-145">클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포하는 것 외의 추가 단계는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-145">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="80af0-146">비즈니스용 Skype Online에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-146">Use the Lync client experience with Skype for Business Online</span></span>](user-experience.md#LyncwithSfBO) <br/> |
|<span data-ttu-id="80af0-147">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="80af0-147">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="80af0-148">클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포하는 것 외의 추가 단계는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-148">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="80af0-149">비즈니스용 Skype 서버 온-프레미스에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-149">Use the Lync client experience with Skype for Business Server on-premises</span></span>](user-experience.md#LyncwithSfBServer) <br/> |
|<span data-ttu-id="80af0-150">Lync Server 2013 및 Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="80af0-150">Lync Server 2013 and Lync Server 2010</span></span>  <br/> |[<span data-ttu-id="80af0-151">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-151">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#SkypewithLynconprem) <br/> |[<span data-ttu-id="80af0-152">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-152">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="80af0-153">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-153">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="80af0-154"><a name="SkypewithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-154"><a name="SkypewithLynconprem"> </a></span></span>

<span data-ttu-id="80af0-155">사내 배포에서 Skype 클라이언트 환경을 구성하려는 경우 이 섹션의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-155">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment.</span></span> <span data-ttu-id="80af0-156">On-premises의 기본 환경</span><span class="sxs-lookup"><span data-stu-id="80af0-156">The default experience for on-premises</span></span>
  
 <span data-ttu-id="80af0-157">**1단계:** 먼저 클라이언트 정책 설정을 지원하는 Lync Server 버전을 실행하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-157">**Step 1:** First, make sure you are running a version of Lync Server that supports the client policy settings.</span></span>
  
- <span data-ttu-id="80af0-158">**Lync Server 2013** - Lync Server 2013 이상 업데이트에 대한 2014년 12월 누적 업데이트(5.0.8308.857)를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-158">**Lync Server 2013** - You must be running the December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013 or a later update.</span></span> <span data-ttu-id="80af0-159">자세한 내용은 [Updates for Lync Server 2013을 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=532772)</span><span class="sxs-lookup"><span data-stu-id="80af0-159">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
- <span data-ttu-id="80af0-160">**Lync Server 2010 - Lync Server 2010** 이상 업데이트에 대한 2015년 2월 누적 업데이트(4.0.7577.710)를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-160">**Lync Server 2010** - You must be running the February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010 or a later update.</span></span> <span data-ttu-id="80af0-161">자세한 내용은 [Updates for Lync Server 2010을 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="80af0-161">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).</span></span>
    
  <span data-ttu-id="80af0-162">**2단계:** 다음으로, 클라이언트 정책을 사용하여 비즈니스용 Skype 클라이언트를 사용하여 Skype 클라이언트 환경을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-162">**Step 2:** Next, use a client policy to set the Skype client experience with the Skype for Business client.</span></span> <span data-ttu-id="80af0-163">클라이언트 정책을 **사용하여** 클라이언트 환경을 설정하는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-163">There are **3 options** for using a client policy to set the client experience.</span></span>
  
  <span data-ttu-id="80af0-164">**옵션 1:** 전역 정책을 사용하여 Skype 클라이언트 환경을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-164">**Option 1:** Set the Skype client experience by using a Global policy.</span></span> <span data-ttu-id="80af0-165">전역 정책은 배포의 모든 사용자에게 적용되지만 사용자 및 사이트 수준 정책은 전역 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-165">Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 <span data-ttu-id="80af0-166">**옵션 2:** 환경에서 사용하는 기존 클라이언트 정책을 수정하여 Skype 클라이언트 환경을 사용하도록 설정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-166">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Skype client experience.</span></span> <span data-ttu-id="80af0-167">이렇게 하면 기존 정책이 할당된 사용자에게만 Skype 클라이언트 환경을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-167">This lets you assign the Skype client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 <span data-ttu-id="80af0-168">**옵션 3:** Skype 클라이언트 환경 설정이 포함된 사용자에게 할당할 새 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-168">**Option 3:** Create a new policy to assign to users that includes the setting for the Skype client experience.</span></span> <span data-ttu-id="80af0-169">먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수 값으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-169">First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

<span data-ttu-id="80af0-170">그런 다음 **PolicyName** 매개 변수의 값으로 정책 **이름(Identity** 매개 변수에 사용한 값)을 사용하여 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-170">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 <span data-ttu-id="80af0-171">**3단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-171">**Step 3:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="80af0-172">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-172">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="80af0-173"><a name="LyncwithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-173"><a name="LyncwithLynconprem"> </a></span></span>

<span data-ttu-id="80af0-174">이는 비즈니스용 Skype 클라이언트가 온-프레미스 Lync Server 배포에 배포될 때의 기본 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-174">This is the default experience when the Skype for Business client is deployed in an on-premises Lync Server deployment.</span></span> <span data-ttu-id="80af0-175">Lync 클라이언트 환경을 사용하도록 클라이언트 정책을 구성할 필요는 없지만 클라이언트의 첫 번째 실행 동작을 제어해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-175">You don't need to configure any client policies to use the Lync client experience, but you may want to control the first run behavior for the client.</span></span> <span data-ttu-id="80af0-176">기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작하면 Skype 클라이언트 환경이 사용되고 Lync 클라이언트 환경을 얻기 위해 클라이언트를 다시 시작해야 하다는 알림이 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-176">By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users that requests that they restart the client to get the Lync client experience.</span></span> <span data-ttu-id="80af0-177">사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시되고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정하여 클라이언트 자습서를 해제하도록 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-177">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial by modifying the system registry on client computers.</span></span> <span data-ttu-id="80af0-178">비즈니스용 Skype 클라이언트를 배포하기 전에 수행해야 하는 단계는 다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80af0-178">For the steps you need to perform before you deploy the Skype for Business client, see one of the following topics:</span></span>
  
- <span data-ttu-id="80af0-179">**Lync Server 2013**, [Configure the client experience with Skype for Business in Lync Server 2013을 참조하세요.](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)</span><span class="sxs-lookup"><span data-stu-id="80af0-179">**Lync Server 2013**, see [Configure the client experience with Skype for Business in Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)</span></span>
    
- <span data-ttu-id="80af0-180">**Lync Server 2010은** [Configure the client experience with Skype for Business in Lync Server 2010을 참조하세요.](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="80af0-180">**Lync Server 2010** see [Configure the client experience with Skype for Business in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))</span></span>
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a><span data-ttu-id="80af0-181">비즈니스용 Skype 서버 온-프레미스에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-181">Use the Lync client experience with Skype for Business Server on-premises</span></span>
<span data-ttu-id="80af0-182"><a name="LyncwithSfBServer"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-182"><a name="LyncwithSfBServer"> </a></span></span>

<span data-ttu-id="80af0-183">온-프레미스 비즈니스용 Skype 서버 배포에서 Lync 클라이언트 환경을 구성하려는 경우 이 섹션의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-183">Follow the steps in this section if you want to configure the Lync client experience in an on-premises Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="80af0-184">사내 배포에서 Skype 클라이언트 환경을 구성하려는 경우 이 섹션의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-184">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment.</span></span> <span data-ttu-id="80af0-185">On-premises의 기본 환경</span><span class="sxs-lookup"><span data-stu-id="80af0-185">The default experience for on-premises</span></span>
  
 <span data-ttu-id="80af0-186">**1단계:** 먼저 비즈니스용 Skype 서버를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-186">**Step 1:** First, deploy Skype for Business Server.</span></span>
  
 <span data-ttu-id="80af0-187">**2단계:** 그런 다음 클라이언트 정책을 사용하여 비즈니스용 Skype 클라이언트에서 Lync 클라이언트 환경을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-187">**Step 2:** Next, use a client policy to set the Lync client experience with the Skype for Business client.</span></span> <span data-ttu-id="80af0-188">클라이언트 정책을 **사용하여** 클라이언트 환경을 설정하는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-188">There are **3 options** for using a client policy to set the client experience.</span></span>
  
 <span data-ttu-id="80af0-189">**옵션 1:** 전역 정책을 사용하여 Lync 클라이언트 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-189">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="80af0-190">전역 정책은 배포의 모든 사용자에게 적용되지만 사용자 및 사이트 수준 정책은 전역 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-190">Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 <span data-ttu-id="80af0-191">**옵션 2:** Lync 클라이언트 환경을 사용하도록 설정하는 설정을 포함하도록 환경에서 사용하는 기존 클라이언트 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-191">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience.</span></span> <span data-ttu-id="80af0-192">이렇게 하면 기존 정책이 할당된 사용자에게만 Lync 클라이언트 환경을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-192">This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 <span data-ttu-id="80af0-193">**옵션 3:** Lync 클라이언트 환경 설정이 포함된 사용자에게 할당할 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-193">**Option 3:** Create a new policy to assign to users that includes the setting for the Lync client experience.</span></span> <span data-ttu-id="80af0-194">먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수 값으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-194">First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

<span data-ttu-id="80af0-195">그런 다음 **PolicyName** 매개 변수의 값으로 정책 **이름(Identity** 매개 변수에 사용한 값)을 사용하여 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-195">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 <span data-ttu-id="80af0-196">**3단계:** 선택 사항 - 기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작할 때 Skype 클라이언트 환경이 사용되고 Lync 클라이언트 환경을 얻기 위해 클라이언트를 다시 시작해야 하는 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-196">**Step 3: Optional** - By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users asking them to restart the client to get the Lync client experience.</span></span> <span data-ttu-id="80af0-197">사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시되고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정하여 클라이언트 자습서를 해제하도록 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-197">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial, by modifying the system registry on client computers.</span></span> <span data-ttu-id="80af0-198">비즈니스용 Skype 클라이언트를 배포하기 전에 수행해야 하는 단계는 비즈니스용 Skype를 통해 클라이언트 [환경 구성을 참조하세요.](../../deploy/deploy-clients/configure-the-client-experience.md)</span><span class="sxs-lookup"><span data-stu-id="80af0-198">For the steps you need to perform before you deploy the Skype for Business client see [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).</span></span>
  
 <span data-ttu-id="80af0-199">**4단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-199">**Step 4:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a><span data-ttu-id="80af0-200">비즈니스용 Skype Online에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="80af0-200">Use the Lync client experience with Skype for Business Online</span></span>
<span data-ttu-id="80af0-201"><a name="LyncwithSfBO"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-201"><a name="LyncwithSfBO"> </a></span></span>

<span data-ttu-id="80af0-202">Lync 클라이언트 환경을 구성하고 비즈니스용 Skype Online을 사용하려는 경우 이 섹션의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-202">Follow the steps in this section if you want to configure the Lync client experience and you using Skype for Business Online.</span></span>
  
<span data-ttu-id="80af0-203">비즈니스용 Skype Online을 사용하는 경우 원격 PowerShell을 사용하여 클라이언트 정책을 구성하여 조직의 비즈니스용 Skype 클라이언트에서 Lync 클라이언트 환경을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-203">If you are using Skype for Business Online, you can still use the Lync client experience with the Skype for Business client in your organization by using Remote PowerShell to configure client policies.</span></span> <span data-ttu-id="80af0-204">클라이언트 정책을 **사용하여** 클라이언트 환경을 설정하는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-204">There are **3 options** for using a client policy to set the client experience.</span></span> <span data-ttu-id="80af0-205">정책 및 매개 변수 이름은 비즈니스용 Skype 또는 Lync Server 온-프레미스를 사용할 때 클라이언트 환경을 구성하는 데 사용하는 설정과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-205">Note that the policy and parameter names are different than the settings you use to configure the client experience when you are using Skype for Business or Lync Server on-premises.</span></span>
  
 <span data-ttu-id="80af0-206">**옵션 1:** 전역 정책을 사용하여 Lync 클라이언트 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-206">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="80af0-207">사용자에게 적용된 클라이언트 및 사이트 정책은 전역 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-207">Note that client and site policies applied to users will take precedence over a Global policy.</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="80af0-208">**옵션 2:** Lync 클라이언트 환경을 사용하도록 설정하는 설정을 포함하도록 환경에서 사용하는 기존 클라이언트 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-208">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience.</span></span> <span data-ttu-id="80af0-209">이렇게 하면 기존 정책이 할당된 사용자에게만 Lync 클라이언트 환경을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-209">This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="80af0-210">**옵션 3:** Lync 클라이언트 환경의 설정을 포함하는 사용자 지정 정책 인스턴스를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="80af0-210">**Option 3:** Use a custom policy instance that includes the setting for the Lync client experience.</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

<span data-ttu-id="80af0-211">클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-211">After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
<span data-ttu-id="80af0-212">첫 실행 환경을 제어하는 방법 및 환경을 구성하는 데 사용할 수 있는 PowerShell 스크립트를 포함하여 비즈니스용 Skype Online을 사용하여 클라이언트 환경을 구성하는 방법에 대한 자세한 내용은 비즈니스용 [Skype와 Lync](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)클라이언트 사용자 인터페이스 간 전환을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80af0-212">For detailed information about how to configure the client experience with Skype for Business Online, including steps about how to control the first run experience and PowerShell scripts you can use to configure your environment, see [Switching between the Skype for Business and the Lync client user interfaces](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md).</span></span>
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a><span data-ttu-id="80af0-213">지원 팀과 최종 사용자가 업데이트를 준비하는 데 도움이 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="80af0-213">Resources to help you prepare your support teams and your end users for the update</span></span>
<span data-ttu-id="80af0-214"><a name="support"> </a></span><span class="sxs-lookup"><span data-stu-id="80af0-214"><a name="support"> </a></span></span>

<span data-ttu-id="80af0-215">사용자와 조직이 보다 쉽게 전환을 준비할 수 있도록 최종 사용자를 계획, 교육 및 참여하는 데 도움이 되는 많은 추가 리소스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af0-215">To make it easier for you and your organization prepare for the transition, we have many additional resources available to help you plan, educate and engage end-users.</span></span>
  
- [<span data-ttu-id="80af0-216">비디오: 비즈니스용 Skype 소개</span><span class="sxs-lookup"><span data-stu-id="80af0-216">Video: Introducing Skype for Business</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [<span data-ttu-id="80af0-217">비즈니스용 Skype 빠른 시작 가이드(다운로드)</span><span class="sxs-lookup"><span data-stu-id="80af0-217">Skype for Business Quick Start Guides (Download)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [<span data-ttu-id="80af0-218">Lync는 이제 비즈니스용 Skype입니다. 새로운 것을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80af0-218">Lync is now Skype for Business — see what's new</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [<span data-ttu-id="80af0-219">비즈니스용 Skype: 새 사용자를 위한 단계별 가이드</span><span class="sxs-lookup"><span data-stu-id="80af0-219">Skype for Business: Step-by-step guide for new users</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [<span data-ttu-id="80af0-220">Lync를 사용할 때 비즈니스용 Skype가 표시하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="80af0-220">Why do I see Skype for Business when I'm using Lync?</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=544712)
