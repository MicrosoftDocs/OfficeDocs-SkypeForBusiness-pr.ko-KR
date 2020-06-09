---
title: 긴급 전화 라우팅 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 긴급 전화 번호를 설정 하 고 긴급 전화의 라우팅 방법을 지정 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b200f5a160e7b13a9412d588f3342eeb5a08ccd8
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638697"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="c2983-103">Microsoft 팀에서 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="c2983-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="c2983-104">조직에 [직접 전화 시스템 라우팅을](direct-routing-landing-page.md) 배포한 경우 Microsoft 팀에서 비상 전화 라우팅 정책을 사용 하 여 비상 전화 번호를 설정 하 고 긴급 통화의 라우팅 방식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="c2983-105">긴급 통화 라우팅 정책은 정책에 할당 된 사용자에 게 향상 된 응급 서비스를 사용할 수 있는지 여부, 비상 서비스를 호출 하는 데 사용 되는 번호 (예: 미국 내 911), 그리고 비상 서비스에 대 한 통화가 라우팅되는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="c2983-106">**Voice**  >  Microsoft 팀 관리 센터에서 또는 Windows PowerShell을 사용 하 여 음성**응급 정책** 으로 이동해 서 긴급 통화 라우팅 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="c2983-107">사용자 및 [네트워크 사이트](cloud-voice-network-settings.md)에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="c2983-108">사용자의 경우 전역 (조직 차원의 기본값) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="c2983-109">사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c2983-110">전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2983-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="c2983-111">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="c2983-112">네트워크 사이트에 대 한 긴급 통화 라우팅 정책을 할당 하 고 사용자에 게 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="c2983-113">사용자 지정 긴급 통화 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c2983-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c2983-114">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="c2983-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c2983-115">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음 **전화 라우팅 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c2983-116">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-116">Click **Add**.</span></span>
3. <span data-ttu-id="c2983-117">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="c2983-118">동적 비상 전화를 사용 하려면 **동적인 비상 전화**를 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="c2983-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="c2983-119">동적 긴급 통화를 사용 하도록 설정 하면 팀에서 서비스의 정책 및 위치 정보를 검색 하 고 긴급 통화의 일부로 해당 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="c2983-120">하나 이상의 긴급 전화 번호를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="c2983-121">이렇게 하려면 **비상 번호**에서 **추가**를 클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="c2983-122">**비상 다이얼 문자열**: 비상 다이얼 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="c2983-123">이 다이얼 문자열은 통화가 비상 통화로 표시 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="c2983-124">직접 라우팅의 경우 긴급 전화 다이얼 문자열 앞에 "+"를 사용 하 여 긴급 전화를 보내는 팀 클라이언트에서 멀리 전환 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="c2983-125">전환이 완료 될 때까지 긴급 전화 접속 문자열과 일치 하는 음성 경로 패턴은 911 및 + 911와 같이 앞에 "+"가 없는 문자열에 대해 일치가 수행 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="c2983-126">예를 들어 ^ \\ +? 911 또는. \*를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="c2983-127">**응급 전화 접속 마스크**: 각 비상 전화 번호에 대해 0 개 이상의 비상 다이얼 마스크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="c2983-128">다이얼 마스크는 비상 다이얼 문자열의 값으로 번역 하려는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="c2983-129">이렇게 하면 대체 비상 번호를 사용 하 여 전화를 걸고 통화에도 비상 서비스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="c2983-130">예를 들어 112을 긴급 전화 접속 마스크 (대부분 유럽의 비상 서비스 번호)로 추가 하 고 비상 다이얼 문자열로 911을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="c2983-131">방문 하는 유럽 지역의 팀 사용자는 911이 미국에서 긴급 번호 라는 것을 알지 못할 수 있으며, 112가 전화를 거는 경우 911에 통화가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="c2983-132">여러 다이얼 마스크를 정의 하려면 각 값을 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="c2983-133">예를 들어 112; 212.</span><span class="sxs-lookup"><span data-stu-id="c2983-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="c2983-134">**Pstn 사용 레코드**: Pstn (공개 교환 전화 네트워크) 사용 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="c2983-135">PSTN 사용 레코드는 사용 하도록 승인 된 사용자 로부터 비상 통화를 라우팅하는 데 사용 되는 경로를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="c2983-136">이 사용과 연결 된 경로는 비상 전화 전용 SIP (세션 초기화 프로토콜) 트렁크 또는 가까운 공공 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 비상 위치 Id 번호 (ELIN) 게이트웨이를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2983-137">다이얼 문자열과 다이얼 마스크는 정책 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="c2983-138">즉, 정책의 경우 여러 응급 번호를 정의할 수 있으며, 다이얼 문자열에 여러 개의 다이얼 마스크를 설정할 수 있지만 각 다이얼 문자열 및 다이얼 마스크는 한 번만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="c2983-139">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c2983-140">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c2983-140">Using PowerShell</span></span>

<span data-ttu-id="c2983-141">[새로운 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2983-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="c2983-142">긴급 통화 라우팅 정책 편집</span><span class="sxs-lookup"><span data-stu-id="c2983-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c2983-143">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="c2983-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c2983-144">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="c2983-145">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음 **전화 라우팅 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c2983-146">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c2983-147">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c2983-148">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c2983-148">Using PowerShell</span></span>

<span data-ttu-id="c2983-149">[Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2983-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="c2983-150">사용자에 게 사용자 지정 긴급 전화 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c2983-150">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c2983-151">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="c2983-151">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c2983-152">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-152">To assign a policy to one user:</span></span>

1. <span data-ttu-id="c2983-153">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c2983-154">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-154">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="c2983-155">**비상 전화 라우팅 정책**에서 할당할 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-155">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="c2983-156">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-156">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="c2983-157">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-157">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="c2983-158">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-158">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c2983-159">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-159">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="c2983-160">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-160">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="c2983-161">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-161">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c2983-162">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음 **전화 라우팅 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-162">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c2983-163">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-163">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c2983-164">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-164">Select **Manage users**.</span></span>
4. <span data-ttu-id="c2983-165">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c2983-165">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c2983-166">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-166">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c2983-167">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-167">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c2983-168">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c2983-168">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="c2983-169">사용자에 게 사용자 지정 긴급 통화 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c2983-169">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="c2983-170">[허용-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2983-170">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="c2983-171">그룹의 사용자에 게 사용자 지정 긴급 전화 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c2983-171">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="c2983-172">이미 확인 한 여러 사용자에 게 사용자 지정 긴급 전화 라우팅 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-172">You may want to assign a custom emergency call routing policy to multiple users that you've already identified.</span></span> <span data-ttu-id="c2983-173">예를 들어 보안 또는 메일 그룹의 모든 사용자에 게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-173">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="c2983-174">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-174">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="c2983-175">이 예제에서는 Contoso HR 그룹의 모든 사용자에 게 HR 비상 통화 라우팅 정책 이라는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-175">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="c2983-176">먼저 [모든 Microsoft 365 또는 Office 365 서비스에 연결의 단계를 단일 Windows powershell 창에](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-176">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c2983-177">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-177">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="c2983-178">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-178">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c2983-179">특정 팀 정책에 그룹의 모든 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-179">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="c2983-180">이 예제에서는 HR 긴급 통화 라우팅 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-180">In this example, it's HR Emergency Call Routing Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallRoutingPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="c2983-181">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-181">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="c2983-182">네트워크 사이트에 사용자 지정 긴급 전화 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c2983-182">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="c2983-183">[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용 하 여 네트워크 사이트에 긴급 통화 라우팅 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-183">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="c2983-184">이 예제에서는 비상 통화 라우팅 정책 1 이라는 정책을 Site1 사이트에 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2983-184">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="c2983-185">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c2983-185">Related topics</span></span>

- [<span data-ttu-id="c2983-186">팀에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="c2983-186">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="c2983-187">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="c2983-187">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c2983-188">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c2983-188">Assign policies to your users in Teams</span></span>](assign-policies.md)
