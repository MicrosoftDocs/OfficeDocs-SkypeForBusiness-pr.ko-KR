---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="03518-102">Lync Server 2013에서 음성 라우팅 테스트 사례 실행</span><span class="sxs-lookup"><span data-stu-id="03518-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03518-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="03518-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="03518-104">음성 라우팅 테스트 사례 도구 모음에서 모든 테스트 사례를 실행 하거나 하나 이상의 선택 된 테스트 사례를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03518-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="03518-105">모든 음성 라우팅 테스트 사례를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="03518-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="03518-106">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="03518-107">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03518-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="03518-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03518-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="03518-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03518-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="03518-110">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="03518-111">**음성 라우팅 테스트** 페이지에서 **작업** 을 클릭 한 다음 **모두 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="03518-112">각 테스트 사례의 합격 또는 불합격 상태는 **합격/불합격** 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="03518-113">테스트 사례가 아직 실행 되지 않은 경우에는 **성공/실패** 열에 N/a가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="03518-114">) 각 테스트 사례에 대 한 자세한 결과를 보려면 테스트 사례 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="03518-115">**테스트 사례 편집** 페이지의 오른쪽에 있는 회색 영역에 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="03518-116">**테스트 결과:** 테스트 사례 실행의 전체 통과 또는 실패 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="03518-117">**정규화 규칙:** 해당 번호와 일치 하는이 테스트 사례에 대해 선택한 다이얼 플랜의 첫 번째 정규화 규칙 ( **번호를 테스트** 필드에 입력 한 값)입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="03518-118">**정규화 된 번호:** 정규화 규칙으로 번역 한 후의 전화 번호 값입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="03518-119">**첫 번째 PSTN 사용:** 전화를 건 번호와 일치 하는이 테스트 사례에 대해 선택한 음성 정책의 첫 번째 PSTN (공개 전화 네트워크) 사용 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="03518-120">**첫 번째 경로:** 첫 번째 PSTN 사용 레코드에서 전화 번호와 일치 하는 첫 번째 음성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="03518-121">예상 되는 <STRONG>PSTN 사용 레코드</STRONG> 및 <STRONG>예상 경로</STRONG> 필드는 음성 라우팅 테스트 사례 구성에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="03518-122">테스트 사례에서 이러한 값을 지정 하지 않으면 테스트 결과의 해당 필드가 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="03518-123">하나 이상의 선택한 음성 라우팅 테스트 사례를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="03518-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="03518-124">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="03518-125">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03518-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="03518-126">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03518-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="03518-127">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03518-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="03518-128">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="03518-129">**음성 라우팅 테스트** 페이지에서 실행할 테스트 사례의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="03518-130">**작업** 메뉴에서 **선택 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="03518-131">각 테스트 사례의 합격 또는 불합격 상태는 **합격/불합격** 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="03518-132">테스트 사례가 아직 실행 되지 않은 경우에는 **성공/실패** 열에 N/a가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="03518-133">) 각 테스트 사례에 대 한 자세한 결과를 보려면 테스트 사례 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03518-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="03518-134">**테스트 사례 편집** 페이지의 오른쪽에 있는 회색 영역에 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="03518-135">**테스트 결과:** 테스트 사례 실행의 전체 통과 또는 실패 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="03518-136">**정규화 규칙:** 해당 번호와 일치 하는이 테스트 사례에 대해 선택한 다이얼 플랜의 첫 번째 정규화 규칙 ( **번호를 테스트** 필드에 입력 한 값)입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="03518-137">**정규화 된 번호:** 정규화 규칙으로 번역 한 후의 전화 번호 값입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="03518-138">**첫 번째 PSTN 사용:** 전화를 건 번호와 일치 하는이 테스트 사례에 대해 선택한 음성 정책의 첫 번째 PSTN 사용 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="03518-139">**첫 번째 경로:** 첫 번째 PSTN 사용 레코드에서 전화 번호와 일치 하는 첫 번째 음성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="03518-140">예상 되는 <STRONG>PSTN 사용 레코드</STRONG> 및 <STRONG>예상 경로</STRONG> 필드는 음성 라우팅 테스트 사례 구성에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="03518-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="03518-141">테스트 사례에서 이러한 값을 지정 하지 않으면 테스트 결과의 해당 필드가 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03518-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03518-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03518-142">See Also</span></span>


[<span data-ttu-id="03518-143">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="03518-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="03518-144">Lync Server 2013에서 음성 라우팅 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="03518-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

