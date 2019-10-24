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
f1keywords: None
ms.custom:
- PowerShell
description: Windows PowerShell의 CsOnlineUser cmdlet을 사용 하 여 조직의 비즈니스용 Skype Online 사용자에 대 한 정보를 얻을 수 있습니다.
ms.openlocfilehash: 973529682224231e997e3900664fb5163156dfc3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "37642268"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="d3b72-103">사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="d3b72-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="d3b72-104">사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="d3b72-104">Manage user accounts</span></span>

<span data-ttu-id="d3b72-105">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="d3b72-106">전체 Lync Online 사용자에 대한 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="d3b72-107">비즈니스용 Skype Online에서 특정 사용자에 대 한 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="d3b72-108">비즈니스용 Skype Online에서 특정 사용자에 대 한 특정 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="d3b72-109">비즈니스용 Skype Online에서 필터링 된 사용자 목록 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="d3b72-110">**집합-CsUser** Cmdlet은 비즈니스용 Skype Online 관리자가 사용할 수 있는 cmdlet 집합에도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="d3b72-111">그러나, **사용자** 는 현재 비즈니스용 Skype Online을 관리 하는 데 사용할 수 없습니다 (예를 들어, _오디오 videodisabled_ 매개 변수를 설정 하는 경우 제외).</span><span class="sxs-lookup"><span data-stu-id="d3b72-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="d3b72-112">다른 매개 변수를 사용 하 여 cmdlet을 실행 하려고 하면 다음과 같은 오류 메시지가 표시 되지 않습니다. "SipAddress"을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="d3b72-113">이 매개 변수는 원격 테 넌 트 PowerShell 내에서 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="d3b72-114">전체 Lync Online 사용자에 대한 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="d3b72-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b72-115"></span></span>

<span data-ttu-id="d3b72-116">비즈니스용 Skype Online을 사용 하도록 설정 된 모든 사용자에 대 한 정보를 반환 하려면 추가 매개 변수 없이 [CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="d3b72-117">무작위로 선택한 단일 사용자 (예: 테스트 목적으로이 계정을 사용 하는 경우)에 대 한 정보를 반환 하려면 **Get-CsOnlineUser** cmdlet을 호출 하 고 _resultsize_ 매개 변수를 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="d3b72-118">이렇게 하면 조직에서 사용 하는 사용자 수에 관계 없이 **CsOnlineUser** cmdlet이 한 명의 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="d3b72-119">5 명의 사용자에 대 한 정보를 반환 하려면 _Resultsize_ 매개 변수 값을 5로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="d3b72-120">비즈니스용 Skype Online에서 특정 사용자에 대 한 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="d3b72-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b72-121"></span></span>

<span data-ttu-id="d3b72-122">[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet을 호출할 때 특정 사용자 계정을 참조 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="d3b72-123">사용자의 AD DS (Active Directory 도메인 서비스) 표시 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="d3b72-124">사용자의 SIP 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="d3b72-125">사용자의 UPN (사용자 계정 이름)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="d3b72-126">비즈니스용 Skype Online에서 특정 사용자에 대 한 특정 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="d3b72-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b72-127"></span></span>

<span data-ttu-id="d3b72-128">기본적으로 [CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet은 각 비즈니스용 Skype Online 사용자 계정에 대 한 방대한 양의 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="d3b72-129">해당 정보의 하위 집합에만 관심이 있는 경우 반환 된 데이터를 **개체 선택** cmdlet에 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="d3b72-130">예를 들어이 명령은 사용자: 진구 Myer에 대 한 모든 데이터를 반환 하 고 **개체 선택** cmdlet을 사용 하 여 화면에 표시 되는 정보를: 진구의 AD DS 표시 이름 및 다이얼 플랜으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="d3b72-131">다음 명령은 모든 사용자의 표시 이름 및 다이얼 플랜을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="d3b72-132">비즈니스용 Skype Online 사용자 계정의 속성을 찾으려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="d3b72-133">비즈니스용 Skype Online에서 필터링 된 사용자 목록 반환</span><span class="sxs-lookup"><span data-stu-id="d3b72-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="d3b72-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="d3b72-134"></span></span>

<span data-ttu-id="d3b72-135">[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 및 _Ldapfilter_ 또는 _Filter_ 매개 변수를 사용 하 여 대상 사용자 집합에 대 한 정보를 쉽게 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="d3b72-136">예를 들어이 명령은 재무 부서에서 근무 하는 모든 사용자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b72-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="d3b72-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d3b72-137">Related topics</span></span>
[<span data-ttu-id="d3b72-138">Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="d3b72-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


