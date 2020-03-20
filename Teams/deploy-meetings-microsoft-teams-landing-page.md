---
title: Microsoft Teams에서의 모임 및 회의
ms.reviewer: ''
description: 다음 배포 리소스를 사용하여 Microsoft Temas에서 모임을 배포하는 데 도움을 줄 수 있습니다.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00dab47ce695d542dcd9b7a30a1b289d0a804dea
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858603"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a><span data-ttu-id="9aa7f-103">Microsoft Teams에서의 모임 및 회의</span><span class="sxs-lookup"><span data-stu-id="9aa7f-103">Meetings and conferencing in Microsoft Teams</span></span>

<span data-ttu-id="9aa7f-104">[시작](get-started-with-teams-quick-start.md)을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9aa7f-105">조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9aa7f-106">이제 [오디오 회의](deploy-audio-conferencing-teams-landing-page.md), 비디오 및 공유를 포함한 모임 작업을 추가할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-106">Now you're ready to add the meetings workload, including [audio conferencing](deploy-audio-conferencing-teams-landing-page.md), video, and sharing.</span></span> <span data-ttu-id="9aa7f-107">이 문서에서는 모임 및 오디오 회의의 배포를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-107">This article walks you through the rollout of meetings and audio conferencing.</span></span> <span data-ttu-id="9aa7f-108">팀 모임, 회의 및 장치 비디오 (3:28 분)를 보고 시작해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-108">Start by watching our Teams meetings, conferencing, and devices video (3:28 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

<span data-ttu-id="9aa7f-109">*2019년 11월의 새로운 기능*: 이제 [Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams를 배포하는 데 도움을 받을 수 있습니다](use-advisor-teams-roll-out.md).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-109">*New in November 2019*: You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span> <span data-ttu-id="9aa7f-110">Advisor for Teams(미리 보기)는 모임 및 회의를 포함하여 Teams의 배포 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-110">Advisor for Teams (preview) walks you through your Teams rollout, including meetings and conferencing.</span></span> <span data-ttu-id="9aa7f-111">Advisor for Teams(미리 보기)는 Office 365 환경을 평가하고 Teams에서 모임 및 회의를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-111">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out meetings and conferencing in Teams.</span></span>


## <a name="meetings-and-conferencing-deployment-decisions"></a><span data-ttu-id="9aa7f-112">모임 및 회의 배포 결정</span><span class="sxs-lookup"><span data-stu-id="9aa7f-112">Meetings and conferencing deployment decisions</span></span>

<span data-ttu-id="9aa7f-113">Teams는 조직을 위해 즉시 사용 가능한 뛰어난 경험을 제공하고 대부분의 조직에 그 기본 설정이 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-113">Teams provides a great out-of-the-box experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="9aa7f-114">이 문서에서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 설정을 변경할지 여부를 결정 하는데 도움을 주고 각 변경 내용에 대해 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-114">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="9aa7f-115">당사는 사용자가 [변경할 가능성이 큰](#core-deployment-decisions) 변경 내용의 핵심 집합에서 시작하여 설정을 두 그룹으로 나누었습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-115">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="9aa7f-116">두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-116">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

> [!Tip]
> <span data-ttu-id="9aa7f-117">모임에 대한 자세한 내용은 다음 세션을 참고 하세요. [IT 전문가를 위한 Microsoft Teams의 모임 소개](https://aka.ms/teams-meetings-intro)</span><span class="sxs-lookup"><span data-stu-id="9aa7f-117">Watch the following session to learn more about Meetings: [Introduction to Meetings in Microsoft Teams for IT Pros](https://aka.ms/teams-meetings-intro)</span></span>


## <a name="meetings-and-conferencing-prerequisites"></a><span data-ttu-id="9aa7f-118">모임 및 회의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9aa7f-118">Meetings and conferencing prerequisites</span></span> 

<span data-ttu-id="9aa7f-119">조직 전체에서 모임 배포를 확장하기 전에 시간을 내어 사용자에게 최상의 경험을 제공할 준비가 되었는지 검토하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-119">Before scaling your meetings deployment across your organization, take time to review and confirm that your environment is ready to provide users with the best possible experience.</span></span> <span data-ttu-id="9aa7f-120">다음의 정보를 검토하고 필요에 따라 환경을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-120">Review the following information and make any required changes to your environment as needed.</span></span>

<span data-ttu-id="9aa7f-121">Teams에서 최상의 경험을 얻으려면 조직이 *Exchange Online 및 SharePoint Online*을 보유하고 사용자는 검증된 O365용 도메인을 보유해야 합니다(예: contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-121">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online, and you must have a verified domain for O365 such as *contoso.com*.</span></span>

<span data-ttu-id="9aa7f-122">조직 전체에서 모임을 확장하려면 모든 사용자가 인터넷에 연결하여 Office 365 서비스에 연결할 수 있도록 해야합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-122">To scale meetings across your organization you should ensure that all user locations have internet access to connect to the Office 365 Services.</span></span> <span data-ttu-id="9aa7f-123">최소한 사용자의 위치에서 다음과 같은 일반 포트가 인터넷에 열려 있는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-123">At a minimum you should make sure that the following common ports are open to the internet from your user's locations:-</span></span>

- <span data-ttu-id="9aa7f-124">Teams를 사용하는 클라이언트가 발신하는 TCP 포트 80 및 443</span><span class="sxs-lookup"><span data-stu-id="9aa7f-124">TCP ports 80 and 443 outgoing from clients that will use Teams</span></span>
- <span data-ttu-id="9aa7f-125">Teams를 사용하는 클라이언트가 발신하는 UDP 포트 3478~3481</span><span class="sxs-lookup"><span data-stu-id="9aa7f-125">UDP ports 3478 through 3481 outgoing from clients that will use Teams</span></span>

<span data-ttu-id="9aa7f-126">[네트워크 테스트 도우미](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2)를 사용하여 네트워크 위치에서 모임 경험을 지원할 음성 및 비디오 트래픽에 대한 준비가 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-126">You can use the [Network Testing Companion](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) to confirm that your network locations are ready for the voice and video traffic that will support your meetings experience.</span></span>

| <span data-ttu-id="9aa7f-127">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-127">Ask yourself</span></span> | <span data-ttu-id="9aa7f-128">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-128">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="9aa7f-129">네트워크가 Teams 모임을 배포할 준비가 되었나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-129">Is my network ready for Teams meetings deployment?</span></span> | <span data-ttu-id="9aa7f-130">네트워크가 준비되었는지 확인하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-130">To verify that your network is ready, see:</span></span><ul><li>[<span data-ttu-id="9aa7f-131">Microsoft Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="9aa7f-131">Prepare your organization's network for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[<span data-ttu-id="9aa7f-132">Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="9aa7f-132">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="9aa7f-133">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="9aa7f-133">Core deployment decisions</span></span>

<span data-ttu-id="9aa7f-134">대부분의 조직이 변경하려는 설정입니다 (Teams의 기본 설정이 조직에 적합하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-134">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="9aa7f-135">Teams 관리자</span><span class="sxs-lookup"><span data-stu-id="9aa7f-135">Teams administrators</span></span>

<span data-ttu-id="9aa7f-136">Teams는 조직의 팀을 관리하는데 사용할 수 있는 사용자 지정 관리자 역할의 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-136">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="9aa7f-137">역할은 관리자에게 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-137">The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="9aa7f-138">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-138">Ask yourself</span></span> | <span data-ttu-id="9aa7f-139">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-139">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="9aa7f-140">Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-140">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="9aa7f-141">Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-141">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="9aa7f-142">Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-142">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="9aa7f-143">관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-143">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="9aa7f-144">Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당할 것인가요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-144">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="meetings-settings"></a><span data-ttu-id="9aa7f-145">모임 설정</span><span class="sxs-lookup"><span data-stu-id="9aa7f-145">Meetings settings</span></span> 

<span data-ttu-id="9aa7f-146">모임 설정은 익명 사용자가 Teams 모임에 참여하고 모임 초대를 설정하고 QoS (서비스 품질)를 설정하려는 경우 실시간 트래픽에 대한 포트를 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-146">Meetings settings are used to control whether anonymous users can join Teams meetings, set up meeting invitations, and if you want to turn on Quality of Service (QoS), set the ports for real-time traffic.</span></span> <span data-ttu-id="9aa7f-147">이러한 설정은 사용자가 조직에서 예약하는 모든 Teams 모임에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-147">These settings will be used for all of the Teams meetings that users schedule in your organization.</span></span> 

| <span data-ttu-id="9aa7f-148">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-148">Ask yourself</span></span> | <span data-ttu-id="9aa7f-149">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-149">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="9aa7f-150">초기 모임 설정을 사용자 지정하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-150">Will I customize the initial meeting settings?</span></span> |<span data-ttu-id="9aa7f-151">모임 설정에 대해 자세히 알아보려면 [Teams 내 모임 자습서](tutorial-meetings-in-teams.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-151">See the [Meetings in Teams tutorial](tutorial-meetings-in-teams.yml) to learn more about meetings settings.</span></span>|
|<span data-ttu-id="9aa7f-152">QoS를 구현할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-152">Will I implement QoS?</span></span>|<span data-ttu-id="9aa7f-153">QoS 개념에 대한 자세한 내용은 [Microsoft Teams의 서비스 품질](qos-in-teams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-153">See [Quality of Service in Microsoft Teams](qos-in-teams.md) for information about QoS concepts.</span></span> <span data-ttu-id="9aa7f-154">시나리오 및 구현.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-154">scenarios, and implementation.</span></span>|
|||

### <a name="meeting-policies"></a><span data-ttu-id="9aa7f-155">모임 정책</span><span class="sxs-lookup"><span data-stu-id="9aa7f-155">Meeting policies</span></span>

<span data-ttu-id="9aa7f-156">모임 정책은 사용자가 Teams 모임에 참가할 때 사용 가능한 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-156">Meeting policies are used to control what features are available to users when they join Teams meetings.</span></span> <span data-ttu-id="9aa7f-157">조직에서 모임을 호스팅하는 사용자에게 기본 정책을 사용하거나 하나 이상의 사용자 지정 모임 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-157">You can use the default policy or create one or more custom meeting policies for people that host meetings in your organization.</span></span> <span data-ttu-id="9aa7f-158">자세한 내용은 [Microsoft Teams의 모임 자습서](tutorial-meetings-in-teams.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-158">To learn more, see the [Meetings in Microsoft Team tutorial](tutorial-meetings-in-teams.yml).</span></span>

| <span data-ttu-id="9aa7f-159">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-159">Ask yourself</span></span> | <span data-ttu-id="9aa7f-160">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-160">Action</span></span> |
|--------------|--------|
|<ul><li><span data-ttu-id="9aa7f-161">초기 모임 정책을 사용자 지정하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-161">Will I customize the initial meeting policies?</span></span></li><li><span data-ttu-id="9aa7f-162">여러개의 모임 정책이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-162">Do I require multiple meeting policies?</span></span></li><li><span data-ttu-id="9aa7f-163">어떠한 사용자 그룹에 어떠한 모임 정책이 적용될지를 어떻게 결정하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-163">How will I determine which groups of users get which meetings policy applied?</span></span></li></ul>|<br><span data-ttu-id="9aa7f-164">[Teams에서의 모임 정책 관리](meeting-policies-in-teams.md)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-164">Read [Manage meeting policies in Teams](meeting-policies-in-teams.md).</span></span>|
|||

### <a name="audio-conferencing"></a><span data-ttu-id="9aa7f-165">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="9aa7f-165">Audio Conferencing</span></span>

<span data-ttu-id="9aa7f-166">오디오 회의는 기존의 유선 전화, PBX(Private Branch Exchange) 또는 휴대폰을 사용하여 전화 회의 참가자가 PSTN(Public Switched Telephone Network)을 통해 회의에 참가할 수 있게 허용하여 모든 회의(임시 또는 예약)에 추가 진입점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-166">Audio Conferencing provides organizations with additional entry points to any meeting (ad hoc or scheduled) by allowing meeting participants to join via public switched telephone network (PSTN) by dialing in using a traditional land line, private branch exchange (PBX), or mobile phone.</span></span> 

<span data-ttu-id="9aa7f-167">오디오 회의를 배포할 준비가 되면 자세한 [오디오 회의 배포](deploy-audio-conferencing-teams-landing-page.md) 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-167">When you're ready to roll out Audio Conferencing, see the in-depth [Audio Conferencing rollout](deploy-audio-conferencing-teams-landing-page.md) guidance.</span></span>

### <a name="meeting-room-and-personal-devices"></a><span data-ttu-id="9aa7f-168">회의실 및 개인 장치 정책</span><span class="sxs-lookup"><span data-stu-id="9aa7f-168">Meeting room and personal devices</span></span>

<span data-ttu-id="9aa7f-169">Teams에서 최적의 모임 경험을 위해 회의실 시스템, 전화, 헤드셋 및 카메라와 같은 Teams 장치 사용을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-169">For an optimal meeting experience in Teams, consider using Teams devices such as room systems, phones, headsets, and cameras.</span></span> <span data-ttu-id="9aa7f-170">자세한 내용은 [지능적인 커뮤니케이션을 위한 Teams 장치](https://products.office.com/microsoft-teams/across-devices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-170">To learn more, see [Teams devices for intelligent communications](https://products.office.com/microsoft-teams/across-devices).</span></span>

| <span data-ttu-id="9aa7f-171">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-171">Ask yourself</span></span> | <span data-ttu-id="9aa7f-172">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-172">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="9aa7f-173">사용자를 위한 개인 장치를 구입하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-173">Will I purchase personal devices for my users?</span></span> |<span data-ttu-id="9aa7f-174">[Teams에서 디바이스 관리](device-management.md)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-174">Read [Manage your devices in Teams](device-management.md).</span></span> |
|<span data-ttu-id="9aa7f-175">회의실용 회의실 시스템 장치를 구입하여 배포하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-175">Will I purchase and deploy room system devices for my conference rooms?</span></span>|<span data-ttu-id="9aa7f-176">[회의실 장치 및 솔루션](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-176">Read [Meeting room devices and solutions](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="reporting"></a><span data-ttu-id="9aa7f-177">보고</span><span class="sxs-lookup"><span data-stu-id="9aa7f-177">Reporting</span></span>

<span data-ttu-id="9aa7f-178">활동 보고서를 사용하여 조직의 사용자가 Teams를 어떻게 사용하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-178">Use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="9aa7f-179">예를 들어, 아직 Teams를 사용하고 있지 않은 경우 Teams를 사용하여 생산성과 공동 작업을 향상 시키는 방법을 모를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-179">For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="9aa7f-180">조직에서 활동 보고서를 사용하여 교육 및 커뮤니케이션 노력에 대한 우선 순위를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-180">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> 


| <span data-ttu-id="9aa7f-181">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-181">Ask yourself</span></span> | <span data-ttu-id="9aa7f-182">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-182">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="9aa7f-183">누가 보고해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-183">Who will be responsible for reporting?</span></span>|<span data-ttu-id="9aa7f-184">[Teams에 대한 활동 보고서 사용](teams-activity-reports.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-184">Read [Use activity reports for Teams](teams-activity-reports.md).</span></span>  |
|<span data-ttu-id="9aa7f-185">누가 사용 현황을 모니터링하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-185">Who will be responsible for monitoring usage?</span></span>|<span data-ttu-id="9aa7f-186">[Teams에서 사용 현황 및 사용자 의견 모니터링](get-started-with-teams-monitor-usage-and-feedback.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-186">Read [Monitor usage and feedback in Teams](get-started-with-teams-monitor-usage-and-feedback.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="9aa7f-187">추가 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="9aa7f-187">Additional deployment decisions</span></span>

<span data-ttu-id="9aa7f-188">조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-188">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="bandwidth-planning"></a><span data-ttu-id="9aa7f-189">대역폭 계획</span><span class="sxs-lookup"><span data-stu-id="9aa7f-189">Bandwidth planning</span></span> 

<span data-ttu-id="9aa7f-190">대역폭 계획을 통해 조직은 광역 네트워크와 인터넷 링크에서 모임을 지원하는 데 필요한 대역폭을 예측하여 네트워크를 올바르게 프로비전하여 확장된 모임 서비스를 지원할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-190">Bandwidth planning lets organizations estimate the bandwidth that will be required to support meetings across their wide area networks and internet links so they can confirm that the network is correctly provisioned to support a scaled out meeting service.</span></span> 

| <span data-ttu-id="9aa7f-191">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-191">Ask yourself</span></span> | <span data-ttu-id="9aa7f-192">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-192">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="9aa7f-193">모임 배포 이전 및 도중에 대역폭 계획을 수행해야하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-193">Do I need to do bandwidth planning prior to and during my Meetings rollout?</span></span> |<span data-ttu-id="9aa7f-194">계획 프로세스를 단순화 하는 방법에 대한 자세한 내용과 도구에 대한 링크는 [네트워크 준비](3-envision-evaluate-my-environment.md#network-readiness)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-194">See [Network Readiness](3-envision-evaluate-my-environment.md#network-readiness) for more information and links to tools to simplify your planning process.</span></span>|
|||

### <a name="meeting-recording-and-archiving"></a><span data-ttu-id="9aa7f-195">모임 녹음/녹화 및 보관</span><span class="sxs-lookup"><span data-stu-id="9aa7f-195">Meeting recording and archiving</span></span>

<span data-ttu-id="9aa7f-196">사용자는 자신의 모임 및 그룹 통화를 녹음/녹화하여 오디오, 비디오, 화면 공유 활동을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-196">Users can record their meetings and group calls to capture audio, video, and screen sharing activity.</span></span> <span data-ttu-id="9aa7f-197">사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검색할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-197">There is also an option for recordings to have automatic transcription, so that users can play back meeting recordings with closed captions and search for important discussion items in the transcript.</span></span> <span data-ttu-id="9aa7f-198">녹음/녹화는 클라우드에서 이루어지고 Microsoft Stream에 저장되므로 사용자는 조직 전체에서 안전하게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-198">The recording happens in the cloud and is saved in Microsoft Stream, so users can share it securely across their organization.</span></span> <span data-ttu-id="9aa7f-199">모임 녹음/녹화를 찾으려면 모임 대화로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-199">To find the recording for a meeting, go to the meeting conversation.</span></span>

<span data-ttu-id="9aa7f-200">자세한 내용은 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-200">To learn more, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

| <span data-ttu-id="9aa7f-201">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-201">Ask yourself</span></span> | <span data-ttu-id="9aa7f-202">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-202">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="9aa7f-203">모임 기록 서비스를 켜나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-203">Will I turn on the meeting transcription service?</span></span>|<span data-ttu-id="9aa7f-204">[녹음/녹화 기록 설정 또는 해제](cloud-recording.md#turn-on-or-turn-off-recording-transcription)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-204">See [Turn on or turn off recording transcription](cloud-recording.md#turn-on-or-turn-off-recording-transcription)</span></span>|
|||


### <a name="live-events-policies"></a><span data-ttu-id="9aa7f-205">라이브 이벤트 정책</span><span class="sxs-lookup"><span data-stu-id="9aa7f-205">Live events policies</span></span>

<span data-ttu-id="9aa7f-206">Teams 라이브 이벤트 정책은 사용자 그룹의 이벤트 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-206">Teams live events policies are used to manage event settings for groups of users.</span></span> <span data-ttu-id="9aa7f-207">기본 정책을 사용하거나 조직 내에서 라이브 이벤트를 보유한 사용자에게 할당할 수있는 추가 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-207">You can use the default policy or create additional policies that can be assigned to users who hold live events within your organization.</span></span> 

| <span data-ttu-id="9aa7f-208">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-208">Ask yourself</span></span> | <span data-ttu-id="9aa7f-209">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-209">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="9aa7f-210">조직에서 Teams의 라이브 이벤트를 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-210">Will my organization use Teams live events?</span></span>| <span data-ttu-id="9aa7f-211">팀의 라이브 이벤트 계획, 설정 및 구성에 대한 자세한 내용은 [라이브 이벤트 문서](teams-live-events/what-are-teams-live-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-211">See the [live events articles](teams-live-events/what-are-teams-live-events.md) for more information about planning for, setting up, and configuring Teams live events.</span></span>|
|||

### <a name="conference-room-systems-rollout"></a><span data-ttu-id="9aa7f-212">회의실 시스템 출시</span><span class="sxs-lookup"><span data-stu-id="9aa7f-212">Conference room systems rollout</span></span>

<span data-ttu-id="9aa7f-213">다수의 회의실을 보유한 조직은 회의실 목록을 작성하고 적절한 장치를 식별한 다음 이를 배포하는 체계적인 접근 방식을 고려해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-213">Organizations with many conference rooms may want to consider a structured approach to inventorying their rooms, identifying the appropriate devices, and then rolling them out.</span></span> 



| <span data-ttu-id="9aa7f-214">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-214">Ask yourself</span></span> | <span data-ttu-id="9aa7f-215">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-215">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="9aa7f-216">회의실 시스템을 배포하려면 무엇을 해야하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-216">What do I need to do to roll out conference room systems?</span></span>|<span data-ttu-id="9aa7f-217">[Microsoft Teams 룸 계획](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)문서를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-217">Check out the [Plan Microsoft Teams Rooms](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) articles.</span></span>|
|||

### <a name="cloud-video-interop"></a><span data-ttu-id="9aa7f-218">클라우드 비디오 interop</span><span class="sxs-lookup"><span data-stu-id="9aa7f-218">Cloud video interop</span></span>

<span data-ttu-id="9aa7f-219">클라우드 비디오 interop을 사용하면 타사 회의실 장치에서 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-219">Cloud video interop makes it possible for third-party meeting room devices to join Teams meetings.</span></span> 

<span data-ttu-id="9aa7f-220">컨텐츠 협업을 통한 화상 회의는 모임을 최대한 활용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-220">Video teleconferencing with content collaboration helps you make the most out of meetings.</span></span> <span data-ttu-id="9aa7f-221">그러나 회의실 시스템과 장치는 업그레이드 하는 데 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-221">However, meeting room systems and devices are expensive to upgrade.</span></span> <span data-ttu-id="9aa7f-222">Teams용 클라우드 비디오 interop은 타사 시스템과 함께 작동하며 회의실 또는 Teams 클라이언트 내에서 모든 참가자에게 네이티브 모임 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-222">Cloud video interop for Teams works with third-party systems and delivers a native meeting experience for all participants – in meeting rooms or inside Teams clients.</span></span> 

| <span data-ttu-id="9aa7f-223">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-223">Ask yourself</span></span> | <span data-ttu-id="9aa7f-224">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-224">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="9aa7f-225">회의실 시스템 배포의 일부로 클라우드 비디오 interop 솔루션을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-225">Will I use a cloud video interop solution as part of my room systems deployment?</span></span> | <span data-ttu-id="9aa7f-226">[Teams용 클라우드 비디오 interop](cloud-video-interop.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-226">Read [Cloud Video Interop for Teams](cloud-video-interop.md).</span></span>|
|||


### <a name="personal-device-rollout"></a><span data-ttu-id="9aa7f-227">개인 장치 배포</span><span class="sxs-lookup"><span data-stu-id="9aa7f-227">Personal device rollout</span></span>

<span data-ttu-id="9aa7f-228">모임이나 음성 배포를 지원하기 위해 개인 장치의 대규모 배포를 계획 중인 경우, 반복 가능한 품질을 제공하는 반복 가능한 사이트별 출시 프로세스 사용을 고려해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-228">When planning a larger rollout of personal devices to support meetings or voice deployments, consider using a repeatable site-by-site rollout process that delivers repeatable quality.</span></span>

| <span data-ttu-id="9aa7f-229">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-229">Ask yourself</span></span> | <span data-ttu-id="9aa7f-230">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-230">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="9aa7f-231">사이트별 접근 방식을 사용하여 모임을 배포하나요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-231">Will I use a site-by-site approach to roll out Meetings?</span></span> |  <span data-ttu-id="9aa7f-232">[Teams용 사이트 인에이블먼트 플레이북](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)은 자체 배포에 사용할 수 있는 훌륭한 기반을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-232">The [Site enablement playbook for Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) provides a good foundation that you can use for your own deployments.</span></span> <span data-ttu-id="9aa7f-233">이 가이드는 음성에 중점을 두지만 장치 전달, 계정 준비, 도입 및 교육에 대한 일반적인 원칙은 대규모 모임 배포에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-233">The guide is focused on voice, but the general principles of device delivery, account readiness, adoption, and training apply to a large meeting deployment.</span></span> |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="9aa7f-234">모임 및 통화 품질 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9aa7f-234">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="9aa7f-235">Teams는 통화 품질 문제를 모니터링하고 문제를 해결하기 위한 두 가지 방법인 [통화 분석 및 통화 품질 대시보드](difference-between-call-analytics-and-call-quality-dashboard.md)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-235">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md).</span></span> <span data-ttu-id="9aa7f-236">Call Analytics에는 각 사용자의 특정 통화 및 모임과 관련된 디바이스, 네트워크 및 연결에 대한 자세한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-236">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="9aa7f-237">Call Analytics는 관리자와 지원 센터 상담원이 특정 통화의 통화 품질 문제를 해결하는데 도움을 주기 위해 설계되었고 통화 품질 대시보드는 관리자와 네트워크 엔지니어가 네트워크를 최적화하는데 도움을 주기 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-237">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="9aa7f-238">통화 품질 대시보드는 특정 사용자로부터 포커스를 이동하고 대신 전체 Teams 조직에 대한 집계 정보를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-238">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="9aa7f-239">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-239">Ask yourself</span></span>|<span data-ttu-id="9aa7f-240">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-240">Action</span></span> |
|------------|-------|
| <span data-ttu-id="9aa7f-241">통화 품질 문제를 모니터링하고 문제를 해결할 책임이 있는 사용자는 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-241">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="9aa7f-242">통화 품질 문제를 해결하는 데 필요한 사용 권한 수준에 대한 내용은 [Call Analytics를 사용하여 통화 품질 저하 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-242">Read [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||

### <a name="operate-your-meetings-service"></a><span data-ttu-id="9aa7f-243">모임 서비스 운영</span><span class="sxs-lookup"><span data-stu-id="9aa7f-243">Operate your meetings service</span></span>

<span data-ttu-id="9aa7f-244">조직에 있는 다른 사용자에게 서비스에 영향을 주는 이벤트를 사전에 알릴 수 있도록 Teams 서비스의 전반적인 상태를 파악하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-244">It's important that you understand the overall health of the Teams service so that you can proactively alert others in your organization of any event that affects the service.</span></span> <span data-ttu-id="9aa7f-245">[내 서비스 운영](1-drive-value-operate-my-service.md) 문서를 통해 서비스 작업에 대한 상세한 안내를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-245">The [Operate my service](1-drive-value-operate-my-service.md) articles provide in-depth guidance for service operations.</span></span>

|<span data-ttu-id="9aa7f-246">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="9aa7f-246">Ask yourself</span></span>|<span data-ttu-id="9aa7f-247">작업</span><span class="sxs-lookup"><span data-stu-id="9aa7f-247">Action</span></span> |
|------------|-------|
|<span data-ttu-id="9aa7f-248">조직에서 모임 서비스를 관리해야 하는 사람은 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-248">Who in my organization will be responsible for managing the meetings service?</span></span> | <span data-ttu-id="9aa7f-249">이 사람이 모임 서비스를 관리하는 데 필요한 팀 관리자 권한을 보유하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-249">Make sure this person has the Teams admin permissions they need in order to manage your meetings service.</span></span> <span data-ttu-id="9aa7f-250">Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-250">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="9aa7f-251">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9aa7f-251">Next steps</span></span>
- <span data-ttu-id="9aa7f-252">조직 전체의 모임 및 회의 [도입을 주도](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-252">[Drive adoption](adopt-microsoft-teams-landing-page.md) of meetings & conferencing throughout your organization.</span></span>
- [<span data-ttu-id="9aa7f-253">오디오 회의 추가</span><span class="sxs-lookup"><span data-stu-id="9aa7f-253">Add audio conferencing</span></span>](deploy-audio-conferencing-teams-landing-page.md)
- [<span data-ttu-id="9aa7f-254">클라우드 음성 출시</span><span class="sxs-lookup"><span data-stu-id="9aa7f-254">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="9aa7f-255">최초 Teams를 배포 시 플래너와 같은 추천 앱을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-255">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="9aa7f-256">Teams의 채택을 주도하면서 다른 [앱, 봇 & 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-256">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
