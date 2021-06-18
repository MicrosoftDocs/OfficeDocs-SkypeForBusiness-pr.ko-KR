---
title: Microsoft Teams에 Reflect를 위한 IT 관리자 가이드
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Teams의 Reflect IT 관리자 가이드입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 981061e4892f679dac2a4e4f47fdcc929e6a02fb
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997707"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a><span data-ttu-id="9fedd-103">Microsoft Teams에 Reflect를 위한 IT 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="9fedd-103">IT Admin Guide to Reflect in Microsoft Teams</span></span>

<span data-ttu-id="9fedd-104">이 문서에서는 [Microsoft Teams의 교육 인사이트](class-insights.md)에서 필수적인 부분인 [Reflect](https://aka.ms/reflect)에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-104">This document provides information concerning [Reflect](https://aka.ms/reflect) – an integral part of [Education Insights in Microsoft Teams](class-insights.md).</span></span> <span data-ttu-id="9fedd-105">Reflect는 학생들이 정기적으로 공유하고 들을 수 있는 기회를 제공함으로써 그들의 감정을 인식하고 탐색하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-105">Reflect helps students recognize and navigate their emotions by providing regular opportunities to share and be heard.</span></span> <span data-ttu-id="9fedd-106">Reflect는 학습자의 정서적 어휘를 넓히고 동료에 대한 공감을 심화시키는 동시에 건강한 교실 커뮤니티를 위한 교육자들에게 귀중한 피드백을 제공하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-106">Reflect can help broaden learners' emotional vocabulary and deepen empathy for their peers while also providing valuable feedback to educators for a healthy classroom community.</span></span>

<span data-ttu-id="9fedd-107">이 체크인 앱은 이미 바쁜 일상 속에 사회 및 정서적 학습을 추가하는 데 있어 교육자를 지원하기 위해 이모티콘과 연구 지원을 받는 정서적 세분성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-107">This check-in app uses emojis and research-backed emotional granularity to support educators in adding social and emotional learning into their already busy routine.</span></span>


## <a name="privacy-and-security"></a><span data-ttu-id="9fedd-108">개인 정보 및 보안</span><span class="sxs-lookup"><span data-stu-id="9fedd-108">Privacy and Security</span></span>
<span data-ttu-id="9fedd-109">Reflect는 학생들의 민감한 정보를 보호하기 위해 Insights와 동일한 개인 정보 및 보안 표준을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-109">Reflect follows the same privacy and security standards as Education Insights to protect students' sensitive information.</span></span>

<span data-ttu-id="9fedd-110">Reflect를 통해 수집 및 표시되는 정보는 [90개가 넘는 규정과 산업 표준](/compliance/regulatory/offering-home)을 충족하며, 학생 및 자녀의 보안 및 기타 유사한 개인 정보 관련 규정에 대한 [GDPR](/compliance/regulatory/gdpr) 및 [FERPA(가족 교육권 및 개인 정보에 관한 법률)](/compliance/regulatory/offering-ferpa)를 포함합니다. </span><span class="sxs-lookup"><span data-stu-id="9fedd-110">The information collected and shown through Reflect meets [more than 90 regulatory and industry standards](/compliance/regulatory/offering-home), including [GDPR](/compliance/regulatory/gdpr) and the Family [Education Rights and Privacy Act (FERPA)](/compliance/regulatory/offering-ferpa) for students and children's security and other, similar, privacy-oriented regulations.</span></span>

<span data-ttu-id="9fedd-111">학생들은 본인이 어떻게 반응했는지만 확인할 수 있고 다른 학생들의 이름을 *절대* 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-111">Students *never* see the names of other students, only how they responded.</span></span> <span data-ttu-id="9fedd-112">반응 분포는 볼 수 있지만 각 반영과 연관된 이름은 *절대* 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-112">While they can see the distribution of responses, they *cannot* see names associated with each reflection.</span></span> 

> [!NOTE]
> <span data-ttu-id="9fedd-113">5명 미만의 학생이 응답하면 데이터는 학생에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-113">If less than five students respond, no data is shown to the students.</span></span> <span data-ttu-id="9fedd-114">이는 학생들이 서로의 반응을 확인할 가능성을 최소화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-114">This is to minimize the possibility of students identifying each other's responses.</span></span>

## <a name="data-collection-and-storage"></a><span data-ttu-id="9fedd-115">데이터 수집 및 저장소</span><span class="sxs-lookup"><span data-stu-id="9fedd-115">Data collection and storage</span></span>
<span data-ttu-id="9fedd-116">데이터는 교육 기관에 속하며, Microsoft는 데이터를 오로지 수집하고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-116">The data belongs to the educational institution, and Microsoft only collects the data and stores it.</span></span> <span data-ttu-id="9fedd-117">Microsoft 직원은 데이터 복구와 같은 서비스를 유지하기 위한 감사 방식으로 규정 준수에 의해 허용되는 경우를 제외하고는 데이터에 액세스하거나 데이터를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-117">Microsoft personnel cannot access the data or see it, except as allowed by compliance in an audited way to maintain the service, such as data recovery.</span></span>

<span data-ttu-id="9fedd-118">데이터는 Insights에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-118">The data is stored in Education Insights.</span></span> <span data-ttu-id="9fedd-119">기본적으로 Insights 활용이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-119">By default, Education Insights is turned on.</span></span> <span data-ttu-id="9fedd-120">옵트아웃하면 반영을 위해 **수집된 정보는 삭제됩니다**.</span><span class="sxs-lookup"><span data-stu-id="9fedd-120">When you opt-out, we **delete all the data collected for Reflect**.</span></span> <span data-ttu-id="9fedd-121">Insights를 다시 설정하면 사용 설정된 이후부터 데이터 수집을 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-121">Turn Education Insights back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="9fedd-122">[Insights IT 관리자 가이드](class-insights.md)에서 Insights자 작동하는 방식(저장소 위치 포함)과 데이터를 삭제하거나 서비스를 삭제하고 싶을 때 [Insights를 켜고 끄는 방법](class-insights.md#turn-insights-on-or-off)을 알아 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-122">In the [IT Admin Guide to Education Insights](class-insights.md), you can read how Education Insights works (including storage locations) and [how to turn Education Insights off or on](class-insights.md#turn-insights-on-or-off) when you want to delete the data or enable the service.</span></span>

<span data-ttu-id="9fedd-123">게스트 데이터는 수집되지 않지만 학생의 반영으로부터 데이터가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-123">Data is collected from student in Reflect, though guest data is not collected.</span></span> <span data-ttu-id="9fedd-124">**학생이 게스트로 정의된 경우 해당 데이터는 수집되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9fedd-124">**If a student is defined as a guest, their data is not collected.**</span></span> 

## <a name="enable-reflect"></a><span data-ttu-id="9fedd-125">반영 사용</span><span class="sxs-lookup"><span data-stu-id="9fedd-125">Enable Reflect</span></span>
<span data-ttu-id="9fedd-126">기관에 대한 앱 설정 정책을 관리하는 경우 Reflect가 *허용* 될 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-126">If you manage the app setup policy for your institution, ensure that Reflect is *allowed* in your tenant.</span></span> <span data-ttu-id="9fedd-127">Teams 관리 센터에서 관련 클래스 팀에 Reflect를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-127">You can also add Reflect to the relevant class teams from the Teams admin center.</span></span>

<span data-ttu-id="9fedd-128">사용자가 앱을 설치하고 상호 작용하도록 하려면 **앱 관리** 페이지의 조직 수준에서 앱과 사용자에게 할당된 **앱 권한 정책** 을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-128">To enable a user to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and the **app permission policy** assigned to the user.</span></span>

<span data-ttu-id="9fedd-129">각 앱을 허용해야 한다고 이전에 정의한 경우 앱 관리 페이지로 이동하여 반영 '허용'을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="9fedd-129">If you have previously defined that each app needs to be allowed, please go to the Manage apps page and 'allow' Reflect.</span></span> <span data-ttu-id="9fedd-130">**앱을 차단하면 조직의 어떤 사용자도 Teams에는 해당 앱이 나타나지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9fedd-130">**When you block an app, the app doesn't appear in Teams for any users in your organization.**</span></span>

> [!NOTE]
> <span data-ttu-id="9fedd-131">Reflect 앱에 액세스하려면 Microsoft 365용 A1, A3 또는 A5 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-131">To have access to the Reflect app, you will need an A1, A3, or A5 license for Microsoft 365.</span></span>

> [!TIP]
> <span data-ttu-id="9fedd-132">자세한 내용은 [앱 허용 방법 또는 수업 팀에 추가하는 방법](manage-apps.md#allow-and-block-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fedd-132">For more details, read [how to allow an app or to add it to a class team](manage-apps.md#allow-and-block-apps).</span></span>

## <a name="where-do-educators-find-reflect"></a><span data-ttu-id="9fedd-133">강사는 어디에서 반영을 찾을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="9fedd-133">Where do educators find Reflect?</span></span>
<span data-ttu-id="9fedd-134">반영을 사용하도록 설정하면 강사는 수업으로 이동하여 **새 대화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-134">Once you have enabled Reflect, educators go to the class and select **New Conversation**.</span></span> <span data-ttu-id="9fedd-135">그런 다음 '**…**'를 선택하여 메시지 확장명을 표시하고 검색 바에서 **Reflect** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-135">They then select '**…**' to bring up messaging extensions and enter **Reflect** in the search bar.</span></span> <span data-ttu-id="9fedd-136">이 대화 상자는 질문을 정의하고 누가 무엇을 볼 수 있는지 설명하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-136">The dialog box guides them through defining the question and who can see what.</span></span>

:::image type="content" source="media/reflect-add-app.png" alt-text="수업 팀에 Reflect 추가":::

<span data-ttu-id="9fedd-138">Reflect 아이콘을 마우스 오른쪽 단추로 클릭하고 **고정** 을 선택하여 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-138">They can right-click on the Reflect icon and select **Pin** for easy access.</span></span>

:::image type="content" source="media/reflect-pin-app.png" alt-text="Reflect 앱 고정":::

> [!TIP]
> <span data-ttu-id="9fedd-140">다음 링크를 통해 Reflect 앱을 찾을 수도 있습니다. [https://aka.ms/getReflect](https://aka.ms/getReflect)</span><span class="sxs-lookup"><span data-stu-id="9fedd-140">You can also locate the Reflect app through this link: [https://aka.ms/getReflect](https://aka.ms/getReflect)</span></span>

> [!TIP]
> <span data-ttu-id="9fedd-141">자세한 내용은 [Reflect 지원 페이지](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="9fedd-141">For more details, visit [Reflect support page](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a).</span></span> <span data-ttu-id="9fedd-142">이 페이지는 교육자와 학생 모두를 위한 지침을 제공하며 첫 번째 Reflect 체크인을 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fedd-142">This page provides guidelines for both educators and students and helps with how to create their first Reflect check-in.</span></span>
