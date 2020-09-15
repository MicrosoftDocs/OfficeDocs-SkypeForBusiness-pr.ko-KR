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
description: 사용자가 팀 대화방 또는 모임에서 데스크톱을 공유할 수 있도록 모임 정책을 구성 하는 방법에 대해 알아봅니다.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652478"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="56e7f-103">Microsoft Teams에서 데스크톱 공유 구성하기</span><span class="sxs-lookup"><span data-stu-id="56e7f-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="56e7f-104">데스크톱 공유를 통해 사용자는 모임이나 채팅 도중에 화면이나 앱을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="56e7f-105">관리자는 사용자가 전체 화면, 앱 또는 파일을 공유할 수 있도록 Microsoft Teams에서 화면 공유를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="56e7f-106">사용자가 제어권을 주거나 요청하고, PowerPoint 공유를 허용하고, 화이트보드를 추가하고, 공유 노트를 허용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="56e7f-107">익명 사용자나 외부 사용자가 공유 화면의 제어권을 요청할 수 있는지 여부도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="56e7f-108">팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="56e7f-109">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="56e7f-109">Anonymous user</span></span>
- <span data-ttu-id="56e7f-110">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="56e7f-110">Guest users</span></span>
- <span data-ttu-id="56e7f-111">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="56e7f-111">B2B user</span></span>
- <span data-ttu-id="56e7f-112">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="56e7f-112">Federated user</span></span>

<span data-ttu-id="56e7f-113">화면 공유를 구성하려면 새 모임 정책을 만든 다음 관리하려는 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="56e7f-114">**[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에서**</span><span class="sxs-lookup"><span data-stu-id="56e7f-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="56e7f-115">**모임** > **모임 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![모임 정책 선택](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="56e7f-117">**모임 정책** 페이지에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![모임 정책 메시지](media/addMeeting.png)

3. <span data-ttu-id="56e7f-119">정책에 고유한 제목을 지정하고 간략한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="56e7f-120">**콘텐츠 공유** 아래의 드롭다운 목록에서 **화면 공유 모드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="56e7f-121">**전체 화면** – 사용자가 전체 데스크톱을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="56e7f-122">**단일 응용 프로그램** – 사용자가 단일 활성 응용 프로그램으로 화면 공유를 제한하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="56e7f-123">**사용 안 함** – 화면 공유를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-123">**Disabled** – Turns off screen sharing.</span></span>

    ![공유 모드 옵션](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="56e7f-125">사용자가 채팅에서 화면 공유를 사용할 수 있도록 호출 정책을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="56e7f-126">그러나 음소거가 해제 될 때까지 해당 오디오는 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="56e7f-127">또한 화면을 공유 하는 사용자는 오디오 **추가** 를 클릭 하 여 오디오를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="56e7f-128">통화 정책을 사용 하지 않도록 설정 하면 사용자가 채팅 세션에서 화면 공유에 오디오를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="56e7f-129">다음 설정을 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="56e7f-130">**참가자가 제어권을 부여 하거나 요청할 수 있도록 허용** -팀 멤버가 발표자의 데스크톱 또는 응용 프로그램에 대 한 제어권을 부여 하거나 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="56e7f-131">**외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용** -이것은 사용자 단위 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="56e7f-132">조직에서이 사용자에 대해이 집합을 보유 하 고 있는지 여부는 모임 이끌이가 설정한 내용에 관계 없이 외부 참가자가 수행할 수 있는 작업을 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="56e7f-133">이 매개 변수는 해당 조직의 모임 정책 내에서 설정한 공유자에 따라 외부 참가자가 제어권을 부여 하거나 공유자 화면 제어권을 요청할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="56e7f-134">**PowerPoint 공유 허용** – 사용자가 PowerPoint 프레젠테이션을 업로드하고 공유하도록 허용하는 모임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="56e7f-135">**화이트보드 허용** – 사용자가 화이트보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="56e7f-136">**공유 노트 허용** – 사용자가 공유 노트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="56e7f-137">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="56e7f-138">PowerShell을 사용하여 공유 데스크톱 구성하기</span><span class="sxs-lookup"><span data-stu-id="56e7f-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="56e7f-139">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet을 사용하여 데스크톱 공유를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-139">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="56e7f-140">다음 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56e7f-140">Set the following parameters:</span></span>

- <span data-ttu-id="56e7f-141">Description</span><span class="sxs-lookup"><span data-stu-id="56e7f-141">Description</span></span>
- <span data-ttu-id="56e7f-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="56e7f-142">ScreenSharingMode</span></span>
- <span data-ttu-id="56e7f-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="56e7f-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="56e7f-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="56e7f-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="56e7f-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="56e7f-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="56e7f-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="56e7f-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="56e7f-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="56e7f-147">AllowWhiteboard</span></span>
- <span data-ttu-id="56e7f-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="56e7f-148">AllowSharedNotes</span></span>

<span data-ttu-id="56e7f-149">[CsTeamsMeetingPolicy cmdlet을 사용하는 방법에 대해 자세히 알아보세요](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="56e7f-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>
