---
title: 모임 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: 모임 구성 설정은 사용자가 만들 수 있는 회의 유형(meetings라고도 불리며)을 정의하고 익명 사용자 및 전화 접속 회의 사용자가 이러한 전화 회의에 참가할 수 있는 방법(또는)을 제어합니다. 이러한 설정은 예약된 모임에만 적용됩니다. 클라이언트에서 모임 시작 옵션을 클릭하여 만든 Ad-Hoc 모임에는 적용되지 않습니다.
ms.openlocfilehash: 053378ef694a66413f11760be5f449cd21e6b764
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095972"
---
# <a name="meeting-configuration"></a><span data-ttu-id="d2abf-105">모임 구성</span><span class="sxs-lookup"><span data-stu-id="d2abf-105">Meeting Configuration</span></span>

<span data-ttu-id="d2abf-106">모임 구성 설정은 사용자가 만들 수 있는 회의 유형("모임"이라고도 불리며)을 정의하고 익명 사용자 및 전화 접속 회의 사용자가 이러한 전화 회의에 참가할 수 있는 방법(또는)을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-106">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences.</span></span> <span data-ttu-id="d2abf-107">이러한 설정은 예약된 모임에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="d2abf-108">클라이언트에서 모임 시작 옵션을 클릭하여 만든 Ad-Hoc 모임에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-108">They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="d2abf-109">모임 구성은 전역, 사이트 또는 풀 수준에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="d2abf-110">**전역 모임 구성:** 전역 모임 구성은 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="d2abf-111">전역 모임 구성을 편집할 수는 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="d2abf-112">전역 모임 구성을 제거하려고 시도하면 모든 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="d2abf-113">**사이트 모임 구성(선택 사항):** 하나 이상의 사이트 모임 구성을 만들 수 있습니다. 각 구성은 특정 사이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="d2abf-114">사이트 구성은 전역 구성에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="d2abf-115">**풀 모임 구성(선택 사항):** 하나 이상의 풀 모임 구성을 만들 수 있으며, 각 구성은 특정 풀에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="d2abf-116">풀 구성은 전역 구성 및 사이트 구성을 에지합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="d2abf-117">모임 **구성 페이지에는** 조직에 대해 정의된 모든 모임 구성의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d2abf-118">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="d2abf-118">Tasks you can perform</span></span>

<span data-ttu-id="d2abf-119">모임 구성 페이지에서는 다음 **작업을 수행할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="d2abf-120">새 사이트 모임 구성 또는 풀 모임 구성 만들기</span><span class="sxs-lookup"><span data-stu-id="d2abf-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="d2abf-121">전역 구성 또는 기존 사이트 구성 또는 풀 구성 변경</span><span class="sxs-lookup"><span data-stu-id="d2abf-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="d2abf-122">사이트 구성 또는 풀 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="d2abf-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d2abf-123">UI 참조</span><span class="sxs-lookup"><span data-stu-id="d2abf-123">UI Reference</span></span>

<span data-ttu-id="d2abf-124">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="d2abf-125">**새로 추가** 새 사이트 모임 구성 또는 풀 모임 구성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="d2abf-126">**편집** 선택한 모임 구성을 열어 편집하거나, 목록의 모든 모임 구성을 선택하거나, 선택한 사이트 구성 또는 풀 구성을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2abf-127">전역 모임 구성의 경우 **삭제를** 통해 설정이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="d2abf-128">**새로 고침** 모임 구성 목록을 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="d2abf-129">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d2abf-130">**이름** 모임 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="d2abf-131">**범위** 모임 구성의 범위(전역, 사이트 또는 풀)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2abf-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="d2abf-132">모임 구성 작업에 대한 자세한 내용은 작업 설명서에서 [Create a or modify a Collection of Meeting Configuration Settings을](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2abf-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span>