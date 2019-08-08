---
title: 비즈니스용 Skype 서버에서 호출 된 ID 프레젠테이션에 대 한 번역 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '요약: 비즈니스용 Skype 서버에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙을 정의 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 3c72e53044abe44660423bbd9bc1adbbeed2a3ed
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234002"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="e2de4-103">비즈니스용 Skype 서버에서 호출 된 ID 프레젠테이션에 대 한 번역 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e2de4-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="e2de4-104">**요약:** 비즈니스용 Skype 서버에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙을 정의 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="e2de4-105">**번역 규칙 작성** 도구에 값 집합을 입력 하 고 비즈니스용 Skype 서버 제어판에서 해당 하는 일치 패턴 및 번역 규칙을 생성할 수 있도록 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e2de4-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="e2de4-106">또는 정규식을 수동으로 작성 하 여 일치 패턴 및 번역 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="e2de4-107">자세한 내용은 [수동으로 번역 규칙 만들기 또는 수정을](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2de4-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="e2de4-108">번역 규칙 작성 도구를 사용 하 여 규칙을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="e2de4-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="e2de4-109">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="e2de4-110">번역 규칙 정의를 시작 하려면 비즈니스용 [Skype server에서 미디어 바이패스를 사용 하 여 트렁크 구성](configure-trunk-with-media-bypass.md) 의 단계를 따르세요. 10 단계에서 비즈니스용 [skype 서버에서 미디어 바이패스 없이 트렁크를 구성](configure-trunk-without-media-bypass.md) 하려면 9 단계를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e2de4-111">**새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 아래에서 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e2de4-112">) **설명**아래에 번역 규칙에 대 한 설명 (예: US 국제 장거리 전화 걸기)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e2de4-113">대화 상자의 **번역 규칙 작성** 섹션에서 다음 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="e2de4-114">**시작 번호**: (선택 사항) 패턴을 일치 시킬 숫자의 선행 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="e2de4-115">예를 들어이 필드에 +를 입력 하 여 전자 164 형식의 숫자와 일치 시킵니다 (+로 시작).</span><span class="sxs-lookup"><span data-stu-id="e2de4-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="e2de4-116">**길이**: 일치 하는 패턴의 자릿수를 지정 하 고 해당 패턴이이 길이의 정확한 숫자, 최소 길이 또는 길이 중 어느 것을 일치 시킬 것인지 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="e2de4-117">예를 들어 11 자리 이상 길이의 숫자와 일치 시키려면 11을 입력 하 고 드롭다운 목록에서 최소한을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="e2de4-118">**제거할 자릿수**: (선택 사항) 제거할 시작 숫자의 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="e2de4-119">예를 들어 숫자의 시작 부분에서 +를 제거 하려면 1을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="e2de4-120">**더할 자릿수**: (선택 사항) 번역 된 숫자 앞에 추가할 숫자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="e2de4-121">예를 들어 규칙을 적용할 때 이진수를 번역 된 번호로 앞에 표시 하려면 011을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="e2de4-122">이러한 필드에 입력 하는 값은 일치 및 **번역 규칙** 필드에 따라 **패턴** 에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-122">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="e2de4-123">예를 들어 앞의 예제 값을 지정 하는 경우 **일치 하는 패턴** 필드의 결과 정규식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-123">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="e2de4-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="e2de4-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="e2de4-125">**번역 규칙** 필드는 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="e2de4-126">이 패턴은 두 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="e2de4-127">일치 하는 패턴의 자릿수를 나타내는 값 (예: $1)</span><span class="sxs-lookup"><span data-stu-id="e2de4-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="e2de4-128">) **추가할 숫자** 필드에 입력 하 여 앞에 입력할 수 있는 값</span><span class="sxs-lookup"><span data-stu-id="e2de4-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="e2de4-129">앞의 예제 값을 사용 하 여 **번역 규칙** 필드에 011 $1이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="e2de4-130">이 번역 규칙이 적용 되 면 + 441235551010이 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="e2de4-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="e2de4-131">**확인** 을 클릭 하 여 번역 규칙을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="e2de4-132">**확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="e2de4-133">**트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2de4-134">번역 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e2de4-135">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2de4-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="e2de4-136">수동으로 번역 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="e2de4-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="e2de4-137">비즈니스용 Skype Server 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="e2de4-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e2de4-138">번역 규칙 정의를 시작 하려면 비즈니스용 [Skype server에서 미디어 바이패스를 사용 하 여 트렁크 구성](configure-trunk-with-media-bypass.md) 의 단계를 따르세요. 10 단계에서 비즈니스용 [skype 서버에서 미디어 바이패스 없이 트렁크를 구성](configure-trunk-without-media-bypass.md) 하려면 9 단계를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="e2de4-139">**새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 필드에 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="e2de4-140">) **설명**에 번역 규칙에 대 한 설명 (예: US 국제 장거리 전화 걸기)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="e2de4-141">**번역 규칙 작성** 섹션의 아래쪽에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="e2de4-142">**정규식 입력**에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e2de4-143">**이 패턴과 일치**하는 경우 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="e2de4-144">**번역 규칙**에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="e2de4-145">예를 들어 **번역 규칙**에서이\+패턴 And011{9}$1 **과 일치** 하는 ^ (\d \d +) $를 입력 하는 경우 규칙은 + 441235551010를 011441235551010로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="e2de4-146">**확인** 을 클릭 하 여 번역 규칙을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="e2de4-147">**확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="e2de4-148">**트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2de4-149">번역 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2de4-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e2de4-150">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2de4-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2de4-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2de4-151">See also</span></span>

[<span data-ttu-id="e2de4-152">비즈니스용 Skype 서버에서 미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="e2de4-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="e2de4-153">비즈니스용 Skype 서버에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="e2de4-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="e2de4-154">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="e2de4-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="e2de4-155">비즈니스용 Skype 서버에서 미디어 바이패스 배포</span><span class="sxs-lookup"><span data-stu-id="e2de4-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

