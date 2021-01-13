---
title: Microsoft Teams에서 음성 라우팅 정책 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 음성 라우팅 정책을 만들고 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802558"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="42a32-103">Microsoft Teams에서 음성 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="42a32-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="42a32-104">조직에서 전화 시스템 [](direct-routing-landing-page.md) 직접 라우팅을 배포한 경우 음성 라우팅 정책을 사용하여 Teams 및 비즈니스용 Skype Online 사용자가 사용자의 PSTN(공용 전환 전화 네트워크)을 수신하고 전화를 걸 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="42a32-105">음성 라우팅 정책은 PSTN 사용 레코드에 대한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="42a32-106">Microsoft Teams 관리 센터에서 음성 라우팅 정책으로 또는 음성 라우팅 정책을 사용하여 음성 라우팅 정책을 만들고  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42a32-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="42a32-107">전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="42a32-108">사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 전역 정책을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="42a32-109">전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="42a32-110">사용자에게 음성 라우팅 정책을 할당해도 Teams에서 PSTN 통화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="42a32-111">또한 전화 시스템 직접 라우팅에 대해 사용자를 사용하도록 설정하고 다른 구성 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="42a32-112">자세한 내용은 직접 라우팅 [구성을 참조합니다.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="42a32-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="42a32-113">사용자 지정 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="42a32-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="42a32-114">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="42a32-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="42a32-115">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 음성 라우팅 정책으로 이동한 다음  >  추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="42a32-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="42a32-116">![Microsoft Teams 관리 센터의 음성 라우팅 정책 추가 페이지의 스크린샷 ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="42a32-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="42a32-117">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="42a32-118">**PSTN** 사용 레코드 아래에서 **PSTN** 사용량 추가를 클릭한 다음 추가할 레코드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="42a32-119">새 PSTN 사용 레코드를 만들어야 하는 경우 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="42a32-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="42a32-120">여러 PSTN 사용 현황 레코드를 추가한 경우 원하는 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="42a32-121">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="42a32-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="42a32-122">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="42a32-123">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="42a32-123">Using PowerShell</span></span>

<span data-ttu-id="42a32-124">[New-CsOnlineVoiceRoutingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="42a32-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="42a32-125">음성 라우팅 정책 편집</span><span class="sxs-lookup"><span data-stu-id="42a32-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="42a32-126">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="42a32-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="42a32-127">전역 정책 또는 만든 모든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42a32-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="42a32-128">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 라우팅  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="42a32-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="42a32-129">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="42a32-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="42a32-130">**PSTN 사용 레코드 추가/제거를** 클릭하고 원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="42a32-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="42a32-131">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="42a32-131">Using PowerShell</span></span>

<span data-ttu-id="42a32-132">[Set-CsOnlineVoiceRoutingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="42a32-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="42a32-133">사용자에게 사용자 지정 음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="42a32-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="42a32-134">[Grant-CsOnlineVoiceRoutingPolicy도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="42a32-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="42a32-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="42a32-135">Related topics</span></span>

[<span data-ttu-id="42a32-136">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="42a32-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="42a32-137">직접 라우팅에 대한 음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="42a32-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="42a32-138">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="42a32-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="42a32-139">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="42a32-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
