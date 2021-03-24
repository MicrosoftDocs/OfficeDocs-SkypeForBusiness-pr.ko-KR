---
title: 클라이언트 버전 정책 새로 만들기 또는 기존 버전 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: 사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다.
ms.openlocfilehash: 57c273198a9c88ae26540518c9f892b218b96118
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100694"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="c08de-104">클라이언트 버전 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="c08de-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="c08de-105">사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="c08de-106">버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="c08de-107">비즈니스용 Skype 서버에 포함된 기능을 가장 잘 활용하고 전체 사용자 환경을 개선하기 위해 클라이언트 버전 필터를 사용하여 환경에서 사용되는 클라이언트 버전을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="c08de-108">클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원할 때 비용을 절감하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c08de-p103">필터는 우선 순위에 따라 나열됩니다. 예를 들어 버전 1.5를 실행하는 클라이언트에 연결을 허용하는 필터 다음에 2.0 이전 버전을 실행하는 클라이언트를 차단하는 필터가 있는 경우 첫 번째 필터가 우선적으로 적용되므로 버전 1.5를 실행하는 클라이언트에 연결이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c08de-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="c08de-111">Tasks you can perform</span></span>

<span data-ttu-id="c08de-112">**새 클라이언트 버전 정책** 또는 **클라이언트 버전 정책 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="c08de-113">클라이언트 버전 정책의 이름이나 설명 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c08de-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="c08de-114">클라이언트 버전 정책에 대한 클라이언트 버전 규칙 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c08de-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c08de-115">UI 참조</span><span class="sxs-lookup"><span data-stu-id="c08de-115">UI Reference</span></span>

<span data-ttu-id="c08de-116">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="c08de-117">**범위** 클라이언트 버전 정책의 범위(사이트, 풀 또는 사용자)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="c08de-118">**이름** 클라이언트 버전 정책의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="c08de-119">**설명** 클라이언트 버전 정책 페이지의 목록에서 정책을 식별하는 데 도움이 되는 설명을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="c08de-120">**새로 추가** 정책에 새 클라이언트 버전 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="c08de-121">**세부 정보 표시** 이 옵션을 선택하면 클라이언트 버전 규칙에 대한 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="c08de-122">**제거** 이 옵션은 정책에서 선택한 클라이언트 버전 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="c08de-123">**위쪽 및 아래쪽 화살표** 이 옵션을 선택하면 선택한 클라이언트 버전 규칙이 우선 순위에서 아래로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="c08de-124">규칙은 나열된 순서대로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c08de-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="c08de-125">클라이언트와 클라이언트 버전 간 상호 연동성에 대한 자세한 내용은 [Client Interoperability 을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)</span><span class="sxs-lookup"><span data-stu-id="c08de-125">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013).</span></span> <span data-ttu-id="c08de-126">클라이언트 버전 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c08de-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>