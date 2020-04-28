---
title: Microsoft Teams에서 데스크톱 공유 구성하기
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: 사용자가 팀 대화방 또는 모임에서 데스크톱을 공유할 수 있도록 모임 정책을 구성 하는 방법에 대해 알아봅니다.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 955a642d2a2309ccbaf9f9d6280170a93a9179ae
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905900"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="0e416-103">Microsoft Teams에서 데스크톱 공유 구성하기</span><span class="sxs-lookup"><span data-stu-id="0e416-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="0e416-104">데스크톱 공유를 통해 사용자는 모임이나 채팅 도중에 화면이나 앱을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="0e416-105">관리자는 사용자가 전체 화면, 앱 또는 파일을 공유할 수 있도록 Microsoft Teams에서 화면 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="0e416-106">사용자가 제어권을 주거나 요청하고, PowerPoint 공유를 허용하고, 화이트보드를 추가하고, 공유 노트를 허용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="0e416-107">익명 사용자나 외부 사용자가 공유 화면의 제어권을 요청할 수 있는지 여부도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="0e416-108">화면 공유를 구성하려면 새 모임 정책을 만든 다음 관리하려는 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="0e416-109">**[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에서**</span><span class="sxs-lookup"><span data-stu-id="0e416-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="0e416-110">**모임** > **모임 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![선택한 모임 정책을 보여 주는 스크린샷](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="0e416-112">**모임 정책** 페이지에서 **새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![모임 정책 메시지를 보여 주는 스크린샷](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="0e416-114">정책에 고유한 제목을 지정하고 간략한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="0e416-115">**콘텐츠 공유** 아래의 드롭다운 목록에서 **화면 공유 모드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="0e416-116">**전체 화면** – 사용자가 전체 데스크톱을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="0e416-117">**단일 응용 프로그램** – 사용자가 단일 활성 응용 프로그램으로 화면 공유를 제한하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="0e416-118">**사용 안 함** – 화면 공유를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-118">**Disabled** – Turns off screen sharing.</span></span>

    ![공유 모드 옵션을 보여 주는 스크린샷](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="0e416-120">다음 설정을 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="0e416-121">**참가자가 제어권을 부여 하거나 요청할 수 있도록 허용** -팀 멤버가 발표자의 데스크톱 또는 응용 프로그램에 대 한 제어권을 부여 하거나 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="0e416-122">**외부 참가자가 제어권을 부여 하거나 요청 하도록 허용** – 게스트 및 외부 (페더레이션된) 사용자가 발표자의 데스크톱 또는 응용 프로그램에 대 한 제어권을 부여 하거나 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="0e416-123">**PowerPoint 공유 허용** – 사용자가 PowerPoint 프레젠테이션을 업로드하고 공유하도록 허용하는 모임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="0e416-124">**화이트보드 허용** – 사용자가 화이트보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="0e416-125">**공유 노트 허용** – 사용자가 공유 노트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="0e416-126">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="0e416-127">PowerShell을 사용하여 공유 데스크톱 구성하기</span><span class="sxs-lookup"><span data-stu-id="0e416-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="0e416-128">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet을 사용하여 데스크톱 공유를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="0e416-129">다음 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e416-129">Set the following parameters:</span></span>

- <span data-ttu-id="0e416-130">Description</span><span class="sxs-lookup"><span data-stu-id="0e416-130">Description</span></span>
- <span data-ttu-id="0e416-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="0e416-131">ScreenSharingMode</span></span>
- <span data-ttu-id="0e416-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="0e416-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="0e416-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="0e416-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="0e416-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="0e416-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="0e416-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="0e416-135">AllowWhiteboard</span></span>
- <span data-ttu-id="0e416-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="0e416-136">AllowSharedNotes</span></span>

<span data-ttu-id="0e416-137">[CsTeamsMeetingPolicy cmdlet을 사용하는 방법에 대해 자세히 알아보세요](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0e416-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

