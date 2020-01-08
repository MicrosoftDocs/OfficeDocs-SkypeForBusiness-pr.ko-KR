---
title: 'Lync Server 2013: 비공식적인 음성 라우팅 테스트 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="ed6ae-102">Lync Server 2013에서 비공식적인 음성 라우팅 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="ed6ae-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed6ae-103">_**마지막으로 수정한 주제:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="ed6ae-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="ed6ae-104">실제 테스트 사례를 만들기 전에 **음성 라우팅 테스트 사례 정보 만들기** 대화 상자를 사용 하 여 비공식적인 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="ed6ae-105">테스트 결과가 만족 스 러 우면 공식적인 테스트 사례로 저장 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="ed6ae-106">비공식적인 음성 라우팅 테스트를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="ed6ae-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="ed6ae-107">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ed6ae-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ed6ae-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed6ae-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed6ae-111">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="ed6ae-112">**음성 라우팅 테스트** 페이지에서 **음성 라우팅 테스트 케이스 정보 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="ed6ae-113">**전화 걸기 번호** 필드에이 테스트에 사용할 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="ed6ae-114">이 번호는 표준화 되어 **결과** 창의 정규화 된 **번호** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="ed6ae-115">**다이얼 플랜** 목록에서 전화를 걸 번호를 테스트 하는 데 사용할 다이얼 플랜을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="ed6ae-116">전역 다이얼 플랜을 기본값으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="ed6ae-117">테스트를 실행할 때이 다이얼 플랜에서 전화를 건 번호와 일치 하는 첫 번째 정규화 규칙이 **결과** 창의 **정규화 규칙** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="ed6ae-118">**음성 정책** 목록에서 전화를 걸 번호를 테스트 하는 데 사용할 음성 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="ed6ae-119">기본값은 전역 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="ed6ae-120">테스트를 실행할 때이 음성 정책에서 일치 하는 첫 번째 PSTN 사용 레코드가 **결과** 창의 **첫 PSTN 사용** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="ed6ae-121">또한이 PSTN 사용 레코드와 연결 된 첫 번째 일치 하는 음성 경로가 **첫 번째 경로** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="ed6ae-122">) 특정 사용자에 게 할당 된 음성 정책에 대해 전화 거는 번호를 테스트 하려면 **사용자 로부터 채우기** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="ed6ae-123">**찾아보기를** 클릭 하 여 **엔터프라이즈 음성 사용자 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="ed6ae-124">**찾기를** 클릭 하 여 엔터프라이즈 음성에 대해 설정 된 사용자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="ed6ae-125">이 테스트에 대해 배정 된 음성 정책이 사용 하려는 사용자 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="ed6ae-126">이제 **정책** 필드가 선택한 사용자에 게 할당 된 음성 정책으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="ed6ae-127">테스트를 실행할 때이 음성 정책에서 일치 하는 첫 번째 PSTN (공개 전화 네트워크) 사용 레코드가 **결과** 창의 **첫 번째 pstn 사용** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="ed6ae-128">또한이 PSTN 사용 레코드와 연결 된 첫 번째 일치 하는 음성 경로가 **첫 번째 경로** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="ed6ae-129">**실행** 을 클릭 하 여 테스트 사례를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="ed6ae-130">결과는 대화 상자의 오른쪽 패널에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="ed6ae-131">) 이 테스트 구성을 정식 테스트 사례로 저장 하려면 **다른 이름으로 저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="ed6ae-132">**음성 라우팅 테스트 사례 정보 저장** 대화 상자의 **이름** 필드에 테스트 사례의 고유한 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="ed6ae-133">이름은 엔터프라이즈 음성 배포의 모든 음성 라우팅 테스트 사례에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="ed6ae-134">길이는 최대 32 자로 지정할 수 있으며, 백슬래시 (\\), 마침표 (.), 밑줄 (\_) 외에도 영숫자 문자를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="ed6ae-135">**음성 라우팅 테스트 케이스 정보 저장** 대화 상자의 나머지 필드는 읽기 전용 이며 비공식적인 테스트 구성 *및* 결과에서 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="ed6ae-136">테스트 사례에 대해 저장 하려는 구성 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ed6ae-137">테스트 결과의 값은 다음과 같이 <STRONG>음성 라우팅 테스트 사례 정보 저장</STRONG> 대화 상자에서 필드를 미리 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="ed6ae-138"><STRONG>예상 번역</STRONG> 은 <STRONG>정규화 된 숫자</STRONG> 필드의 값으로 미리 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="ed6ae-139"><STRONG>예상 경로</STRONG> 는 <STRONG>첫 번째 경로</STRONG> 필드의 값으로 미리 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="ed6ae-140"><STRONG>필요한 pstn 사용 레코드</STRONG> 는 <STRONG>첫 번째 PSTN 사용</STRONG> 필드의 값으로 미리 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="ed6ae-141">테스트 실행 중에 이러한 값과 일치 하는 항목을 찾지 못한 경우 <STRONG>음성 라우팅 테스트 케이스 정보</STRONG> 대화 상자에서 해당 필드가 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="ed6ae-142">**확인** 을 클릭 하 여 테스트 사례를 저장 하거나, 반환 하려면 **취소** 를 클릭 하 여 **음성 라우팅 테스트 사례 정보 보기** 대화 상자로 돌아간 다음 저장 하기 전에 테스트를 더 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="ed6ae-143">**커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed6ae-144">음성 라우팅 테스트 사례를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 테스트 사례를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="ed6ae-145">자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed6ae-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed6ae-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed6ae-146">See Also</span></span>


[<span data-ttu-id="ed6ae-147">Lync Server 2013에서 음성 라우팅 테스트 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="ed6ae-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="ed6ae-148">Lync Server 2013에서 음성 라우팅 테스트 사례 실행</span><span class="sxs-lookup"><span data-stu-id="ed6ae-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="ed6ae-149">Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기</span><span class="sxs-lookup"><span data-stu-id="ed6ae-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="ed6ae-150">Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기</span><span class="sxs-lookup"><span data-stu-id="ed6ae-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="ed6ae-151">Lync Server 2013에서 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="ed6ae-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="ed6ae-152">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="ed6ae-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

