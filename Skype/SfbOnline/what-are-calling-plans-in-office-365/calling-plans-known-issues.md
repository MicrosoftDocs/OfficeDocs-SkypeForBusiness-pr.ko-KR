---
title: 통화 플랜 알려진 문제
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: PSTN 통화에 대한 통화 계획의 알려진 문제 및 해당 통화에 대해 할 수 있는 작업을 배워야 합니다.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220738"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="38a52-103">통화 플랜 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38a52-103">Calling Plans known issues</span></span>

<span data-ttu-id="38a52-104">통화 요금제는 비즈니스용 Skype Online의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="38a52-105">다음은 추적되고 적극적으로 조사되는 현재 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="38a52-106">향후 빌드에서 기능이 업데이트될 때 잠재적으로 해결될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="38a52-107">통화 플랜 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38a52-107">Calling Plans known issues</span></span>

|<span data-ttu-id="38a52-108">**알려진 문제**</span><span class="sxs-lookup"><span data-stu-id="38a52-108">**Known issue**</span></span>|<span data-ttu-id="38a52-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="38a52-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38a52-110">Tech Preview 라이선스에서 호출 계획의 프로덕션 라이선스로 전환하는 경우 라이선스가 자동으로 업데이트되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="38a52-111">새 라이선스를 먼저 구입하여 사용자에게 할당할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="38a52-112">사용자로부터 프로모션(Tech Preview) 라이선스를 제거한 다음 새  국내 통화 요금제  및/또는 국내 및 국제 통화 요금제 라이선스를 사용자에게 즉시 할당합니다. </span><span class="sxs-lookup"><span data-stu-id="38a52-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="38a52-113">여러 사용자에 대한 라이선스를 제거하고 추가하는 경우 Windows PowerShell 사용하여 모든 사용자에서 라이선스를 제거한 다음, 라이선스를 사용하여 모든 사용자에게 라이선스를 즉시 할당하는 것이 Windows PowerShell. </span><span class="sxs-lookup"><span data-stu-id="38a52-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="38a52-114">이렇게 하면 대량의 사용자 라이선스 할당을 처리할 때 서비스 중단이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="38a52-115">샘플 PowerShell 스크립트는 비즈니스용 Skype 및 Microsoft Teams 라이선스 [할당을 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="38a52-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="38a52-116">**참고:** 하이브리드 사용자에 대해 프레미스 PSTN 연결을  사용하는 경우 전화 시스템 라이선스만 **할당하면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="38a52-117">음성 통화 **요금제도** 할당하면 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="38a52-118">그러나 Microsoft 365 또는 Office 365에 있는 사용자에 대해 Microsoft 365 또는 Office 365에서 통화  요금제를 사용하도록  설정하는 경우 해당 사용자에게 국내 통화 요금제 또는 국내 및 국제 통화 요금제 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a52-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="38a52-119">비즈니스용 Skype 및 Microsoft Teams 라이선스 [할당을 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="38a52-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="38a52-120">이 번호보다 많은 전화 번호를 필요로 하는 경우 비즈니스 제품에 대한 지원에 [문의하세요. 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="38a52-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="38a52-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="38a52-121">Related topics</span></span>
[<span data-ttu-id="38a52-122">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="38a52-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="38a52-123">통화 요금제에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="38a52-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="38a52-124">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="38a52-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="38a52-125">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="38a52-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="38a52-126">[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="38a52-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
