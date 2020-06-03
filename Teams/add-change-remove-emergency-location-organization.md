---
title: 긴급 위치 추가, 변경, 제거
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
description: 'Microsoft 팀 관리 센터에서 조직의 긴급 위치를 추가, 변경 또는 제거 하는 방법에 대해 알아봅니다. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bed76fdfff2a6af2dabb3eef5c01dcfb39f422a
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539465"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="66308-103">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="66308-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="66308-104">비상 위치는 전화 번호와 연결 되어야 하지만,이 문제가 발생 하는 경우 국가와 지역에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66308-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="66308-105">예를 들어 미국에서 사용자에 게 전화 번호를 할당할 때 비상 위치를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="66308-106">영국에서는 Office 365에서 전화 번호를 받고 현재 서비스 공급자 로부터 전화 번호를 전송 하면 비상 위치를 전화 번호에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="66308-107">거주 국가 또는 지역에 관계 없이 긴급 위치에 위치 또는 위치를 추가 하 고 긴급 위치를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66308-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="66308-108">조직의 실제 위치 수에 따라 빌딩, 바닥, 사무실 등의 위치를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66308-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="66308-109">[비상 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66308-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="66308-110">통화 요금제와 비용을 가져오는 방법을 알아보려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66308-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="66308-111">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 조직의 긴급 위치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66308-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="66308-112">긴급 위치 추가</span><span class="sxs-lookup"><span data-stu-id="66308-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="66308-113">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="66308-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="66308-114">Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="66308-115">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-115">Click **Add**.</span></span>
3. <span data-ttu-id="66308-116">위치에 대 한 이름과 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="66308-117">국가 또는 지역을 선택한 다음 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66308-118">벨기에, 프랑스, 독일, 아일랜드, 네덜란드, 스페인에서는 Office 365에서 전화 번호를 성공적으로 활성화 하는 것을 이해 하는 것이 중요 합니다. 번호를 구하는 데 사용 되는 비상 위치에 설정 된 주소는 전화 번호의 지역 번호와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>
5. <span data-ttu-id="66308-119">주소를 찾을 수 없는 경우 수동으로 주소를 편집 하려면 **수동으로 주소 편집**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="66308-120">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="66308-121">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="66308-121">Using PowerShell</span></span>

<span data-ttu-id="66308-122">[새로운 CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66308-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="66308-123">긴급 위치 변경</span><span class="sxs-lookup"><span data-stu-id="66308-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="66308-124">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="66308-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="66308-125">Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="66308-126">목록에서 변경 하려는 위치를 선택 하 고 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="66308-127">원하는 변경 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-127">Make the changes you want.</span></span>
4. <span data-ttu-id="66308-128">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="66308-129">주소의 유효성을 검사 하지 않은 경우에만 위치에 대 한 주소 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66308-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="66308-130">주소가 이미 확인 되었고 주소를 변경 해야 하는 경우 위치를 삭제 하 고 올바른 주소로 새 위치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66308-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="66308-131">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="66308-131">Using PowerShell</span></span>

<span data-ttu-id="66308-132">[Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66308-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="66308-133">긴급 위치 제거</span><span class="sxs-lookup"><span data-stu-id="66308-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="66308-134">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="66308-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="66308-135">Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="66308-136">목록에서 제거 하려는 위치를 선택 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66308-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="66308-137">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="66308-137">Using PowerShell</span></span>

<span data-ttu-id="66308-138">[제거-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66308-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="66308-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="66308-139">Related topics</span></span>

- [<span data-ttu-id="66308-140">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="66308-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="66308-141">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="66308-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="66308-142">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="66308-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="66308-143">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="66308-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
