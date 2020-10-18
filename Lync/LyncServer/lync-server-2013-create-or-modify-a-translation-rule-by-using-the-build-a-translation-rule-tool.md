---
title: 변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정
description: 변환 규칙 작성 도구를 사용 하 여 변환 규칙을 만들거나 수정 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116048fff834e797bca76a895f45cd0ebc83ab94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574524"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="50372-103">Lync Server 2013의 변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="50372-103">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50372-104">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="50372-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="50372-105">**변환 규칙 작성** 도구에서 값 집합을 입력 하 고 Lync Server 제어판을 사용 하도록 설정 하 여 해당 일치 패턴 및 변환 규칙을 생성할 수 있도록 변환 규칙을 정의 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="50372-106">또는 정규 표현식을 수동으로 작성하여 일치 패턴과 변환 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50372-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="50372-107">자세한 내용은 [Lync Server 2013에서 수동으로 변환 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-translation-rule-manually.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50372-107">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="50372-108">변환 규칙 작성 도구를 사용하여 규칙을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="50372-108">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="50372-109">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="50372-110">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50372-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="50372-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50372-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50372-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50372-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50372-113">변환 규칙 정의를 시작 하려면 [Lync server 2013에서 미디어 바이패스를 사용 하 여 온 트렁크 to media bypass](lync-server-2013-configure-a-trunk-with-media-bypass.md) 에서 10 단계까지 또는 [lync server 2013에서는 미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 하는 방법을 설명 하는 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="50372-114">**새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 아래에서 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-114">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="50372-115">(선택 사항) **설명** 아래에서 변환 규칙에 대한 설명을 **미국 국제 시외 전화**와 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-115">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="50372-116">대화 상자의 **변환 규칙 작성** 섹션에 있는 다음 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-116">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="50372-117">**시작 숫자**: (선택 사항) 패턴을 일치시킬 선행 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-117">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="50372-118">예를 들어 **+** +로 시작 하는 E. 164 형식의 번호를 일치 시키려면이 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-118">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="50372-p105">**길이**: 일치하는 패턴의 자릿수를 지정하고 패턴을 이 길이와 정확히 일치하는 번호와 일치시킬지 또는 이 길이 이상인 번호와 일치시킬지 또는 길이에 상관없이 일치시킬지 여부를 선택합니다 예를 들어 **11**을 입력하고 드롭다운 목록에서 **최소**를 선택하면 길이가 11자리 이상인 번호와 일치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50372-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="50372-121">**제거할 숫자**: (선택 사항) 제거할 시작 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-121">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="50372-122">예를 들어 **1** 을 입력 하 여 **+** 숫자의 시작 부분에서 번호를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-122">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="50372-p107">**추가할 숫자**: (선택 사항) 변환된 번호의 앞에 추가할 자릿수를 지정합니다. 예를 들어 **011**을 입력하면 규칙이 적용될 때 변환된 번호 앞에 011이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="50372-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="50372-p108">이 필드에 입력한 값은 **일치시킬 패턴** 및 **변환 규칙** 필드에 적용됩니다. 예를 들어 위의 예 값을 지정한 경우 **일치시킬 패턴** 필드의 정규식 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50372-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="50372-127">**^\\+ ( \\ d {9} \\ d +) $**</span><span class="sxs-lookup"><span data-stu-id="50372-127">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="50372-p109">**변환 규칙** 필드에서는 변환된 번호 형식에 대한 패턴이 지정됩니다. 이 패턴은 두 부분으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50372-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="50372-130">일치하는 패턴의 자릿수를 나타내는 값(예: **$1**)</span><span class="sxs-lookup"><span data-stu-id="50372-130">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="50372-131">(선택 사항) **추가할 숫자** 필드에 입력하여 번호 앞에 추가할 수 있는 값</span><span class="sxs-lookup"><span data-stu-id="50372-131">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="50372-132">위의 예 값을 사용하면 **변환 규칙** 필드에 **011$1**이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="50372-132">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="50372-133">이 변환 규칙이 적용되면 +441235551010이 011441235551010이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50372-133">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="50372-134">**확인**을 클릭하여 변환 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-134">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="50372-135">**확인**을 클릭하여 트렁크 구성을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-135">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="50372-136">**트렁크 구성** 페이지에서 **커밋**을 클릭하고 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-136">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="50372-137">변환 규칙을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50372-137">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="50372-138">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50372-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50372-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50372-139">See Also</span></span>


[<span data-ttu-id="50372-140">Lync Server 2013에서 수동으로 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="50372-140">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="50372-141">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="50372-141">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="50372-142">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="50372-142">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="50372-143">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="50372-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="50372-144">Lync Server 2013의 글로벌 미디어 바이패스 옵션</span><span class="sxs-lookup"><span data-stu-id="50372-144">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

