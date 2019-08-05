---
title: 비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '요약: 비즈니스용 Skype 서버에서 정규화 규칙을 정의 하 고, 만들고, 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 4739bdb50e0a76c088cb6129539438c1ac6d795a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197709"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="01e50-103">비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="01e50-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="01e50-104">**요약:** 비즈니스용 Skype 서버에서 정규화 규칙을 정의 하 고, 만들고, 수정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="01e50-105">비즈니스용 Skype 서버에서 정규화 규칙을 정의, 만들기, 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="01e50-106">정규화 규칙 빌드를 사용 하 여 정규화 규칙을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="01e50-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="01e50-107">비즈니스용 Skype Server 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="01e50-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="01e50-108">) [비즈니스용 Skype Server에서 다이얼 플랜 만들기 또는 수정](dial-plans.md) 의 단계를 따라 11 단계 또는 10 단계를 통해 [다이얼 플랜 수정을 수정](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="01e50-109">**새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 에 정규화 되는 번호 패턴을 설명 하는 이름 (예: 5DigitExtension)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="01e50-110">) **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 확장명 변환").</span><span class="sxs-lookup"><span data-stu-id="01e50-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="01e50-111">**정규화 규칙 작성**에서 다음 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="01e50-112">**시작 번호** ) 패턴을 일치 시킬 전화 거는 번호의 선행 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="01e50-113">예를 들어 패턴을 425으로 시작 하는 전화 번호와 일치 시 키 려 고 type425 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="01e50-114">**길이가** 일치 하는 패턴의 자릿수를 지정 하 고 해당 패턴이이 길이에 정확 하 게 일치 하도록 할지, 적어도이 길이의 전화 접속 번호와 일치 하거나, 원하는 길이의 전화 접속 번호와 일치 시킬 것인지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="01e50-115">**제거할 숫자** ) 패턴을 일치 시킬 전화 번호에서 제거할 시작 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="01e50-116">**더할 숫자** ) 패턴을 일치 시킬 전화 번호에 추가할 숫자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="01e50-117">이러한 필드에 입력 하는 값은 일치 및 **번역 규칙** **에 따라 패턴** 에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="01e50-118">예를 들어 **시작 자릿수** 를 비워 두면 **Length** 필드에 type7를 선택 하 고, \*\*\*\* **제거할 자리**에 0을 지정 하 고 **일치 시킬 패턴** 의 정규식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="01e50-119">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="01e50-119">^(\d{7})$</span></span>

6. <span data-ttu-id="01e50-120">**번역 규칙**에서 다음과 같이 변환 된 전자 164 전화번호의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="01e50-121">일치 패턴에 지정 된 자릿수를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="01e50-122">예를 들어 일치 하는 패턴이 ^ (\d{7}) $ 이면 번역 규칙에서 $1이 7 자리 번호 매기기 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="01e50-123">) 숫자를 **추가할** 숫자 필드에 값을 입력 하 여 앞으로 변환할 숫자를 지정 합니다 (예: + 1425).</span><span class="sxs-lookup"><span data-stu-id="01e50-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="01e50-124">예를 들어 **일치 하는 패턴** 에 ^ (\d{7}) $가 있는 경우, 전화를 걸고 \*\*\*\* 있는 번호의 패턴으로 + 1425 $1이 포함 된 경우이 규칙은 5550100에서 + 14255550100로 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="01e50-125">) 정규화 규칙이 조직 내부의 전화 번호를 반환 하는 경우 **내부 확장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="01e50-126">) 번호를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-126">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="01e50-127">테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-127">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01e50-128">아직 테스트를 통과 하지 않은 정규화 규칙을 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="01e50-129">자세한 내용은 [음성 라우팅 테스트](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="01e50-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="01e50-130">**확인** 을 클릭 하 여 정규화 규칙을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="01e50-131">**확인** 을 클릭 하 여 다이얼 플랜을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="01e50-132">**다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01e50-133">정규화 규칙을 만들거나 변경할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="01e50-134">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="01e50-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="01e50-135">정규화 규칙을 수동으로 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="01e50-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="01e50-136">비즈니스용 Skype Server 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="01e50-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="01e50-137">) [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](dial-plans.md)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="01e50-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="01e50-138">**새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 에 정규화 되는 번호 패턴을 설명 하는 이름 (예: 정규화 rule5DigitExtension의 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="01e50-139">) **설명** 필드에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 확장명 변환").</span><span class="sxs-lookup"><span data-stu-id="01e50-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="01e50-140">**정규화 규칙 작성**에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="01e50-141">**정규식 입력**에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="01e50-142">**이 패턴과 일치**하는 경우 전화를 거는 전화 번호와 일치 하는 데 사용할 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="01e50-143">**번역 규칙**에서 번역 된 전자 전화번호의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="01e50-144">예를 들어 **이 패턴과 일치** 하는 ^{7}(\d) $를 입력 하 고 **번역 규칙**에 + 1425 $1을 입력할 경우 규칙은 5550100에서 + 14255550100로 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="01e50-145">) 정규화 규칙이 조직 내부의 전화 번호를 반환 하는 경우 **내부 확장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="01e50-146">) 번호를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-146">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="01e50-147">테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-147">The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="01e50-148">**확인** 을 클릭 하 여 정규화 규칙을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="01e50-149">**확인** 을 클릭 하 여 다이얼 플랜을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="01e50-150">**다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01e50-151">정규화 규칙을 만들거나 변경할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e50-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="01e50-152">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="01e50-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


