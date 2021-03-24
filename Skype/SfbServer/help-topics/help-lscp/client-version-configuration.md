---
title: 클라이언트 버전 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: 환경에서 지원하려는 클라이언트 버전을 지정하는 것 외에도, 아직 버전 정책이 정의되지 않은 클라이언트에 대해 기본 동작을 지정할 수 있습니다. 이렇게 하면 환경에서 사용되는 클라이언트 버전을 제한할 수 있으므로 여러 클라이언트 버전 지원과 연관된 비용을 제어할 수 있습니다.
ms.openlocfilehash: 31facafd00a25993aa16f5d89b1fad5a97e566a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095622"
---
# <a name="client-version-configuration"></a><span data-ttu-id="28033-104">클라이언트 버전 구성</span><span class="sxs-lookup"><span data-stu-id="28033-104">Client Version Configuration</span></span>

<span data-ttu-id="28033-p102">환경에서 지원하려는 클라이언트 버전을 지정하는 것 외에도, 아직 버전 정책이 정의되지 않은 클라이언트에 대해 기본 동작을 지정할 수 있습니다. 이렇게 하면 환경에서 사용되는 클라이언트 버전을 제한할 수 있으므로 여러 클라이언트 버전 지원과 연관된 비용을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="28033-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="28033-107">Tasks you can perform</span></span>

<span data-ttu-id="28033-108">**클라이언트 버전 구성** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="28033-109">**기본(전역)** 클라이언트 버전 구성을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="28033-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="28033-110">특정 사이트에 대한 클라이언트 버전 구성 만들기</span><span class="sxs-lookup"><span data-stu-id="28033-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="28033-111">기존 클라이언트 버전 구성을 사용 및 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="28033-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="28033-112">익명 사용자는 사이트와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="28033-113">UI 참조</span><span class="sxs-lookup"><span data-stu-id="28033-113">UI Reference</span></span>

<span data-ttu-id="28033-114">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28033-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="28033-115">**새로 추가** 특정 사이트에 대한 클라이언트 버전 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="28033-116">**편집** 클라이언트 버전 정책의 옵션을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="28033-117">이 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="28033-118">**세부 정보 표시** 이 옵션을 선택하면 클라이언트 버전 구성에 대한 옵션을 변경할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="28033-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="28033-119">**모두 선택** 이 옵션은 목록의 모든 클라이언트 버전 구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="28033-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="28033-120">**삭제** 이 옵션은 선택한 모든 클라이언트 버전 구성을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="28033-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="28033-121">**새로 고침** 클라이언트 버전 구성 목록을 새로 고쳐 모든 클라이언트 버전 구성의 옵션 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28033-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="28033-122">클라이언트 및 클라이언트 버전 간의 상호 운용성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28033-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="28033-123">클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28033-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>