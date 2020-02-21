---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="af13f-102">Lync Server 2013에서 음성 라우팅 테스트 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="af13f-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af13f-103">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="af13f-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="af13f-104">테스트 사례를 만들려면</span><span class="sxs-lookup"><span data-stu-id="af13f-104">To create a test case</span></span>

1.  <span data-ttu-id="af13f-105">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="af13f-106">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af13f-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="af13f-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="af13f-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af13f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af13f-109">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭하고 **음성 라우팅 테스트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="af13f-110">**음성 라우팅 테스트** 페이지에서 **새로 만들기**를 클릭하여 새 테스트 사례를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="af13f-111">**이름**에 테스트 사례의 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="af13f-112">이 이름은 엔터프라이즈 음성 배포의 모든 음성 라우팅 테스트 사례에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="af13f-113">이 길이는 최대 32 자까지 사용할 수 있으며 백슬래시 (\\), 마침표 (.) 또는 밑줄 (\_) 외에 영숫자 문자를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="af13f-p104">**테스트를 위해 전화를 건 번호**에 이 테스트 사례에 대해 지정하는 라우팅 구성을 테스트하기 위해 사용하려는 전화를 건 번호를 입력합니다. 다이얼 플랜 및 음성 정책에 따라 이 번호는 정규화되어 출력으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="af13f-p105">**다이얼 플랜** 목록에서 테스트를 실행할 때 사용할 다이얼 플랜을 선택합니다. 기본값은 전역 다이얼 플랜입니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="af13f-p106">**음성 정책** 목록에서 테스트를 실행할 때 사용할 음성 정책을 선택합니다. 기본값은 전역 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="af13f-p107">**예상 변환**에 변환 후 표시하려는 형식으로 전화 번호를 입력합니다. 이 값은 선택한 다이얼 플랜에서 일치하는 첫 번째 정규화 규칙으로 현재 테스트 중인 전화 번호가 변환된 이후의 값입니다. 테스트 사례를 실행할 때 테스트 중인 번호가 **예상 변환**의 값으로 표시되지 않으면 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="af13f-p108">(선택 사항) **예상 PSTN 사용** 목록에서 지정된 다이얼 플랜 및 음성 정책을 기반으로 테스트 사례를 실행할 때 사용할 PSTN(공중 전화망) 사용 레코드를 선택할 수 있습니다. 다른 PSTN 사용 레코드가 사용된 경우 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="af13f-p109">(선택 사항) **예상 경로** 목록에서는 지정된 다이얼 플랜 및 음성 정책을 기반으로 테스트 사례를 실행할 때 사용될 것으로 예상되는 음성 경로를 선택할 수 있습니다. 다른 음성 경로가 사용되는 경우에는 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="af13f-p110">(선택 사항) **실행**을 클릭하여 테스트 사례를 실행합니다. 결과는 페이지의 아래쪽 패널에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="af13f-129">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-129">Click **OK**.</span></span>

14. <span data-ttu-id="af13f-130">**커밋**, **모두 커밋**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af13f-131">음성 라우팅 테스트 사례를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="af13f-132">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af13f-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="af13f-133">테스트에 사용 되는 다이얼 플랜에서 + 12065551219와 같이 더하기 기호로 시작 하는 전화 번호를 정규화 하면 해당 계획으로 인해 음성 라우팅 테스트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="af13f-134">(다이얼 플랜 및 음성 경로는 작동 하지만 실제로 테스트-CsDialPlan 플랜은 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="af13f-135">하지만 음성 라우팅 테스트에 실패할 수 있습니다. 이는 음성 경로를 테스트할 때 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af13f-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af13f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af13f-136">See Also</span></span>


[<span data-ttu-id="af13f-137">Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기</span><span class="sxs-lookup"><span data-stu-id="af13f-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="af13f-138">Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기</span><span class="sxs-lookup"><span data-stu-id="af13f-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="af13f-139">Lync Server 2013에서 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="af13f-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="af13f-140">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="af13f-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

