---
title: 'Lync Server 2013: 수동으로 정규화 규칙 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e265563bb7091b72967174a2de11f07d8b8cc29b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="aea4c-102">Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="aea4c-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aea4c-103">_**마지막으로 수정 된 항목:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="aea4c-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="aea4c-104">정규화 규칙을 수동으로 만들거나 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="aea4c-105">Lync Server 제어판에서 정규화 규칙 작성을 사용 하 여 정규화 규칙을 만들거나 수정 하려면 [Lync server 2013에서 작성 a 정규화 규칙을 사용 하 여 정규화 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aea4c-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="aea4c-106">정규화 규칙을 수동으로 정의하려면</span><span class="sxs-lookup"><span data-stu-id="aea4c-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="aea4c-107">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="aea4c-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aea4c-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="aea4c-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aea4c-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aea4c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aea4c-111">반드시 [Lync server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 단계를 수행 하거나 [lync server 2013에서 다이얼 플랜을 수정](lync-server-2013-modify-a-dial-plan.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="aea4c-112">**새 정규화 규칙** 또는 **정규화 규칙 편집**의 **이름**에 정규화 중인 숫자 패턴을 설명하는 이름을 입력합니다(예: 정규화 규칙의 이름을 **5DigitExtension**으로 지정).</span><span class="sxs-lookup"><span data-stu-id="aea4c-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="aea4c-113">(선택 사항) **설명** 필드에 정규화 규칙에 대한 설명을 입력합니다(예: "Translates 5-digit extensions").</span><span class="sxs-lookup"><span data-stu-id="aea4c-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="aea4c-114">**정규화 규칙 작성**에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="aea4c-115">**정규식 입력**에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="aea4c-116">**다음 패턴과 일치시킴**에서 전화 건 전화 번호와 일치시키는 데 사용할 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="aea4c-117">**변환 규칙**에서 변환된 E.164 전화 번호 형식에 대한 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="aea4c-118">예를 들어 **변환 규칙**에서 **이 패턴과 일치** 하는 **^ (\\d{7}) $** 및 **+ 1425 $1** 을 입력 하면 규칙은 5550100에서 + 14255550100로 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="aea4c-119">(선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="aea4c-p104">(선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 **이동**을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aea4c-122">아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="aea4c-123">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aea4c-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="aea4c-124">정규화 규칙을 저장하려면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="aea4c-125">다이얼 플랜을 저장하려면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="aea4c-126">**다이얼 플랜** 페이지에서 **커밋**을 클릭한 다음 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aea4c-127">정규화 규칙을 만들거나 변경할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aea4c-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="aea4c-128">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aea4c-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aea4c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aea4c-129">See Also</span></span>


[<span data-ttu-id="aea4c-130">Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="aea4c-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="aea4c-131">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="aea4c-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="aea4c-132">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="aea4c-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="aea4c-133">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="aea4c-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="aea4c-134">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="aea4c-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

