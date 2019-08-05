---
title: 지정되지 않은 전화 번호
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: 지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.
ms.openlocfilehash: 684519d29177b9daf4be57c650e811f00945adfb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191673"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="d752e-104">지정되지 않은 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d752e-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="d752e-105">Exchange UM은 비즈니스용 Skype 2019을 Exchange 2013 또는 Exchange 2016와 통합할 때 비즈니스용 Skype 서버 2019에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="d752e-106">Exchange 2019에서 지원 되는 변경 사항으로 인해 클라우드 보이스 메일과 클라우드 자동 전화 교환 기능 때문에 Exchange UM 통합이 더욱 강조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="d752e-p103">지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="d752e-p104">할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다. 할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다. 할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다. 테이블에 할당되지 않은 내선 번호를 포함하면 특정 번호에 대해 발생하는 동작을 조정할 수 있습니다. 예를 들어 고객 서비스 센터의 내선 번호를 변경하려면 테이블에 기존의 고객 서비스 센터 번호를 포함하고 새 번호를 제공하는 알림에 이 번호를 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d752e-115">지정되지 않은 번호 테이블을 구성하려면 하나 이상의 알림을 정의하거나 Exchange UM 자동 전화 교환을 설정한 상태여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="d752e-116">**지정되지 않은 번호** 페이지에는 조직에 대해 정의되어 있는 지정되지 않은 번호 범위 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d752e-117">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="d752e-117">Tasks you can perform</span></span>

<span data-ttu-id="d752e-118">**지정되지 않은 번호** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="d752e-119">새 지정되지 않은 번호 범위 만들기</span><span class="sxs-lookup"><span data-stu-id="d752e-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="d752e-120">기존 지정되지 않은 번호 범위 변경</span><span class="sxs-lookup"><span data-stu-id="d752e-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="d752e-121">지정되지 않은 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="d752e-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="d752e-122">지정되지 않은 번호와 일치하는 수신 전화에 먼저 적용할 동작을 결정하기 위해 지정되지 않은 번호 범위의 순서 변경</span><span class="sxs-lookup"><span data-stu-id="d752e-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d752e-123">UI 참조</span><span class="sxs-lookup"><span data-stu-id="d752e-123">UI Reference</span></span>

<span data-ttu-id="d752e-124">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="d752e-125">**새로운** 지정 하지 않은 번호 범위를 새로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="d752e-126">**편집** 선택한 지정 하지 않은 번호 범위를 편집용으로 열거나, 목록에서 지정 하지 않은 번호 범위를 모두 선택 하거나, 선택한 지정 되지 않은 숫자 범위를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="d752e-127">**위로 이동** 비즈니스용 Skype 서버가 더 빨리 검색 하 고 목록의 다른 범위에 대해 지정 된 작업을 적용 하기 전에 지정 된 작업을 적용 하도록 선택 되지 않은 번호 범위를 목록에서 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d752e-128">비즈니스용 Skype Server는 할당 되지 않은 번호 테이블을 위에서 아래로 검색 하 고 지정 된 번호와 일치 하는 첫 번째 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="d752e-129">예를 들어 최후의 방법 동작을 지정하는 범위가 있는 경우 해당 범위는 목록 맨 아래에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="d752e-130">**아래로 이동** 목록에서 선택 되지 않은 번호 범위를 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="d752e-131">**모두 커밋** 지정 하지 않은 숫자 범위에 대 한 모든 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d752e-132">이 명령은 **새 지정되지 않은 번호** 페이지 및 **지정되지 않은 번호 편집** 페이지에서 수행한 모든 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="d752e-133">**새로 고침** 지정 하지 않은 번호 범위 목록을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="d752e-134">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d752e-135">**이름** 지정 되지 않은 숫자 범위를 식별 하는 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="d752e-136">**상태** 데이터베이스에 저장 된 숫자 범위를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="d752e-137">**시작 범위** 지정 되지 않은 숫자 범위의 시작 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="d752e-138">**끝 범위** 지정 되지 않은 숫자 범위의 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="d752e-139">**대상** 지정 되지 않은이 범위의 번호로 들어오는 호출을 처리 하는 알림 응용 프로그램을 호스트 하는 응용 프로그램 서비스의 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="d752e-140">**공지 사항** 이 지정 되지 않은 번호 범위에 대해 재생 될 공지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d752e-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="d752e-141">알림 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype에서 알림 신청 계획](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d752e-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="d752e-142">지정되지 않은 번호 범위를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d752e-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


