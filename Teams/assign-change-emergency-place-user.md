---
title: 지정, 사용자의 긴급 위치에 대 한 위치 변경
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 이 문서에서는 조직의 사용자에 대 한 긴급 위치를 할당 하거나 변경 하는 방법을 설명 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539515"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="99904-103">사용자에 대 한 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="99904-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="99904-104">사용자에 게 전화 번호를 할당할 때 각 활성 전화 번호에는 비상 위치가 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="99904-105">(Office 365에서 전화 번호를 받을 때 주소를 연결 하거나 전화 번호를 전송 하는 경우) 비상 위치와 번호를 연결 하는 경우 실제 위치 내에서 더 정확한 위치를 제공 하는 위치를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99904-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="99904-106">장소는 바닥, 건물 날개 또는 사용자가 위치한 사무실 번호 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99904-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="99904-107">지정 된 비상 위치에 대해 무제한의 장소를 가질 수 있으며 사용자가 다른 사무실 이나 건물으로 이동 하는 경우에는 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99904-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="99904-108">예를 들어 사용자가 밑면 34에서 floor 35로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="99904-109">통화 계획을 가져오는 방법과 비용을 파악 하려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99904-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="99904-110">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 사용자에 대 한 긴급 위치를 지정 하거나 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99904-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="99904-111">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="99904-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="99904-112">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **전화 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="99904-113">**전화 번호** 페이지에서 **숫자** 탭을 클릭 하 고 목록에서 사용자 번호를 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="99904-114">**편집** 창의 **응급 위치**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="99904-115">장소를 할당 하려면 위치를 검색 한 다음 검색 결과에서 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="99904-116">사용자에 게 이미 할당 된 위치를 변경 하려면 **X** 를 클릭 하 여 기존 위치를 제거 하 고을 검색 한 후 할당할 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="99904-117">전화 번호 정보를 사용 하 여 사용자에 게 전자 메일을 보낼지 여부에 따라 **전화 번호 정보로 전자 메일 사용자**를 끄거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="99904-118">기본적으로이 기능은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99904-118">By default, this is on.</span></span>

5. <span data-ttu-id="99904-119">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99904-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="99904-120">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="99904-120">Using PowerShell</span></span>

<span data-ttu-id="99904-121">[Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99904-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="99904-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="99904-122">Related topics</span></span>

- [<span data-ttu-id="99904-123">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="99904-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="99904-124">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="99904-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="99904-125">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="99904-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="99904-126">사용자의 응급 위치 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="99904-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="99904-127">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="99904-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="99904-128">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="99904-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
