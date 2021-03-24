---
title: 비즈니스용 Skype 서버에서 호출된 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '요약: 비즈니스용 Skype 서버에서 번역 규칙 작성 도구를 사용하여 변환 규칙을 정의하는 방법을 설명하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 3f4754184e69e7b574709d0272afc9989553cfe5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103644"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="9cdcb-103">비즈니스용 Skype 서버에서 호출된 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="9cdcb-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="9cdcb-104">**요약:** 비즈니스용 Skype 서버에서 변환 규칙 작성 도구를 사용하여 변환 규칙을 정의하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="9cdcb-105">변환 규칙 작성 도구에 값 집합을 입력하고 비즈니스용  Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성하도록 설정하여 변환 규칙을 정의하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="9cdcb-106">또는 정규 표현식을 수동으로 작성하여 일치 패턴과 변환 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="9cdcb-107">자세한 내용은 [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-107">For details, see [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="9cdcb-108">변환 규칙 작성 도구를 사용하여 규칙을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9cdcb-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="9cdcb-109">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="9cdcb-110">변환 규칙 정의를 시작하고 10단계를 통해 비즈니스용 [Skype](configure-trunk-with-media-bypass.md) 서버에서 미디어 우회를 통해 트렁크 구성 또는 9단계까지 비즈니스용 [Skype](configure-trunk-without-media-bypass.md) 서버에서 미디어 우회 없이 트렁크 구성의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="9cdcb-111">**새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 아래에서 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="9cdcb-112">(선택 사항) 설명 **아래에서** 변환 규칙에 대한 설명을 입력합니다(예: 미국 국제 장거리 전화 걸기).</span><span class="sxs-lookup"><span data-stu-id="9cdcb-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="9cdcb-113">대화 상자의 **변환 규칙 작성** 섹션에 있는 다음 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="9cdcb-114">**시작 숫자**: (선택 사항) 패턴을 일치시킬 선행 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="9cdcb-115">예를 들어 이 필드에 +를 입력하면 +로 시작하는 E.164 형식의 번호가 일치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="9cdcb-116">**길이:** 일치 패턴의 자릿수와 이 길이의 숫자를 일치할지, 적어도 이 길이 또는 길이를 일치할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="9cdcb-117">예를 들어 11을 입력하고 드롭다운 목록에서 최소 11자릿수의 숫자와 일치하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="9cdcb-118">**제거할 숫자**: (선택 사항) 제거할 시작 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="9cdcb-119">예를 들어 1을 입력하여 번호의 시작점에서 +를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="9cdcb-120">**추가할 숫자**: (선택 사항) 변환된 번호의 앞에 추가할 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="9cdcb-121">예를 들어 011을 입력하면 규칙이 적용될 때 변환된 번호 앞에 011이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="9cdcb-p106">이 필드에 입력한 값은 **일치시킬 패턴** 및 **변환 규칙** 필드에 적용됩니다. 예를 들어 위의 예 값을 지정한 경우 **일치시킬 패턴** 필드의 정규식 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="9cdcb-124">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="9cdcb-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="9cdcb-125">**변환 규칙** 필드에서는 변환된 번호 형식에 대한 패턴이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="9cdcb-126">이 패턴은 두 부분으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="9cdcb-127">일치하는 패턴의 자릿수를 나타내는 값(예: $1)</span><span class="sxs-lookup"><span data-stu-id="9cdcb-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="9cdcb-128">(선택 사항) **추가할 숫자** 필드에 입력하여 번호 앞에 추가할 수 있는 값</span><span class="sxs-lookup"><span data-stu-id="9cdcb-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="9cdcb-129">위의 예 값을 사용하면 변환 규칙 필드에 **011$1** 이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="9cdcb-130">이 변환 규칙이 적용되면 +441235551010이 011441235551010이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="9cdcb-131">**확인** 을 클릭하여 변환 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="9cdcb-132">**확인** 을 클릭하여 트렁크 구성을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="9cdcb-133">**트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9cdcb-134">변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="9cdcb-135">자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in Skype for Business를](voice-route-config-changes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="9cdcb-136">변환 규칙을 수동으로 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9cdcb-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="9cdcb-137">비즈니스용 Skype 서버 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="9cdcb-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="9cdcb-138">변환 규칙 정의를 시작하고 10단계를 통해 비즈니스용 [Skype](configure-trunk-with-media-bypass.md) 서버에서 미디어 우회를 통해 트렁크 구성 또는 9단계까지 비즈니스용 [Skype](configure-trunk-without-media-bypass.md) 서버에서 미디어 우회 없이 트렁크 구성의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="9cdcb-139">**새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 필드에 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="9cdcb-140">(선택 사항) **설명에** 변환 규칙에 대한 설명을 입력합니다(예: 미국 국제 장거리 전화 걸기).</span><span class="sxs-lookup"><span data-stu-id="9cdcb-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="9cdcb-141">**변환 규칙 작성** 섹션 아래쪽의 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="9cdcb-142">**정규식 입력** 에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="9cdcb-143">**다음 패턴과 일치시킴** 에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="9cdcb-144">**변환 규칙** 에 변환된 숫자 형식의 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="9cdcb-145">예를 들어 이 패턴 일치에 ^ \+ (\d {9} \d+)$를 입력하고 **변환** 규칙에 011$1을 입력하면 규칙은 +441235551010을 011441235551010으로 변환합니다. </span><span class="sxs-lookup"><span data-stu-id="9cdcb-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="9cdcb-146">**확인** 을 클릭하여 변환 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="9cdcb-147">**확인** 을 클릭하여 트렁크 구성을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="9cdcb-148">**트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9cdcb-149">변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="9cdcb-150">자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in Skype for Business를](voice-route-config-changes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9cdcb-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cdcb-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cdcb-151">See also</span></span>

[<span data-ttu-id="9cdcb-152">비즈니스용 Skype 서버에서 미디어 우회를 통해 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="9cdcb-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="9cdcb-153">비즈니스용 Skype 서버에서 미디어 우회 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="9cdcb-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="9cdcb-154">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="9cdcb-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="9cdcb-155">비즈니스용 Skype 서버에서 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="9cdcb-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)