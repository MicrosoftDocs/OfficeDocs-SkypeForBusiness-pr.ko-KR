---
title: 직접 라우팅에 대한 긴급 통화 라우팅 정책 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 긴급 통화 라우팅 정책을 사용하여 비상 Microsoft Teams 설정하고 긴급 통화가 라우팅되는 방법을 지정하는 방법에 대해 자세히 알아보습니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 86f73bed2e086efee666e5592ca3f42e9756096c
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354308"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a><span data-ttu-id="9be80-103">직접 라우팅에 대한 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="9be80-103">Manage emergency call routing policies for Direct Routing</span></span>

<span data-ttu-id="9be80-104">조직에서 직접 라우팅을 전화 시스템 경우 해당 조직에서 긴급 통화 라우팅 정책을 사용하여 Microsoft Teams 긴급 번호를 설정하고 긴급 통화가 라우팅되는 방법을 지정할 수 있습니다. [](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="9be80-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="9be80-105">긴급 통화 라우팅 정책은 정책을 할당한 사용자에게 향상된 응급 서비스를 사용하도록 설정하는지 여부, 긴급 서비스를 호출하는 데 사용되는 번호(예: 미국의 911) 및 응급 서비스에 대한 호출 라우팅 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-105">An emergency call routing policy determines whether enhanced emergency services are enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="9be80-106">관리 센터의 Voice Emergency 정책으로 Microsoft Teams 또는 전화 통화를 사용하여 긴급 통화 라우팅 정책을  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9be80-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="9be80-107">정책은 사용자 및 네트워크 사이트에 [할당될 수 있습니다.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9be80-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="9be80-108">사용자의 경우 전역(Org-wide default) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="9be80-109">사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="9be80-110">전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="9be80-111">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="9be80-112">네트워크 사이트 및 사용자에게 긴급 호출 라우팅 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 재지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="9be80-113">사용자 지정 긴급 호출 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9be80-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9be80-114">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9be80-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9be80-115">관리 센터의 왼쪽 Microsoft Teams 음성 긴급 정책으로 이동한 다음 라우팅 정책 호출  >   **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9be80-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="9be80-116">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-116">Click **Add**.</span></span>
3. <span data-ttu-id="9be80-117">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="9be80-118">동적 긴급 호출을 사용하도록 설정하려면 동적 긴급 호출 **을 를 켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9be80-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="9be80-119">동적 긴급 호출을 사용하도록 Teams 서비스에서 정책 및 위치 정보를 검색하고 해당 정보를 긴급 호출의 일부로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="9be80-120">하나 이상의 긴급 번호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="9be80-121">이렇게하려면 긴급 번호에서 **추가** **를** 클릭한 다음 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="9be80-122">**긴급 다이얼 문자열**: 긴급 다이얼 문자열을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="9be80-123">이 다이얼 문자열은 호출이 긴급 호출인 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="9be80-124">직접 라우팅의 경우 긴급 전화 Teams 앞에 "+"를 사용하여 긴급 전화를 보내는 클라이언트에서 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="9be80-125">전환이 완료될 때까지 비상 다이얼 문자열과 일치하는 음성 경로 패턴은 911 및 +911과 같은 이전 "+"이 없는 문자열에 대해 일치하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="9be80-126">예를 들어 ^ \\ +?911 또는 .\*입니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="9be80-127">**긴급 다이얼 마스크**: 각 긴급 번호에 대해 0개 이상의 긴급 다이얼 마스크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="9be80-128">다이얼 마스크는 긴급 다이얼 문자열의 값으로 변환하려는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="9be80-129">이렇게 하면 대체 긴급 번호에 전화를 걸 수 있으며 통화 도달 응급 서비스를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="9be80-130">예를 들어 112를 유럽 대부분의 응급 서비스 번호인 비상 다이얼 마스크로 추가하고 911을 긴급 다이얼 문자열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="9be80-131">Teams 유럽의 한 사용자가 911이 미국의 긴급 번호인지 알지 못하고 112에 전화를 걸면 911에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="9be80-132">여러 다이얼 마스크를 정의하기 위해 각 값을 세미코론으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="9be80-133">예를 들어 112;212.</span><span class="sxs-lookup"><span data-stu-id="9be80-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="9be80-134">**PSTN 사용 레코드:** PSTN(공용 전환 전화 네트워크) 사용 레코드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="9be80-135">PSTN 사용 레코드는 사용 권한이 부여된 사용자의 긴급 호출을 라우팅하는 데 사용되는 경로를 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="9be80-136">이 사용과 연결된 경로는 긴급 통화 전용 SIP(세션 시작 프로토콜) 트렁크 또는 가장 가까운 PSAP(공공 안전 응답 지점)에 긴급 호출을 라우팅하는 ELIN(긴급 위치 식별 번호) 게이트웨이를 지적해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9be80-137">전화 걸기 문자열 및 다이얼 마스크는 정책 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="9be80-138">즉, 정책의 경우 여러 긴급 번호를 정의할 수 있으며 다이얼 문자열에 대해 여러 다이얼 마스크를 설정할 수 있지만 각 다이얼 문자열 및 다이얼 마스크는 한 번만 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="9be80-139">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9be80-140">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="9be80-140">Using PowerShell</span></span>

<span data-ttu-id="9be80-141">[New-CsTeamsEmergencyCallRoutingPolicy 를 참조합니다.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="9be80-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="9be80-142">긴급 통화 라우팅 정책 편집</span><span class="sxs-lookup"><span data-stu-id="9be80-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9be80-143">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9be80-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9be80-144">전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="9be80-145">관리 센터의 왼쪽 Microsoft Teams 음성 긴급 정책으로 이동한 다음 라우팅 정책 호출  >   **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9be80-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="9be80-146">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="9be80-147">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9be80-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9be80-148">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="9be80-148">Using PowerShell</span></span>

<span data-ttu-id="9be80-149">[Set-CsTeamsEmergencyCallRoutingPolicy 를 참조합니다.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="9be80-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="9be80-150">사용자에게 사용자 지정 긴급 통화 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9be80-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="9be80-151">[Grant-CsTeamsEmergencyCallRoutingPolicy 를 참조합니다.](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="9be80-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="9be80-152">네트워크 사이트에 사용자 지정 긴급 통화 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9be80-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="9be80-153">[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 호출 라우팅 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="9be80-154">이 예제에서는 Site1 사이트에 긴급 통화 라우팅 정책 1이라는 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9be80-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="9be80-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9be80-155">Related topics</span></span>

[<span data-ttu-id="9be80-156">긴급 통화 정책 관리 Teams</span><span class="sxs-lookup"><span data-stu-id="9be80-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="9be80-157">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="9be80-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="9be80-158">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9be80-158">Assign policies to your users in Teams</span></span>](assign-policies.md)