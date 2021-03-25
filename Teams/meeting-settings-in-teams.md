---
title: 모임 설정 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 사용자가 조직에서 예약하는 모든 Teams 모임 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: a8fe3f0c2375e7322397fabfeb1d3f5456d7c55b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117896"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="99ca2-103">Microsoft Teams에서의 모임 설정 관리</span><span class="sxs-lookup"><span data-stu-id="99ca2-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="99ca2-104">관리자는 Teams 모임 설정을 사용하여 익명 사용자가 Teams 모임에 참여하고 모임 초대를 사용자 지정하고 QoS(서비스 품질)을 활성화하고 실시간 트래픽에 대한 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="99ca2-105">이 설정은 사용자가 조직에서 예약하는 모든 Teams 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="99ca2-106">Microsoft Teams 관리 센터의 **모임** > **모임 설정** 에서 이러한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="99ca2-107">익명 사용자가 모임에 참가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="99ca2-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="99ca2-108">익명 참가를 사용하면 누구나 모임 초대의 링크를 클릭하여 익명 사용자로 모임에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="99ca2-109">자세한 내용은 [Teams 계정 없이 모임에 참가](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="99ca2-110">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="99ca2-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="99ca2-111">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-111">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="99ca2-112">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-112">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="99ca2-113">관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-113">Go to the admin center.</span></span>

2. <span data-ttu-id="99ca2-114">왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-114">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="99ca2-115">**참가자** 아래에서 **익명 사용자가 모임에 참가할 수 있습니다** 를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-115">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="99ca2-116">![관리 센터에서 모임에 대한 참가자 설정의 스크린샷](media/meeting-settings-participants.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 참가자 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="99ca2-116">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="99ca2-117">익명 사용자가 조직의 사용자가 예약한 모임에 참여하지 못하게 하려면 이 설정을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-117">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a><span data-ttu-id="99ca2-118">익명 사용자가 모임에서 앱과 상호 작용할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="99ca2-118">Allow anonymous users to interact with apps in meetings</span></span>

<span data-ttu-id="99ca2-119">이제 익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-119">Anonymous users will now inherit the user-level global default permission policy.</span></span> <span data-ttu-id="99ca2-120">그러면 익명 사용자가 사용자 수준 사용 권한 정책에서 앱을 사용하도록 설정한 동안에는 익명 사용자가 Teams 모임에서 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-120">This control will then allow anonymous users to interact with apps in Teams meetings as long as the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="99ca2-121">익명 사용자는 모임에서 이미 사용 가능한 앱만 상호 작용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-121">Note that anonymous users can only interact with apps that are already available in a meeting and cannot acquire and/or manage these apps.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="99ca2-122">기본적으로 익명 사용자가 모임에서 앱과 상호 작용할 수 있도록 허용하는 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-122">By default, the setting to allow anonymous users to interact with apps in meetings is enabled.</span></span>

<span data-ttu-id="99ca2-123">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="99ca2-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="99ca2-124">이 설정에 액세스하려면 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-124">You must be a Teams service admin to access this setting.</span></span> <span data-ttu-id="99ca2-125">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-125">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="99ca2-126">관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-126">Go to the admin center.</span></span>

2. <span data-ttu-id="99ca2-127">왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-127">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="99ca2-128">**참가자** 에서 **익명 사용자가 모임의 앱과 상호 작용 가능** 에 대한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-128">Under **Participants**, the setting for **Anonymous users can interact with apps in meetings** can be changed.</span></span>

> [!CAUTION]
> <span data-ttu-id="99ca2-129">익명 사용자가 조직의 사용자가 예약한 모임에 앱과 상호 작용하지 못하게 하려면 이 설정을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-129">If you don't want anonymous users to interact with apps in meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="99ca2-130">모임 초대장의 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="99ca2-130">Customize meeting invitations</span></span>

<span data-ttu-id="99ca2-131">조직의 요구에 맞게 Teams 모임 초대장을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-131">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="99ca2-132">조직의 로고를 추가하고 지원 웹 사이트에 대한 링크와 법적 고지 사항 및 텍스트 전용 바닥글과 같은 유용한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-132">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="99ca2-133">모임 초대장에 대한 로고 만들기 팁</span><span class="sxs-lookup"><span data-stu-id="99ca2-133">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="99ca2-134">너비가 188픽셀, 높이가 30픽셀(상당히 작음) 이하인 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-134">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="99ca2-135">이미지를 JPG 또는 PNG 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-135">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="99ca2-136">초대장을 받은 모든 사용자가 액세스할 수 있는 위치(예: 공용 웹사이트)에 이미지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-136">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="99ca2-137">이제 이것을 모임 초대장에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-137">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="99ca2-138">다음 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-138">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="99ca2-139">모임 초대장의 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="99ca2-139">Customize your meeting invitations</span></span>

<span data-ttu-id="99ca2-140">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="99ca2-140">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="99ca2-141">관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-141">Go to the admin center.</span></span>
2. <span data-ttu-id="99ca2-142">왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-142">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="99ca2-143">**전자 메일 초대장** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-143">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="99ca2-144">![사용자 지정할 수 있는 모임 초대장 설정의 스크린샷](media/meeting-settings-invitation.png "Teams 모임에 대해 사용자 지정할 수 있는 모임 초대장 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="99ca2-144">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="99ca2-145">**로고 URL** 로고가 저장된 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-145">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="99ca2-146">**법률 정보 URL** 법률적인 우려에 대해 사용자의 방문을 원하는 법률 정보 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-146">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="99ca2-147">**도움말 URL** 사용자에게 문제가 발생했을 때 사용자의 방문을 원하는 지원 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-147">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="99ca2-148">**바닥글** 바닥글에 포함할 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-148">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="99ca2-149">**초대장 미리보기** 를 클릭하여 모임 초대장의 미리보기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-149">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="99ca2-150">모두 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-150">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="99ca2-151">변경 사항을 적용하려면 1시간 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-151">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="99ca2-152">그런 다음 Teams 모임을 예약하여 모임 초대장 모양을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-152">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="99ca2-153">Teams 모임에 대한 실시간 미디어 트래픽 처리 방법 설정</span><span class="sxs-lookup"><span data-stu-id="99ca2-153">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="99ca2-154"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="99ca2-154"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="99ca2-155">QoS(서비스 품질)를 사용하여 네트워크 트래픽의 우선 순위를 지정하는 경우 QoS 마커를 활성화하고 각 미디어 트래픽 유형에 대한 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-155">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="99ca2-156">다양한 트래픽 유형에 대한 포트 범위를 설정하는 것은 실시간 미디어를 처리하는 한 단계입니다. 자세한 내용은 [Teams의 QoS(서비스 품질)](qos-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-156">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99ca2-157">Teams 서비스에 대해 Microsoft Teams 관리 센터에서 QoS를 활성화하거나 설정을 변경하는 경우, Teams에서 QoS에 대한 변경 사항을 완전히 구현하려면 모든 네트워크 장치 및 [모든 사용자 장치에 일치하는 설정을 적용](QoS-in-Teams-clients.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-157">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="99ca2-158">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="99ca2-158">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="99ca2-159">관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-159">Go to the admin center.</span></span>
2. <span data-ttu-id="99ca2-160">왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-160">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="99ca2-161">**네트워크** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-161">Under **Network**, do the following:</span></span>

    <span data-ttu-id="99ca2-162">![관리 센터에서 모임에 대한 네트워크 설정의 스크린샷](media/meeting-settings-network.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 네트워크 설정의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="99ca2-162">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="99ca2-163">DSCP 마커를 QoS에 사용하려면 **실시간 미디어 트래픽에 대한 QoS(서비스 품질) 마커 삽입** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-163">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="99ca2-164">마커의 사용 옵션만 선택할 수 있습니다. 각 트래픽 유형에 대해 사용자 지정 마커를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-164">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="99ca2-165">DSCP 마커에 대한 자세한 내용은 [QoS 구현 방법 선택](QoS-in-Teams.md#select-a-qos-implementation-method)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-165">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="99ca2-166">DSCP 태그 지정은 일반적으로 원본 포트를 통해 수행되며 UDP 트래픽은 기본적으로 대상 포트가 3478인 전송 릴레이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-166">DSCP tagging is typically done via Source Ports and UDP traffic will route to Transport Relay with destination port of 3478 by default.</span></span> <span data-ttu-id="99ca2-167">회사에서 대상 포트에 태그를 지정해야 하는 경우 지원 팀에 문의하여 UDP 포트 3479(오디오), 3480(비디오) 및 3481(공유)가 있는 전송 릴레이로의 통신을 사용 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-167">If your company requires tagging on destination ports, please contact support to enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video), and 3481 (Sharing).</span></span>
    - <span data-ttu-id="99ca2-168">포트 범위를 지정하려면 **각 유형의 실시간 미디어 트래픽에 대한 포트 범위 선택** 옆에 있는 **포트 범위 지정** 을 선택한 다음 오디오, 비디오 및 화면 공유를 위한 시작 및 종료 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-168">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="99ca2-169">QoS를 구현하려면 이 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-169">Selecting this option is required to implement QoS.</span></span> 
        > [!Note]
        > <span data-ttu-id="99ca2-170">**실시간 트래픽에 대한 QoS(서비스 품질) 표식** 이 켜져 있는 경우 포트 설정을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-170">If **Quality of Service (QoS) markers for real-time media traffic** is on, then you have to manage your port settings.</span></span> <span data-ttu-id="99ca2-171">포트 설정은 자동으로 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-171">They aren't managed automatically.</span></span>
        
        > [!IMPORTANT]
        > <span data-ttu-id="99ca2-172">**사용 가능한 포트 자동 사용** 을 선택하면 1024에서 65535 사이의 사용 가능한 포트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-172">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="99ca2-173">QoS를 구현하지 않는 경우에만 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-173">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="99ca2-174">포트 범위를 너무 좁게 선택하면 통화 손실이 발생하고 통화 품질이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-174">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="99ca2-175">아래의 권장 사항이 최소 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-175">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="99ca2-176">사용자 환경에서 어떤 포트 범위를 사용해야 하는지 잘 모르는 경우 다음 설정을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-176">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="99ca2-177">자세한 내용은 [Microsoft Teams에서 QoS(서비스 품질) 구현](QoS-in-Teams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ca2-177">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="99ca2-178">이는 필수 DSCP 마킹 및 Teams와 ExpressRoute에서 사용하는 해당 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-178">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="99ca2-179">포트 범위 및 DSCP 마킹</span><span class="sxs-lookup"><span data-stu-id="99ca2-179">Port ranges and DSCP markings</span></span>

<span data-ttu-id="99ca2-180">미디어 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="99ca2-180">Media traffic type</span></span>| <span data-ttu-id="99ca2-181">클라이언트 원본 포트 범위 \*</span><span class="sxs-lookup"><span data-stu-id="99ca2-181">Client source port range \*</span></span> |<span data-ttu-id="99ca2-182">프로토콜</span><span class="sxs-lookup"><span data-stu-id="99ca2-182">Protocol</span></span>|<span data-ttu-id="99ca2-183">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="99ca2-183">DSCP value</span></span>|<span data-ttu-id="99ca2-184">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="99ca2-184">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="99ca2-185">오디오</span><span class="sxs-lookup"><span data-stu-id="99ca2-185">Audio</span></span>            | <span data-ttu-id="99ca2-186">50,000~50,019</span><span class="sxs-lookup"><span data-stu-id="99ca2-186">50,000–50,019</span></span>               |<span data-ttu-id="99ca2-187">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="99ca2-187">TCP/UDP</span></span> |<span data-ttu-id="99ca2-188">46</span><span class="sxs-lookup"><span data-stu-id="99ca2-188">46</span></span>        |<span data-ttu-id="99ca2-189">Expedited Forwarding(EF)</span><span class="sxs-lookup"><span data-stu-id="99ca2-189">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="99ca2-190">비디오</span><span class="sxs-lookup"><span data-stu-id="99ca2-190">Video</span></span>            | <span data-ttu-id="99ca2-191">50,020~50,039</span><span class="sxs-lookup"><span data-stu-id="99ca2-191">50,020–50,039</span></span>               |<span data-ttu-id="99ca2-192">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="99ca2-192">TCP/UDP</span></span> |<span data-ttu-id="99ca2-193">34</span><span class="sxs-lookup"><span data-stu-id="99ca2-193">34</span></span>        |<span data-ttu-id="99ca2-194">Assured Forwarding(AF41)</span><span class="sxs-lookup"><span data-stu-id="99ca2-194">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="99ca2-195">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="99ca2-195">Application/Screen Sharing</span></span>| <span data-ttu-id="99ca2-196">50,040~50,059</span><span class="sxs-lookup"><span data-stu-id="99ca2-196">50,040–50,059</span></span>      |<span data-ttu-id="99ca2-197">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="99ca2-197">TCP/UDP</span></span> |<span data-ttu-id="99ca2-198">18</span><span class="sxs-lookup"><span data-stu-id="99ca2-198">18</span></span>        |<span data-ttu-id="99ca2-199">Assured Forwarding(AF21)</span><span class="sxs-lookup"><span data-stu-id="99ca2-199">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="99ca2-200">\* 할당하는 포트 범위는 겹칠 수 없으며 서로 근접해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-200">\* The port ranges you assign can't overlap and should be adjacent to each other.</span></span>

<span data-ttu-id="99ca2-201">QoS를 한동안 사용하고 나면 이 세 가지 작업 각각의 수요에 대한 사용량 정보가 제공되며 특정 요구에 따라 변경할 사항을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-201">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="99ca2-202">[통화 품질 대시보드](turning-on-and-using-call-quality-dashboard.md)가 여기에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ca2-202">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>