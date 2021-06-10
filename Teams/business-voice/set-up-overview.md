---
title: 설정 Microsoft 365 Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 중소기업 또는 Microsoft 365 Business Voice 조직에서 비즈니스를 설정하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 892b093003accf782b7fb6c0a6234bf1f8beb952
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656041"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="d6124-103">설정 Microsoft 365 Business Voice</span><span class="sxs-lookup"><span data-stu-id="d6124-103">Set up Microsoft 365 Business Voice</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEu8R]  

</br>

<span data-ttu-id="d6124-104">Business Voice는 기존 전화 통신 공급자를 대체할 수 있는 완전한 전화 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="d6124-105">처음 전화 번호를 설정하는 새로운 비즈니스이든, 레거시온-프레미스 전화 통신 공급자에서 이동하는 기존 비즈니스이든, 이러한 문서의 단계는 비즈니스 음성을 사용하여 시작하고 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="d6124-106">비즈니스 음성 설정이 완료된 경우:</span><span class="sxs-lookup"><span data-stu-id="d6124-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="d6124-107">주 회사 전화선에서 수신자 부담 전화 또는 수신자 부담 전화 통화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="d6124-108">원하는 경우 통화 메뉴를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="d6124-109">Business Voice를 사용하여 설정한 사용자에게는 사용자가 직접 전화를 걸 수 있는 자체 전화 번호가 설치되어 있는 모든 장치에서 전화를 걸고 받는 데 사용할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="d6124-110">모임 참가자는 클라이언트에서 참가할 수 없는 경우 일반 전화를 사용하여 모임에 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="d6124-111">기존 전화 번호가 있는 경우 비즈니스 음성으로 이동한 후에도 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="d6124-112">비즈니스 음성에 대해 자세히 알아보고 싶으면 어떤 정보를 [Microsoft 365 Business Voice.](whats-business-voice.md)</span><span class="sxs-lookup"><span data-stu-id="d6124-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6124-113">이 문서의 정보는 통화 계획이 있는 비즈니스 **음성에만** 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="d6124-114">통화 플랜이 포함된 Business Voice는 선택된 국가 및 지역에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="d6124-115">비즈니스 음성 설정을 시작하기 전에 [](country-region-availability.md) 비즈니스 음성에 대한 국가 및 지역 가용성을 확인하여 국가 또는 지역이 통화 계획으로 비즈니스 음성을 지원하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="d6124-116">테넌트가 통화 플랜을 포함한 Business Voice를 지원하지 않는 국가 또는 지역에있는 경우 [Microsoft 리셀러 또는 파트너에게 도움 받기](reseller-partner-support.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d6124-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="d6124-117">Microsoft Teams와 Business Voice는 사용자의 사서함이 Microsoft 365에 있는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="d6124-118">온-프레미스 Exchange 서버의 사서함은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="d6124-119">이 설정 프로세스는 하이브리드 배포를 지원하지 비즈니스용 Skype 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="d6124-120">비즈니스용 Skype 하이브리드 배포가 있고 비즈니스 음성을 설정하려는 경우 [조직에서 전화 시스템 설정](../setting-up-your-phone-system.md)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d6124-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d6124-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="d6124-121">Before you begin</span></span>

<span data-ttu-id="d6124-122">비즈니스 음성을 설정하기 전에 몇 가지 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="d6124-123">다음 작업은 조직이 비즈니스 음성에 대한 준비가 됐는지 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="d6124-124">**비즈니스 음성 라이선스를** 구입하고 무료 전화 번호를 얻거나 장거리 전화 통화를 원할 경우 통신 크레딧을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="d6124-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="d6124-125">자세한 내용은 사용하려면 구입해야 하는 [Microsoft 365 Business Voice.](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="d6124-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="d6124-126">**인터넷 연결이 비즈니스 음성을 지원할 수 있는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="d6124-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="d6124-127">자세한 내용은 비즈니스 [음성에 대한 인터넷 연결 확인을 참조하세요.](get-ready-internet.md)</span><span class="sxs-lookup"><span data-stu-id="d6124-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="d6124-128">**사용자의 Teams** 설정하고, 음성메일 인사말을 설정하고, 사용자가 사용자에 대한 정보를 배울 수 있도록 Teams.</span><span class="sxs-lookup"><span data-stu-id="d6124-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="d6124-129">자세한 내용은 사용자가 사용자에 대해 준비를 완료하는 방법을 Microsoft 365 Business Voice? 를 [참조하세요.](prepare-users.md)</span><span class="sxs-lookup"><span data-stu-id="d6124-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="d6124-130">비즈니스 음성에 대한 조직을 준비한 후 다음 단계: 비즈니스 음성 설정 **시작 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d6124-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d6124-131">다음 단계: 비즈니스 음성 설정 시작</span><span class="sxs-lookup"><span data-stu-id="d6124-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
