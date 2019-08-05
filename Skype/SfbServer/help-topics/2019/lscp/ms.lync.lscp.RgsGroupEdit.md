---
title: 응답 그룹이 새로 만들거나 기존 에이전트 그룹을 편집 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: 에이전트 그룹은 응답 그룹(에이전트라고도 함)에 대한 전화를 받을 수 있는 사람과 그룹의 모든 에이전트에 적용되는 설정을 정의합니다.
ms.openlocfilehash: bafa1ae490da49c8a4af096129a122315a2a7809
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196266"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="61c65-103">응답 그룹: 새 에이전트 그룹 만들기 또는 기존 그룹 편집</span><span class="sxs-lookup"><span data-stu-id="61c65-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="61c65-104">에이전트 그룹은 응답 그룹(에이전트라고도 함)에 대한 전화를 받을 수 있는 사람과 그룹의 모든 에이전트에 적용되는 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="61c65-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="61c65-105">UI Reference</span></span>

<span data-ttu-id="61c65-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="61c65-107">**이름** 각 에이전트 그룹에는 고유한 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="61c65-108">그룹의 기능을 식별 하는 설명적인 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="61c65-109">예를 들어 지원 센터.</span><span class="sxs-lookup"><span data-stu-id="61c65-109">For example, Help Desk.</span></span>

- <span data-ttu-id="61c65-110">**설명** 이 필드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-110">**Description** This field is optional.</span></span> <span data-ttu-id="61c65-111">이 기능을 사용 하 여 그룹에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="61c65-112">**참가 정책** 에이전트가 응답 그룹에 로그인 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="61c65-p103">그룹의 에이전트가 로그인 및 로그아웃할 필요가 없도록 지정하려면 **비공식**을 선택합니다. 비공식 에이전트는 로그인하면 자동으로 로그인됩니다. **비공식**이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="61c65-115">그룹의 에이전트가 로그인 및 로그 아웃 하도록 지정 하려면 **정식** 을 선택 합니다. 이 옵션을 선택 하면 에이전트는 클라이언트에서 메뉴 항목을 클릭 하 여 브라우저를 열고 로그인 및 로그 아웃을 위한 웹 페이지 콘솔을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="61c65-116">**알림 시간 (초)** 사용 가능한 다음 에이전트에 대 한 통화를 제공 하기 전에 에이전트를 연결 하는 시간 (초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="61c65-117">값은 10 초 이상 180 초 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="61c65-118">기본값은 20 초입니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="61c65-119">**라우팅 방법** 에이전트가 전화를 받는 순서를 결정 하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="61c65-120">새 전화를 유휴 시간이 가장 길었던 에이전트(현재 상태가 **온라인** 또는 **대화 불가능**이었던 에이전트)가 먼저 받도록 하려면 **최장 유휴 시간**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="61c65-p105">대화 가능한 모든 에이전트가 새 전화를 동시에 받도록 하려면 **병렬**을 선택합니다. 전화를 수락하는 첫 번째 에이전트에게 전화가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="61c65-123">각 에이전트가 차례로 새 전화를 받도록 하려면 **라운드 로빈**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="61c65-124">항상 **에이전트** 목록에 나열된 순서대로 에이전트가 새 전화를 받도록 하려면 **직렬**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="61c65-125">현재 상태에 관계 없이 응답 그룹 응용 프로그램과 동시에 로그인 한 모든 상담원에 게 새 통화를 제공 하려면 **전화 교환을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="61c65-126">상담원으로 구성 된 전화 교환 및 클라이언트 사용자는 대기 중인 모든 통화를 볼 수 있으며 모든 순서에 따라 대기 중인 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="61c65-127">이 경우 통화를 수락한 첫 번째 에이전트에 통화가 전송되고 다른 참가자 및 사용자에게는 통화가 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="61c65-128">**상담원** 다음 중 한 가지 방법으로 응답 그룹의 에이전트로 사용할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="61c65-129">**기존 전자 메일 그룹 사용** 을 선택 하 여 Exchange 메일 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="61c65-130">메일 그룹의 전자 메일 주소를 **메일 그룹 주소**에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61c65-p108">메일 그룹은 에이전트 그룹당 하나만 선택할 수 있습니다. 메일 그룹에 중첩된 메일 그룹이 포함되는 경우 중첩된 메일 그룹은 에이전트 그룹에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61c65-133">에이전트가 메일 그룹에 나열되는 순서는 에이전트가 라운드 로빈 및 직렬 라우팅의 전화를 받는 순서에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61c65-134">숨겨진 구성원 또는 숨겨진 목록은 응답 그룹 관리자 또는 사용자에 게 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="61c65-135">자세한 내용은 [비즈니스용 Skype에서 에이전트 그룹 만들기 또는 수정을](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61c65-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="61c65-p110">응답 그룹에 대해 에이전트로 할당할 사용자를 선택하려면 **사용자 지정 에이전트 그룹 정의**를 선택합니다. 목록에 에이전트를 추가하려면 **선택**을 클릭합니다. 목록에서 선택한 에이전트를 삭제하려면 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="61c65-p111">위쪽 및 아래쪽 화살표를 사용하여 에이전트 목록에서 선택한 에이전트를 위쪽 및 아래쪽으로 이동합니다. 목록의 에이전트 순서는 에이전트가 라운드 로빈 및 직렬 라우팅의 전화를 받는 순서에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61c65-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="61c65-141">응답 그룹 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [비즈니스용 Skype 서버에서 응답 그룹 응용 프로그램 계획](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61c65-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="61c65-142">에이전트 그룹 사용에 대한 자세한 내용은 작업 설명서의 [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c65-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


