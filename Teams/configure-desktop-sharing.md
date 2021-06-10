---
title: Microsoft Teams에서 데스크톱 공유 구성하기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: 사용자가 채팅 또는 모임에서 자신의 데스크톱을 공유할 수 있도록 모임 정책을 Teams 방법을 알아보습니다.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35db312d7a4530f05db3cbad59d1b2b29a4e3847
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856467"
---
# <a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="2b324-103">Microsoft Teams에서 데스크톱 공유 구성하기</span><span class="sxs-lookup"><span data-stu-id="2b324-103">Configure desktop sharing in Microsoft Teams</span></span>

<span data-ttu-id="2b324-104">데스크톱 공유를 통해 사용자는 모임이나 채팅 도중에 화면이나 앱을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="2b324-105">관리자는 사용자가 전체 화면, 앱 또는 파일을 공유할 수 있도록 Microsoft Teams에서 화면 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="2b324-106">사용자가 제어권을 주거나 요청하고, PowerPoint 공유를 허용하고, 화이트보드를 추가하고, 공유 노트를 허용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="2b324-107">익명 사용자나 외부 사용자가 공유 화면의 제어권을 요청할 수 있는지 여부도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="2b324-108">Teams 모임의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="2b324-109">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="2b324-109">Anonymous user</span></span>
- <span data-ttu-id="2b324-110">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="2b324-110">Guest users</span></span>
- <span data-ttu-id="2b324-111">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="2b324-111">B2B user</span></span>
- <span data-ttu-id="2b324-112">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="2b324-112">Federated user</span></span>

<span data-ttu-id="2b324-113">화면 공유를 구성하려면 새 모임 정책을 만든 다음 관리하려는 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="2b324-114">**[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에서**</span><span class="sxs-lookup"><span data-stu-id="2b324-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="2b324-115">**모임** > **모임 정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![선택한 모임 정책](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="2b324-117">모임 정책 **페이지에서** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2b324-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![모임 정책 메시지](media/addMeeting.png)

3. <span data-ttu-id="2b324-119">정책에 고유한 제목을 지정하고 간략한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="2b324-120">**콘텐츠 공유** 아래의 드롭다운 목록에서 **화면 공유 모드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="2b324-121">**전체 화면** – 사용자가 전체 데스크톱을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="2b324-122">**단일 응용 프로그램** – 사용자가 단일 활성 응용 프로그램으로 화면 공유를 제한하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="2b324-123">**사용 안 함** – 화면 공유를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-123">**Disabled** – Turns off screen sharing.</span></span>

    ![공유 모드 옵션](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="2b324-125">사용자가 채팅에서 화면 공유를 사용하기 위해 통화 정책을 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="2b324-126">그러나 오디오가 음소차를 해제할 때까지 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="2b324-127">또한 화면을 공유하는 사용자는 오디오 추가를 클릭하여 **오디오를** 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="2b324-128">통화 정책을 사용하지 않도록 설정한 경우 사용자는 채팅 세션에서 화면 공유에 오디오를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="2b324-129">다음 설정을 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="2b324-130">**참가자가 제어를 제공하거나 요청할** 수 있도록 허용 - 팀 구성원이 발표자 데스크톱 또는 애플리케이션에 대한 제어를 제공하거나 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="2b324-131">외부 참가자가 제어를 **제공하거나 요청하도록** 허용합니다. 이는 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="2b324-132">조직이 사용자에 대해 이 정책을 설정했는지 여부는 모임 이끌이의 설정과 관계없이 외부 참가자가 수행할 수 있는 작업을 제어하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="2b324-133">이 매개 변수는 공유자가 소속 조직의 모임 정책 내에서 설정한 정책에 따라 외부 참가자가 공유자 화면의 제어권을 받거나 제어권을 요청할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="2b324-134">**PowerPoint 공유 허용** – 사용자가 PowerPoint 프레젠테이션을 업로드하고 공유하도록 허용하는 모임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="2b324-135">**화이트보드 허용** – 사용자가 화이트보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="2b324-136">**공유 노트 허용** – 사용자가 공유 노트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="2b324-137">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="2b324-138">PowerShell을 사용하여 공유 데스크톱 구성하기</span><span class="sxs-lookup"><span data-stu-id="2b324-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="2b324-139">[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet을 사용하여 데스크톱 공유를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-139">You can also use the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="2b324-140">다음 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b324-140">Set the following parameters:</span></span>

- <span data-ttu-id="2b324-141">Description</span><span class="sxs-lookup"><span data-stu-id="2b324-141">Description</span></span>
- <span data-ttu-id="2b324-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="2b324-142">ScreenSharingMode</span></span>
- <span data-ttu-id="2b324-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="2b324-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="2b324-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="2b324-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="2b324-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="2b324-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="2b324-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="2b324-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="2b324-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="2b324-147">AllowWhiteboard</span></span>
- <span data-ttu-id="2b324-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="2b324-148">AllowSharedNotes</span></span>

<span data-ttu-id="2b324-149">[CsTeamsMeetingPolicy cmdlet을 사용하는 방법에 대해 자세히 알아보세요](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2b324-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>