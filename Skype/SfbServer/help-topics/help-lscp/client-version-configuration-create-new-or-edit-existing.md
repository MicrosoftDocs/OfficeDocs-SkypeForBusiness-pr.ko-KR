---
title: 클라이언트 버전 구성 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다. 전역 클라이언트 버전 구성은 비즈니스용 Skype 서버에 설치 되 고 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다. 전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다. 클라이언트 버전 제어를 수행하지 않으려면 전역 클라이언트 버전 구성을 사용하지 않도록 설정하면 됩니다.
ms.openlocfilehash: 3ead41348d6a9010187f968140ce4c1146a42db0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823101"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="a1e87-106">클라이언트 버전 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="a1e87-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="a1e87-107">클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="a1e87-108">전역 클라이언트 버전 구성은 비즈니스용 Skype 서버에 설치 되 고 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="a1e87-109">전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="a1e87-110">클라이언트 버전 제어를 수행하지 않으려면 전역 클라이언트 버전 구성을 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="a1e87-p103">사이트별로 클라이언트 버전 제어를 사용하거나 사용하지 않도록 설정할 수 있는 사이트별 클라이언트 버전 구성을 만들 수도 있습니다. 사이트별 구성은 전역 구성보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a1e87-113">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="a1e87-113">Tasks you can perform</span></span>

<span data-ttu-id="a1e87-114">**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="a1e87-115">클라이언트 버전 구성의 이름 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a1e87-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="a1e87-116">클라이언트 버전 제어를 전역적으로 또는 특정 사이트에 대해 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a1e87-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="a1e87-117">클라이언트 버전 구성에 대한 기본 작업 추가 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a1e87-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a1e87-118">UI 참조</span><span class="sxs-lookup"><span data-stu-id="a1e87-118">UI Reference</span></span>

<span data-ttu-id="a1e87-119">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="a1e87-120">**범위** 클라이언트 버전 구성의 범위 (전역 또는 사이트)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="a1e87-121">**이름** 클라이언트 버전 구성의 이름을 추가 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="a1e87-122">**버전 제어 사용** 구성의 범위에 따라 클라이언트 버전 제어를 전역적으로 또는 사이트에 대해 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="a1e87-123">**기본 작업** 사용자가 특정 클라이언트 버전 정책이 없는 클라이언트 응용 프로그램을 사용 하 여 로그온 하려고 할 때 적용 되는 기본 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="a1e87-124">사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-124">You have the following options:</span></span>

  - <span data-ttu-id="a1e87-125">**허용** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치 하지 않는 경우 클라이언트에서 로그온 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="a1e87-126">**차단** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치 하지 않는 경우 클라이언트가 로그온 할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="a1e87-127">**URL이 있는 블록** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치 하지 않고 클라이언트가 로그온 할 수 없도록 하 고 최신 클라이언트를 다운로드 하는 URL이 포함 된 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="a1e87-128">**URL에 허용** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치 하지 않는 경우 클라이언트가 로그온 할 수 있도록 허용 하 고 최신 클라이언트를 다운로드할 수 있는 URL이 포함 된 오류 메시지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="a1e87-129">**URL** **Url을 사용 하 여 차단** 또는 **Url을 사용 하도록**선택한 경우 오류 메시지에 포함할 클라이언트 다운로드 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="a1e87-p105">클라이언트와 클라이언트 버전 간 상호 운용성에 대한 자세한 내용은 계획 설명서의 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)을 참조하세요. 클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1e87-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

