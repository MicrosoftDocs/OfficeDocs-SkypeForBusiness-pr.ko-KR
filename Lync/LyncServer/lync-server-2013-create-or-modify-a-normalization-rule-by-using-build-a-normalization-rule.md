---
title: 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc758fa99bd14dff345d7efa9d4c96b151abca57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="2bd08-102">Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="2bd08-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bd08-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2bd08-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2bd08-104">Lync Server 제어판에서 정규화 규칙을 만들거나 수정 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="2bd08-105">또는 정규화 규칙을 수동으로 만들거나 수정 하려면 [Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bd08-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="2bd08-106">정규화 규칙 작성을 사용 하 여 규칙을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="2bd08-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="2bd08-107">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2bd08-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bd08-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2bd08-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2bd08-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bd08-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2bd08-111">반드시 [Lync server 2013에서 11 단계까지 만든 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 단계를 수행 하거나 [lync server 2013에서 10 단계까지 다이얼 플랜을 수정](lync-server-2013-modify-a-dial-plan.md) 합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2bd08-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="2bd08-112">**새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 으로 정규화 되는 번호 패턴을 설명 하는 이름 (예: **: 5digitextension**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="2bd08-113">반드시 **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 내선 번호 변환").</span><span class="sxs-lookup"><span data-stu-id="2bd08-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="2bd08-114">**정규화 규칙 작성**의 다음 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="2bd08-115">**시작 숫자**   (선택 사항) 패턴을 일치 시킬 전화 건 번호의 선행 숫자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="2bd08-116">예를 들어 425로 시작 하는 전화 번호를 패턴으로 일치 시키려면 **425** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="2bd08-117">**길이**   일치 하는 패턴의 자릿수를 지정 하 고 패턴을이 길이와 정확히 일치 시킬 것인지, 아니면 적어도이 길이에 해당 하는 전화 건 번호를 지정할지, 전화 건 번호와 일치 하는 것을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="2bd08-118">**제거할 숫자 (**   선택 사항) 패턴을 일치 시킬 전화 건 번호에서 제거할 시작 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="2bd08-119">**추가할 숫자 (**   선택 사항) 패턴을 일치 시킬 전화 건 번호에 추가할 숫자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="2bd08-120">이러한 필드에 입력 하는 값은 일치 및 **변환 규칙** **에 대 한 패턴** 에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-120">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="2bd08-121">예를 들어 **시작 자리** 를 비워 두면 **길이** 필드에 **7** 을 입력 하 고, **정확히**선택 하 고, **제거할 숫자**에 **0** 을 지정 하 여 **일치 시킬 패턴** 의 정규식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-121">For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="2bd08-122">**^ (\\d{7}) $**</span><span class="sxs-lookup"><span data-stu-id="2bd08-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="2bd08-123">**변환 규칙**에서 다음과 같이 변환 된 E. 164 전화 번호 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="2bd08-124">일치 패턴에 지정 된 자릿수를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="2bd08-125">예를 들어 일치 하는 패턴이 **^ (\\d{7}) $** 이 고 변환 규칙에서 **$1** 은 7 자리 전화 걸기 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="2bd08-126">반드시 숫자를 **추가할** 숫자 필드에 값을 입력 하 여 변환 된 번호 앞에 추가할 자릿수를 지정 합니다 (예: **+ 1425**).</span><span class="sxs-lookup"><span data-stu-id="2bd08-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="2bd08-127">예를 들어 **일치 시킬 패턴이** **\\^ (d{7}) $** 를 포함 하는 경우 전화 건 번호의 패턴으로 **+ 1425 $1** 이 E. 164 전화 번호의 패턴으로 포함 된 경우 규칙은 5550100에서 + 14255550100로 정규화 됩니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2bd08-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="2bd08-128">(선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="2bd08-129">반드시 숫자를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-129">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="2bd08-130">테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-130">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2bd08-131">아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="2bd08-132">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bd08-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="2bd08-133">정규화 규칙을 저장하려면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="2bd08-134">다이얼 플랜을 저장하려면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="2bd08-135">**다이얼 플랜** 페이지에서 **커밋**을 클릭한 다음 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2bd08-136">정규화 규칙을 만들거나 변경할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd08-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="2bd08-137">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bd08-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bd08-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bd08-138">See Also</span></span>


[<span data-ttu-id="2bd08-139">Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="2bd08-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="2bd08-140">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="2bd08-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="2bd08-141">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="2bd08-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="2bd08-142">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="2bd08-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="2bd08-143">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="2bd08-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

