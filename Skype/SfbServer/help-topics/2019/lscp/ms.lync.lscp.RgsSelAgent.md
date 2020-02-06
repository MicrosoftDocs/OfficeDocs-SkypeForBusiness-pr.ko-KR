---
title: 에이전트 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: 상담원은 응답 그룹 통화에 응답 하도록 지정 된 사용자입니다. 응답 그룹에는 해당 응답 그룹에 대한 전화를 받을 수 있는 에이전트를 식별하는 에이전트 그룹이 할당되어 있어야 합니다. 에이전트 그룹을 만드는 방법 중 하나는 적합한 사용자를 선택하여 사용자 지정 그룹을 정의하는 것입니다. 비즈니스용 Skype Server 및 Enterprise Voice에서 적격 사용자를 사용할 수 있습니다.
ms.openlocfilehash: 0efc0c0afeff33472075c68cf4300bb5ecf51c66
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793476"
---
# <a name="select-agents"></a><span data-ttu-id="47c9b-106">에이전트 선택</span><span class="sxs-lookup"><span data-stu-id="47c9b-106">Select Agents</span></span>

<span data-ttu-id="47c9b-107">상담원은 응답 그룹 통화에 응답 하도록 지정 된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="47c9b-108">응답 그룹에는 해당 응답 그룹에 대한 전화를 받을 수 있는 에이전트를 식별하는 에이전트 그룹이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="47c9b-109">에이전트 그룹을 만드는 방법 중 하나는 적합한 사용자를 선택하여 사용자 지정 그룹을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="47c9b-110">비즈니스용 Skype Server 및 Enterprise Voice에서 적격 사용자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="47c9b-111">**에이전트 선택** 대화 상자를 사용하여 에이전트 그룹에 추가할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="47c9b-112">UI 참조</span><span class="sxs-lookup"><span data-stu-id="47c9b-112">UI Reference</span></span>

<span data-ttu-id="47c9b-113">다음 목록에서는 **에이전트 선택**의 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="47c9b-114">**찾기** 사용자의 SIP 주소 또는 표시 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="47c9b-115">주소 또는 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="47c9b-116">검색 상자를 비워 두어 비즈니스용 Skype Server 및 Enterprise Voice에 대해 설정 된 모든 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="47c9b-117">**표시할 최대 사용자 수** 표시 되는 반환 되는 결과의 수를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="47c9b-118">많은 결과가 예상 되는 경우이 카운터를 사용 하 여 검색을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="47c9b-119">다음 목록에서는 **에이전트 선택** 대화 상자의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="47c9b-120">**상담원** 검색에서 반환 된 사용자 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="47c9b-121">**SIP 주소** 검색 결과로 반환 되는 사용자 SIP 주소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="47c9b-122">**전화 통신** 사용자에 대해 정의 된 **전화 통신** 필드의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="47c9b-123">**사용 하도록 설정** 사용자에 대해 정의 된 **Lync Server 사용** 필드의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c9b-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="47c9b-124">에이전트 그룹 사용에 대한 자세한 내용은 작업 설명서의 [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47c9b-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


