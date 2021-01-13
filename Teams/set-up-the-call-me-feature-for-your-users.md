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
description: 사용자가 자신의 컴퓨터를 오디오에 사용할 때 오디오 부분에 참가할 수 없는 경우 전화로 오디오 부분에 참가할 수 있도록 Teams에서 통화 기능을 설정하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821098"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="7fb4c-103">사용자의 전화 받기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="7fb4c-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="7fb4c-104">Microsoft Teams에서  통화 기능을 사용하면 전화로 모임의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="7fb4c-105">이 시나리오는 오디오에 컴퓨터를 사용할 수 없는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="7fb4c-106">사용자는 다른 모임 참가자가 자신의 화면을 공유하거나 자신의 컴퓨터를 통해 비디오를 재생하는 경우와 같이 휴대폰이나 유선 전화 및 모임의 콘텐츠 부분을 통해 모임의 오디오 부분을 &mdash; &mdash; 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="7fb4c-107">COVID-19 발생과 관련하여 경험한 대로 모임이 많은 기간에는 PSTN 회의 번호 또는 <strong>전화 번호</strong>를 사용해 전화를 거는 대신 <strong>Teams 모임 참가</strong> 버튼을 눌러 모임에 참석하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="7fb4c-108">이러면 모임이 증가하여 PSTN 네트워크가 정체되는 시기에 오디오 품질을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7fb4c-109">COVID-19 발생 기간에는 PSTN 회의 번호 또는 **전화 번호**</strong>를 사용해 전화를 거는 대신 **Teams 모임 참가** 버튼을 눌러 모임에 참석하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="7fb4c-110">이는 주로 COVID-19의 영향을 받는 국가의 전화 통신 인프라의 혼잡 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="7fb4c-111">PSTN 통화를 피하면 오디오 품질이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="7fb4c-112">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="7fb4c-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="7fb4c-113">오디오에 휴대폰을 사용하여 모임 참가</span><span class="sxs-lookup"><span data-stu-id="7fb4c-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="7fb4c-114">**참가를** 클릭하여 모임에 참가한  다음 오디오 및 비디오 설정 선택 화면에서 전화 **오디오를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="7fb4c-115">여기에서 사용자는 모임 전화를 걸고 모임에 참가하거나 모임에 수동으로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![전화 오디오 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="7fb4c-117">**Teams 모임 전화 걸기**</span><span class="sxs-lookup"><span data-stu-id="7fb4c-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="7fb4c-118">오디오 **화면용 전화** 사용 화면에서 사용자가 자신의 전화 번호를 입력한 다음 통화를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fb4c-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="7fb4c-119">모임에서 사용자에게 전화를 걸고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-119">The meeting calls the user and joins them to the meeting.</span></span>

![오디오 화면용 전화 사용의 전화 번호 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="7fb4c-121">**수동으로 전화 접속**</span><span class="sxs-lookup"><span data-stu-id="7fb4c-121">**Dial in manually**</span></span>

<span data-ttu-id="7fb4c-122">참가하는 또 다른 방법은 모임에 직접 전화를 걸 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="7fb4c-123">오디오 **화면에서 전화** 접속을  수동으로 클릭하여 모임에 전화 접속하는 데 사용할 전화 번호 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![수동 전화 접속 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="7fb4c-125">모임 중에 오디오에 문제가 있는 경우 다시 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="7fb4c-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="7fb4c-126">사용자가 모임 중에 컴퓨터를 사용할 때 오디오 문제가 있는 경우 사용자는 오디오에 휴대폰을 사용하여 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="7fb4c-127">Teams는 오디오 또는 장치 문제가 발생하는 경우를 감지하고 전화 걸기 옵션을 표시하여 사용자가 자신의 휴대폰을 사용할 수 있도록 **리디렉션합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fb4c-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="7fb4c-128">다음은 Teams에서 마이크를 감지하지  못하면 표시되는 메시지 및 전화 걸기 옵션의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![전화 걸기 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="7fb4c-130">사용자가 전화 걸기 **기능을 다시** 클릭하면 오디오 화면용 **휴대폰이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="7fb4c-131">여기에서 전화 번호를 입력하고 Teams 모임 통화를 하여 모임에 참가하거나 모임에 수동으로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="7fb4c-132">전화 걸기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="7fb4c-132">Set up the Call me feature</span></span>

<span data-ttu-id="7fb4c-133">조직의 사용자에 대해 전화 걸기 기능을 사용하도록 설정하려면 다음을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="7fb4c-134">모임(모임 이끌이)을 예약하는 조직의 사용자가 오디오 회의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="7fb4c-135">자세한 내용은 [Teams에](set-up-audio-conferencing-in-teams.md) 대한 오디오 회의 설정 및 Teams에서 사용자의 오디오 회의 설정 [관리를 참조하세요.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7fb4c-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="7fb4c-136">사용자는 모임에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-136">Users can dial out from meetings.</span></span> <span data-ttu-id="7fb4c-137">자세한 내용은 Teams에서 사용자의 오디오 회의 설정 관리를 [참조하세요.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7fb4c-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="7fb4c-138">사용자가 활성화된 모임에서 전화 접속을 하지  않은 경우 전화 걸기 옵션을 사용할 수 없습니다. 사용자는 모임에 참가하기 위한 전화를 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="7fb4c-139">대신 오디오 화면의 사용 전화기에서 전화  번호 목록을 볼 수 있습니다. 이 목록은 전화기에서 모임에 수동으로 전화를 걸 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb4c-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
