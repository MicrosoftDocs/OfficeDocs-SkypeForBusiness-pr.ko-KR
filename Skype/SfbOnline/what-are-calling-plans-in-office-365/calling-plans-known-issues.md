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
description: PSTN 호출 계획에 대한 알려진 문제 및 해당 호출에 대해 할 수 있는 작업을 알아보습니다.
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238024"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="b4345-103">통화 플랜 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b4345-103">Calling Plans known issues</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="b4345-104">전화 요금제는 온라인에서 찾을 수 있는 비즈니스용 Skype 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="b4345-105">다음은 추적되고 적극적으로 조사되는 현재 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="b4345-106">이 기능은 향후 빌드에서 업데이트될 때 잠재적으로 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="b4345-107">통화 플랜 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b4345-107">Calling Plans known issues</span></span>

|<span data-ttu-id="b4345-108">**알려진 문제**</span><span class="sxs-lookup"><span data-stu-id="b4345-108">**Known issue**</span></span>|<span data-ttu-id="b4345-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="b4345-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4345-110">통화 계획에 대한 프로덕션 라이선스로 기술 미리 보기 라이선스에서 프로덕션 라이선스로 전환하는 것이 라이선스를 자동으로 업데이트하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="b4345-111">새 라이선스를 먼저 구입하여 사용자에게 할당할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="b4345-112">사용자로부터 프로모션(Tech Preview) 라이선스를 제거한 다음 새  국내 통화 계획  및/또는 국내 및 국제 통화 계획 라이선스를 사용자에게 즉시 할당합니다. </span><span class="sxs-lookup"><span data-stu-id="b4345-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="b4345-113">여러 사용자에 대한 라이선스를 제거하고 추가하는 경우 라이선스를 사용하여 모든 사용자에서 라이선스를 제거한  다음 Windows PowerShell 라이선스를 사용하여 모든 사용자에 대한 라이선스를 즉시 할당하는 것이 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4345-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="b4345-114">이렇게 하면 대량의 사용자 라이선스 할당을 처리할 때 서비스 중단이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="b4345-115">샘플 PowerShell 스크립트는 비즈니스용 Skype 및 Microsoft Teams [할당을 참조합니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="b4345-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="b4345-116">**참고:** 하이브리드 사용자에 대해 프레미스 PSTN 연결을  사용하는 경우 라이선스를 전화 시스템 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4345-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="b4345-117">음성 **통화 요금제도** 할당하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4345-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="b4345-118">그러나 통화 요금제에 Microsoft 365 Office 365 또는 Microsoft 365 Office 365 사용자에 대해 통화 요금제 또는 국내 및 국제 통화 요금제 라이선스를 할당해야 합니다.  </span><span class="sxs-lookup"><span data-stu-id="b4345-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="b4345-119">라이선스 [비즈니스용 Skype 및 Microsoft Teams 할당을 참조합니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="b4345-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b4345-120">이보다 더 많은 전화 번호가 필요한 경우 비즈니스 제품에 대한 지원에 [문의하세요 - 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="b4345-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="b4345-121">관련 주제</span><span class="sxs-lookup"><span data-stu-id="b4345-121">Related topics</span></span>
[<span data-ttu-id="b4345-122">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="b4345-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="b4345-123">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="b4345-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="b4345-124">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="b4345-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="b4345-125">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="b4345-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="b4345-126">[비즈니스용 Skype 온라인: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b4345-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
