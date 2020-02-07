---
title: 모임 설정 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 사용자가 조직에서 예약한 팀 모임에 대 한 설정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bed367c9c40bb7124235abf204bbfa0395859685
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836468"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="66898-103">Microsoft 팀에서 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="66898-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="66898-104">관리자는 팀 모임 설정을 사용 하 여 익명 사용자가 팀 모임에 참가 하 고, 모임 초대를 사용자 지정 하 고, 서비스 품질 (QoS)을 사용할 수 있는지 여부를 제어 하 고, 실시간 트래픽에 대 한 포트 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="66898-105">이러한 설정은 사용자가 조직에서 예약 하는 모든 팀 모임에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66898-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="66898-106">Microsoft 팀 관리 센터의 **모임** > **모임 설정** 에서 이러한 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="66898-107">익명 사용자가 모임에 참가할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="66898-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="66898-108">익명 참가를 사용 하면 모든 사용자가 모임 초대의 링크를 클릭 하 여 익명 사용자로 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="66898-109">자세히 알아보려면 [팀 계정 없이 모임 참가](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="66898-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>


<span data-ttu-id="66898-110">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="66898-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66898-111">왼쪽 탐색 창에서 **모임** > **모임 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-111">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="66898-112">**참가자**에서 **익명 사용자가 모임에 참가할 수 있도록**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-112">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="66898-113">![관리 센터의 모임 참가자 설정 스크린샷](media/meeting-settings-participants.png "Microsoft 팀 관리 센터의 팀 모임에 대 한 참가자 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="66898-113">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="66898-114">익명 사용자가 조직의 사용자가 예약한 모임에 참가 하는 것을 원하지 않는다면이 설정을 끄세요.</span><span class="sxs-lookup"><span data-stu-id="66898-114">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="66898-115">모임 초대의 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="66898-115">Customize meeting invitations</span></span>

<span data-ttu-id="66898-116">조직의 요구 사항에 맞게 팀 모임 초대를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-116">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="66898-117">조직의 로고를 추가 하 고, 지원 웹사이트 링크, 법적 고 지 사항, 텍스트 전용 바닥글 등의 유용한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-117">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="66898-118">모임 초대에 대 한 로고 만들기 팁</span><span class="sxs-lookup"><span data-stu-id="66898-118">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="66898-119">너비가 188 픽셀을 초과 하지 않는 이미지를 만들 수 있습니다 (크기는 매우 작아서 약 30 픽셀).</span><span class="sxs-lookup"><span data-stu-id="66898-119">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="66898-120">이미지를 JPG 또는 PNG 형식으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-120">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="66898-121">초대를 받는 모든 사람이 액세스할 수 있는 위치 (예: 공용 웹 사이트)에 이미지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-121">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="66898-122">이제 모임 초대에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-122">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="66898-123">다음 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66898-123">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="66898-124">모임 초대 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="66898-124">Customize your meeting invitations</span></span>

<span data-ttu-id="66898-125">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="66898-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66898-126">왼쪽 탐색 창에서 **모임** > **모임 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-126">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="66898-127">**전자 메일 초대장**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-127">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="66898-128">![사용자 지정할 수 있는 모임 초대 설정의 스크린샷](media/meeting-settings-invitation.png "팀 모임에 대해 사용자 지정할 수 있는 모임 초대 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="66898-128">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="66898-129">**로고 URL** 로고가 저장 된 위치에 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-129">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="66898-130">**올바른 URL** 조직에 다른 사용자가 관심을 가질 수 있도록 법률 웹 사이트가 있는 경우 여기에 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-130">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="66898-131">**도움말 URL** 조직에 문제가 발생 하는 경우 사용자에 게 보낼 지원 웹 사이트가 있는 경우 여기에 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-131">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="66898-132">**바닥글** 바닥글로 포함할 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-132">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="66898-133">변경 내용이 전파 되는 시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="66898-133">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="66898-134">그런 다음 팀 회의 일정을 계획 하 여 모임 초대의 모양을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-134">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="66898-135">팀 모임에 대 한 실시간 미디어 트래픽을 처리 하는 방법을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-135">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="66898-136"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="66898-136"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="66898-137">[Qos (](qos-in-teams.md) 서비스 품질)를 사용 하 여 네트워크 트래픽의 우선 순위를 지정 하는 경우 qos 마커를 사용 하도록 설정 하 고 각 미디어 트래픽 유형에 대해 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-137">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> <span data-ttu-id="66898-138">여러 트래픽 유형에 대해 포트 범위를 설정 하는 것은 실시간 미디어를 처리 하는 단계 중 하나입니다. [팀에서 QoS (서비스 품질)](qos-in-teams.md) 를 자세히 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="66898-138">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66898-139">Microsoft 팀 서비스에 대 한 Microsoft 팀 관리 센터에서 QoS를 사용 하거나 설정을 변경 하는 경우 팀에서 QoS에 대 한 변경 내용을 완벽 하 게 구현 하려면 [모든 사용자 장치](QoS-in-Teams-clients.md) 및 모든 내부 네트워크 장치에 일치 하는 설정을 적용 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-139">If you enable QoS or change settings in the Microsoft Teams admin center for the Microsoft Teams service, you will also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="66898-140">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="66898-140">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66898-141">왼쪽 탐색 창에서 **모임** > **모임 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-141">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="66898-142">**네트워크**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-142">Under **Network**, do the following:</span></span>

    <span data-ttu-id="66898-143">![관리 센터의 모임에 대 한 네트워크 설정 스크린샷](media/meeting-settings-network.png "Microsoft 팀 관리 센터의 팀 모임에 대 한 네트워크 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="66898-143">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="66898-144">QoS에 DSCP 표시를 사용 하는 것을 허용 하려면 **실시간 미디어 트래픽에 qos (서비스 품질) 마커를 삽입**하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-144">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="66898-145">마커를 사용 하는 옵션만 사용할 수 있습니다. 각 트래픽 유형에 대해 사용자 지정 표식을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-145">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="66898-146">DSCP 마커에 대 한 자세한 내용은 [QoS 구현 방법 선택을](QoS-in-Teams.md#select-a-qos-implementation-method) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66898-146">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    > [!NOTE] 
    > <span data-ttu-id="66898-147">**실시간 미디어 트래픽에 대 한 QoS (서비스 품질) 마커** 를 설정 하면 UDP 포트 3479 (오디오), 3480 (비디오) 및 3481 (공유)로 전송 릴레이와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-147">Turning on **Insert Quality of Service (QoS) markers for real-time media traffic** will also enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video) and 3481 (Sharing).</span></span>
    - <span data-ttu-id="66898-148">포트 범위를 지정 하려면 **각 실시간 미디어 트래픽 형식에 대 한 포트 범위 선택**옆의 **포트 범위 지정**을 선택한 다음 오디오, 비디오 및 화면 공유를 위한 시작 및 종료 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-148">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="66898-149">QoS를 구현 하려면이 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-149">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="66898-150">**사용 가능한 포트를 자동으로 사용**을 선택 하는 경우 1024 및 65535 사이의 사용 가능한 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-150">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="66898-151">QoS를 구현 하지 않는 경우에만이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-151">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="66898-152">너무 좁은 포트 범위를 선택 하면 통화 손실이 발생 하 고 통화 품질이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-152">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="66898-153">아래 권장 사항은 최소가입니다.</span><span class="sxs-lookup"><span data-stu-id="66898-153">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="66898-154">환경에서 사용할 포트 범위가 확실 하지 않은 경우 다음 설정을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-154">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="66898-155">자세한 내용은 [Microsoft 팀에서 QoS (서비스 품질) 구현을](QoS-in-Teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66898-155">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="66898-156">이는 필요한 DSCP 표식 및 제안 된 적절 한 미디어 포트 범위를 팀과 Express에서 모두 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66898-156">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="66898-157">_포트 범위 및 DSCP 표식_</span><span class="sxs-lookup"><span data-stu-id="66898-157">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="66898-158">미디어 트래픽 형식</span><span class="sxs-lookup"><span data-stu-id="66898-158">Media traffic type</span></span>| <span data-ttu-id="66898-159">클라이언트 원본 포트 범위\*</span><span class="sxs-lookup"><span data-stu-id="66898-159">Client source port range \*</span></span> |<span data-ttu-id="66898-160">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="66898-160">Protocol</span></span>|<span data-ttu-id="66898-161">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="66898-161">DSCP value</span></span>|<span data-ttu-id="66898-162">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="66898-162">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="66898-163">오디오</span><span class="sxs-lookup"><span data-stu-id="66898-163">Audio</span></span>            | <span data-ttu-id="66898-164">50000 – 50019</span><span class="sxs-lookup"><span data-stu-id="66898-164">50,000–50,019</span></span>               |<span data-ttu-id="66898-165">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="66898-165">TCP/UDP</span></span> |<span data-ttu-id="66898-166">46</span><span class="sxs-lookup"><span data-stu-id="66898-166">46</span></span>        |<span data-ttu-id="66898-167">전달 발송 (EF)</span><span class="sxs-lookup"><span data-stu-id="66898-167">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="66898-168">비디오만</span><span class="sxs-lookup"><span data-stu-id="66898-168">Video</span></span>            | <span data-ttu-id="66898-169">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="66898-169">50,020–50,039</span></span>               |<span data-ttu-id="66898-170">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="66898-170">TCP/UDP</span></span> |<span data-ttu-id="66898-171">34</span><span class="sxs-lookup"><span data-stu-id="66898-171">34</span></span>        |<span data-ttu-id="66898-172">전달 보장 (AF41)</span><span class="sxs-lookup"><span data-stu-id="66898-172">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="66898-173">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="66898-173">Application/Screen Sharing</span></span>| <span data-ttu-id="66898-174">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="66898-174">50,040–50,059</span></span>      |<span data-ttu-id="66898-175">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="66898-175">TCP/UDP</span></span> |<span data-ttu-id="66898-176">awg</span><span class="sxs-lookup"><span data-stu-id="66898-176">18</span></span>        |<span data-ttu-id="66898-177">전달 보장 (AF21)</span><span class="sxs-lookup"><span data-stu-id="66898-177">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="66898-178">\*지정 하는 포트 범위는 겹칠 수 없으며 서로 옆에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66898-178">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="66898-179">특정 기간 동안 QoS를 사용 하는 경우에는 이러한 세 가지 작업 부하 각각에 대 한 사용 정보가 필요 하며, 사용자는 해당 요구 사항에 따라 변경할 내용을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66898-179">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="66898-180">[통화 음질 대시보드가](turning-on-and-using-call-quality-dashboard.md) 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66898-180">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
