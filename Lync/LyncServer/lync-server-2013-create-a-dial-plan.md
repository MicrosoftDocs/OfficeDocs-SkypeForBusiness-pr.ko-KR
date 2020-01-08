---
title: 'Lync Server 2013: 다이얼 플랜 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8734ce4503ef62eb0fc04aab376f2819d1fc8fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="65c48-102">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="65c48-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65c48-103">_**마지막으로 수정한 주제:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="65c48-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="65c48-104">새 다이얼 플랜을 만들려면 다음 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="65c48-105">다이얼 플랜을 편집 하려는 경우 [에는 Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="65c48-106">다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="65c48-106">To create a dial plan</span></span>

1.  <span data-ttu-id="65c48-107">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="65c48-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="65c48-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="65c48-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="65c48-111">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **다이얼 플랜**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="65c48-112">**다이얼 플랜** 페이지에서 **새로 만들기** 를 클릭 하 고 다이얼 플랜의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="65c48-113">**사이트 다이얼 플랜** 은 사용자 다이얼 플랜에 할당 된 사용자 또는 그룹을 제외한 전체 사이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-113">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="65c48-114">다이얼 플랜의 범위에 대해 **사이트** 를 선택 하는 경우 **사이트 선택** 대화 상자에서 사이트를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-114">If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="65c48-115">사이트에 대 한 다이얼 플랜을 이미 만든 경우 사이트 **선택** 대화 상자에 해당 사이트가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-115">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="65c48-116">**풀 다이얼 플랜** 은 PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 등록자에 게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-116">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="65c48-117">다이얼 플랜의 범위에 대해 **Pool (풀** )을 선택 하는 경우 **서비스 선택** 대화 상자에서 PSTN 게이트웨이 또는 등록자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-117">If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="65c48-118">서비스에 대해 다이얼 플랜을 이미 만든 경우 (PSTN 게이트웨이 또는 등록자) 해당 서비스는 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-118">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="65c48-119">지정 된 사용자 또는 그룹에 **사용자 다이얼 플랜** 을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-120">다이얼 플랜 범위를 선택한 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="65c48-121">사용자 다이얼 플랜을 만드는 경우 **새 다이얼 플랜** 대화 상자의 **이름** 필드에 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-121">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="65c48-122">이 이름이 저장 된 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-122">After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-123">사이트 다이얼 플랜의 경우 <STRONG>이름</STRONG> 필드는 사이트 이름으로 미리 채워져 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="65c48-124">풀 다이얼 플랜의 경우 <STRONG>이름</STRONG> 필드는 PSTN 게이트웨이 또는 등록자 이름으로 미리 채워 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="65c48-125">**간단한 이름** 필드는 **이름** 필드에 표시 되는 것과 동일한 이름으로 미리 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-125">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="65c48-126">필요에 따라이 필드를 편집 하 여 다이얼 플랜이 적용 되는 사이트, 서비스 또는 사용자를 반영 하는 보다 설명적인 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-126">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="65c48-127"><STRONG>단순한 이름은</STRONG> Lync Server 배포 내의 모든 다이얼 플랜에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="65c48-128">영문자 또는 숫자, 하이픈 (-), 마침표 (.) 또는 밑줄 (_) 일 수 있는 256 유니코드 문자는 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="65c48-129"><STRONG>지원 되지 않는</STRONG> 문자는 RFC 3966 ()http://www.ietf.org/rfc/rfc3966.txt)에 정의 된 대로 공백 및 예약 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="65c48-130"><STRONG>간단한 이름</STRONG> 에 <STRONG>지원 되지</STRONG> 않는 예약 된 문자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="65c48-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="65c48-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="65c48-132">) **설명** 필드에 다이얼 플랜에 대 한 추가 설명 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="65c48-133">) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용 하려는 경우 **전화 접속 회의 영역**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-133">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="65c48-134">전화 접속 액세스 번호에이 다이얼 플랜을 사용 하지 않으려면이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-134">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-135">전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜에 연결 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="65c48-136">) 외부 회선을 사용 하기 위해 사용자가 하나 이상의 추가 선행 번호 (예: 9)를 사용 해야 하는 경우에만 **external access 접두사** 필드에 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="65c48-137">접두사 값에 4 자 (\#, \*및 0-9)를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-138">외부 액세스 접두사를 지정 하는 경우 접두사를 수용할 수 있는 새 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="65c48-139">다음과 같이 다이얼 플랜에 대 한 정규화 규칙을 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="65c48-140">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="65c48-141">**정규화 규칙 선택**에서 다이얼 플랜에 연결 하려는 규칙을 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="65c48-142">새 정규화 규칙을 정의 하 고 다이얼 플랜에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="65c48-143">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="65c48-144">다이얼 플랜에 이미 연결 된 정규화 규칙을 편집 하려면 규칙 이름을 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="65c48-145">규칙 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="65c48-146">기존 정규화 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용할 수 있도록 규칙 이름을 강조 표시 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="65c48-147">복사본 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="65c48-148">다이얼 플랜에서 정규화 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-149">각 다이얼 플랜에는 하나 이상의 관련 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="65c48-150">다이얼 플랜에 필요한 모든 정규화 규칙을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013에서 다이얼 플랜 및 정규화 규칙</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="65c48-151">다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-151">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="65c48-152">목록에서 규칙의 위치를 변경 하려면 규칙 이름을 강조 표시 한 다음 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-152">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="65c48-153">Lync Server는 위에서 아래로 표준화 규칙 목록을 트래버스 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="65c48-154">전화 거는 번호가 둘 이상의 정규화 규칙을 충족 하도록 다이얼 플랜을 구성한 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 먼저 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="65c48-155">기본 <STRONG>모든 정규화 유지</STRONG> 규칙 <STRONG>^ (\d{11}) $</STRONG> 는 11 자리 숫자와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="65c48-156">예를 들어 1425으로 시작 하는 11 자리 숫자와 일치 하는 정규화 규칙을 추가 하는 경우, 더 제한적인 <STRONG>^ (1425 \ d{7}) $</STRONG> 규칙 아래에 <STRONG>모두 유지</STRONG> 를 정렬 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="65c48-157">) 번호를 입력 하 여 다이얼 플랜을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-157">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="65c48-158">테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-158">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-159">아직 테스트를 통과 하지 않은 다이얼 플랜을 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="65c48-160">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="65c48-161">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-161">Click **OK**.</span></span>

14. <span data-ttu-id="65c48-162">**다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c48-163">다이얼 플랜을 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c48-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="65c48-164">자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65c48-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65c48-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65c48-165">See Also</span></span>


[<span data-ttu-id="65c48-166">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="65c48-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="65c48-167">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="65c48-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="65c48-168">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="65c48-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

