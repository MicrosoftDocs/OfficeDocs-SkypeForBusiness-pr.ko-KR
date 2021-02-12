---
title: 비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 발신자 ID를 구성하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804188"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="9f3fb-103">비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="9f3fb-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="9f3fb-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 발신자 ID를 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="9f3fb-105">비즈니스용 Skype 서버를 사용하여 호출된 사용자 전화 번호(즉, 전화  _번호)를_ E.164 형식에서 트렁크 피어(즉, 연결된 게이트웨이, PBX(Private Branch Exchange) 또는 SIP 트렁크)에 필요한 로컬 전화 번호 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="9f3fb-106">이렇게하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 규칙을 하나 이상 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="9f3fb-107">비즈니스용 Skype 서버는 발신자 전화 번호(즉, 발신자 전화 번호)를 E.164 형식에서 트렁크 피어에 필요한 로컬 전화 걸기 형식으로 변환하는 옵션도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="9f3fb-108">예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9f3fb-109">비즈니스용 Skype 서버 제어판을 사용하여 발신자 ID를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9f3fb-110">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="9f3fb-111">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **트렁크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="9f3fb-112">**트렁크** 구성 페이지에서 기존 트렁크(예: 전역 트렁크)를 두 번 클릭하여 트렁크 구성 편집 대화 **상자를** 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="9f3fb-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="9f3fb-113">발신자 ID 프레젠테이션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="9f3fb-114">Enterprise Voice 배포에서 사용 가능한 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9f3fb-115">호출 **번호 변환 규칙에서** 트렁크와 연결하려는 규칙을 클릭한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f3fb-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="9f3fb-116">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="9f3fb-117">새 규칙을 정의하는 데 대한 자세한 내용은 배포 설명서에서 변환 규칙  [정의를](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="9f3fb-118">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="9f3fb-119">자세한 내용은 배포 설명서에서 [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="9f3fb-120">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="9f3fb-121">자세한 내용은 [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="9f3fb-122">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="9f3fb-123">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


