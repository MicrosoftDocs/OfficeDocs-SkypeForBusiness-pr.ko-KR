---
title: 응답 그룹 큐 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 응답 그룹 큐는 상담원이 전화에 대답할 때까지 응답 그룹에 대 한 통화를 보류 합니다.
ms.openlocfilehash: ae1809a725a8bcb343347975e432adc053ad1d66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690813"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="d52e7-103">응답 그룹 큐: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="d52e7-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="d52e7-104">응답 그룹 큐는 상담원이 전화에 대답할 때까지 응답 그룹에 대 한 통화를 보류 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d52e7-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="d52e7-105">UI Reference</span></span>

<span data-ttu-id="d52e7-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d52e7-107">**이름** 각 대기열에는 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="d52e7-108">큐에 대 한 설명이 포함 된 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="d52e7-109">**설명** 이 필드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-109">**Description** This field is optional.</span></span> <span data-ttu-id="d52e7-110">이 기능을 사용 하 여 대기열에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="d52e7-111">**Groups** 큐에 할당 하려는 에이전트 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="d52e7-112">**선택을** 클릭 하 여 목록에 에이전트 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="d52e7-113">목록에서 선택한 에이전트 그룹을 삭제 하려면 **제거** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="d52e7-114">위쪽 및 아래쪽 화살표를 사용하여 목록에서 선택한 에이전트 그룹을 위쪽 및 아래쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="d52e7-115">에이전트 그룹의 순서는 비즈니스용 Skype 서버에서 사용 가능한 에이전트를 검색 하는 순서에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="d52e7-116">즉, 목록의 첫 번째 그룹에서 사용 가능한 에이전트를 먼저 검색한 다음 두 번째 그룹 및 그 이후 그룹 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="d52e7-117">**큐 시간 초과 사용** 에이전트가 통화에 응답 하기 전에 호출자가 대기를 대기할 최대 기간을 지정 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="d52e7-118">이 옵션을 선택 하는 경우 다음도 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="d52e7-119">**시간 제한 기간 (초)** 호출자가 전화에 응답 하기 전에 대기할 수 있는 최대 시간 (초)을 선택 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="d52e7-120">**통화 동작** 통화 시간 초과 시 발생 하는 작업을 선택 합니다. 선택 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="d52e7-121">**연결 끊기**</span><span class="sxs-lookup"><span data-stu-id="d52e7-121">**Disconnect**</span></span>

  - <span data-ttu-id="d52e7-122">**음성 메일로 착신 전환** 이 옵션을 선택 하는 경우 sip **주소**에 음성 메일 주소를 sip 형식으로 입력 합니다 (<username> @ <domainname> 예: sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d52e7-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="d52e7-123">**전화 번호로 착신 전환** 이 옵션을 선택 하는 경우 **sip 주소** 에서 전화 번호를 sip 형식으로 입력 합니다<number> @ <domainname> (예: sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d52e7-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="d52e7-124">**SIP 주소로 착신 전환** 다른 사용자에 게 통화를 착신 전환 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="d52e7-125">**Sip 주소**에서 sip<username>@<domainname>형식으로 사용자의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="d52e7-126">**다른 큐로 착신 전환** 이 옵션을 선택 하는 경우에는 통화 시간이 초과 될 때 전화를 받을 대기열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="d52e7-127">**큐 오버플로 사용** 큐에서 보유할 수 있는 최대 통화 수를 지정 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="d52e7-128">이 옵션을 선택 하는 경우 다음도 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="d52e7-129">**최대 통화 수** 대기열이 저장할 수 있는 최대 통화 수를 선택 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="d52e7-130">**통화 착신 전환** 큐 오버플로 임계값이 충족 될 때 조치를 취해야 하는 통화를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="d52e7-131">**통화 동작** 큐 오버플로 임계값에 도달 했을 때 발생 하는 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="d52e7-132">선택 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-132">Your choices are:</span></span>

  - <span data-ttu-id="d52e7-133">**연결 끊기**</span><span class="sxs-lookup"><span data-stu-id="d52e7-133">**Disconnect**</span></span>

  - <span data-ttu-id="d52e7-134">**음성 메일로 착신 전환** 이 옵션을 선택 하는 경우 sip **주소**에 음성 메일 주소를 sip 형식으로 입력 합니다 (<username> @ <domainname> 예: sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d52e7-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="d52e7-135">**전화 번호로 착신 전환** 이 옵션을 선택 하는 경우 **sip 주소** 에서 전화 번호를 sip 형식으로 입력 합니다<number> @ <domainname> (예: sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d52e7-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="d52e7-136">**SIP 주소로 착신 전환** 다른 사용자에 게 통화를 착신 전환 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="d52e7-137">**Sip 주소**에서 sip<username>@<domainname>형식으로 사용자의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="d52e7-138">**다른 큐로 착신 전환** 이 옵션을 선택 하는 경우 큐 오버플로 임계값이 충족 될 때 전화를 받을 큐를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d52e7-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="d52e7-139">응답 그룹 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [비즈니스용 Skype 서버에서 응답 그룹 응용 프로그램 계획](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d52e7-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="d52e7-140">큐 사용에 대한 자세한 내용은 작업 설명서의 [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d52e7-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


