---
title: 사용자의 응급 위치 할당 또는 변경
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
description: 이 문서에서는 조직의 사용자에 대한 긴급 위치를 할당하거나 변경하는 방법에 대해 알아보고 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102984"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="71ac4-103">사용자의 응급 위치 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="71ac4-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="71ac4-104">통화 계획을 설정할 때 각 전화 번호 또는 사용자에게 긴급 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="71ac4-105">유럽 국가에서는 Microsoft 365 또는 Office 365에서 전화 번호를 얻거나 Microsoft 365 또는 Office 365로 전화 번호를 이전할 때 긴급 위치가 전화 번호와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="71ac4-106">미국의 경우 긴급 위치가 사용자에게 할당될 때 전화 번호와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="71ac4-107">할당된 사용자가 새 위치로 이동하는 경우 비상 주소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="71ac4-108">긴급 주소 및 위치에 대한 자세한 내용은 긴급 위치, 장소 및 통화 [라우팅이란? 을 참조하세요.](./what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="71ac4-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="71ac4-109">통화 계획 및 비용에 대한 자세한 내용은 [Teams 추가 기능 라이선스 를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="71ac4-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="71ac4-110">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자에 대한 긴급 위치를 할당하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="71ac4-111">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="71ac4-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="71ac4-112">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **음성**  >  **전화 번호 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71ac4-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="71ac4-113">전화 번호 **페이지에서** 숫자 탭을 **클릭하고** 목록에서 사용자 번호를 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71ac4-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="71ac4-114">편집 **창의** 긴급 **위치 아래에서** 다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="71ac4-115">긴급 위치를 할당하려면 긴급 위치를 검색하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="71ac4-116">사용자에게 이미 할당된 긴급 위치를 변경하려면 **X를** 클릭하여 기존 위치를 제거한 다음, 할당할 위치를 검색하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="71ac4-117">전화 번호 정보가 있는 사용자에게 전자 메일을 보낼지 여부에 따라 전화 번호 정보가 있는 전자 메일 사용자를 끄거나 **끄거나 끄기**</span><span class="sxs-lookup"><span data-stu-id="71ac4-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="71ac4-118">기본적으로 이 설정은 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ac4-118">By default, this is on.</span></span>

5. <span data-ttu-id="71ac4-119">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71ac4-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="71ac4-120">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="71ac4-120">Using PowerShell</span></span>

<span data-ttu-id="71ac4-121">[Set-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/set-csonlinevoiceuser)</span><span class="sxs-lookup"><span data-stu-id="71ac4-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="71ac4-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="71ac4-122">Related topics</span></span>

- [<span data-ttu-id="71ac4-123">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="71ac4-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="71ac4-124">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="71ac4-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="71ac4-125">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="71ac4-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="71ac4-126">사용자에게 응급 위치의 장소 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="71ac4-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="71ac4-127">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="71ac4-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="71ac4-128">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="71ac4-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="71ac4-129">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="71ac4-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)