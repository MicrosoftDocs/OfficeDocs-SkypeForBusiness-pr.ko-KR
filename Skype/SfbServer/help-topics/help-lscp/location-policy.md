---
title: 위치 정책
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 위치 정책은 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정합니다.
ms.openlocfilehash: e780256ba025328c6a84d709aaa4c6f522b219df
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700103"
---
# <a name="location-policy"></a><span data-ttu-id="bb871-103">위치 정책</span><span class="sxs-lookup"><span data-stu-id="bb871-103">Location Policy</span></span>

<span data-ttu-id="bb871-104">위치 정책은 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="bb871-105">위치 정책에는 전역 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="bb871-106">**글로벌 정책:** 전역 정책은 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="bb871-107">전역 정책을 편집할 수는 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="bb871-108">전역 정책을 제거하려고 하면 모든 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="bb871-109">**사이트 정책 (선택 사항):** 특정 사이트에 적용 되는 하나 이상의 사이트 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="bb871-110">사이트 정책은 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="bb871-111">**사용자 정책 (선택 사항):** 특정 사용자 또는 사용자 그룹에 적용 되는 하나 이상의 사용자 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="bb871-112">사용자 정책은 전역 정책 및 사이트 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="bb871-113">서브넷 그룹인 네트워크 사이트에 위치 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="bb871-114">네트워크 사이트에 할당된 위치 정책은 다른 모든 사용자 정책보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="bb871-115">Cmdlet을 사용 하 여 네트워크 사이트에 위치 정책을 할당 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015의 네트워크 사이트에 위치 정책 추가](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb871-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="bb871-116">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트에 위치 정책을 할당 하는 방법에 대 한 자세한 내용은 [네트워크 사이트 구성을](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb871-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="bb871-117">**위치 정책** 페이지에는 조직에 대해 정의된 모든 위치 정책의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bb871-118">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="bb871-118">Tasks you can perform</span></span>

<span data-ttu-id="bb871-119">**위치 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="bb871-120">새 사이트 위치 정책 또는 사용자 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="bb871-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="bb871-121">전역 정책 또는 기존 사이트 정책/사용자 정책 변경</span><span class="sxs-lookup"><span data-stu-id="bb871-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="bb871-122">사이트 정책 또는 사용자 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="bb871-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bb871-123">UI 참조</span><span class="sxs-lookup"><span data-stu-id="bb871-123">UI Reference</span></span>

<span data-ttu-id="bb871-124">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="bb871-125">**새로운** 새 사이트 위치 정책 또는 사용자 위치 정책을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="bb871-126">**편집** 선택한 위치 정책을 열어 편집 하거나 목록에서 모든 위치 정책을 선택 하거나 선택한 사이트 정책 또는 사용자 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb871-127">전역 정책의 경우 **삭제**를 클릭하면 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="bb871-128">**새로 고침** 위치 정책 목록을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="bb871-129">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="bb871-130">**이름** 위치 정책을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="bb871-131">**범위** 위치 정책의 범위 (전역, 사이트 또는 사용자)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="bb871-132">**E9-1-1** 이 위치 정책을 할당 한 사용자가 E9-1-1에 대해 사용 하도록 설정 되어 있는지 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="bb871-133">**위치** 클라이언트가 비즈니스용 Skype 서버를 사용 하 여 새 위치에 등록할 때 사용자에 게 위치 정보를 입력 하 라는 메시지를 표시할지 여부 및 위치 정보를 입력 하지 않고 메시지가 표시 되지 않도록 할 것인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="bb871-134">**PSTN 사용** 이 프로필을 사용 하는 클라이언트에서 비상 전화를 라우팅하는 데 사용 되는 음성 경로를 결정 하는 데 사용 되는 PSTN (공개 전환 통신망) 사용량을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="bb871-135">**E9-1-1 번호** 응급 서비스에 연결 하기 위해 전화를 거는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="bb871-136">**E9-1-1 마스크** 사용자가 전화를 걸어 긴급 전화 번호로 번역 되는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb871-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="bb871-137">Enterprise Voice 응급 서비스 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [E9-1-1 개요](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb871-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="bb871-138">위치 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb871-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


