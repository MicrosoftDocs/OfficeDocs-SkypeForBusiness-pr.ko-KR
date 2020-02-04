---
title: 'Lync Server 2013: 음성 경로 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0731383eea99e7510ef1748777e7139e2d9f369
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="92f43-102">Lync Server 2013에서 음성 경로 수정</span><span class="sxs-lookup"><span data-stu-id="92f43-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92f43-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="92f43-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="92f43-104">이 항목에서는 음성 경로를 편집 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="92f43-105">새 경로를 만들려면 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="92f43-106">음성 경로를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="92f43-106">To modify a voice route</span></span>

1.  <span data-ttu-id="92f43-107">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="92f43-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="92f43-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92f43-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="92f43-111">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="92f43-112">**경로** 페이지에서 다음 방법 중 하나를 사용 하 여 음성 경로를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="92f43-113">음성 경로 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="92f43-114">음성 경로 이름을 클릭 하 고 **편집**을 클릭 한 다음 **복사**를 클릭 하 고 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-114">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="92f43-115">방금 만든 음성 경로의 새 복사본을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-115">Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="92f43-116">**음성 경로 편집** 페이지의 **이름** 필드에 음성 경로를 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="92f43-117">) **설명** 필드에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="92f43-118">이 경로에 적용할 패턴을 지정 하려면 **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하거나 수동으로 정규식을 작성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="92f43-119">**일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-119">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="92f43-120">두 가지 패턴 일치 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-120">You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="92f43-121">**허용 하려는 숫자의 시작 숫자:** 이 경로에 대해 수용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함).</span><span class="sxs-lookup"><span data-stu-id="92f43-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="92f43-122">예를 들어 **+ 425** 을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="92f43-123">경로에 포함 하려는 각 접두사 값에 대해이를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="92f43-124">**예외:** 접두사 값에 하나 이상의 예외를 지정 하려는 경우 접두사를 강조 표시 하 고 **예외**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="92f43-125">이 경로에 적용 *하지* 않으려는 일치 패턴에 대 한 값을 하나 이상 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="92f43-126">예를 들어 경로에서 + 425237으로 시작 하는 숫자를 제외 하려면 **예외** 필드에 **+ 425237** 값을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="92f43-127">일치 패턴을 수동으로 정의 하려면 **일치 하는 패턴 빌드** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 해당 하는 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="92f43-128">정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="92f43-129">발신 전화를 거는 전화 ID를 통화 수신자에 게 표시 하지 않으려면 **발신자 Id 표시 안** 함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-129">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="92f43-130">이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 ID** 를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-130">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="92f43-131">하나 이상의 PSTN (공개 교환 전화 네트워크) trunks를 음성 경로에 연결 하려면 **추가**를 클릭 한 다음 목록에서 트렁크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f43-132">배포에 Microsoft Office Communications Server 2007 R2 중재 서버가 포함 된 경우 목록 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="92f43-133">하나 이상의 PSTN 용도를 음성 경로에 연결 하려면 **선택을** 클릭 하 고 엔터프라이즈 음성 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f43-134">사용할 수 있는 각 PSTN 사용 레코드의 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 PSTN 사용 레코드 보기</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="92f43-135">PSTN 사용 레코드를 만들거나 편집 하려면 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync server 2013에서 음성 정책 만들기 및 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync server 2013에서 음성 정책 수정 및 pstn 사용 레코드 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="92f43-136">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-136">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="92f43-137">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-137">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f43-138">PSTN 사용 레코드가 나열 되는 순서와는 달리, 음성 경로에 있는 PSTN 사용 레코드의 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="92f43-139">그러나 RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도 별로 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="92f43-140">(Lync Server는 목록을 위에서 아래로 트래버스 합니다.)</span><span class="sxs-lookup"><span data-stu-id="92f43-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="92f43-141">) **번역 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-141">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="92f43-142">필드 아래에 테스트 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-142">The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f43-143">아직 테스트를 통과 하지 않은 음성 경로를 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="92f43-144">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="92f43-145">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-145">Click **OK**.</span></span>

14. <span data-ttu-id="92f43-146">**라우팅** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f43-147">음성 경로를 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92f43-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="92f43-148">자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92f43-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92f43-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92f43-149">See Also</span></span>


[<span data-ttu-id="92f43-150">Lync Server 2013에서 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="92f43-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="92f43-151">Lync Server 2013에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="92f43-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="92f43-152">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="92f43-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="92f43-153">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="92f43-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="92f43-154">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="92f43-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="92f43-155">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="92f43-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

