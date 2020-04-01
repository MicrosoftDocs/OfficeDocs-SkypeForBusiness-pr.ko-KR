---
title: 사용자의 전화 받기 기능 설정
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 사용자가 오디오에 대 한 컴퓨터를 사용할 수 없는 경우에 휴대폰으로 오디오 부분에 참가할 수 있도록 팀에서 전화 걸기 기능을 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cee6937a1bdc2bef6d2184066cb32a4aa94d8e6
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096853"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="698fe-103">사용자의 전화 받기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="698fe-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="698fe-104">Microsoft 팀에서 전화 **걸기** 기능을 통해 사용자는 휴대폰으로 모임의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="698fe-105">이 방법은 오디오를 사용 하는 것이 불가능할 수 있는 시나리오에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="698fe-106">사용자는 휴대폰 또는 육지 모임의 오디오 부분을 받고 다른 모임 참가자가 화면을 공유 하거나 컴퓨터를 통해 비디오&mdash;&mdash;를 재생할 때 모임의 콘텐츠 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="698fe-107">COVID가 발생 하는 동안 사용자는 PSTN 컨퍼런스 번호를 사용 하거나 **전화**</strong>를 사용 하 여 전화를 걸고 있지 않고 **팀 모임 참가** 단추를 클릭 하 여 모임에 참가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-107">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="698fe-108">이는 주로 COVID-19의 영향을 받는 국가 전화 통신 인프라의 정체 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-108">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="698fe-109">PSTN 통화를 방지 하 여 더 나은 음질을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-109">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="698fe-110">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="698fe-110">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="698fe-111">오디오 용 전화를 사용 하 여 모임 참가</span><span class="sxs-lookup"><span data-stu-id="698fe-111">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="698fe-112">**참가** 를 클릭 하 여 모임에 참가 한 다음 **오디오 및 비디오 설정 선택** 화면에서 **전화 오디오** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-112">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="698fe-113">여기서는 사용자가 모임 통화를 진행 하 고 참가 하거나 수동으로 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-113">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![전화 오디오 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="698fe-115">**팀 모임 통화 허용**</span><span class="sxs-lookup"><span data-stu-id="698fe-115">**Let the Teams meeting call**</span></span>

<span data-ttu-id="698fe-116">**오디오 용 전화 사용** 화면에서 사용자가 전화 번호를 입력 한 **다음 전화를 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="698fe-116">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="698fe-117">모임이 사용자에 게 전화를 걸고 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-117">The meeting calls the user and joins them to the meeting.</span></span>

![오디오 사용 화면의 전화 걸기 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="698fe-119">**수동으로 전화 접속**</span><span class="sxs-lookup"><span data-stu-id="698fe-119">**Dial in manually**</span></span>

<span data-ttu-id="698fe-120">참가 하는 또 다른 방법은 모임에 직접 전화 접속 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-120">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="698fe-121">**오디오 용 전화 사용** 화면에서 **수동으로 전화 접속** 을 클릭 하 여 모임에 전화를 걸 때 사용할 전화 번호 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-121">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![수동으로 전화 접속 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="698fe-123">모임 중 오디오에 문제가 있는 경우 다시 전화 받기</span><span class="sxs-lookup"><span data-stu-id="698fe-123">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="698fe-124">사용자가 모임 중에 컴퓨터를 사용할 때 오디오 문제가 발생 하는 경우 사용자는 오디오를 사용 하 여 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-124">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="698fe-125">팀은 오디오 또는 장치 문제가 발생 하는 경우를 감지 하 고 사용자에 게 **콜백 옵션을** 표시 하 여 전화를 사용 하도록 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-125">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="698fe-126">다음은 팀에서 마이크를 감지 하지 못하는 경우 표시 되는 메시지 및 **콜백 옵션의** 예입니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-126">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![콜백 옵션 스크린샷](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="698fe-128">사용자가 **오디오를 사용** 하는 것을 전화 걸기 화면을 표시 하는 **me 뒤로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-128">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="698fe-129">여기서는 전화 번호를 입력 하 고 팀이 통화를 하 여 모임에 참가 하거나 수동으로 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-129">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="698fe-130">전화 걸기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="698fe-130">Set up the Call me feature</span></span>

<span data-ttu-id="698fe-131">조직의 사용자에 게 전화 걸기 기능을 사용 하도록 설정 하려면 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-131">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="698fe-132">모임을 예약 하는 조직의 사용자 (모임 이끌이)는 오디오 회의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-132">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="698fe-133">자세한 내용은 팀 [에 대 한 오디오 회의 설정](set-up-audio-conferencing-in-teams.md) 및 [팀에서 사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="698fe-133">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="698fe-134">사용자가 모임에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-134">Users can dial out from meetings.</span></span> <span data-ttu-id="698fe-135">자세히 알아보려면 [팀에서 사용자에 대 한 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="698fe-135">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="698fe-136">사용자가 모임에서 전화를 걸지 않은 경우 **call me** 옵션을 사용할 수 없으며 사용자가 모임에 참가 하는 전화를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-136">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="698fe-137">대신 사용자는 휴대폰에서 직접 전화 접속 하는 데 사용할 수 있는 **오디오 사용** 화면의 전화 번호 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="698fe-137">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
