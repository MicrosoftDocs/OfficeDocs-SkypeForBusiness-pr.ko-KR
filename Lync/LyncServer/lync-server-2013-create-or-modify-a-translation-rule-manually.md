---
title: 'Lync Server 2013: 수동으로 번역 규칙 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="ca243-102">Lync Server 2013에서 수동으로 번역 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="ca243-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca243-103">_**마지막으로 수정한 주제:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="ca243-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="ca243-104">일치 패턴 및 번역 규칙에 대 한 정규식을 작성 하 여 번역 규칙을 정의 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ca243-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="ca243-105">또는 **번역 규칙 작성** 도구에서 값 집합을 입력 하 고 Lync Server 제어판을 사용 하 여 일치 하는 해당 패턴 및 번역 규칙을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="ca243-106">자세한 내용은 [Lync Server 2013에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca243-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="ca243-107">수동으로 번역 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="ca243-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="ca243-108">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ca243-109">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca243-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ca243-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca243-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca243-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca243-112">번역 규칙 정의를 시작 하려면 lync [server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md) 의 단계를 수행 하 고 lync server 2013에서 9 단계까지 [미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="ca243-113">**새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 필드에 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="ca243-114">) **설명**에 번역 규칙에 대 한 설명 (예: **US 국제 장거리 전화 걸기**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="ca243-115">**번역 규칙 작성** 섹션의 아래쪽에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="ca243-116">**정규식 입력**에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="ca243-117">**이 패턴과 일치**하는 경우 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="ca243-118">**번역 규칙**에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="ca243-119">예를 들어 **이 패턴과 일치** 하는 \*\* ^ \\+{9}\\\\(d d +) $\*\* 를 입력 하 고 **번역 규칙**에 **011 $1** 이 있으면 규칙에서 + 441235551010를 011441235551010로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="ca243-120">**확인** 을 클릭 하 여 번역 규칙을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="ca243-121">**확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="ca243-122">**트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca243-123">번역 규칙을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca243-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ca243-124">자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca243-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca243-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca243-125">See Also</span></span>


[<span data-ttu-id="ca243-126">Lync Server 2013에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="ca243-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="ca243-127">Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="ca243-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ca243-128">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="ca243-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="ca243-129">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="ca243-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ca243-130">Lync Server 2013의 글로벌 미디어 우회 옵션</span><span class="sxs-lookup"><span data-stu-id="ca243-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

