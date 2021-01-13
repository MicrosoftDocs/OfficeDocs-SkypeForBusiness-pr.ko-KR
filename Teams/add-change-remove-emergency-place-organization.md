---
title: 긴급 위치에 대한 위치 추가, 변경, 제거
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
description: Microsoft Teams 관리 센터에서 조직의 긴급 위치에 대한 장소를 추가, 변경 또는 제거하는 방법을 배워야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806278"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="8723c-103">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="8723c-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="8723c-104">조직의 물리적 위치 수에 따라 건물, 층 및 사무실에 위치를 추가하여 보다 구체적인 긴급 위치를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8723c-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="8723c-105">자세한 [내용은 긴급 통화](what-are-emergency-locations-addresses-and-call-routing.md) 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8723c-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="8723c-106">통화 요금제와 비용에 대한 자세한 내용은 Teams 추가 기능 [라이선스를 참조합니다.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="8723c-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="8723c-107">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 조직의 긴급 위치를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8723c-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="8723c-108">긴급 위치에 위치 추가</span><span class="sxs-lookup"><span data-stu-id="8723c-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8723c-109">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8723c-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="8723c-110">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 위치 긴급  >  **주소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="8723c-111">목록에서 위치를 추가할 위치의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8723c-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="8723c-112">위치 **탭에서** 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="8723c-113">장소 이름을 입력한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8723c-114">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8723c-114">Using PowerShell</span></span>

<span data-ttu-id="8723c-115">[New-CsOnlineLisLocation을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="8723c-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="8723c-116">긴급 위치의 위치 변경</span><span class="sxs-lookup"><span data-stu-id="8723c-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8723c-117">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8723c-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="8723c-118">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 위치 긴급  >  **주소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="8723c-119">목록에서 위치를 변경할 위치의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8723c-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="8723c-120">위치 **탭에서** 변경할 장소를 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="8723c-121">장소 정보를 업데이트한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8723c-122">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8723c-122">Using PowerShell</span></span>

<span data-ttu-id="8723c-123">[Set-CsOnlineLisLocation을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="8723c-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="8723c-124">긴급 위치에서 장소 제거</span><span class="sxs-lookup"><span data-stu-id="8723c-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8723c-125">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8723c-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="8723c-126">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 위치 긴급  >  **주소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="8723c-127">목록에서 위치를 제거할 위치의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8723c-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="8723c-128">위치 **탭에서** 제거할 장소를 선택한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8723c-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8723c-129">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8723c-129">Using PowerShell</span></span>

<span data-ttu-id="8723c-130">[Remove-CsOnlineLisLocation을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="8723c-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="8723c-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8723c-131">Related topics</span></span>

- [<span data-ttu-id="8723c-132">조직의 응급 위치에 대한 장소 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="8723c-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="8723c-133">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="8723c-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="8723c-134">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="8723c-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
