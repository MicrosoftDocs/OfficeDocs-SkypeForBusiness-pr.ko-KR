---
title: 클라이언트 버전 정책
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: 사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다. 비즈니스용 Skype 서버 2015에 포함된 기능을 가장 잘 활용하고 전체 사용자 환경을 개선하기 위해 클라이언트 버전 필터를 사용하여 사용자 환경에서 사용되는 클라이언트 버전을 제한할 수 있습니다. 클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원할 때 비용을 절감하는 데에도 도움이 됩니다.
ms.openlocfilehash: 7147df6d6f2460c1b341cced6a9ecc207943da8d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833398"
---
# <a name="client-version-policy"></a><span data-ttu-id="22de2-106">클라이언트 버전 정책</span><span class="sxs-lookup"><span data-stu-id="22de2-106">Client Version Policy</span></span>

<span data-ttu-id="22de2-107">사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="22de2-108">버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="22de2-109">비즈니스용 Skype 서버 2015에 포함된 기능을 가장 잘 활용하고 전체 사용자 환경을 개선하기 위해 클라이언트 버전 필터를 사용하여 사용자 환경에서 사용되는 클라이언트 버전을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="22de2-110">클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원할 때 비용을 절감하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="22de2-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="22de2-111">Tasks you can perform</span></span>

<span data-ttu-id="22de2-112">**클라이언트 버전 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="22de2-113">**기본(전역)** 클라이언트 버전 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="22de2-114">특정 사이트 또는 풀에 대한 클라이언트 버전 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="22de2-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="22de2-115">개별 사용자에게 할당할 수 있는 클라이언트 버전 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="22de2-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="22de2-116">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="22de2-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="22de2-117">UI Reference</span></span>

<span data-ttu-id="22de2-118">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="22de2-119">**신규** 다음 각 클라이언트 버전 정책을 하나 이상 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="22de2-120">사이트 정책</span><span class="sxs-lookup"><span data-stu-id="22de2-120">Site policy</span></span>

  - <span data-ttu-id="22de2-121">풀 정책</span><span class="sxs-lookup"><span data-stu-id="22de2-121">Pool policy</span></span>

  - <span data-ttu-id="22de2-122">사용자 정책</span><span class="sxs-lookup"><span data-stu-id="22de2-122">User policy</span></span>

- <span data-ttu-id="22de2-123">**편집** 클라이언트 버전 정책의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="22de2-124">이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="22de2-125">**세부 정보 표시** 이 옵션을 선택하면 클라이언트 버전 정책에 대한 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="22de2-126">**모두 선택** 이 옵션은 목록의 모든 클라이언트 버전 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="22de2-127">**삭제** 이 옵션은 선택한 모든 클라이언트 버전 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="22de2-128">**새로 고침** 클라이언트 버전 정책 목록을 새로 고쳐 모든 클라이언트 버전 정책의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22de2-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="22de2-129">클라이언트 및 클라이언트 버전 간의 상호 운용성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="22de2-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="22de2-130">클라이언트 버전 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="22de2-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

