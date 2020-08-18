---
title: 포트 주문 수동 제출
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 포트 주문 요청을 수동으로 제출 하는 방법에 대해 알아보세요.
ms.openlocfilehash: a6eda920def415e61278dc4b3ac20d2f58edbb69
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788582"
---
# <a name="manually-submit-a-port-order"></a><span data-ttu-id="c0a25-103">포트 주문 수동 제출</span><span class="sxs-lookup"><span data-stu-id="c0a25-103">Manually submit a port order</span></span>

<span data-ttu-id="c0a25-104">일부 국가 및 지역에서는 전화 번호를 얻기 위해 서비스 요청을 수동으로 제출 하거나 전화 번호를 전송 하거나 전화 번호를 해제 하거나 주소를 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-104">In some countries and regions, you may have to manually submit a service request to get phone numbers, transfer phone numbers, release phone numbers, or change addresses.</span></span> <span data-ttu-id="c0a25-105">각 국가 및 지역에 필요한 항목을 확인 하거나 번호 포팅에 대해 자세히 알아보려면 [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a25-105">To see what's required for each country and region or to learn more about number porting, see [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

<span data-ttu-id="c0a25-106">이 문서에 나와 있는 단계를 사용 하 여 국가 또는 지역이 [Microsoft 팀 관리 센터의 포팅 마법사](transfer-phone-numbers-to-teams.md)에 나열 되어 있지 않은 경우 수동으로 포트 순서를 만들고 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-106">Use the steps in this article to manually create and submit a port order if your country or region isn't listed in the [porting wizard in the Microsoft Teams admin center](transfer-phone-numbers-to-teams.md).</span></span>

## <a name="manually-submit-a-new-port-order-request"></a><span data-ttu-id="c0a25-107">새 포트 주문 요청을 수동으로 제출</span><span class="sxs-lookup"><span data-stu-id="c0a25-107">Manually submit a new port order request</span></span>

<span data-ttu-id="c0a25-108">LOA (승인 된 사용자) 양식을 해당 지역 또는 Microsoft 365 관리 센터의 PSTN 서비스 데스크에 직접 전송 하 여 서비스 요청을 만들어 새 포트 주문을 수동으로 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-108">You can manually submit a new port order by creating a service request by sending your completed Letter of Authorization (LOA) form directly to the PSTN service desk for your region or in the Microsoft 365 admin center.</span></span>

### <a name="send-your-letter-of-authorization-directly-to-the-pstn-service-desk"></a><span data-ttu-id="c0a25-109">권한 부여의 문자를 PSTN 서비스 데스크에 직접 전송</span><span class="sxs-lookup"><span data-stu-id="c0a25-109">Send your Letter of Authorization directly to the PSTN service desk</span></span>

<span data-ttu-id="c0a25-110">국가 또는 지역에 대 한 [LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 다운로드 하 고 양식을 작성 한 다음 해당 지역의 [PSTN 서비스 데스크](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) 에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-110">Download the [LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for your country or region, complete the form, and then send it to the [PSTN service desk](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) for your region:</span></span>

- <span data-ttu-id="c0a25-111">미국 및 캐나다의 경우 요청을 [보냅니다](mailto:ptn@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0a25-111">In the United States and Canada, [send your request](mailto:ptn@microsoft.com).</span></span>
- <span data-ttu-id="c0a25-112">유럽에서 [요청을 보냅니다](mailto:ptneu@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0a25-112">In Europe, [send your request](mailto:ptneu@microsoft.com).</span></span>
- <span data-ttu-id="c0a25-113">아시아에서 [요청을 보냅니다](mailto:ptnapac@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0a25-113">In Asia, [send your request](mailto:ptnapac@microsoft.com).</span></span>

### <a name="submit-a-service-request-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c0a25-114">Microsoft 365 관리 센터에서 서비스 요청 제출</span><span class="sxs-lookup"><span data-stu-id="c0a25-114">Submit a service request in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c0a25-115">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **Support**  >  **새 서비스 요청**지원으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-115">In the left navigation of the Microsoft 365 admin center, go to **Support** > **New service request**.</span></span>  <span data-ttu-id="c0a25-116">**지원** 목록이 표시 되지 않으면 왼쪽 탐색 모음에서 **탐색 사용자 지정** 으로 이동 하 여 추가한 다음 **지원** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-116">If you don't see **Support** listed, add it by going to **Customize navigation** in the left navigation, and then select the **Support** check box.</span></span>
2. <span data-ttu-id="c0a25-117">**도움이 필요 하세요?** 창에서 **고객 지원에 문의**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-117">In the **Need help?** pane, select **Contact support**.</span></span>
3. <span data-ttu-id="c0a25-118">**고객 지원** 창에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-118">In the **Contact support** pane, do the following:</span></span>

    1. <span data-ttu-id="c0a25-119">제목 (예: 포트 주문 요청) 및 요청에 대 한 설명을 입력 하 고 전화 번호와 전자 메일 주소를 확인 하 고 선호 하는 연락처 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-119">Enter a title (for example, Port order request) and description for your request, confirm your phone number and email address, and select your preferred contact method.</span></span>
    2. <span data-ttu-id="c0a25-120">**첨부** **파일에서 파일 추가**를 클릭 한 다음 완료 된 [LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-120">Under **Attachments**, click **Add a file**, and then upload your completed [LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>
    3. <span data-ttu-id="c0a25-121">**대화 상대**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-121">Click **Contact me**.</span></span>

## <a name="what-else-should-you-know-about-number-porting"></a><span data-ttu-id="c0a25-122">번호 포팅에 대해 알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="c0a25-122">What else should you know about number porting</span></span>

- <span data-ttu-id="c0a25-123">통화 계획을 사용 하려면 라이선스를 구입 하 여 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-123">To use Calling Plans you must purchase and assign licenses to your users.</span></span> <span data-ttu-id="c0a25-124">[팀 추가 기능 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a25-124">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

- <span data-ttu-id="c0a25-125">각 사용자에 게 부여할 새 전화 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a25-125">You must assign the new phone numbers you have to each of your users.</span></span> <span data-ttu-id="c0a25-126">[사용자의 전화 번호 지정, 변경 또는 제거를](../assign-change-or-remove-a-phone-number-for-a-user.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0a25-126">See [Assign, change, or remove a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0a25-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c0a25-127">Related topics</span></span>

- [<span data-ttu-id="c0a25-128">포트 순서</span><span class="sxs-lookup"><span data-stu-id="c0a25-128">What's a port order?</span></span>](port-order-overview.md)
- [<span data-ttu-id="c0a25-129">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="c0a25-129">Different kinds of phone numbers used for Calling Plans</span></span>](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="c0a25-130">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="c0a25-130">Manage phone numbers for your organization</span></span>](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="c0a25-131">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="c0a25-131">Emergency calling terms and conditions</span></span>](../emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="c0a25-132">[비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c0a25-132">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
