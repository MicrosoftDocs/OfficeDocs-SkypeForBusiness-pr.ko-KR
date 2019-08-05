---
title: 클라이언트 버전 정책
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: 사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 한 클라이언트에서 사용할 수 있는 기능이 다른 클라이언트의 기능에 의해 제한될 수 있습니다. 비즈니스용 Skype 서버 2015에 포함 된 기능을 최대한 활용 하 고 전반적인 사용자 환경을 개선 하기 위해 클라이언트 버전 필터를 사용 하 여 환경에서 사용 되는 클라이언트 버전을 제한할 수 있습니다. 클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원하는 데 드는 비용을 절감하는 데에도 도움이 됩니다.
ms.openlocfilehash: 50687531fe9622240b8caeb75a61c3ac705fe84a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197063"
---
# <a name="client-version-policy"></a><span data-ttu-id="d8206-106">클라이언트 버전 정책</span><span class="sxs-lookup"><span data-stu-id="d8206-106">Client Version Policy</span></span>

<span data-ttu-id="d8206-107">사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="d8206-108">버전이 다른 두 클라이언트가 상호 작용할 경우 한 클라이언트에서 사용할 수 있는 기능이 다른 클라이언트의 기능에 의해 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="d8206-109">비즈니스용 Skype 서버 2015에 포함 된 기능을 최대한 활용 하 고 전반적인 사용자 환경을 개선 하기 위해 클라이언트 버전 필터를 사용 하 여 환경에서 사용 되는 클라이언트 버전을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="d8206-110">클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원하는 데 드는 비용을 절감하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d8206-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="d8206-111">Tasks you can perform</span></span>

<span data-ttu-id="d8206-112">**클라이언트 버전 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="d8206-113">기본 ( **전역**) 클라이언트 버전 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="d8206-114">특정 사이트 또는 풀에 대한 클라이언트 버전 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d8206-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="d8206-115">개별 사용자에게 할당할 수 있는 클라이언트 버전 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d8206-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="d8206-116">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d8206-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="d8206-117">UI Reference</span></span>

<span data-ttu-id="d8206-118">다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d8206-119">**새로운** 다음과 같은 각 클라이언트 버전 정책 중 하나 이상을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="d8206-120">사이트 정책</span><span class="sxs-lookup"><span data-stu-id="d8206-120">Site policy</span></span>

  - <span data-ttu-id="d8206-121">풀 정책</span><span class="sxs-lookup"><span data-stu-id="d8206-121">Pool policy</span></span>

  - <span data-ttu-id="d8206-122">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="d8206-122">User policy</span></span>

- <span data-ttu-id="d8206-123">**편집** 클라이언트 버전 정책의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="d8206-124">이 옵션을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="d8206-125">**세부 정보 표시** 이 옵션은 클라이언트 버전 정책에 대 한 옵션을 변경할 수 있는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="d8206-126">**모두 선택** 이 옵션은 목록에서 모든 클라이언트 버전 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="d8206-127">**삭제** 이 옵션을 선택 하면 선택한 모든 클라이언트 버전 정책이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="d8206-128">**새로 고침** 클라이언트 버전 정책 목록을 새로 고쳐 모든 클라이언트 버전 정책에 대 한 옵션의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8206-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="d8206-p104">클라이언트와 클라이언트 버전 간 상호 운용성에 대한 자세한 내용은 계획 설명서의 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)을 참조하세요. 클라이언트 버전 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8206-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

