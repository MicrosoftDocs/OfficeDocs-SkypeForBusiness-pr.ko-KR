---
title: 클라이언트 버전 구성 새로 만들기 또는 기존 버전 편집
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
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: 클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다. 전역 클라이언트 버전 구성은 비즈니스용 Skype 서버와 함께 설치되고 전체 서버 배포에 대해 클라이언트 버전 제어를 활성화 또는 비활성화하는 데 사용됩니다. 전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다. 클라이언트 버전 제어를 수행하지 않으려면 전역 클라이언트 버전 구성을 사용하지 않도록 설정하면 됩니다.
ms.openlocfilehash: 173bd8d2eb7ca47811497e07b8824aff6a4e6a20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095632"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="60d26-106">클라이언트 버전 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="60d26-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="60d26-107">클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="60d26-108">전역 클라이언트 버전 구성은 비즈니스용 Skype 서버와 함께 설치되고 전체 서버 배포에 대해 클라이언트 버전 제어를 활성화 또는 비활성화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="60d26-109">전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="60d26-110">클라이언트 버전 제어를 수행하지 않으려면 전역 클라이언트 버전 구성을 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="60d26-p103">사이트별로 클라이언트 버전 제어를 사용하거나 사용하지 않도록 설정할 수 있는 사이트별 클라이언트 버전 구성을 만들 수도 있습니다. 사이트별 구성은 전역 구성보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="60d26-113">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="60d26-113">Tasks you can perform</span></span>

<span data-ttu-id="60d26-114">**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="60d26-115">클라이언트 버전 구성의 이름 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="60d26-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="60d26-116">클라이언트 버전 제어를 전역적으로 또는 특정 사이트에 대해 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="60d26-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="60d26-117">클라이언트 버전 구성에 대한 기본 작업 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="60d26-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="60d26-118">UI 참조</span><span class="sxs-lookup"><span data-stu-id="60d26-118">UI Reference</span></span>

<span data-ttu-id="60d26-119">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="60d26-120">**범위** 클라이언트 버전 구성의 범위(전역 또는 사이트)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="60d26-121">**이름** 클라이언트 버전 구성의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="60d26-122">**버전 제어 사용** 구성 범위에 따라 전역적으로 또는 사이트에 대해 클라이언트 버전 제어를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="60d26-123">**기본 작업** 사용자가 특정 클라이언트 버전 정책이 없는 클라이언트 응용 프로그램을 사용하여 로그온을 시도할 때 적용되는 기본 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="60d26-124">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-124">You have the following options:</span></span>

  - <span data-ttu-id="60d26-125">**허용** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="60d26-126">**차단** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="60d26-127">**URL로 차단** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 방지하고 새 클라이언트를 다운로드할 수 있는 URL이 포함된 오류 메시지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="60d26-128">**URL로 허용** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 허용하고 새 클라이언트를 다운로드할 수 있는 URL이 포함된 오류 메시지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="60d26-129">**URL** **URL로** 차단 또는 **URL로** 허용을 선택한 경우 오류 메시지에 포함할 클라이언트 다운로드 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d26-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="60d26-130">클라이언트 및 클라이언트 버전 간의 상호 운용성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d26-130">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="60d26-131">클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="60d26-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>