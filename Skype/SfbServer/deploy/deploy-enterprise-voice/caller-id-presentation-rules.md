---
title: 비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션의 번역 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 발신자 ID를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: ca35b3398732296f435196ffeb38d915472b303d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233979"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="9c06e-103">비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션의 번역 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="9c06e-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="9c06e-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 발신자 ID를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="9c06e-105">비즈니스용 Skype 서버를 사용 하는 경우, 호출 된 상대방의 전화 번호 (전화 번호)를 _트렁크 피어_ 에 필요한 로컬 전화 걸기 형식으로 변환할 수 있습니다 (즉, 연결 된 게이트웨이, 사설 분기 교환 ( PBX) 또는 SIP 트렁크).</span><span class="sxs-lookup"><span data-stu-id="9c06e-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="9c06e-106">이렇게 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 하나 이상의 번역 규칙을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="9c06e-107">비즈니스용 Skype 서버는 또한 전화 상대의 전화 번호 (즉, 발신자가 통화 하는 전화 번호)를 트렁크 피어에 필요한 지역 전화 걸기 형식으로 변환 하는 옵션도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="9c06e-108">예를 들어 다이얼 문자열의 시작 부분에서 + 44을 제거 하 고 0144으로 바꾸는 번역 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9c06e-109">비즈니스용 Skype Server 제어판을 사용 하 여 발신자 ID를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="9c06e-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9c06e-110">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="9c06e-111">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="9c06e-112">**트렁크 구성** 페이지에서 기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="9c06e-113">발신자 ID 프레젠테이션을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="9c06e-114">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 번역 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9c06e-115">**전화 번호 번역 규칙**에서 트렁크와 연결할 규칙을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="9c06e-116">새 번역 규칙을 정의 하 고 트렁크에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="9c06e-117">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c06e-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="9c06e-118">트렁크에 이미 연결 된 번역 규칙을 편집 하려면 규칙 이름을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="9c06e-119">자세한 내용은 배포 설명서에서 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c06e-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="9c06e-120">기존 번역 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="9c06e-121">자세한 내용은 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c06e-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="9c06e-122">트렁크에서 번역 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c06e-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="9c06e-123">두 규칙이 충돌할 수 있으므로 연결 된 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙과 트렁크를 연결 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9c06e-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


