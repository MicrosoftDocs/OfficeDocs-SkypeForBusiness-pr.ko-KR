---
title: 회의 정책
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: 회의 정책은 사용자가 회의(모임이라고도 함) 중에 사용할 수 있는 기능을 정의합니다.
ms.openlocfilehash: 23377ce4974be1139cf5ff3e7d090cb83d8f2504
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824868"
---
# <a name="conferencing-policy"></a><span data-ttu-id="d7d75-103">회의 정책</span><span class="sxs-lookup"><span data-stu-id="d7d75-103">Conferencing Policy</span></span>

<span data-ttu-id="d7d75-104">회의 정책은 사용자가 회의(모임이라고도 함) 중에 사용할 수 있는 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="d7d75-105">회의 정책에는 전역 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="d7d75-106">**글로벌 정책:** 전역 정책은 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="d7d75-107">글로벌 정책을 편집할 수는 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="d7d75-108">글로벌 정책을 제거하려고 하면 모든 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="d7d75-109">**사이트 정책(선택 사항):** 하나 이상의 사이트 회의 정책을 만들 수 있습니다. 각 정책은 특정 사이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="d7d75-110">사이트 정책은 글로벌 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="d7d75-111">**사용자 정책(선택 사항):** 하나 이상의 사용자 회의 정책을 만들 수 있습니다. 각 정책은 특정 사용자 또는 사용자 그룹에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="d7d75-112">사용자 정책은 글로벌 정책 및 사이트 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="d7d75-113">회의 **정책 페이지에는** 조직에 대해 정의된 모든 회의 정책 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d7d75-114">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="d7d75-114">Tasks you can perform</span></span>

<span data-ttu-id="d7d75-115">**위치 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="d7d75-116">새 사이트 회의 정책 또는 사용자 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d7d75-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="d7d75-117">글로벌 정책 또는 기존 사이트 정책/사용자 정책 변경</span><span class="sxs-lookup"><span data-stu-id="d7d75-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="d7d75-118">사이트 정책 또는 사용자 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="d7d75-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d7d75-119">UI 참조</span><span class="sxs-lookup"><span data-stu-id="d7d75-119">UI Reference</span></span>

<span data-ttu-id="d7d75-120">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="d7d75-121">**신규** 새 사이트 회의 정책 또는 사용자 회의 정책을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="d7d75-122">**편집** 선택한 회의 정책을 열어 편집하거나, 목록의 모든 회의 정책을 선택하거나, 선택한 사이트 정책 또는 사용자 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7d75-123">글로벌 정책의 경우 **삭제** 를 클릭하면 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="d7d75-124">**새로 고침** 회의 정책 목록을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="d7d75-125">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d7d75-126">**이름** 회의 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="d7d75-127">**범위** 회의 정책의 범위(전역, 사이트 또는 사용자)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="d7d75-128">**데이터 공동 작업** 회의 정책이 회의에서 데이터 공동 작업을 허용하도록 지정하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="d7d75-129">**응용 프로그램 공유** 회의 정책이 회의에서 응용 프로그램 공유를 허용하도록 지정하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="d7d75-130">**오디오** 회의 정책이 회의에서 오디오를 허용하도록 지정하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="d7d75-131">**비디오** 회의 정책이 회의에서 비디오를 허용하도록 지정하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="d7d75-132">**PSTN** 회의 정책이 PSTN 전화 접속 회의를 허용하도록 지정하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="d7d75-133">**기록** 회의 정책이 회의에서 녹음/녹화를 허용하도록 지정하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d75-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="d7d75-134">회의 기능에 대한 자세한 내용은 계획 설명서에서 회의 [개요를](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7d75-134">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="d7d75-135">회의 정책 작업에 대한 자세한 내용은 작업 설명서에서 [회의](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) 정책을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7d75-135">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


