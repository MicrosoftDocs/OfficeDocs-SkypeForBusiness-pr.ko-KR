---
title: 클라이언트 버전 규칙
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
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: 클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온을 시도할 때 수행해야 하는 작업을 정의합니다.
ms.openlocfilehash: 14e9c0d14ce988ec89d8bb13410272c4734ae882
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829498"
---
# <a name="client-version-rule"></a><span data-ttu-id="8fc9f-104">클라이언트 버전 규칙</span><span class="sxs-lookup"><span data-stu-id="8fc9f-104">Client Version Rule</span></span>

<span data-ttu-id="8fc9f-105">클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-105">A client version policy is made up of a set of client version rules.</span></span> <span data-ttu-id="8fc9f-106">이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온을 시도할 때 수행해야 하는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-106">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="8fc9f-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="8fc9f-107">Tasks you can perform</span></span>

<span data-ttu-id="8fc9f-108">**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="8fc9f-109">클라이언트 버전 정책에 새 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="8fc9f-110">기존 클라이언트 버전 정책을 구성하는 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="8fc9f-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8fc9f-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="8fc9f-111">UI Reference</span></span>

<span data-ttu-id="8fc9f-112">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="8fc9f-113">**사용자 에이전트** 목록에서 클라이언트 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="8fc9f-114">다음 표에서는 사용자 에이전트 코드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="8fc9f-115">**클라이언트 이름**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-115">**Client Name**</span></span>|<span data-ttu-id="8fc9f-116">**사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fc9f-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="8fc9f-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="8fc9f-118">OC</span><span class="sxs-lookup"><span data-stu-id="8fc9f-118">OC</span></span>  <br/> |
|<span data-ttu-id="8fc9f-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="8fc9f-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="8fc9f-120">CWA</span><span class="sxs-lookup"><span data-stu-id="8fc9f-120">CWA</span></span>  <br/> |
|<span data-ttu-id="8fc9f-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="8fc9f-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="8fc9f-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="8fc9f-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="8fc9f-123">Communicator Phone Edition 플랫폼</span><span class="sxs-lookup"><span data-stu-id="8fc9f-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="8fc9f-124">CPE</span><span class="sxs-lookup"><span data-stu-id="8fc9f-124">CPE</span></span>  <br/> |
|<span data-ttu-id="8fc9f-125">통합 통신 플랫폼</span><span class="sxs-lookup"><span data-stu-id="8fc9f-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="8fc9f-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="8fc9f-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="8fc9f-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="8fc9f-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="8fc9f-128">AOC</span><span class="sxs-lookup"><span data-stu-id="8fc9f-128">AOC</span></span>  <br/> |
|<span data-ttu-id="8fc9f-129">Live Meeting Add-In</span><span class="sxs-lookup"><span data-stu-id="8fc9f-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="8fc9f-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="8fc9f-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="8fc9f-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="8fc9f-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="8fc9f-132">LMC</span><span class="sxs-lookup"><span data-stu-id="8fc9f-132">LMC</span></span>  <br/> |
|<span data-ttu-id="8fc9f-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="8fc9f-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="8fc9f-134">WM</span><span class="sxs-lookup"><span data-stu-id="8fc9f-134">WM</span></span>  <br/> |
|<span data-ttu-id="8fc9f-135">실시간 통신 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8fc9f-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="8fc9f-136">RTC</span><span class="sxs-lookup"><span data-stu-id="8fc9f-136">RTC</span></span>  <br/> |
|<span data-ttu-id="8fc9f-137">Lync 2010 for iPad</span><span class="sxs-lookup"><span data-stu-id="8fc9f-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="8fc9f-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="8fc9f-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="8fc9f-139">Lync 2010 for iPhone</span><span class="sxs-lookup"><span data-stu-id="8fc9f-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="8fc9f-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="8fc9f-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="8fc9f-141">Lync 2010 for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="8fc9f-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="8fc9f-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="8fc9f-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="8fc9f-143">Nokia용 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8fc9f-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="8fc9f-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="8fc9f-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="8fc9f-145">Lync 2010 for Android</span><span class="sxs-lookup"><span data-stu-id="8fc9f-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="8fc9f-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="8fc9f-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="8fc9f-147">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="8fc9f-147">Mobility service</span></span>  <br/> |<span data-ttu-id="8fc9f-148">McxService</span><span class="sxs-lookup"><span data-stu-id="8fc9f-148">McxService</span></span>  <br/> |

- <span data-ttu-id="8fc9f-149">**버전 번호** 다음 필드의 버전 번호를 지정하거나 와일드카드를 사용하여 클라이언트 버전 번호를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="8fc9f-150">**주 버전** 클라이언트의 주 릴리스에 해당하는 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="8fc9f-151">**부 버전** 클라이언트의 부 릴리스에 해당하는 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="8fc9f-152">**빌드** 클라이언트의 주 릴리스 및 부 릴리스에 해당하는 빌드 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="8fc9f-153">**업데이트** 클라이언트의 업데이트된 릴리스에 해당하는 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="8fc9f-154">**비교 작업** 이전 단계에서 지정한 클라이언트 버전에 대해 일치하는 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="8fc9f-155">다음 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-155">The following operations are available:</span></span>

  - <span data-ttu-id="8fc9f-156">**같아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-156">**Same as**</span></span>

  - <span data-ttu-id="8fc9f-157">**아닌**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-157">**Is not**</span></span>

  - <span data-ttu-id="8fc9f-158">**보다 새로 추가**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-158">**Newer than**</span></span>

  - <span data-ttu-id="8fc9f-159">**보다 이상 또는 같아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="8fc9f-160">**이전 버전**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-160">**Older than**</span></span>

  - <span data-ttu-id="8fc9f-161">**보다 오래되거나 같아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-161">**Older than or same as**</span></span>

- <span data-ttu-id="8fc9f-162">**작업** 이전 단계의 조건이 충족될 때 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="8fc9f-163">다음 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-163">The following actions are available:</span></span>

  - <span data-ttu-id="8fc9f-164">**허용** 클라이언트가 로그온할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="8fc9f-165">**허용 및 업그레이드** 클라이언트가 로그온하여 Windows Server Update Service 또는 Microsoft Update에서 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="8fc9f-166">이 작업은 사용자 에이전트 **OC를** 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fc9f-167">이 작업을 선택하면 사용자가 다음에 비즈니스용 Skype에 로그인할 때 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="8fc9f-168">알림에는 Windows Server Update Service 또는 Microsoft Update에 업데이트가 아직 게시되지 않았더라도 사용할 수 있는 업데이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="8fc9f-169">혼란을 방지하기 위해서는 업데이트를 사용할 수 있게 된 뒤에만 이 작업을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="8fc9f-170">**URL을 사용하여 허용** 클라이언트가 로그온할 수 있으며 다른 클라이언트 버전을 다운로드할 위치와 관련한 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="8fc9f-171">URL 필드에 URL을 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="8fc9f-172">**Block** 클라이언트가 로그온하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="8fc9f-173">**차단 및 업그레이드** 클라이언트 로그온을 방지하고 클라이언트가 Windows Server Update Service 또는 Microsoft Update에서 업데이트를 받을 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="8fc9f-174">이 작업은 사용자 에이전트 **OC를** 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="8fc9f-175">**URL을 사용하여** 차단하면 클라이언트가 로그온할 수 있으며 다른 클라이언트 버전을 다운로드할 위치와 관련한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-175">**Block with URL** prevents the client from logging on and displays a message about where to download another client version.</span></span> <span data-ttu-id="8fc9f-176">URL 필드에 URL을 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8fc9f-176">You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="8fc9f-177">클라이언트 및 클라이언트 버전 간의 상호 운용성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-177">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="8fc9f-178">클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fc9f-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

