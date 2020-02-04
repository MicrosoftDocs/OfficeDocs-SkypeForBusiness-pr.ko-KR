---
title: 'Lync Server 2013: 발신자 ID 프레젠테이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afe4682250bd6065ba368d7812dfdcd5626042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="19215-102">Lync Server 2013의 발신자 ID 프레젠테이션</span><span class="sxs-lookup"><span data-stu-id="19215-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19215-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="19215-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="19215-104">Lync Server 2010을 사용 하면 호출 된 파티의 전화 번호 (전화 번호)를 트렁크 피어에 필요한 로컬 전화 걸기 형식 (연결 된 게이트웨이, 개인 분기 교환 (PBX) 또는 SIP 트렁크)으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19215-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="19215-105">이렇게 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 하나 이상의 번역 규칙을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="19215-106">Lync Server 2013는 전화 상대방의 전화 번호 (즉, 발신자가 전화를 거는 전화 번호)를 트렁크 피어에 필요한 지역 전화 걸기 형식으로 변환 하는 옵션도 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="19215-107">예를 들어 다이얼 문자열의 시작 부분에서 + 44을 제거 하 고 0144으로 바꾸는 번역 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19215-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="19215-108">**Lync Server 제어판을 사용 하 여 발신자 ID를 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="19215-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="19215-109">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="19215-110">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19215-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="19215-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="19215-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19215-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19215-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="19215-113">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="19215-114">**트렁크 구성** 페이지에서 기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="19215-115">발신자 ID 프레젠테이션을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="19215-116">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 번역 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="19215-117">**전화 번호 번역 규칙**에서 트렁크와 연결할 규칙을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="19215-118">새 번역 규칙을 정의 하 고 트렁크에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="19215-119">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19215-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="19215-120">트렁크에 이미 연결 된 번역 규칙을 편집 하려면 규칙 이름을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="19215-121">자세한 내용은 배포 설명서의 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19215-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="19215-122">기존 번역 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="19215-123">자세한 내용은 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19215-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="19215-124">트렁크에서 번역 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19215-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="19215-125">두 규칙이 충돌할 수 있으므로 연결 된 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙과 트렁크를 연결 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="19215-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

