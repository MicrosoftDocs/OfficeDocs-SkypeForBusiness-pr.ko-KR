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
description: 사용자가 조직에서 예약하는 모든 Teams 모임 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 761504400639c8ed53c617f6c816dd7c4703a530
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489140"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="7b90c-103">Microsoft Teams에서의 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="7b90c-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="7b90c-104">관리자는 Teams 모임 설정을 사용하여 익명 사용자가 Teams 모임에 참여하고 모임 초대를 사용자 지정하고 QoS(서비스 품질)을 활성화하고 실시간 트래픽에 대한 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="7b90c-105">이 설정은 사용자가 조직에서 예약하는 모든 Teams 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="7b90c-106">Microsoft Teams 관리 센터의 **모임** > **모임 설정**에서 이러한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="7b90c-107">익명 사용자가 모임에 참가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="7b90c-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="7b90c-108">익명 참가를 사용하면 누구나 모임 초대의 링크를 클릭하여 익명 사용자로 모임에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="7b90c-109">자세한 내용은 [Teams 계정 없이 모임에 참가](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b90c-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="7b90c-110">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="7b90c-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7b90c-111">관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a>.</span></span>

2. <span data-ttu-id="7b90c-112">왼쪽 탐색 모음에서 **모임** > **모임 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-112">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="7b90c-113">**참가자** 아래에서 **익명 사용자가 모임에 참가할 수 있습니다**를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-113">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="7b90c-114">![관리 센터에서 모임에 대한 참가자 설정의 스크린샷](media/meeting-settings-participants.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 참가자 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="7b90c-114">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="7b90c-115">익명 사용자가 조직의 사용자가 예약한 모임에 참여하지 못하게 하려면 이 설정을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-115">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="7b90c-116">모임 초대장의 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7b90c-116">Customize meeting invitations</span></span>

<span data-ttu-id="7b90c-117">조직의 요구에 맞게 Teams 모임 초대장을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-117">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="7b90c-118">조직의 로고를 추가하고 지원 웹 사이트에 대한 링크와 법적 고지 사항 및 텍스트 전용 바닥글과 같은 유용한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-118">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="7b90c-119">모임 초대장에 대한 로고 만들기 팁</span><span class="sxs-lookup"><span data-stu-id="7b90c-119">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="7b90c-120">너비가 188픽셀, 높이가 30픽셀(상당히 작음) 이하인 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-120">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="7b90c-121">이미지를 JPG 또는 PNG 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-121">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="7b90c-122">초대장을 받은 모든 사용자가 액세스할 수 있는 위치(예: 공용 웹사이트)에 이미지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-122">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="7b90c-123">이제 이것을 모임 초대장에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-123">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="7b90c-124">다음 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b90c-124">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="7b90c-125">모임 초대장의 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7b90c-125">Customize your meeting invitations</span></span>

<span data-ttu-id="7b90c-126">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="7b90c-126">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7b90c-127"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>..</span></span>
2. <span data-ttu-id="7b90c-128">왼쪽 탐색 모음에서 **모임** > **모임 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-128">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="7b90c-129">**전자 메일 초대장**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-129">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="7b90c-130">![사용자 지정할 수 있는 모임 초대장 설정의 스크린샷](media/meeting-settings-invitation.png "Teams 모임에 대해 사용자 지정할 수 있는 모임 초대장 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="7b90c-130">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="7b90c-131">**로고 URL** 로고가 저장된 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-131">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="7b90c-132">**법률 정보 URL** 법률적인 우려에 대해 사용자의 방문을 원하는 법률 정보 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-132">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="7b90c-133">**도움말 URL** 사용자에게 문제가 발생했을 때 사용자의 방문을 원하는 지원 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-133">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="7b90c-134">**바닥글** 바닥글에 포함할 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-134">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="7b90c-135">**초대장 미리보기**를 클릭하여 모임 초대장의 미리보기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-135">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="7b90c-136">모두 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-136">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="7b90c-137">변경 사항을 적용하려면 1시간 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-137">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="7b90c-138">그런 다음 Teams 모임을 예약하여 모임 초대장 모양을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-138">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="7b90c-139">Teams 모임에 대한 실시간 미디어 트래픽 처리 방법 설정</span><span class="sxs-lookup"><span data-stu-id="7b90c-139">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="7b90c-140"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="7b90c-140"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="7b90c-141">[QoS](qos-in-teams.md)(서비스 품질)를 사용하여 네트워크 트래픽의 우선 순위를 지정하는 경우 QoS 마커를 활성화하고 각 미디어 트래픽 유형에 대한 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-141">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> <span data-ttu-id="7b90c-142">다양한 트래픽 유형에 대한 포트 범위를 설정하는 것은 실시간 미디어를 처리하는 한 단계입니다. 자세한 내용은 [Teams의 QoS(서비스 품질)](qos-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b90c-142">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b90c-143">Microsoft Teams 서비스에 대해 Microsoft Teams 관리 센터에서 QoS를 활성화하거나 설정을 변경하는 경우, Teams에서 QoS에 대한 변경 사항을 완전히 구현하려면 모든 네트워크 장치 및 [모든 사용자 장치에 일치하는 설정을 적용](QoS-in-Teams-clients.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-143">If you enable QoS or change settings in the Microsoft Teams admin center for the Microsoft Teams service, you will also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="7b90c-144">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="7b90c-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="7b90c-145"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-145">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>
2. <span data-ttu-id="7b90c-146">왼쪽 탐색 모음에서 **모임** > **모임 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-146">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="7b90c-147">**네트워크**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-147">Under **Network**, do the following:</span></span>

    <span data-ttu-id="7b90c-148">![관리 센터에서 모임에 대한 네트워크 설정의 스크린샷](media/meeting-settings-network.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 네트워크 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="7b90c-148">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="7b90c-149">DSCP 마커를 QoS에 사용하려면 **실시간 미디어 트래픽에 대한 QoS(서비스 품질) 마커 삽입**을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-149">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="7b90c-150">마커의 사용 옵션만 선택할 수 있습니다. 각 트래픽 유형에 대해 사용자 지정 마커를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-150">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="7b90c-151">DSCP 마커에 대한 자세한 내용은 [QoS 구현 방법 선택](QoS-in-Teams.md#select-a-qos-implementation-method)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b90c-151">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="7b90c-152">**실시간 미디어 트래픽에 대한 QoS(서비스 품질) 마커 삽입**을 켜면 UDP 포트 3479(오디오), 3480(비디오) 및 3481(공유)을 사용하여 전송 릴레이와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-152">Turning on **Insert Quality of Service (QoS) markers for real-time media traffic** will also enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video) and 3481 (Sharing).</span></span>
    - <span data-ttu-id="7b90c-153">포트 범위를 지정하려면 **각 유형의 실시간 미디어 트래픽에 대한 포트 범위 선택** 옆에 있는 **포트 범위 지정**을 선택한 다음 오디오, 비디오 및 화면 공유를 위한 시작 및 종료 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-153">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="7b90c-154">QoS를 구현하려면 이 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-154">Selecting this option is required to implement QoS.</span></span>
        > [!IMPORTANT]
        > <span data-ttu-id="7b90c-155">**사용 가능한 포트 자동 사용**을 선택하면 1024에서 65535 사이의 사용 가능한 포트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-155">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="7b90c-156">QoS를 구현하지 않는 경우에만 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-156">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="7b90c-157">포트 범위를 너무 좁게 선택하면 통화 손실이 발생하고 통화 품질이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-157">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="7b90c-158">아래의 권장 사항이 최소 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-158">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="7b90c-159">사용자 환경에서 어떤 포트 범위를 사용해야 하는지 잘 모르는 경우 다음 설정을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-159">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="7b90c-160">자세한 내용은 [Microsoft Teams에서 QoS(서비스 품질) 구현](QoS-in-Teams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b90c-160">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="7b90c-161">이는 필수 DSCP 마킹 및 Teams와 ExpressRoute에서 사용하는 해당 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-161">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="7b90c-162">포트 범위 및 DSCP 마킹</span><span class="sxs-lookup"><span data-stu-id="7b90c-162">Port ranges and DSCP markings</span></span>

<span data-ttu-id="7b90c-163">미디어 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="7b90c-163">Media traffic type</span></span>| <span data-ttu-id="7b90c-164">클라이언트 원본 포트 범위 \*</span><span class="sxs-lookup"><span data-stu-id="7b90c-164">Client source port range \*</span></span> |<span data-ttu-id="7b90c-165">프로토콜</span><span class="sxs-lookup"><span data-stu-id="7b90c-165">Protocol</span></span>|<span data-ttu-id="7b90c-166">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="7b90c-166">DSCP value</span></span>|<span data-ttu-id="7b90c-167">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="7b90c-167">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="7b90c-168">오디오</span><span class="sxs-lookup"><span data-stu-id="7b90c-168">Audio</span></span>            | <span data-ttu-id="7b90c-169">50,000~50,019</span><span class="sxs-lookup"><span data-stu-id="7b90c-169">50,000–50,019</span></span>               |<span data-ttu-id="7b90c-170">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7b90c-170">TCP/UDP</span></span> |<span data-ttu-id="7b90c-171">46</span><span class="sxs-lookup"><span data-stu-id="7b90c-171">46</span></span>        |<span data-ttu-id="7b90c-172">Expedited Forwarding(EF)</span><span class="sxs-lookup"><span data-stu-id="7b90c-172">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="7b90c-173">비디오</span><span class="sxs-lookup"><span data-stu-id="7b90c-173">Video</span></span>            | <span data-ttu-id="7b90c-174">50,020~50,039</span><span class="sxs-lookup"><span data-stu-id="7b90c-174">50,020–50,039</span></span>               |<span data-ttu-id="7b90c-175">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7b90c-175">TCP/UDP</span></span> |<span data-ttu-id="7b90c-176">34</span><span class="sxs-lookup"><span data-stu-id="7b90c-176">34</span></span>        |<span data-ttu-id="7b90c-177">Assured Forwarding(AF41)</span><span class="sxs-lookup"><span data-stu-id="7b90c-177">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="7b90c-178">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="7b90c-178">Application/Screen Sharing</span></span>| <span data-ttu-id="7b90c-179">50,040~50,059</span><span class="sxs-lookup"><span data-stu-id="7b90c-179">50,040–50,059</span></span>      |<span data-ttu-id="7b90c-180">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7b90c-180">TCP/UDP</span></span> |<span data-ttu-id="7b90c-181">awg</span><span class="sxs-lookup"><span data-stu-id="7b90c-181">18</span></span>        |<span data-ttu-id="7b90c-182">Assured Forwarding(AF21)</span><span class="sxs-lookup"><span data-stu-id="7b90c-182">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="7b90c-183">\* 할당하는 포트 범위는 겹칠 수 없으며 서로 근접해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-183">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="7b90c-184">QoS를 한동안 사용하고 나면 이 세 가지 작업 각각의 수요에 대한 사용량 정보가 제공되며 특정 요구에 따라 변경할 사항을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-184">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="7b90c-185">[통화 품질 대시보드](turning-on-and-using-call-quality-dashboard.md)가 여기에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b90c-185">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
