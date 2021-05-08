---
title: 전화번호를 Business Voice로 이식
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 현재 공급자에서 Microsoft 365 Business Voice로 기존 전화 번호를 이동하는 방법에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26f686197963f53f20477ccd9a16935c86a16d9f
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282615"
---
# <a name="step-7-port-phone-numbers-to-business-voice-optional"></a><span data-ttu-id="c9e03-103">7단계: 전화번호를 Business Voice로 포팅하기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c9e03-103">Step 7: Port phone numbers to Business Voice (optional)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9e03-104">이 문서의 정보는 통화 플랜이 **포함된** Business Voice에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-104">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="c9e03-105">통화 플랜이 포함된 Business Voice는 선택된 국가 및 지역에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-105">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="c9e03-106">이 문서를 읽기 전에 [Business Voice의 국가 및 지역 가용성](country-region-availability.md)을 확인하여 해당 국가 또는 지역에서 통화 플랜이 포함된 Business Voice를 지원하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e03-106">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="c9e03-107">테넌트가 통화 플랜을 포함한 Business Voice를 지원하지 않는 국가 또는 지역에있는 경우 [Microsoft 리셀러 또는 파트너에게 도움 받기](reseller-partner-support.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e03-107">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="c9e03-108">이 설정 가이드의 앞부분에는 주요 회사 라인과 Business Voice 라이선스를 할당한 모든 사용자에 대한 전화번호가 입력되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-108">Earlier in this setup guide, you acquired phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="c9e03-109">**신규 업체이고 Business Voice에 가져올 기존 전화 번호가 없는 경우 이 단계를 건너뛸 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c9e03-109">**If you're a new business and don't have any existing phone numbers that you want to bring to Business Voice, you can skip this step.**</span></span>

<span data-ttu-id="c9e03-110">Business Voice로 옳길 때 유지하기 원하는 전화번호가 이미 있는 경우 Business Voice로 가져오기 위한 전화번호 이식이라는 절차를 사용해 전화번호를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-110">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="c9e03-111">전화번호를 Business Voice로 이식한 이후 사용자 및 서비스에 전화번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-111">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="c9e03-112">이전 숫자는 이 설정 가이드의 앞부분에서 획득한 임시 숫자를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-112">The old numbers replace the temporary numbers that you acquired earlier in this setup guide.</span></span>

<span data-ttu-id="c9e03-113">전화번호를 Business Voice로 옮기기 전에 [전화번호 전송에 대해 자주 묻는 질문](../phone-number-calling-plans/port-order-overview.md)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e03-113">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../phone-number-calling-plans/port-order-overview.md).</span></span> <span data-ttu-id="c9e03-114">이 문서에는 지원되는 국가 또는 지역, 전송할 수 있는 번호와 전송할 수 없는 번호, 필요한 정보 등의 질문과 대답이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-114">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="c9e03-115">전화번호를 Business Voice로 옮길 준비가 되면 [Office 365로 전화번호 전송](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md)의 단계에 따라 이식 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-115">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to create a port order.</span></span> <span data-ttu-id="c9e03-116">이식 명령은 사용 중인 이동 통신 사업자에게서 Business Voice로 전화번호를 옮기기 위해 필요한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-116">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="c9e03-117">전화번호를 Business Voice로 옮긴 후에는 사용자들에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-117">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="c9e03-118">이렇게 하려면 [사용자의 전화번호 변경](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c9e03-118">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="c9e03-119">이 단계를 수행하면 사용자에게 임시로 할당된 전화번호가 이식한 원래 전화번호로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-119">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="c9e03-120">도움이 필요하면 알려주세요!</span><span class="sxs-lookup"><span data-stu-id="c9e03-120">If you need help, let us know!</span></span> <span data-ttu-id="c9e03-121">전화번호를 최대한 쉽게 Business Voice로 옮기도록 도움을 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-121">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="c9e03-122">다음 정보가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e03-122">Be sure to include the following information:</span></span>

- <span data-ttu-id="c9e03-123">기관 ID (예: ***contoso***.onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="c9e03-123">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="c9e03-124">도움이 필요한 전화번호 유형 및 개수</span><span class="sxs-lookup"><span data-stu-id="c9e03-124">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="c9e03-125">계정 승인자</span><span class="sxs-lookup"><span data-stu-id="c9e03-125">The authorizing person on your account</span></span>
- <span data-ttu-id="c9e03-126">보유하고 있는 문제 또는 질문에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="c9e03-126">A description of the issue or question that you have</span></span>

<span data-ttu-id="c9e03-127">캐나다 및 미국 전화번호에 대한 도움이 필요하면 [ptn@microsoft.com](mailto:ptn@microsoft.com)에 요청을 보내세요.</span><span class="sxs-lookup"><span data-stu-id="c9e03-127">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="c9e03-128">유럽 전화번호에 대한 도움이 필요하면 [ptneu@microsoft.com](mailto:ptneu@microsoft.com)에 요청을 보내세요.</span><span class="sxs-lookup"><span data-stu-id="c9e03-128">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c9e03-129">다음 단계: Business Voice 설정 완료</span><span class="sxs-lookup"><span data-stu-id="c9e03-129">Next step: Finish Business Voice setup</span></span>](set-up-finish.md)
