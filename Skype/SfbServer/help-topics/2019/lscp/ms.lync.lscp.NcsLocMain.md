---
title: 위치 정책
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 위치 정책은 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정합니다.
ms.openlocfilehash: 9f6d7468520b3398f186adeacffd5b393ce159b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109574"
---
# <a name="location-policy"></a><span data-ttu-id="c7360-103">위치 정책</span><span class="sxs-lookup"><span data-stu-id="c7360-103">Location Policy</span></span>

<span data-ttu-id="c7360-104">위치 정책은 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="c7360-105">위치 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="c7360-106">**글로벌 정책:** 전역 정책은 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="c7360-107">글로벌 정책을 편집할 수는 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="c7360-108">글로벌 정책을 제거하려고 하면 모든 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="c7360-109">**사이트 정책(선택 사항):** 하나 이상의 사이트 위치 정책을 만들 수 있습니다. 각 정책은 특정 사이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="c7360-110">사이트 정책은 글로벌 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="c7360-111">**사용자 정책(선택 사항):** 하나 이상의 사용자 위치 정책을 만들 수 있습니다. 각 정책은 특정 사용자 또는 사용자 그룹에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="c7360-112">사용자 정책은 글로벌 정책 및 사이트 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="c7360-113">서브넷 그룹인 네트워크 사이트에 위치 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="c7360-114">네트워크 사이트에 할당된 위치 정책은 다른 모든 사용자 정책보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="c7360-115">cmdlet을 사용하여 네트워크 사이트에 위치 정책을 할당하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 [추가를 참조하세요.](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)</span><span class="sxs-lookup"><span data-stu-id="c7360-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="c7360-116">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 사이트에 위치 정책을 할당하는 데 대한 자세한 내용은 [Configuring Network Sites을 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites)</span><span class="sxs-lookup"><span data-stu-id="c7360-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).</span></span>

<span data-ttu-id="c7360-117">**위치 정책** 페이지에는 조직에 대해 정의된 모든 위치 정책의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c7360-118">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="c7360-118">Tasks you can perform</span></span>

<span data-ttu-id="c7360-119">**위치 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="c7360-120">새 사이트 위치 정책 또는 사용자 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c7360-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="c7360-121">글로벌 정책 또는 기존 사이트 정책/사용자 정책 변경</span><span class="sxs-lookup"><span data-stu-id="c7360-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="c7360-122">사이트 정책 또는 사용자 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="c7360-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c7360-123">UI 참조</span><span class="sxs-lookup"><span data-stu-id="c7360-123">UI Reference</span></span>

<span data-ttu-id="c7360-124">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c7360-125">**새로 추가** 새 사이트 위치 정책 또는 사용자 위치 정책을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="c7360-126">**편집** 선택한 위치 정책을 열어 편집하거나, 목록의 모든 위치 정책을 선택하거나, 선택한 사이트 정책 또는 사용자 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7360-127">글로벌 정책의 경우 **삭제** 를 클릭하면 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="c7360-128">**새로 고침** 위치 정책 목록을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="c7360-129">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c7360-130">**이름** 위치 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="c7360-131">**범위** 위치 정책의 범위(전역, 사이트 또는 사용자)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="c7360-132">**E9-1-1** 이 위치 정책이 할당된 사용자가 E9-1-1을 사용할 수 있도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="c7360-133">**위치** 클라이언트가 새 위치에서 비즈니스용 Skype 서버에 등록할 때 위치 정보를 입력하라는 메시지가 사용자에게 표시될지 여부와 위치 정보를 입력하지 않고 메시지를 해지할 경우 고지 메시지가 표시될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="c7360-134">**PSTN 사용** 이 프로필을 사용하여 클라이언트의 긴급 통화를 라우팅하는 데 사용되는 음성 경로를 결정하는 데 사용되는 PSTN(Public Switched Telephone Network) 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="c7360-135">**E9-1-1 번호** 응급 서비스에 연결하기 위해 전화를 걸 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="c7360-136">**E9-1-1 마스크** 사용자가 전화를 걸 때 긴급 전화 번호로 변환되는 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7360-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="c7360-137">응급 서비스 Enterprise Voice 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of E9-1-1를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7360-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) in the Planning documentation.</span></span> <span data-ttu-id="c7360-138">위치 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7360-138">For details about working with location policies, see [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in the Operations documentation.</span></span>