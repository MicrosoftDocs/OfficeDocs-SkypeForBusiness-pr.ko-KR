---
title: 에이전트 선택
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: 에이전트는 응답 그룹 통화에 응답할 수 있도록 지정된 사용자입니다. 응답 그룹에는 해당 응답 그룹에 대한 전화를 받을 수 있는 에이전트를 식별하는 에이전트 그룹이 할당되어 있어야 합니다. 에이전트 그룹을 만드는 방법 중 하나는 적합한 사용자를 선택하여 사용자 지정 그룹을 정의하는 것입니다. 적합한 사용자는 비즈니스용 Skype 서버 및 비즈니스용 Skype 서버에 Enterprise Voice.
ms.openlocfilehash: c245ea9816d60fc8448eeeb00bdfc8351e345784
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108004"
---
# <a name="select-agents"></a><span data-ttu-id="6120f-106">에이전트 선택</span><span class="sxs-lookup"><span data-stu-id="6120f-106">Select Agents</span></span>

<span data-ttu-id="6120f-107">에이전트는 응답 그룹 통화에 응답할 수 있도록 지정된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="6120f-108">응답 그룹에는 해당 응답 그룹에 대한 전화를 받을 수 있는 에이전트를 식별하는 에이전트 그룹이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="6120f-109">에이전트 그룹을 만드는 방법 중 하나는 적합한 사용자를 선택하여 사용자 지정 그룹을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="6120f-110">적합한 사용자는 비즈니스용 Skype 서버 및 비즈니스용 Skype 서버에 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6120f-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="6120f-111">**에이전트 선택** 대화 상자를 사용하여 에이전트 그룹에 추가할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6120f-112">UI 참조</span><span class="sxs-lookup"><span data-stu-id="6120f-112">UI Reference</span></span>

<span data-ttu-id="6120f-113">다음 목록에서는 **에이전트 선택** 대화 상자의 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="6120f-114">**찾기** 사용자의 SIP 주소 또는 표시 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="6120f-115">주소 또는 이름의 전체 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="6120f-116">검색 상자를 비워 두면 비즈니스용 Skype 서버 및 비즈니스용 Skype 서버를 사용할 수 있는 모든 사용자가 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6120f-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="6120f-117">**표시할 최대 사용자 수** 표시되는 반환된 결과 수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="6120f-118">많은 결과가 예상된 경우 이 카운터를 사용하여 검색을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="6120f-119">다음 목록에서는 **에이전트 선택** 대화 상자의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="6120f-120">**에이전트** 검색에서 반환된 사용자 이름을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="6120f-121">**SIP 주소** 검색에서 반환된 사용자 SIP 주소를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="6120f-122">**전화 통신** 사용자에 대해 정의된 전화 통신 **필드의** 값을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="6120f-123">**사용** 사용자에 대해 정의된 **Lync Server에 대해 사용** 필드의 값을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6120f-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="6120f-124">에이전트 그룹을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6120f-124">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>