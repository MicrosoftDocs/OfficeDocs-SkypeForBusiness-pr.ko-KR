---
title: 클라이언트 버전 규칙
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전을 사용하여 로그온을 시도할 때 수행할 동작을 정의합니다.
ms.openlocfilehash: ab67f926f7a2e0ddc91f33bc9657d8fd4104e3a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197134"
---
# <a name="client-version-rule"></a><span data-ttu-id="1d79e-104">클라이언트 버전 규칙</span><span class="sxs-lookup"><span data-stu-id="1d79e-104">Client Version Rule</span></span>

<span data-ttu-id="1d79e-p102">클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전을 사용하여 로그온을 시도할 때 수행할 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1d79e-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="1d79e-107">Tasks you can perform</span></span>

<span data-ttu-id="1d79e-108">**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="1d79e-109">클라이언트 버전 정책에 새 규칙 추가</span><span class="sxs-lookup"><span data-stu-id="1d79e-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="1d79e-110">기존 클라이언트 버전 정책을 구성하는 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="1d79e-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1d79e-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="1d79e-111">UI Reference</span></span>

<span data-ttu-id="1d79e-112">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="1d79e-113">**사용자 에이전트** 목록에서 클라이언트 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="1d79e-114">다음 표에서는 사용자 에이전트 코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-114">The following table defines user agent codes.</span></span> <span data-ttu-id="1d79e-115">이 목록에는 레거시 클라이언트 유형이 포함 되며, 일부는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="1d79e-116">**클라이언트 이름**</span><span class="sxs-lookup"><span data-stu-id="1d79e-116">**Client Name**</span></span>|<span data-ttu-id="1d79e-117">**사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="1d79e-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d79e-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="1d79e-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="1d79e-119">OC</span><span class="sxs-lookup"><span data-stu-id="1d79e-119">OC</span></span>  <br/> |
|<span data-ttu-id="1d79e-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="1d79e-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="1d79e-121">CWA</span><span class="sxs-lookup"><span data-stu-id="1d79e-121">CWA</span></span>  <br/> |
|<span data-ttu-id="1d79e-122">Lync Phone Edition, Office Communicator 휴대폰</span><span class="sxs-lookup"><span data-stu-id="1d79e-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="1d79e-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="1d79e-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="1d79e-124">Communicator Phone Edition 플랫폼</span><span class="sxs-lookup"><span data-stu-id="1d79e-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="1d79e-125">CPE</span><span class="sxs-lookup"><span data-stu-id="1d79e-125">CPE</span></span>  <br/> |
|<span data-ttu-id="1d79e-126">통합 통신 플랫폼</span><span class="sxs-lookup"><span data-stu-id="1d79e-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="1d79e-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="1d79e-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="1d79e-128">Lync 2010 참석자</span><span class="sxs-lookup"><span data-stu-id="1d79e-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="1d79e-129">AOC</span><span class="sxs-lookup"><span data-stu-id="1d79e-129">AOC</span></span>  <br/> |
|<span data-ttu-id="1d79e-130">Live Meeting 추가 기능</span><span class="sxs-lookup"><span data-stu-id="1d79e-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="1d79e-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="1d79e-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="1d79e-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="1d79e-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="1d79e-133">LMC</span><span class="sxs-lookup"><span data-stu-id="1d79e-133">LMC</span></span>  <br/> |
|<span data-ttu-id="1d79e-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="1d79e-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="1d79e-135">WM</span><span class="sxs-lookup"><span data-stu-id="1d79e-135">WM</span></span>  <br/> |
|<span data-ttu-id="1d79e-136">실시간 통신 클라이언트</span><span class="sxs-lookup"><span data-stu-id="1d79e-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="1d79e-137">RTC</span><span class="sxs-lookup"><span data-stu-id="1d79e-137">RTC</span></span>  <br/> |
|<span data-ttu-id="1d79e-138">IPad 용 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1d79e-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="1d79e-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="1d79e-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="1d79e-140">IPhone 용 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1d79e-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="1d79e-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="1d79e-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="1d79e-142">Windows Phone 용 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1d79e-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="1d79e-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="1d79e-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="1d79e-144">Nokia 용 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1d79e-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="1d79e-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="1d79e-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="1d79e-146">Android 용 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1d79e-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="1d79e-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="1d79e-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="1d79e-148">모바일 서비스</span><span class="sxs-lookup"><span data-stu-id="1d79e-148">Mobility service</span></span>  <br/> |<span data-ttu-id="1d79e-149">McxService</span><span class="sxs-lookup"><span data-stu-id="1d79e-149">McxService</span></span>  <br/> |

- <span data-ttu-id="1d79e-150">**버전 번호** 다음 필드에 대 한 버전 번호를 지정 하거나 와일드 카드를 사용 하 여 클라이언트 버전 번호를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="1d79e-151">**주 버전** 클라이언트의 주요 릴리스에 해당 하는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="1d79e-152">**부 버전** 클라이언트의 부 릴리스에 해당 하는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="1d79e-153">**빌드** 클라이언트의 주 및 부 릴리스에 해당 하는 빌드 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="1d79e-154">**업데이트** 업데이트 된 클라이언트의 릴리스에 해당 하는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="1d79e-155">**비교 연산** 앞 단계에서 지정한 클라이언트 버전에 대 한 일치 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="1d79e-156">다음과 같은 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-156">The following operations are available:</span></span>

  - <span data-ttu-id="1d79e-157">**같음**</span><span class="sxs-lookup"><span data-stu-id="1d79e-157">**Same as**</span></span>

  - <span data-ttu-id="1d79e-158">**일치하지 않음**</span><span class="sxs-lookup"><span data-stu-id="1d79e-158">**Is not**</span></span>

  - <span data-ttu-id="1d79e-159">**보다 최근임**</span><span class="sxs-lookup"><span data-stu-id="1d79e-159">**Newer than**</span></span>

  - <span data-ttu-id="1d79e-160">**보다 최근이거나 같음**</span><span class="sxs-lookup"><span data-stu-id="1d79e-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="1d79e-161">**보다 오래됨**</span><span class="sxs-lookup"><span data-stu-id="1d79e-161">**Older than**</span></span>

  - <span data-ttu-id="1d79e-162">**보다 오래되거나 같음**</span><span class="sxs-lookup"><span data-stu-id="1d79e-162">**Older than or same as**</span></span>

- <span data-ttu-id="1d79e-163">**작업** 앞 단계의 조건이 충족 되는 경우 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="1d79e-164">사용할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-164">The following actions are available:</span></span>

  - <span data-ttu-id="1d79e-165">**허용** 클라이언트가 로그온 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="1d79e-166">**허용 및 업그레이드** 클라이언트가 Windows Server Update 서비스 또는 Microsoft Update에서 로그온 하 고 업데이트를 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="1d79e-167">이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d79e-168">이 작업을 선택 하면 다음에 사용자가 비즈니스용 Skype에 로그인 할 때 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="1d79e-169">알림에는 Windows Server Update Service 또는 Microsoft Update에 업데이트가 아직 게시되지 않았더라도 사용할 수 있는 업데이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="1d79e-170">혼란을 방지하기 위해서는 업데이트를 사용할 수 있는 경우에만 이 작업을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="1d79e-171">**URL에 허용** 클라이언트가 로그온 하도록 허용 하 고 다른 클라이언트 버전을 다운로드할 위치에 대 한 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="1d79e-172">**URL** 필드에서 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="1d79e-173">**차단** 클라이언트가 로그온 할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="1d79e-174">**차단 및 업그레이드** 클라이언트가 로그온 할 수 없고 클라이언트가 Windows Server Update 서비스 또는 Microsoft 업데이트에서 업데이트를 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="1d79e-175">이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="1d79e-p110">**URL로 차단**을 선택하면 클라이언트가 로그온할 수 없도록 차단하고 다른 클라이언트 버전을 다운로드할 위치에 대한 메시지를 표시합니다. **URL** 필드에서 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d79e-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="1d79e-178">클라이언트와 클라이언트 버전 간의 상호 운용성에 대 한 자세한 내용은 계획 설명서의 [클라이언트 상호 운용성](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d79e-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="1d79e-179">클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d79e-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

