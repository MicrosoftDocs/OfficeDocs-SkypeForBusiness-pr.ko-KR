---
title: Microsoft 팀에서 음성 라우팅 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 음성 라우팅 정책을 만들고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e3dc656043776d3a2f0e5b37a0c35ab98b7c03f7
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938129"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="800b6-103">Microsoft 팀에서 음성 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="800b6-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="800b6-104">조직에 [직접 전화 시스템 라우팅을](direct-routing-landing-page.md) 배포한 경우 비즈니스용 Skype Online 사용자가 온-프레미스 전화 통신 인프라를 사용 하 여 PSTN (공개 교환 전화 네트워크)에 전화를 걸거나 받을 수 있도록 음성 라우팅 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="800b6-105">음성 라우팅 정책은 PSTN 사용 레코드에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="800b6-106">**Voice**  >  Microsoft 팀 관리 센터에서 음성**음성 라우팅 정책** 으로 가거나 Windows PowerShell을 사용 하 여 음성 라우팅 정책을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="800b6-107">전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="800b6-108">사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="800b6-109">전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="800b6-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="800b6-110">사용자에 게 음성 라우팅 정책을 할당 하 여 팀에서 PSTN 통화를 할 수는 없다는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="800b6-111">또한 사용자가 전화 시스템 다이렉트 라우팅과 다른 구성 단계를 완료 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="800b6-112">자세히 알아보려면 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800b6-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="800b6-113">사용자 지정 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="800b6-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="800b6-114">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="800b6-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="800b6-115">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **음성 라우팅 정책**으로 이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="800b6-116">![Microsoft 팀 관리 센터의 음성 라우팅 정책 추가 페이지 스크린샷](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="800b6-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="800b6-117">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="800b6-118">**Pstn 사용 레코드**에서 **pstn 사용량 추가**를 클릭 한 다음 추가 하려는 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="800b6-119">새 PSTN 사용 레코드를 만들어야 할 경우 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="800b6-120">여러 PSTN 사용 레코드를 추가한 경우 원하는 순서 대로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="800b6-121">작업을 마치면 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="800b6-122">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="800b6-123">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="800b6-123">Using PowerShell</span></span>

<span data-ttu-id="800b6-124">[새로운 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800b6-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="800b6-125">음성 라우팅 정책 편집</span><span class="sxs-lookup"><span data-stu-id="800b6-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="800b6-126">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="800b6-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="800b6-127">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="800b6-128">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **음성 라우팅 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="800b6-129">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="800b6-130">**PSTN 사용 레코드 추가/제거**를 클릭 하 고 원하는 대로 변경한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="800b6-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="800b6-131">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="800b6-131">Using PowerShell</span></span>

<span data-ttu-id="800b6-132">[Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800b6-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="800b6-133">사용자에 게 사용자 지정 음성 라우팅 정책 지정</span><span class="sxs-lookup"><span data-stu-id="800b6-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="800b6-134">[허용-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="800b6-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="800b6-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="800b6-135">Related topics</span></span>

[<span data-ttu-id="800b6-136">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="800b6-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="800b6-137">다이렉트 라우팅에 대 한 음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="800b6-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="800b6-138">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="800b6-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="800b6-139">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="800b6-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
