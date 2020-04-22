---
title: 사용자를 위한 비즈니스용 Skype 2015 클라이언트 환경 계획
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 skype에 대 한 새로운 비즈니스 및 사용자가 온라인으로 Skype를 사용 하 고 있는지 여부, 비즈니스용 skype 서버 2019, 비즈니스용 Skype 서버 2015, lync server 2013 또는 Lync Server 2010에 대 한 업데이트를 준비 하기 위해 수행 해야 하는 단계와 환경에 대해 알아봅니다.'
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777753"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a><span data-ttu-id="09a52-103">사용자를 위한 비즈니스용 Skype 2015 클라이언트 환경 계획</span><span class="sxs-lookup"><span data-stu-id="09a52-103">Plan the Skype for Business 2015 client experience for your users</span></span>
 
<span data-ttu-id="09a52-104">**요약:** 비즈니스용 skype에 대 한 새로운 비즈니스 및 사용자가 온라인으로 Skype를 사용 하 고 있는지 여부, 비즈니스용 skype 서버 2019, 비즈니스용 Skype 서버 2013 2015, lync server 2010 등의 작업을 준비 하기 위해 수행할 수 있는 단계와 환경에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-104">**Summary:** Learn about the new Skype for Business and the steps you can take to prepare your environment and your users for the update, whether you're using Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013, or Lync Server 2010.</span></span>
  
<span data-ttu-id="09a52-105">Lync 2013의 4 월 14th, 2015 Office 업데이트에는 새로운 비즈니스용 Skype 사용자 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-105">The April 14th, 2015 Office Update for Lync 2013 includes the new Skype for Business user interface.</span></span> <span data-ttu-id="09a52-106">관리자는이 업데이트를 사용 하 여 클라이언트의 디자인을 제어 하 고 Lync 2013 클라이언트 환경을 유지할지 또는 향상 된 비즈니스용 Skype 클라이언트 환경을 사용할지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-106">This update enables administrators to control the look and feel of the client and choose whether to retain the Lync 2013 client experience or use the improved Skype for Business client experience.</span></span> <span data-ttu-id="09a52-107">비즈니스용 Skype 클라이언트는 Lync 2013 클라이언트를 효과적으로 교체 했으며 관리자가 기존 Lync 클라이언트 환경 및 새로운 비즈니스용 Skype 클라이언트 환경 중에서 선택할 수 있는 기능을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-107">The Skype for Business client effectively replaced the Lync 2013 client, and added the ability for administrators to choose between the existing Lync client experience and the new Skype for Business client experience.</span></span> <span data-ttu-id="09a52-108">이 업데이트에 대 한 자세한 내용은 [4 월 14 일 2015 업데이트 For Lync 2013 (비즈니스용 Skype) (KB2889923)](https://support.microsoft.com/kb/2889923/)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09a52-108">For information about this update, see [April 14, 2015 update for Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).</span></span>
  
<span data-ttu-id="09a52-109">5 월 12 일 2015 업데이트 된 비즈니스용 Skype 클라이언트를 포함 하는 또 다른 월별 업데이트가 Office에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-109">On May 12th, 2015 there will be another monthly update from Office that includes the updated Skype for Business client.</span></span> <span data-ttu-id="09a52-110">4 월 업데이트를 적용 하지 않은 대부분의 고객은 Office 2013의 12 월 업데이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-110">Many customers that did not apply the April update will pick up the May 12th update for Office 2013.</span></span> <span data-ttu-id="09a52-111">이 항목의 정보는 조직, 환경 및 사용자가 클라이언트 업데이트를 준비 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-111">The information in this topic will help you prepare your organization, your environment, and your users for the client update.</span></span> <span data-ttu-id="09a52-112">사용자 및 지원 팀이 쉽게 전환할 수 있도록 하려면이 항목의 정보를 참조 하 여 조직에서 클라이언트 업데이트를 배포 하기 전에 사용자에 게 적용할 클라이언트 환경을 결정 하 고 환경을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-112">To make the transition easy for your users and support teams, use the information in this topic to help you decide which client experience you want for your users and then make the changes to your environment before deploying the client update in your organization.</span></span>
  
- [<span data-ttu-id="09a52-113">사용자에 게 필요한 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="09a52-113">What client experience do you want for your users?</span></span>](user-experience.md#clientexperience)
    
- [<span data-ttu-id="09a52-114">비즈니스용 Skype 클라이언트에 대 한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="09a52-114">Prepare your environment for the Skype for Business client</span></span>](user-experience.md#usinglync)
    
- [<span data-ttu-id="09a52-115">업데이트를 위해 지원 팀과 최종 사용자를 준비 하는 데 도움이 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="09a52-115">Resources to help you prepare your support teams and your end users for the update</span></span>](user-experience.md#support)
    
> [!NOTE]
> <span data-ttu-id="09a52-116">Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="09a52-117">클라이언트 환경에서 Lync 2013 클라이언트를 사용 하도록 구성 하기 전에 클라이언트 버전에서 번호 16으로 시작 하지 않는지 확인 하십시오. 예: x.x.x.</span><span class="sxs-lookup"><span data-stu-id="09a52-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a><span data-ttu-id="09a52-118">사용자에 게 필요한 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="09a52-118">What client experience do you want for your users?</span></span>
<span data-ttu-id="09a52-119"><a name="clientexperience"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-119"><a name="clientexperience"> </a></span></span>

<span data-ttu-id="09a52-120">새로운 비즈니스용 Skype 클라이언트를 사용 하 여 Lync 또는 비즈니스용 Skype 중에서 사용자에 게 제공 되는 클라이언트 환경을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-120">With the new Skype for Business client, you can control which client experience your users get, either Lync or Skype for Business.</span></span> <span data-ttu-id="09a52-121">기본 클라이언트 환경은 Lync 또는 비즈니스용 Skype 온-프레미스를 사용 중인지, 아니면 온라인 상태에 있는지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-121">The default client experience depends on whether you are using Lync or Skype for Business on-premises or online.</span></span> <span data-ttu-id="09a52-122">비즈니스용 Skype Online (Lync Online)을 사용 하는 경우 microsoft 365 Apps for enterprise (Microsoft 365 Business Standard 또는 Office 2013)를 사용할 경우 업데이트 된 비즈니스용 Skype 클라이언트 환경 (Skype의 모양과 느낌에 따라)이 기본 사용자 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-122">If you are using Skype for Business Online (Lync Online) today with Microsoft 365 Apps for enterprise, Microsoft 365 Business Standard or Office 2013, the updated Skype for Business client experience—inspired by the look and feel of Skype—will be the default user experience.</span></span> <span data-ttu-id="09a52-123">현재 Lync Server 온-프레미스를 사용 하는 경우 Lync 클라이언트 환경이 기본이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-123">If you are using Lync Server on-premises today, the Lync client experience will be the default.</span></span>
  
<span data-ttu-id="09a52-124">클라이언트 정책을 사용 하 여 사용자에 게 제공 되는 클라이언트 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-124">You can configure which client experience your users get by using client policies.</span></span> <span data-ttu-id="09a52-125">클라이언트 정책은 Lync 또는 비즈니스용 Skype에 로그인 할 때 사용자에 게 적용 되는 구성 설정 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-125">A client policy is a set of configuration settings that are applied to users when they login to Lync or Skype for Business.</span></span>
  
### <a name="skype-for-business-client-experience"></a><span data-ttu-id="09a52-126">비즈니스용 Skype 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="09a52-126">Skype for Business client experience</span></span>

<span data-ttu-id="09a52-127">Lync의 모든 기능 외에도 비즈니스용 Skype에서는 간소화 된 컨트롤 및 Skype의 익숙한 아이콘을 포함 하는 새로운 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-127">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons from Skype.</span></span> <span data-ttu-id="09a52-128">비즈니스용 Skype의 몇 가지 새로운 기능은 새로운 비즈니스용 Skype 클라이언트 환경 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-128">Some new features in Skype for Business are available only with the new Skype for Business client experience.</span></span> <span data-ttu-id="09a52-129">비즈니스용 Skype의 새로운 기능에 대 한 자세한 내용은 [비즈니스용 Skype 검색](https://go.microsoft.com/fwlink/p/?LinkId=528686)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-129">To learn more about the new features in Skype for Business, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).</span></span>
  
### <a name="lync-client-experience"></a><span data-ttu-id="09a52-130">Lync 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="09a52-130">Lync client experience</span></span>

<span data-ttu-id="09a52-131">Lync 클라이언트 환경은 사용자가 이미 익숙한 Lync 2013 클라이언트 환경과 매우 유사 하지만 사용자에 게 알리기 위해 몇 가지 사항을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-131">The Lync client experience is very similar to the Lync 2013 client experience that your users are already familiar with, but there are a few changes that you'll want to let your users know about.</span></span> <span data-ttu-id="09a52-132">Lync 클라이언트 환경과 Lync 2013 클라이언트의 차이점을 확인 하려면 [왜 lync 사용 중 비즈니스용 Skype가 표시 되는 이유는 무엇 인가요?](https://go.microsoft.com/fwlink/p/?LinkId=544712) 그리고이 항목의 뒷부분에 나오는 추가 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-132">To see what's different between the Lync client experience and the Lync 2013 client, see [Why do I see Skype for Business when I'm using Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) and the additional links later in this topic.</span></span>
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a><span data-ttu-id="09a52-133">비즈니스용 Skype 클라이언트에 대 한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="09a52-133">Prepare your environment for the Skype for Business client</span></span>
<span data-ttu-id="09a52-134"><a name="usinglync"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-134"><a name="usinglync"> </a></span></span>

<span data-ttu-id="09a52-135">환경에서 클라이언트 업데이트를 준비 하려면 몇 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-135">There are a few things you'll need to do to get your environment ready for the client update.</span></span> <span data-ttu-id="09a52-136">클라이언트 환경 구성에 대 한 변경 작업을 시작 하기 전에 먼저 클라이언트 정책 설정을 지 원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-136">Before you start making any changes to configure the client experience, you first need to make sure that you are using a version of Skype for Business Server or Lync Server that supports the client policy settings.</span></span>
  
<span data-ttu-id="09a52-137">클라이언트 환경을 제어 하기 위해 정책 설정을 지 원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용 하 고 있는지 확인 한 후에는 해당 환경에서 정책 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-137">Once you've confirmed that you're using a version of Skype for Business Server or Lync Server that supports the policy settings to control the client experience, you'll need to configure the policy settings in your environment.</span></span> <span data-ttu-id="09a52-138">수행 해야 하는 구체적인 단계는 사용 중인 비즈니스용 Skype 서버 또는 Lync Server의 버전과 사용자가 온-프레미스 또는 온라인 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-138">The specific steps you need to follow depend on the version of Skype for Business Server or Lync Server that you are using, and whether your users are on-premises or online.</span></span> 
  
<span data-ttu-id="09a52-139">클라이언트 환경을 사용자에 게 제공 하기 전에 이러한 변경 작업을 수행 하 여 먼저 비즈니스용 Skype 클라이언트를 시작할 때부터 클라이언트 환경을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-139">You'll want to make these changes before the client update is delivered to your users so that you can control the client experience from the first time they start the Skype for Business client.</span></span> <span data-ttu-id="09a52-140">다음 표에서는 사용자를 위해 원하는 클라이언트 환경에 맞게 환경을 구성 하기 위해 수행 해야 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-140">The following tables points you to the steps you need to take to configure your environment for the desired client experience for your users.</span></span>
  
|<span data-ttu-id="09a52-141">**배포**</span><span class="sxs-lookup"><span data-stu-id="09a52-141">**Deployment**</span></span>|<span data-ttu-id="09a52-142">**비즈니스용 Skype 클라이언트 환경**</span><span class="sxs-lookup"><span data-stu-id="09a52-142">**Skype for Business client experience**</span></span>|<span data-ttu-id="09a52-143">**Lync 클라이언트 환경**</span><span class="sxs-lookup"><span data-stu-id="09a52-143">**Lync client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09a52-144">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="09a52-144">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="09a52-145">클라이언트 빌드 4711.1002 (4 월, 2015) 이상을 배포 하는 것 외에는 추가 단계가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-145">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="09a52-146">비즈니스용 Skype 온라인에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="09a52-146">Use the Lync client experience with Skype for Business Online</span></span>](user-experience.md#LyncwithSfBO) <br/> |
|<span data-ttu-id="09a52-147">비즈니스용 Skype 서버 2015</span><span class="sxs-lookup"><span data-stu-id="09a52-147">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="09a52-148">클라이언트 빌드 4711.1002 (4 월, 2015) 이상을 배포 하는 것 외에는 추가 단계가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-148">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="09a52-149">Lync 클라이언트 환경 사용 (비즈니스용 Skype 서버에서 온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="09a52-149">Use the Lync client experience with Skype for Business Server on-premises</span></span>](user-experience.md#LyncwithSfBServer) <br/> |
|<span data-ttu-id="09a52-150">Lync Server 2013 및 Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="09a52-150">Lync Server 2013 and Lync Server 2010</span></span>  <br/> |[<span data-ttu-id="09a52-151">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="09a52-151">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#SkypewithLynconprem) <br/> |[<span data-ttu-id="09a52-152">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="09a52-152">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="09a52-153">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="09a52-153">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="09a52-154"><a name="SkypewithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-154"><a name="SkypewithLynconprem"> </a></span></span>

<span data-ttu-id="09a52-155">온-프레미스 배포에서 Skype 클라이언트 환경을 구성 하려면이 섹션의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-155">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment.</span></span> <span data-ttu-id="09a52-156">온-프레미스의 기본 환경</span><span class="sxs-lookup"><span data-stu-id="09a52-156">The default experience for on-premises</span></span>
  
 <span data-ttu-id="09a52-157">**1 단계:** 먼저 클라이언트 정책 설정을 지 원하는 Lync Server 버전을 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-157">**Step 1:** First, make sure you are running a version of Lync Server that supports the client policy settings.</span></span>
  
- <span data-ttu-id="09a52-158">**Lync server 2013** -lync server 2013 이상 업데이트의 경우 12 월 2014 5.0.8308.857 (누적 업데이트)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-158">**Lync Server 2013** - You must be running the December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013 or a later update.</span></span> <span data-ttu-id="09a52-159">자세한 내용은 [Lync Server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532772)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-159">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
- <span data-ttu-id="09a52-160">**Lync server 2010** -lync server 2010 이상 업데이트에 대해 2 월 2015 4.0.7577.710 (누적 업데이트)를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-160">**Lync Server 2010** - You must be running the February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010 or a later update.</span></span> <span data-ttu-id="09a52-161">자세한 내용은 [Lync Server 2010에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532771)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-161">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).</span></span>
    
  <span data-ttu-id="09a52-162">**2 단계:** 다음으로, 클라이언트 정책을 사용 하 여 비즈니스용 Skype 클라이언트에서 Skype 클라이언트 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-162">**Step 2:** Next, use a client policy to set the Skype client experience with the Skype for Business client.</span></span> <span data-ttu-id="09a52-163">클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하기 위한 옵션에는 **3** 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-163">There are **3 options** for using a client policy to set the client experience.</span></span>
  
  <span data-ttu-id="09a52-164">**옵션 1:** 글로벌 정책을 사용 하 여 Skype 클라이언트 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-164">**Option 1:** Set the Skype client experience by using a Global policy.</span></span> <span data-ttu-id="09a52-165">전역 정책은 배포의 모든 사용자에 게 적용 되지만, 사용자 및 사이트 수준 정책은 글로벌 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-165">Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 <span data-ttu-id="09a52-166">**옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Skype 클라이언트 환경을 사용 하도록 설정할 수 있는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-166">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Skype client experience.</span></span> <span data-ttu-id="09a52-167">이렇게 하면 기존 정책이 할당 된 사용자 에게만 Skype 클라이언트 환경을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-167">This lets you assign the Skype client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 <span data-ttu-id="09a52-168">**옵션 3:** Skype 클라이언트 환경에 대 한 설정을 포함 하는 사용자에 게 할당할 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-168">**Option 3:** Create a new policy to assign to users that includes the setting for the Skype client experience.</span></span> <span data-ttu-id="09a52-169">먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수의 값으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-169">First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

<span data-ttu-id="09a52-170">그런 다음 정책 이름 ( **Identity** 매개 변수에 사용 된 값)을 사용 하 여 **PolicyName** 매개 변수의 값으로 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-170">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 <span data-ttu-id="09a52-171">**3 단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트를 배포 하 고 빌드 4711.1002 (4 월, 2015) 이상을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-171">**Step 3:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="09a52-172">Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="09a52-172">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="09a52-173"><a name="LyncwithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-173"><a name="LyncwithLynconprem"> </a></span></span>

<span data-ttu-id="09a52-174">이는 비즈니스용 Skype 클라이언트를 온-프레미스 Lync Server 배포에 배포할 때 기본으로 사용 되는 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-174">This is the default experience when the Skype for Business client is deployed in an on-premises Lync Server deployment.</span></span> <span data-ttu-id="09a52-175">Lync 클라이언트 환경을 사용 하기 위해 클라이언트 정책을 구성할 필요는 없지만 클라이언트에 대 한 첫 번째 실행 동작을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-175">You don't need to configure any client policies to use the Lync client experience, but you may want to control the first run behavior for the client.</span></span> <span data-ttu-id="09a52-176">기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하면 Skype 클라이언트 환경이 사용 되며, 사용자에 게 클라이언트를 다시 시작 하 여 Lync 클라이언트 환경을 가져오기 위해 요청 하는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-176">By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users that requests that they restart the client to get the Lync client experience.</span></span> <span data-ttu-id="09a52-177">사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 하 고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정 하 여 클라이언트 자습서를 끌 수 있도록 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-177">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial by modifying the system registry on client computers.</span></span> <span data-ttu-id="09a52-178">비즈니스용 Skype 클라이언트를 배포 하기 전에 수행 해야 하는 단계는 다음 항목 중 하나를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09a52-178">For the steps you need to perform before you deploy the Skype for Business client, see one of the following topics:</span></span>
  
- <span data-ttu-id="09a52-179">**Lync server 2013**에 [대 한 자세한 내용은 lync Server 2013에서 비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성](https://go.microsoft.com/fwlink/p/?LinkId=532732) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-179">**Lync Server 2013**, see [Configure the client experience with Skype for Business in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)</span></span>
    
- <span data-ttu-id="09a52-180">**Lync server 2010** [lync Server 2010에서 비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성](https://go.microsoft.com/fwlink/p/?LinkId=532733) 참조</span><span class="sxs-lookup"><span data-stu-id="09a52-180">**Lync Server 2010** see [Configure the client experience with Skype for Business in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)</span></span>
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a><span data-ttu-id="09a52-181">Lync 클라이언트 환경 사용 (비즈니스용 Skype 서버에서 온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="09a52-181">Use the Lync client experience with Skype for Business Server on-premises</span></span>
<span data-ttu-id="09a52-182"><a name="LyncwithSfBServer"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-182"><a name="LyncwithSfBServer"> </a></span></span>

<span data-ttu-id="09a52-183">온-프레미스 비즈니스용 Skype 서버 배포에서 Lync 클라이언트 환경을 구성 하려면이 섹션의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-183">Follow the steps in this section if you want to configure the Lync client experience in an on-premises Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="09a52-184">온-프레미스 배포에서 Skype 클라이언트 환경을 구성 하려면이 섹션의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-184">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment.</span></span> <span data-ttu-id="09a52-185">온-프레미스의 기본 환경</span><span class="sxs-lookup"><span data-stu-id="09a52-185">The default experience for on-premises</span></span>
  
 <span data-ttu-id="09a52-186">**1 단계:** 먼저 비즈니스용 Skype 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-186">**Step 1:** First, deploy Skype for Business Server.</span></span>
  
 <span data-ttu-id="09a52-187">**2 단계:** 다음으로, 클라이언트 정책을 사용 하 여 비즈니스용 Skype 클라이언트와의 Lync 클라이언트 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-187">**Step 2:** Next, use a client policy to set the Lync client experience with the Skype for Business client.</span></span> <span data-ttu-id="09a52-188">클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하기 위한 옵션에는 **3** 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-188">There are **3 options** for using a client policy to set the client experience.</span></span>
  
 <span data-ttu-id="09a52-189">**옵션 1:** 글로벌 정책을 사용 하 여 Lync 클라이언트 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-189">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="09a52-190">전역 정책은 배포의 모든 사용자에 게 적용 되지만, 사용자 및 사이트 수준 정책은 글로벌 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-190">Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 <span data-ttu-id="09a52-191">**옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Lync 클라이언트 환경을 사용 하도록 설정할 수 있는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-191">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience.</span></span> <span data-ttu-id="09a52-192">이렇게 하면 기존 정책이 할당 된 사용자 에게만 Lync 클라이언트 환경을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-192">This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 <span data-ttu-id="09a52-193">**옵션 3:** Lync 클라이언트 환경에 대 한 설정을 포함 하는 사용자에 게 할당할 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-193">**Option 3:** Create a new policy to assign to users that includes the setting for the Lync client experience.</span></span> <span data-ttu-id="09a52-194">먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수의 값으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-194">First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

<span data-ttu-id="09a52-195">그런 다음 정책 이름 ( **Identity** 매개 변수에 사용 된 값)을 사용 하 여 **PolicyName** 매개 변수의 값으로 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-195">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 <span data-ttu-id="09a52-196">**3 단계: 선택 사항** -기본적으로 사용자가 비즈니스용 skype 클라이언트를 처음 시작 하면 skype 클라이언트 환경이 사용 되며, 사용자에 게 클라이언트를 다시 시작 하 여 Lync 클라이언트 환경을 확인 하 라는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-196">**Step 3: Optional** - By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users asking them to restart the client to get the Lync client experience.</span></span> <span data-ttu-id="09a52-197">사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 하 고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정 하 여 클라이언트 자습서를 해제할 수 있도록 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-197">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial, by modifying the system registry on client computers.</span></span> <span data-ttu-id="09a52-198">비즈니스용 Skype 클라이언트를 배포 하기 전에 수행 해야 하는 단계에 대해서 [는 비즈니스용 skype를 사용 하 여 클라이언트 환경 구성을](../../deploy/deploy-clients/configure-the-client-experience.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-198">For the steps you need to perform before you deploy the Skype for Business client see [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).</span></span>
  
 <span data-ttu-id="09a52-199">**4 단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트를 배포 하 고 빌드 4711.1002 (4 월, 2015) 이상을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-199">**Step 4:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a><span data-ttu-id="09a52-200">비즈니스용 Skype 온라인에서 Lync 클라이언트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="09a52-200">Use the Lync client experience with Skype for Business Online</span></span>
<span data-ttu-id="09a52-201"><a name="LyncwithSfBO"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-201"><a name="LyncwithSfBO"> </a></span></span>

<span data-ttu-id="09a52-202">Lync 클라이언트 환경을 구성 하 고 비즈니스용 Skype 온라인을 사용 하려면이 섹션의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-202">Follow the steps in this section if you want to configure the Lync client experience and you using Skype for Business Online.</span></span>
  
<span data-ttu-id="09a52-203">비즈니스용 Skype Online을 사용 하는 경우에도 원격 PowerShell을 사용 하 여 클라이언트 정책을 구성 하 여 조직의 비즈니스용 Skype 클라이언트에서 Lync 클라이언트 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-203">If you are using Skype for Business Online, you can still use the Lync client experience with the Skype for Business client in your organization by using Remote PowerShell to configure client policies.</span></span> <span data-ttu-id="09a52-204">클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하기 위한 옵션에는 **3** 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-204">There are **3 options** for using a client policy to set the client experience.</span></span> <span data-ttu-id="09a52-205">정책과 매개 변수 이름은 비즈니스용 Skype 또는 Lync Server 온-프레미스를 사용 하는 경우 클라이언트 환경을 구성 하는 데 사용 하는 설정과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-205">Note that the policy and parameter names are different than the settings you use to configure the client experience when you are using Skype for Business or Lync Server on-premises.</span></span>
  
 <span data-ttu-id="09a52-206">**옵션 1:** 글로벌 정책을 사용 하 여 Lync 클라이언트 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-206">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="09a52-207">사용자에 게 적용 되는 클라이언트 및 사이트 정책은 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-207">Note that client and site policies applied to users will take precedence over a Global policy.</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="09a52-208">**옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Lync 클라이언트 환경을 사용 하도록 설정할 수 있는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-208">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience.</span></span> <span data-ttu-id="09a52-209">이렇게 하면 기존 정책이 할당 된 사용자 에게만 Lync 클라이언트 환경을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-209">This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="09a52-210">**옵션 3:** Lync 클라이언트 환경에 대 한 설정을 포함 하는 사용자 지정 정책 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-210">**Option 3:** Use a custom policy instance that includes the setting for the Lync client experience.</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

<span data-ttu-id="09a52-211">클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트를 배포 하 고 빌드 4711.1002 (4 월, 2015) 이상을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-211">After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
<span data-ttu-id="09a52-212">환경을 구성 하는 데 사용할 수 있는 첫 번째 실행 환경 및 PowerShell 스크립트를 제어 하는 방법에 대 한 단계를 비롯 하 여 비즈니스용 Skype Online에서 클라이언트 환경을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 skype 및 Lync 클라이언트 사용자 인터페이스 간 전환](https://aka.ms/SfBOUI)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09a52-212">For detailed information about how to configure the client experience with Skype for Business Online, including steps about how to control the first run experience and PowerShell scripts you can use to configure your environment, see [Switching between the Skype for Business and the Lync client user interfaces](https://aka.ms/SfBOUI).</span></span>
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a><span data-ttu-id="09a52-213">업데이트를 위해 지원 팀과 최종 사용자를 준비 하는 데 도움이 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="09a52-213">Resources to help you prepare your support teams and your end users for the update</span></span>
<span data-ttu-id="09a52-214"><a name="support"> </a></span><span class="sxs-lookup"><span data-stu-id="09a52-214"><a name="support"> </a></span></span>

<span data-ttu-id="09a52-215">사용자와 조직에서 전환을 쉽게 준비할 수 있도록 하기 위해 최종 사용자에 게 계획, 교육 및 참여 하는 데 도움이 되는 추가 리소스가 많이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09a52-215">To make it easier for you and your organization prepare for the transition, we have many additional resources available to help you plan, educate and engage end-users.</span></span>
  
- [<span data-ttu-id="09a52-216">비디오: 비즈니스용 Skype 소개</span><span class="sxs-lookup"><span data-stu-id="09a52-216">Video: Introducing Skype for Business</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [<span data-ttu-id="09a52-217">비즈니스용 Skype 빠른 시작 가이드 (다운로드)</span><span class="sxs-lookup"><span data-stu-id="09a52-217">Skype for Business Quick Start Guides (Download)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [<span data-ttu-id="09a52-218">Lync now 비즈니스용 Skype-새로운 기능 참조</span><span class="sxs-lookup"><span data-stu-id="09a52-218">Lync is now Skype for Business — see what's new</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [<span data-ttu-id="09a52-219">비즈니스용 Skype: 새 사용자를 위한 단계별 가이드</span><span class="sxs-lookup"><span data-stu-id="09a52-219">Skype for Business: Step-by-step guide for new users</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [<span data-ttu-id="09a52-220">Lync를 사용 하는 경우 비즈니스용 Skype가 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="09a52-220">Why do I see Skype for Business when I'm using Lync?</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

