---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="6a40c-102">Lync Server 2013에서 음성 라우팅 테스트 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="6a40c-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a40c-103">_**마지막으로 수정한 주제:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="6a40c-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="6a40c-104">테스트 사례를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6a40c-104">To create a test case</span></span>

1.  <span data-ttu-id="6a40c-105">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6a40c-106">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a40c-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6a40c-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a40c-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a40c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6a40c-109">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="6a40c-110">**음성 라우팅 테스트** 페이지에서 **새로** 만들기를 클릭 하 여 새 테스트 사례를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="6a40c-111">**이름**에 테스트 사례에 대 한 고유한 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="6a40c-112">이름은 엔터프라이즈 음성 배포의 모든 음성 라우팅 테스트 사례에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="6a40c-113">길이는 최대 32 자로 지정할 수 있으며, 백슬래시 (\\), 마침표 (.), 밑줄 (\_) 외에도 영숫자 문자를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="6a40c-114">**전화를 걸 번호**에서이 테스트 사례에 대해 지정 하는 라우팅 구성을 테스트 하는 데 사용할 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="6a40c-115">다이얼 플랜, 경로 및 음성 정책에 따라이 번호는 표준화 되어 출력으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="6a40c-116">**다이얼 플랜** 목록에서 테스트를 실행할 때 사용할 다이얼 플랜을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="6a40c-117">전역 다이얼 플랜을 기본값으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="6a40c-118">**음성 정책** 목록에서 테스트를 실행할 때 사용할 음성 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="6a40c-119">기본값은 전역 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="6a40c-120">**번역 후 예상한**형식으로 전화 번호를 입력 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a40c-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="6a40c-121">선택한 다이얼 플랜에서 일치 하는 첫 번째 정규화 규칙으로 번역 된 후 테스트 하는 전화 번호의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="6a40c-122">테스트 사례를 실행할 때 테스트 하는 숫자가 **예상한 번역**값을 반환 하지 않으면 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="6a40c-123">) **필요한 pstn 사용** 목록에서 지정 된 다이얼 플랜 및 음성 정책을 기반으로 테스트 사례를 실행할 때 사용 될 것으로 예상 되는 pstn (공용 전환 전화 네트워크) 사용 레코드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="6a40c-124">다른 PSTN 사용 레코드가 사용 되는 경우 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="6a40c-125">) 예상 되는 **경로** 목록에서 지정 된 다이얼 플랜 및 음성 정책을 기반으로 테스트 사례를 실행할 때 사용할 예상 되는 음성 경로를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="6a40c-126">다른 음성 경로를 사용 하는 경우 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="6a40c-127">) **실행** 을 클릭 하 여 테스트 사례를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="6a40c-128">결과는 페이지의 오른쪽 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="6a40c-129">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-129">Click **OK**.</span></span>

14. <span data-ttu-id="6a40c-130">**커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6a40c-131">음성 라우팅 테스트 사례를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="6a40c-132">자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a40c-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="6a40c-133">테스트에 사용 되는 다이얼 플랜에서 더하기 기호 (예: + 12065551219)로 시작 하는 전화 번호를 정규화 하면 해당 요금제로 인해 음성 라우팅 테스트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="6a40c-134">(다이얼 플랜 및 음성 경로는 작동 하는 반면, 실제로 테스트-CsDialPlan 플랜은 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="6a40c-135">그러나 음성 라우팅 테스트에 실패할 가능성이 있습니다. 이는 음성 경로 테스트 시 염두에 두어야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6a40c-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a40c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a40c-136">See Also</span></span>


[<span data-ttu-id="6a40c-137">Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기</span><span class="sxs-lookup"><span data-stu-id="6a40c-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="6a40c-138">Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기</span><span class="sxs-lookup"><span data-stu-id="6a40c-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="6a40c-139">Lync Server 2013에서 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="6a40c-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="6a40c-140">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="6a40c-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

