---
title: 클라이언트 버전 정책 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 한 클라이언트에서 사용할 수 있는 기능이 다른 클라이언트의 기능에 의해 제한될 수 있습니다. 비즈니스용 Skype 서버 2015에 포함 된 기능을 최대한 활용 하 고 전반적인 사용자 환경을 개선 하기 위해 클라이언트 버전 필터를 사용 하 여 환경에서 사용 되는 클라이언트 버전을 제한할 수 있습니다. 클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원하는 데 드는 비용을 절감하는 데에도 도움이 됩니다.
ms.openlocfilehash: f89089f34086a36c3e652bf8527ba4db7d108a11
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197064"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="68e1e-106">클라이언트 버전 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="68e1e-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="68e1e-107">사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="68e1e-108">버전이 다른 두 클라이언트가 상호 작용할 경우 한 클라이언트에서 사용할 수 있는 기능이 다른 클라이언트의 기능에 의해 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="68e1e-109">비즈니스용 Skype 서버 2015에 포함 된 기능을 최대한 활용 하 고 전반적인 사용자 환경을 개선 하기 위해 클라이언트 버전 필터를 사용 하 여 환경에서 사용 되는 클라이언트 버전을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="68e1e-110">클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원하는 데 드는 비용을 절감하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68e1e-p103">필터는 우선 순위에 따라 나열됩니다. 예를 들어 버전 1.5를 실행하는 클라이언트에 연결을 허용하는 필터 다음에 2.0 이전 버전을 실행하는 클라이언트를 차단하는 필터가 있는 경우 첫 번째 필터가 우선하고 버전 1.5를 실행하는 클라이언트에 연결이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="68e1e-113">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="68e1e-113">Tasks you can perform</span></span>

<span data-ttu-id="68e1e-114">**새 클라이언트 버전 정책** 또는 **클라이언트 버전 정책 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="68e1e-115">클라이언트 버전 정책의 이름이나 설명 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="68e1e-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="68e1e-116">클라이언트 버전 정책에 대한 클라이언트 버전 규칙 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="68e1e-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="68e1e-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="68e1e-117">UI Reference</span></span>

<span data-ttu-id="68e1e-118">다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="68e1e-119">**범위** 클라이언트 버전 정책의 범위 (사이트, 풀 또는 사용자)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="68e1e-120">**이름** 클라이언트 버전 정책의 이름을 추가 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="68e1e-121">**설명** 클라이언트 버전 정책 페이지의 목록에서 정책을 식별 하는 데 도움이 되는 설명을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="68e1e-122">**새로운** 정책에 새 클라이언트 버전 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="68e1e-123">**세부 정보 표시** 이 옵션은 클라이언트 버전 규칙에 대 한 옵션을 변경할 수 있는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="68e1e-124">**제거** 이 옵션은 정책에서 선택한 클라이언트 버전 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="68e1e-125">**위쪽 및 아래로 화살표** 이 옵션은 선택한 클라이언트 버전 규칙을 우선 순위에서 위 또는 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="68e1e-126">규칙은 나열 된 순서 대로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e1e-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="68e1e-p105">클라이언트와 클라이언트 버전 간 상호 운용성에 대한 자세한 내용은 계획 설명서의 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)을 참조하세요. 클라이언트 버전 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68e1e-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

