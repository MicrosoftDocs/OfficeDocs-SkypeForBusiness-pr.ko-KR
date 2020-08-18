---
title: 사용자의 응급 위치 할당 또는 변경
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
description: 이 문서에서는 조직의 사용자에 대 한 긴급 위치를 할당 하거나 변경 하는 방법에 대해 설명 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f2e927e90a7ac6b79d6eb63c807e063ca7d78c7
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788662"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="18cc6-103">사용자의 응급 위치 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="18cc6-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="18cc6-104">통화 계획을 설정 하는 경우 각 전화 번호 또는 사용자에 게 긴급 위치를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="18cc6-105">유럽 국가에서 긴급 위치는 Microsoft 365 또는 Office 365에서 전화를 거는 경우 나 전화 번호를 Microsoft 365 또는 Office 365로 전송 하는 경우와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="18cc6-106">미국에서 비상 위치는 사용자에 게 할당 될 때 전화 번호와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="18cc6-107">사용자가 할당 한 새 위치로 이동 하는 경우 긴급 주소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="18cc6-108">긴급 주소 및 위치에 대 한 자세한 내용은 [응급 위치, 장소 및 통화 라우팅 이란?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18cc6-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="18cc6-109">통화 요금제와 비용을 가져오는 방법을 알아보려면 [팀 추가 기능 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18cc6-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
  
<span data-ttu-id="18cc6-110">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 사용자에 대 한 긴급 위치를 할당 하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18cc6-111">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="18cc6-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18cc6-112">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **전화 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="18cc6-113">**전화 번호** 페이지에서 **숫자** 탭을 클릭 하 고 목록에서 사용자 번호를 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="18cc6-114">**편집** 창의 **응급 위치**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="18cc6-115">긴급 위치를 지정 하려면을 검색 하 고 긴급 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="18cc6-116">사용자에 게 이미 할당 된 비상 위치를 변경 하려면 **X** 를 클릭 하 여 기존 위치를 제거한 다음 할당 하려는 위치를 검색 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="18cc6-117">전화 번호 정보를 사용 하 여 사용자에 게 전자 메일을 보낼지 여부에 따라 **전화 번호 정보로 전자 메일 사용자**를 끄거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="18cc6-118">기본적으로이 기능은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-118">By default, this is on.</span></span>

5. <span data-ttu-id="18cc6-119">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18cc6-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="18cc6-120">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="18cc6-120">Using PowerShell</span></span>

<span data-ttu-id="18cc6-121">[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18cc6-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="18cc6-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="18cc6-122">Related topics</span></span>

- [<span data-ttu-id="18cc6-123">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="18cc6-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="18cc6-124">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="18cc6-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="18cc6-125">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="18cc6-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="18cc6-126">사용자에게 응급 위치의 장소 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="18cc6-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="18cc6-127">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="18cc6-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="18cc6-128">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="18cc6-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="18cc6-129">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="18cc6-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
