---
title: 비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '요약: 비즈니스용 Skype 서버에서 정규화 규칙을 정의, 생성 및 수정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830768"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="cdcb6-103">비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="cdcb6-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="cdcb6-104">**요약:** 비즈니스용 Skype 서버에서 정규화 규칙을 정의, 생성 및 수정하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="cdcb6-105">비즈니스용 Skype 서버에서 정규화 규칙을 정의, 생성 및 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="cdcb6-106">정규화 규칙 작성을 사용하여 정규화 규칙을 정의</span><span class="sxs-lookup"><span data-stu-id="cdcb6-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="cdcb6-107">비즈니스용 Skype 서버 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="cdcb6-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cdcb6-108">(선택 사항) 11단계를 통해 비즈니스용 [Skype](dial-plans.md) 서버에서 다이얼 플랜 만들기 [](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) 또는 수정 또는 10단계를 통해 다이얼 플랜 수정의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="cdcb6-109">**새 정규화** 규칙 또는 정규화 규칙 편집에서 **Name에서** 정규화되는 숫자 패턴을 설명하는 이름을 입력합니다(예: 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="cdcb6-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="cdcb6-110">(선택 사항) **설명에서** 정규화 규칙에 대한 설명을 입력합니다(예: "5자리 내선 번호 변환").</span><span class="sxs-lookup"><span data-stu-id="cdcb6-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cdcb6-111">정규화 **규칙 작성에서** 다음 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="cdcb6-112">**시작 숫자(선택** 사항) 패턴과 일치할 전화 걸기 번호의 선행 숫자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="cdcb6-113">예를 들어 패턴이 425로 시작되는 전화 걸기 번호와 일치하게 하려는 경우 type425를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="cdcb6-114">**Length** 일치하는 패턴의 자릿수와 패턴이 이 길이와 정확히 일치할지, 적어도 이 길이의 전화 걸기 번호를 일치할지 또는 모든 길이의 전화 걸기 번호를 일치할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="cdcb6-115">**제거할 숫자(선택** 사항) 패턴을 일치할 전화 걸기 번호에서 제거할 시작 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="cdcb6-116">**추가할 숫자(선택** 사항) 패턴을 일치할 전화 걸기 번호에 추가할 숫자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="cdcb6-117">이러한 필드에 입력하는 값은 일치 및 변환 **규칙에 따라 패턴에** **반영됩니다.**</span><span class="sxs-lookup"><span data-stu-id="cdcb6-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="cdcb6-118">예를 들어 시작  숫자를 비워 두면 **Length** 필드에 type7을 입력하고 정확하게 선택하고 제거할 **숫자에** 0을 지정하면 패턴에서 일치할 정규식이 다음과 **같습니다.**</span><span class="sxs-lookup"><span data-stu-id="cdcb6-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="cdcb6-119">^(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="cdcb6-119">^(\d{7})$</span></span>

6. <span data-ttu-id="cdcb6-120">변환 **규칙에서** 변환된 E.164 전화 번호 형식에 대한 패턴을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="cdcb6-121">일치 패턴에 지정된 자릿수의 수를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="cdcb6-122">예를 들어 일치하는 패턴이 ^(\d )$이면 변환 규칙의 {7} $1은 7자리 전화 걸기 번호를 나타냈습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="cdcb6-123">(선택 사항) 숫자에 값을 **입력하여** 변환된 번호(예: +1425)에 추가할 숫자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="cdcb6-124">예를 들어  일치시키면 패턴에 전화 걸기 번호의 패턴으로^(\d )$가 포함되어 있으며 변환 규칙에 E.164 전화 번호의 패턴으로 {7} +1425$1이 포함되어 있는 경우 규칙은 5550100을 +14255550100으로 정규화합니다. </span><span class="sxs-lookup"><span data-stu-id="cdcb6-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cdcb6-125">(선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cdcb6-126">(선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 이동을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cdcb6-126">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="cdcb6-127">테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-127">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cdcb6-128">아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="cdcb6-129">자세한 내용은 [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="cdcb6-130">정규화 규칙을 저장하려면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cdcb6-131">다이얼 플랜을 저장하려면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cdcb6-132">**다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cdcb6-133">정규화 규칙을 만들거나 변경할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cdcb6-134">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="cdcb6-135">정규화 규칙을 수동으로 정의하려면</span><span class="sxs-lookup"><span data-stu-id="cdcb6-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="cdcb6-136">비즈니스용 Skype 서버 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="cdcb6-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cdcb6-137">(선택 사항) 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 [수정의 단계를 따릅니다.](dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="cdcb6-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="cdcb6-138">**새 정규화** 규칙 또는 정규화 규칙 편집에서 **Name으로** 정규화되는 숫자 패턴을 설명하는 이름을 입력합니다.(예: 정규화 규칙5DigitExtension의 이름).</span><span class="sxs-lookup"><span data-stu-id="cdcb6-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="cdcb6-139">(선택 사항) **설명** 필드에 정규화 규칙에 대한 설명을 입력합니다(예: "Translates 5-digit extensions").</span><span class="sxs-lookup"><span data-stu-id="cdcb6-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cdcb6-140">**정규화 규칙 작성** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="cdcb6-141">**정규식 입력** 에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="cdcb6-142">**다음 패턴과 일치시킴** 에서 전화 건 전화 번호와 일치시키는 데 사용할 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="cdcb6-143">**변환 규칙** 에서 변환된 E.164 전화 번호 형식에 대한 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="cdcb6-144">예를 들어 이 패턴 일치에 ^(\d )$를 입력하고 변환 규칙에서 {7} +1425$1을 입력하면 규칙이 5550100에서 +14255550100으로 정규화됩니다.  </span><span class="sxs-lookup"><span data-stu-id="cdcb6-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cdcb6-145">(선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cdcb6-p107">(선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 **이동** 을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="cdcb6-148">정규화 규칙을 저장하려면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cdcb6-149">다이얼 플랜을 저장하려면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cdcb6-150">**다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cdcb6-151">정규화 규칙을 만들거나 변경할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cdcb6-152">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cdcb6-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


