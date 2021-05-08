---
title: 사용자 계정 관리
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 조직에서 Get-CsOnlineUser cmdlet을 Windows PowerShell 조직의 온라인 사용자에 대한 정보를 비즈니스용 Skype.
ms.openlocfilehash: aec79f589f6b1fb0c9d38fd4bc70421b30f66a56
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238724"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="f66cf-103">사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="f66cf-103">Manage user accounts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a><span data-ttu-id="f66cf-104">사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="f66cf-104">Manage user accounts</span></span>

<span data-ttu-id="f66cf-105">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="f66cf-106">전체 Lync Online 사용자에 대한 정보 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="f66cf-107">온라인에서 특정 사용자에 대한 비즈니스용 Skype 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="f66cf-108">온라인에서 특정 사용자에 대한 특정 비즈니스용 Skype 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="f66cf-109">온라인에서 필터링된 사용자 비즈니스용 Skype 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="f66cf-110">**Set-CsUser** cmdlet도 온라인 관리자에게 사용할 수 있는 cmdlet 비즈니스용 Skype 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="f66cf-111">그러나 **Set-CsUser는** _AudioVideoDisabled_ 매개 변수를 설정하는 비즈니스용 Skype 온라인을 관리하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="f66cf-112">다른 매개 변수로 cmdlet을 실행하려고 하면 "SipAddress"를 설정할 수 없습니다. 이와 유사한 오류 메시지로 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="f66cf-113">이 매개 변수는 원격 테넌트 PowerShell 내에서 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="f66cf-114">전체 Lync Online 사용자에 대한 정보 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="f66cf-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f66cf-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="f66cf-116">온라인에서 사용하도록 설정된 모든 비즈니스용 Skype 정보를 반환하기 위해 추가 매개 변수 없이 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="f66cf-117">임의로 선택한 단일 사용자에 대한 정보를 반환하려면(예: 이 계정을 테스트 목적으로 사용하려면 **Get-CsOnlineUser** cmdlet)를 호출하고 _ResultSize_ 매개 변수를 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="f66cf-118">그러면 조직의 사용자 수에 관계없이 **Get-CsOnlineUser** cmdlet이 한 사용자에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="f66cf-119">5명 사용자에 대한 정보를 반환하기 위해 _ResultSize_ 매개 변수의 값을 5로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="f66cf-120">온라인에서 특정 사용자에 대한 비즈니스용 Skype 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="f66cf-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="f66cf-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="f66cf-122">[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet을 호출할 때 특정 사용자 계정을 참조하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="f66cf-123">사용자의 AD DS(Active Directory Domain Services) 표시 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="f66cf-124">사용자의 SIP 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="f66cf-125">사용자의 사용자 주체 이름(UPN)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="f66cf-126">온라인에서 특정 사용자에 대한 특정 비즈니스용 Skype 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="f66cf-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f66cf-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="f66cf-128">기본적으로 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet은 각 온라인 사용자 계정에 대한 엄청난 비즈니스용 Skype 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="f66cf-129">해당 정보의 하위 집합에만 관심이 있는 경우 반환된 데이터를 **Select-Object** cmdlet에 파이프합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="f66cf-130">예를 들어 이 명령은 사용자 Ken Myer에 대한 모든 데이터를 반환한 다음 **Select-Object** cmdlet을 사용하여 화면에 표시되는 정보를 Ken의 AD DS 표시 이름 및 다이얼 플랜으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="f66cf-131">다음 명령은 모든 사용자의 표시 이름 및 다이얼 플랜을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="f66cf-132">온라인 사용자 계정의 속성을 비즈니스용 Skype 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f66cf-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="f66cf-133">온라인에서 필터링된 사용자 비즈니스용 Skype 반환</span><span class="sxs-lookup"><span data-stu-id="f66cf-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="f66cf-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f66cf-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="f66cf-135">[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 및 _LdapFilter_ 또는 _Filter_ 매개 변수를 사용하여 대상 사용자 집합에 대한 정보를 쉽게 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="f66cf-136">예를 들어 이 명령은 재무 부서에서 작업하는 모든 사용자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f66cf-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="f66cf-137">관련 주제</span><span class="sxs-lookup"><span data-stu-id="f66cf-137">Related topics</span></span>
[<span data-ttu-id="f66cf-138">비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f66cf-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
