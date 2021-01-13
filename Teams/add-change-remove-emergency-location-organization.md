---
title: 긴급 위치 추가, 변경, 제거
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
description: 'Microsoft Teams 관리 센터에서 조직의 긴급 위치를 추가, 변경 또는 제거하는 방법을 배워야 합니다. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799948"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="ae6d0-103">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="ae6d0-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="ae6d0-104">긴급 위치는 전화 번호와 연결되어야 하지만 이 경우 국가와 지역마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="ae6d0-105">예를 들어 미국의 경우 사용자에게 전화 번호를 할당할 때 긴급 위치를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="ae6d0-106">영국에서는 Microsoft 365 또는 Office 365에서 전화 번호를 옮기거나 현재 서비스 공급자로부터 전화 번호를 이전할 때 긴급 위치를 전화 번호에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="ae6d0-107">현재 국가 또는 지역에 상관없이 긴급 위치에 장소 또는 장소를 추가하고 긴급 위치를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="ae6d0-108">조직의 물리적 위치 수에 따라 건물, 층 및 사무실을 위한 장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="ae6d0-109">긴급 [통화 관리를 참조합니다.](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="ae6d0-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="ae6d0-110">통화 요금제와 비용에 대한 자세한 내용은 Teams 추가 기능 [라이선스를 참조합니다.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="ae6d0-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="ae6d0-111">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 조직의 긴급 위치를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="ae6d0-112">긴급 위치 추가</span><span class="sxs-lookup"><span data-stu-id="ae6d0-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae6d0-113">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ae6d0-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ae6d0-114">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 위치 긴급  >  **주소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ae6d0-115">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-115">Click **Add**.</span></span>
3. <span data-ttu-id="ae6d0-116">위치에 대한 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="ae6d0-117">국가 또는 지역을 선택한 다음 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ae6d0-118">벨기에, 프랑스, 독일, 아일랜드, 네덜란드 및 스페인에서는 Microsoft 365 또는 Office 365에서 전화 번호를 성공적으로 활성화하려면 전화 번호를 획득하는 데 사용되는 긴급 위치에 설정된 주소가 전화 번호의 지역 번호와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="ae6d0-119">주소를 찾을 수 없는 경우 주소를 수동으로 편집하려면 수동으로 주소 **편집을 켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="ae6d0-120">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ae6d0-121">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ae6d0-121">Using PowerShell</span></span>

<span data-ttu-id="ae6d0-122">[New-CsOnlineLisCivicAddress를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="ae6d0-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="ae6d0-123">긴급 위치 변경</span><span class="sxs-lookup"><span data-stu-id="ae6d0-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae6d0-124">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ae6d0-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ae6d0-125">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 위치 긴급  >  **주소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ae6d0-126">목록에서 변경할 위치를 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="ae6d0-127">원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-127">Make the changes you want.</span></span>
4. <span data-ttu-id="ae6d0-128">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ae6d0-129">주소의 유효성이 검사되지 않은 경우 위치에 대한 주소 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="ae6d0-130">주소의 유효성이 이미 검사되고 주소를 변경해야 하는 경우 위치를 삭제한 다음 올바른 주소로 새 위치를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6d0-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ae6d0-131">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ae6d0-131">Using PowerShell</span></span>

<span data-ttu-id="ae6d0-132">[Set-CsOnlineLisCivicAddress를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="ae6d0-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="ae6d0-133">긴급 위치 제거</span><span class="sxs-lookup"><span data-stu-id="ae6d0-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae6d0-134">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ae6d0-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ae6d0-135">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 위치 긴급  >  **주소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ae6d0-136">목록에서 제거할 위치를 선택한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae6d0-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ae6d0-137">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ae6d0-137">Using PowerShell</span></span>

<span data-ttu-id="ae6d0-138">[Remove-CsOnlineLisCivicAddress를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="ae6d0-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae6d0-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ae6d0-139">Related topics</span></span>

- [<span data-ttu-id="ae6d0-140">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="ae6d0-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="ae6d0-141">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="ae6d0-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ae6d0-142">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="ae6d0-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ae6d0-143">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="ae6d0-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
