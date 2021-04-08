---
title: 사용자의 전화 받기 기능 설정
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 사용자가 오디오를 위해 컴퓨터를 사용할 때 오디오 부분에 참가할 수 있도록 Teams에서 전화 통화 기능을 설정하는 방법에 대해 알아보십시오.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623136"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="028f1-103">사용자의 전화 받기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="028f1-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="028f1-104">Microsoft Teams에서 전화 통화 **기능은** 사용자가 전화로 모임의 오디오 부분에 참가할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="028f1-105">오디오에 컴퓨터를 사용할 수 없는 경우 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="028f1-106">사용자는 다른 모임 참가자가 자신의 화면을 공유하거나 컴퓨터를 통해 비디오를 재생하는 경우와 같이 휴대폰 또는 대지 회선 및 모임의 콘텐츠 부분을 통해 모임의 오디오 부분을 &mdash; &mdash; 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="028f1-107">COVID-19 발생과 관련하여 경험한 대로 모임이 많은 기간에는 PSTN 회의 번호 또는 <strong>전화 번호</strong>를 사용해 전화를 거는 대신 <strong>Teams 모임 참가</strong> 버튼을 눌러 모임에 참석하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="028f1-108">이러면 모임이 증가하여 PSTN 네트워크가 정체되는 시기에 오디오 품질을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="028f1-109">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="028f1-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="028f1-110">오디오에 휴대폰을 사용하여 모임 참가</span><span class="sxs-lookup"><span data-stu-id="028f1-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="028f1-111">참가를 클릭하여 모임에  참가한 다음  비디오 및 오디오 옵션 선택 화면에서 전화 오디오를 클릭하고 지금 **참가를 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="028f1-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="028f1-112">여기에서 사용자는 모임 통화를 하게 하여 모임에 참가하거나 모임에 수동으로 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![전화 오디오 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="028f1-114">**Teams 모임에 전화를 걸 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="028f1-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="028f1-115">오디오용 **휴대폰** 사용 화면에서 사용자가 자신의 전화 번호를 입력한 다음 나를 호출 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="028f1-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="028f1-116">모임에서 사용자를 호출하고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-116">The meeting calls the user and joins them to the meeting.</span></span>

![오디오 화면용 휴대폰 사용에서 전화 걸기 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="028f1-118">**수동으로 전화 접속**</span><span class="sxs-lookup"><span data-stu-id="028f1-118">**Dial in manually**</span></span>

<span data-ttu-id="028f1-119">참가하는 또 다른 방법은 모임에 직접 전화 접속하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="028f1-120">오디오용 **휴대폰** 사용 화면에서  수동으로 전화 접속을 클릭하여 모임에 전화 접속하는 데 사용할 전화 번호 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![수동으로 다이얼 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="028f1-122">모임 중에 오디오에 문제가 있는 경우 다시 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="028f1-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="028f1-123">사용자가 모임 중에 컴퓨터를 사용할 때 오디오 문제가 있는 경우 사용자는 오디오에 휴대폰을 사용하여 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="028f1-124">팀은 오디오 또는 디바이스 문제가 발생하는 경우를 감지하고 전화 걸기 옵션을 표시하여 사용자가 휴대폰을 사용할 수 있도록 **리디렉션합니다.**</span><span class="sxs-lookup"><span data-stu-id="028f1-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="028f1-125">다음은 Teams가 마이크를 감지하지  않는 경우 표시되는 메시지 및 통화 다시 호출 옵션의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![전화 걸기 옵션의 스크린샷](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="028f1-127">사용자가 다시 전화 걸기 를 **클릭하면** 오디오 화면에 휴대폰 **사용이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="028f1-128">여기에서는 전화 번호를 입력하고 Teams 모임에 전화를 걸고 모임에 참가하거나 모임에 수동으로 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="028f1-129">전화 걸기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="028f1-129">Set up the Call me feature</span></span>

<span data-ttu-id="028f1-130">조직의 사용자에 대해 전화 걸기 기능을 사용하도록 설정하려면 다음을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="028f1-131">모임(모임 이끌이)을 예약하는 조직의 사용자가 오디오 회의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="028f1-132">자세한 내용은 Teams에 대한 [오디오](set-up-audio-conferencing-in-teams.md) 회의 설정 및 Teams의 사용자에 대한 오디오 회의 설정 관리를 [참조하세요.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="028f1-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="028f1-133">모임 이끌이는 모임에서 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="028f1-134">자세한 내용은 [Teams의 사용자에](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)대한 오디오 회의 설정 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028f1-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="028f1-135">모임 이끌이가 모임에서 전화 접속을 사용할 수  없는 경우 비디오  및 오디오 옵션 선택 화면의 전화 오디오 옵션은 누구도 사용할 수 없습니다. 다른 사용자가 모임에 참가할 전화를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="028f1-136">전화 접속을 사용하도록 설정한 사용자의 경우 모임에 참가한 후 참가자 표시 아이콘에서 자신의 번호로 전화를 걸 수 있는 다른 사용자와 조인할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028f1-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
