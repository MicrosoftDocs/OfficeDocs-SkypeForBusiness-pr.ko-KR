---
title: 'Lync Server 2013: 음성 경로 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a25f9d070c81d45ffc966be49560dc67c292c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="a1910-102">Lync Server 2013에서 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="a1910-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1910-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1910-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1910-104">다음 절차에서는 Lync Server 2013 제어판을 사용 하 여 새 음성 경로를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="a1910-105">기존 경로를 편집 하려면이 절차에 대 한 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="a1910-106">Lync Server 제어판을 사용 하 여 음성 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a1910-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1910-107">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="a1910-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1910-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1910-110">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="a1910-111">**회람**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-111">Click **Route**.</span></span>

5.  <span data-ttu-id="a1910-112">**새로 만들기** 를 클릭 하 여 **새 음성 경로** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="a1910-113">**Name (이름**)에 음성 경로를 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="a1910-114">) **설명**에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="a1910-115">이 경로에 적용할 패턴을 지정 하려면 **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하거나 수동으로 정규식을 작성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="a1910-116">**일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-116">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="a1910-117">두 가지 패턴 일치 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-117">You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="a1910-118">**허용 하려는 숫자의 시작 숫자:** 이 경로에 대해 수용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함).</span><span class="sxs-lookup"><span data-stu-id="a1910-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="a1910-119">예를 들어 **+ 425**을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="a1910-120">경로에 포함 하려는 각 접두사 값에 대해이를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="a1910-121">**예외:** 접두사 값에 하나 이상의 예외를 지정 하려는 경우 접두사를 강조 표시 하 고 **예외**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="a1910-122">이 경로에 적용 *하지* 않으려는 일치 패턴에 대 한 값을 하나 이상 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="a1910-123">예를 들어 경로에서 + 425237으로 시작 하는 숫자를 제외 하려면 **예외** 필드에 **+ 425237** 값을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a1910-124">일치 패턴을 수동으로 정의 하려면 **일치 하는 패턴 빌드** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 해당 하는 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="a1910-125">정규식을 작성 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 정규식"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="a1910-126">전화의 ID가 통화 수신자에 게 표시 되지 않도록 하려면 **발신자 Id 표시 안 함** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-126">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="a1910-127">이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 ID** 를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-127">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="a1910-128">하나 이상의 trunks 음성 경로에 연결 하려면 **추가** 를 클릭 한 다음 목록에서 트렁크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1910-129">배포에 Microsoft Office Communications Server 2007 R2 중재 서버가 포함 된 경우 목록 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="a1910-130">하나 이상의 PSTN (공개 전환 전화 네트워크)을 음성 경로에 연결 하려면 **선택을** 클릭 하 고 엔터프라이즈 음성 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1910-131">사용할 수 있는 각 PSTN 사용 레코드의 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 PSTN 사용 레코드 보기</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="a1910-132">PSTN 사용 레코드를 만들거나 편집 하려면 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync server 2013에서 음성 정책 만들기 및 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync server 2013에서 음성 정책 수정 및 pstn 사용 레코드 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="a1910-133">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-133">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="a1910-134">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-134">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1910-135">PSTN 사용 레코드가 나열 되는 순서와는 대조적으로, PSTN 사용 레코드가 음성 경로에 나열 되는 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="a1910-136">그러나 사용 빈도에 따라 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="a1910-137">예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="a1910-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="a1910-138">(Lync Server는 목록을 위에서 아래로 트래버스 합니다.)</span><span class="sxs-lookup"><span data-stu-id="a1910-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="a1910-139">) **번역 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-139">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="a1910-140">필드 아래에 테스트 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-140">The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1910-141">아직 테스트를 통과 하지 않은 음성 경로를 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="a1910-142">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="a1910-143">**확인** 을 클릭 하 여 음성 경로를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1910-144">음성 경로를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1910-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a1910-145">자세한 내용은 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1910-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1910-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1910-146">See Also</span></span>


[<span data-ttu-id="a1910-147">Lync Server 2013에서 음성 경로 수정</span><span class="sxs-lookup"><span data-stu-id="a1910-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="a1910-148">Lync Server 2013에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="a1910-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="a1910-149">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="a1910-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="a1910-150">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="a1910-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="a1910-151">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="a1910-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="a1910-152">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="a1910-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

