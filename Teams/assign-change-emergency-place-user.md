---
title: 사용자에 대한 긴급 위치 지정, 위치 변경
author: cichur
ms.author: v-cichur
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
description: 이 문서에서는 조직의 사용자에 대한 긴급 위치의 위치를 할당하거나 변경하는 방법을 배웠습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809528"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="85585-103">사용자의 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="85585-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="85585-104">사용자에게 전화 번호를 할당할 때 각 활성 전화 번호에 연결된 긴급 위치가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85585-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="85585-105">(Office 365에서 전화 번호를 옮기거나 전화 번호를 전송할 때 주소를 연결합니다.) 긴급 위치와 번호를 연결하면 물리적 위치 내에서 더 정확한 위치를 제공하는 위치를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85585-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="85585-106">장소는 사용자가 있는 층, 건물 날개 또는 사무실 번호일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85585-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="85585-107">특정 긴급 위치에 대해 장소를 제한 없이 사용할 수 있으며 사용자가 다른 사무실이나 건물로 이동하는 경우 장소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85585-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="85585-108">예를 들어 사용자가 34층에서 35층으로 이동하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="85585-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="85585-109">통화 요금제 및 비용에 대한 자세한 내용은 Teams 추가 기능 [라이선스를 참조합니다.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="85585-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="85585-110">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 사용자의 긴급 위치를 할당하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85585-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85585-111">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="85585-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="85585-112">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성**  >  **전화 번호를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85585-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="85585-113">전화 번호 **페이지에서** 번호  탭을 클릭하고 목록에서 사용자 번호를 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85585-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="85585-114">편집 **창의** 긴급 위치 **아래에서** 다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="85585-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="85585-115">장소를 할당하려면 위치 또는 위치를 검색한 다음 검색 결과에서 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85585-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="85585-116">사용자에게 이미 할당된 위치를 변경하려면 **X를** 클릭하여 기존 위치와 위치를 제거하고 검색한 다음 할당할 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85585-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="85585-117">전화 번호 정보를 통해 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 전자 메일 사용자를 끄거나 **끄거나 끄면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="85585-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="85585-118">기본적으로 이 설정은 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85585-118">By default, this is on.</span></span>

5. <span data-ttu-id="85585-119">적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85585-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="85585-120">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="85585-120">Using PowerShell</span></span>

<span data-ttu-id="85585-121">[Set-CsOnlineLisLocation을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="85585-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="85585-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="85585-122">Related topics</span></span>

- [<span data-ttu-id="85585-123">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="85585-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="85585-124">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="85585-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="85585-125">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="85585-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="85585-126">사용자의 응급 위치 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="85585-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="85585-127">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="85585-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="85585-128">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="85585-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
