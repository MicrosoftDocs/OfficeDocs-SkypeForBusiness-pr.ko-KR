---
title: 클라이언트 버전 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 환경에서 지원 하려는 클라이언트 버전을 지정 하는 것 외에도 아직 버전 정책이 정의 되어 있지 않은 클라이언트에 대 한 기본 작업을 지정할 수 있습니다. 이렇게 하면 환경에서 사용 되는 클라이언트 버전을 제한할 수 있으며,이를 통해 여러 클라이언트 버전 지원과 관련 된 비용을 제어 하는 데 도움이 됩니다.
ms.openlocfilehash: e5675a2b3cab2309a78c2d8dc88041beee8cc619
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794567"
---
# <a name="client-version-configuration"></a><span data-ttu-id="47053-104">클라이언트 버전 구성</span><span class="sxs-lookup"><span data-stu-id="47053-104">Client Version Configuration</span></span>

<span data-ttu-id="47053-105">환경에서 지원 하려는 클라이언트 버전을 지정 하는 것 외에도 아직 버전 정책이 정의 되어 있지 않은 클라이언트에 대 한 기본 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="47053-106">이렇게 하면 환경에서 사용 되는 클라이언트 버전을 제한할 수 있으며,이를 통해 여러 클라이언트 버전 지원과 관련 된 비용을 제어 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47053-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="47053-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="47053-107">Tasks you can perform</span></span>

<span data-ttu-id="47053-108">**클라이언트 버전 구성** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="47053-109">기본 ( **전역**) 클라이언트 버전 구성을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="47053-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="47053-110">특정 사이트에 대 한 클라이언트 버전 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47053-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="47053-111">기존 클라이언트 버전 구성을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47053-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="47053-112">익명 사용자는 사이트와 연결 되어 있지 않기 때문에 익명 사용자는 글로벌 수준 정책에 의해서만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="47053-113">UI 참조</span><span class="sxs-lookup"><span data-stu-id="47053-113">UI Reference</span></span>

<span data-ttu-id="47053-114">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47053-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="47053-115">**새로운** 특정 사이트에 대 한 클라이언트 버전 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="47053-116">**편집** 클라이언트 버전 정책의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="47053-117">이 옵션을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="47053-118">**세부 정보 표시** 이 옵션은 클라이언트 버전 구성에 대 한 옵션을 변경할 수 있는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47053-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="47053-119">**모두 선택** 이 옵션은 목록에서 모든 클라이언트 버전 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47053-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="47053-120">**삭제** 이 옵션은 선택한 모든 클라이언트 버전 구성을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="47053-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="47053-121">**새로 고침** 클라이언트 버전 구성 목록을 새로 고쳐 모든 클라이언트 버전 구성의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47053-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="47053-122">클라이언트와 클라이언트 버전 간의 상호 운용성에 대 한 자세한 내용은 계획 설명서의 [클라이언트 상호 운용성](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47053-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="47053-123">클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47053-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

