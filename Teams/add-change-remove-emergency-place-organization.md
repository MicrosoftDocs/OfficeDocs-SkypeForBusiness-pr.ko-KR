---
title: 응급 위치에 대 한 위치 추가, 변경, 제거
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
description: Microsoft 팀 관리 센터에서 조직의 긴급 위치를 추가, 변경 또는 제거 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232499"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="ac602-103">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="ac602-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="ac602-104">조직의 실제 위치 수에 따라 건물, 바닥, 사무실 위치를 추가 하 여 보다 구체적인 비상 위치를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="ac602-105">자세한 내용은 [비상 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac602-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="ac602-106">통화 요금제와 비용을 가져오는 방법을 알아보려면 [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac602-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="ac602-107">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 조직의 긴급 위치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="ac602-108">비상 위치에 위치 추가</span><span class="sxs-lookup"><span data-stu-id="ac602-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ac602-109">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ac602-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ac602-110">Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ac602-111">목록에서 위치를 추가 하려는 위치의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="ac602-112">**위치** 탭에서 **위치 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="ac602-113">위치 이름을 입력 한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ac602-114">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ac602-114">Using PowerShell</span></span>

<span data-ttu-id="ac602-115">[새로운 CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac602-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="ac602-116">비상 연락망 위치 변경</span><span class="sxs-lookup"><span data-stu-id="ac602-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ac602-117">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ac602-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ac602-118">Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ac602-119">목록에서 위치를 변경 하려는 위치의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="ac602-120">**위치** 탭에서 변경 하려는 위치를 선택 하 고 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="ac602-121">위치 정보를 업데이트 한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ac602-122">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ac602-122">Using PowerShell</span></span>

<span data-ttu-id="ac602-123">[Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac602-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="ac602-124">비상 위치에서 위치 제거</span><span class="sxs-lookup"><span data-stu-id="ac602-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ac602-125">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ac602-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ac602-126">Microsoft 팀 관리 센터의 왼쪽 탐색에서 **위치**  >  **긴급 주소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ac602-127">목록에서 위치를 제거 하려는 위치의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="ac602-128">**위치** 탭에서 제거 하려는 위치를 선택 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac602-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ac602-129">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ac602-129">Using PowerShell</span></span>

<span data-ttu-id="ac602-130">[제거-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac602-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ac602-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ac602-131">Related topics</span></span>

- [<span data-ttu-id="ac602-132">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="ac602-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ac602-133">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="ac602-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ac602-134">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="ac602-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
