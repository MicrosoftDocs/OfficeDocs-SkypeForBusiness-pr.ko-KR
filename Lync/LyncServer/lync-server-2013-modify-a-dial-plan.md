---
title: 'Lync Server 2013: 다이얼 플랜 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db84f9b353450419a8cc8029e4a24d01f0df76b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534415"
---
# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="ad5c0-102">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="ad5c0-102">Modify a dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad5c0-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ad5c0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ad5c0-104">기존의 다이얼 플랜을 수정하려면 다음 절차의 단계를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="ad5c0-105">새 다이얼 플랜을 만들려면 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="ad5c0-106">다이얼 플랜을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="ad5c0-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="ad5c0-107">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ad5c0-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ad5c0-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ad5c0-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ad5c0-111">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭한 다음 **다이얼 플랜**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="ad5c0-112">**다이얼 플랜** 페이지에서 다이얼 플랜 이름을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5c0-p104">다이얼 플랜 범위 및 이름은 다이얼 플랜이 만들어질 때 설정되었습니다. 이러한 설정은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="ad5c0-115">(선택 사항) **다이얼 플랜 편집**에서 **이름** 필드에 나타나는 것과 동일한 이름으로 미리 채워진 **단순한 이름** 필드를 편집하여 다이얼 플랜을 적용할 사이트, 서비스 또는 사용자를 나타내는 자세한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad5c0-116"><STRONG>단순 이름은</STRONG> Lync Server 2013 배포 내의 모든 다이얼 플랜에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="ad5c0-117">256 유니코드 문자를 초과할 수 없으며, 각각의 문자는 알파벳 문자 또는 숫자, 하이픈(-), 마침표(.), 더하기 기호(+) 또는 밑줄(_)이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="ad5c0-118"><STRONG>단순한 이름</STRONG> 필드에는 공백이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="ad5c0-119">(선택 사항) **설명** 필드에 다이얼 플랜에 대한 자세한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="ad5c0-p106">(선택 사항) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용하려면 **전화 접속 회의 지역**을 지정합니다. 전화 접속 액세스 번호에 이 다이얼 플랜을 사용하지 않으려면 이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5c0-122">전화 접속 회의 액세스 번호를 하나 이상의 다이얼 플랜과 연결하려면 전화 접속 회의 지역이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="ad5c0-123">(선택 사항) 사용자가 외부 회선에 연결하기 위해 하나 이상의 추가 선행 번호(예: 9)를 눌러야 하는 경우에만 **외부 액세스 접두사** 필드에 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="ad5c0-124">접두사 값으로 최대 4 자 (즉, 0-9)를 입력할 수 있습니다 \# \* .</span><span class="sxs-lookup"><span data-stu-id="ad5c0-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5c0-125">외부 액세스 접두사를 지정하면 접두사를 수용하기 위해 새 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="ad5c0-126">다이얼 플랜의 정규화 규칙을 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="ad5c0-127">Enterprise Voice 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ad5c0-128">**정규화 규칙 선택** 대화 상자에서 다이얼 플랜과 연결할 규칙을 강조한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="ad5c0-129">새 정규화 규칙을 정의하고 다이얼 플랜과 연결하려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="ad5c0-130">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="ad5c0-131">다이얼 플랜과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름을 강조하고 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="ad5c0-132">규칙 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="ad5c0-133">기존의 정규화 규칙을 복사한 후 이를 기반으로 새 규칙을 정의하려면 규칙 이름을 강조하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="ad5c0-134">복사본 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="ad5c0-135">정규화 규칙을 다이얼 플랜에서 제거하려면 규칙 이름을 강조하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5c0-136">각각의 다이얼 플랜마다 적어도 하나의 정규화 규칙이 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="ad5c0-137">다이얼 플랜에 필요한 모든 정규화 규칙을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013에서 다이얼 플랜 및 정규화 규칙</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="ad5c0-p113">다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬되어 있는지 확인합니다. 목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad5c0-140">Lync Server는 정규화 규칙 목록을 위에서 아래로 이동 하 고 전화 건 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="ad5c0-141">전화를 건 번호가 둘 이상의 정규화 규칙과 일치하도록 다이얼 플랜을 구성하는 경우 더 제한적인 규칙을 덜 제한적인 규칙보다 위에 정렬되게 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="ad5c0-142">기본 <STRONG>모든 정규화 유지</STRONG> 규칙 <STRONG>^ (\d {11} ) $</STRONG> 는 11 자리 숫자와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="ad5c0-143">예를 들어 1425으로 시작 하는 11 자리 번호와 일치 하는 정규화 규칙을 추가 하는 경우에는 <STRONG>모두 유지</STRONG> 를 보다 제한적인 <STRONG>^ (1425 {7} ) $</STRONG> rule 아래에 정렬 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="ad5c0-p116">(선택 사항) 다이얼 플랜을 테스트할 번호를 입력한 다음 **이동**을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5c0-146">아직 테스트를 통과하지 않은 다이얼 플랜을 저장한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ad5c0-147">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="ad5c0-148">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-148">Click **OK**.</span></span>

13. <span data-ttu-id="ad5c0-149">**다이얼 플랜** 페이지에서 **커밋**을 클릭한 다음 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5c0-150">다이얼 플랜을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하며 구성 변경을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ad5c0-151">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad5c0-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad5c0-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad5c0-152">See Also</span></span>


[<span data-ttu-id="ad5c0-153">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="ad5c0-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="ad5c0-154">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="ad5c0-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ad5c0-155">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="ad5c0-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

