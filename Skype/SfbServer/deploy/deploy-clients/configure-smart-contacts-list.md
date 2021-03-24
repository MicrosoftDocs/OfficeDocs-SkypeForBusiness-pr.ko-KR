---
title: 비즈니스용 Skype 클라이언트에서 스마트 연락처 목록 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '요약: 비즈니스용 Skype 클라이언트에서 스마트 연락처 목록 기능을 켜는 방법을 학습합니다.'
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095802"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="580d9-103">비즈니스용 Skype 클라이언트에서 스마트 연락처 목록 구성</span><span class="sxs-lookup"><span data-stu-id="580d9-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="580d9-104">**요약:** 비즈니스용 Skype 클라이언트에서 스마트 연락처 목록 기능을 켜는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="580d9-105">스마트 연락처 목록 기능을 사용하면 최종 사용자의 연락처 목록을 자동으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="580d9-106">비즈니스용 Skype를 처음 사용하는 경우 사용자는 자신의 관리자와 팀의 다른 사용자를 자동으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="580d9-107">이 기능은 Microsoft 365 및 Office 365 사용자에 대해 기본적으로 설정되지만 클라이언트 정책 설정을 구성하여 이 기능을 명시적으로 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="580d9-108">이 기능을 구성할 때 다음에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="580d9-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="580d9-109">최대 13명인 사용자는 다음 순서로 스마트 연락처 목록에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="580d9-110">관리자</span><span class="sxs-lookup"><span data-stu-id="580d9-110">Manager</span></span>

  2. <span data-ttu-id="580d9-111">지시문(사전순)</span><span class="sxs-lookup"><span data-stu-id="580d9-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="580d9-112">피어(사전순)</span><span class="sxs-lookup"><span data-stu-id="580d9-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="580d9-113">사용자가 처음 로그인하면 My Group이라는 새 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="580d9-114">그룹은 관리자 필드에 채워진 사용자 별칭에 따라 사용자의 AD 그룹 관계에 있는 사용자로 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="580d9-115">AD 그룹 구성원 자격을 변경하면 처음 채워진 후 내 그룹이 업데이트되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="580d9-116">사용자가 연락처나 그룹을 삭제하면 연락처와 그룹이 모두 다시 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="580d9-117">자동 태그 지정이 설정되어 있는 경우 목록의 연락처에 현재 상태 변경에 대한 태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="580d9-118">자동 태그 지정은 기본적으로 설정되어 있지만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="580d9-119">그룹의 모든 새 사용자는 연락처 목록에 추가된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="580d9-120">사용자는 자신의 내 그룹 또는 선택한 다른 그룹에 새 구성원을 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="580d9-121">이 기능은 처음 로그인하는 사용자에게만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="580d9-122">사용자가 이전에 모바일 장치 또는 Mac을 비롯한 모든 장치에서 로그인한 경우 해당 사용자에 대해 이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="580d9-123">스마트 연락처 목록 구성</span><span class="sxs-lookup"><span data-stu-id="580d9-123">Configure Smart contacts list</span></span>

<span data-ttu-id="580d9-124">사용자에 대해 스마트 연락처 목록 기능을 사용하도록 설정하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="580d9-125">새 CsClientPolicy 항목을 만들어 전역 클라이언트 정책에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="580d9-126">주소부 검색이 웹 검색 전용으로 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="580d9-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="580d9-127">스마트 연락처 목록을 사용하도록 설정하는 정책 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="580d9-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="580d9-128">스마트 연락처 목록 기능을 사용하도록 설정하는 정책 항목을 만들하려면 다음과 같이 EnableClientAutoPopulateWithTeam 옵션과 함께 [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="580d9-129">다음으로 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet을 사용하여 글로벌 정책에 다음과 같이 변경 내용을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-129">Next, use the [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="580d9-130">선택적으로 다음과 같이 자동 태그 지정을 해제하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="580d9-131">또한 해당 정책에 대한 AddressBookAvailability 매개 변수를 WebSearchOnly로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="580d9-132">자세한 내용은 [Set-CsClientPolicy를 참조하세요.](/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="580d9-132">For more information, see [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="580d9-133">문제 해결</span><span class="sxs-lookup"><span data-stu-id="580d9-133">Troubleshoot</span></span>

<span data-ttu-id="580d9-134">스마트 연락처 목록이 예상대로 작동하지 않는 경우 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="580d9-135">구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-135">Validate the configuration.</span></span> 

- <span data-ttu-id="580d9-136">AD 조직 정보가 채워지는지 확인</span><span class="sxs-lookup"><span data-stu-id="580d9-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="580d9-137">추가 분석을 위해 새 사용자에 대한 비즈니스용 Skype 클라이언트 로그를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="580d9-138">비즈니스용 Skype 클라이언트 UI에 주소장에 연결할 수 없다는 메시지가 표시되지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="580d9-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="580d9-139">주소부 연결을 확인하기 위해 비즈니스용 Skype 클라이언트 검색 표시줄에서 사용자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="580d9-140">AD DS 복제 문제는 사용자가 비즈니스용 Skype에 처음 로그인할 때 연락처를 해결하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580d9-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>