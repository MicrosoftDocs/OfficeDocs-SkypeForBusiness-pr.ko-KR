---
title: Android에서 Microsoft Teams 룸 배포
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Android에서 배포하는 방법을 Microsoft Teams 룸 이 문서를 읽어보아야 합니다.
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120800"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a><span data-ttu-id="a2c48-103">Android에서 Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="a2c48-103">Deploy Microsoft Teams Rooms on Android</span></span>

<span data-ttu-id="a2c48-104">Android에서 Microsoft Teams 룸 배포는 다음 단계로 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-104">Deployment of Microsoft Teams Rooms on Android can be broken down into the following phases:</span></span>

- <span data-ttu-id="a2c48-105">**사이트 준비** 배포 위치(회의실)가 배포 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="a2c48-106">**서비스 준비** 리소스 계정을 만들고 디바이스에 [할당합니다(관리](resource-account-ui.md)센터를 사용하여 Microsoft 365 참조).</span><span class="sxs-lookup"><span data-stu-id="a2c48-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="a2c48-107">전용 룸 라이선스를 사용하는 것이 좋습니다. 제대로 라이선스가 부여된 최종 사용자 계정은 Android에서 로그인할 Teams 룸 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to Teams Rooms on Android.</span></span>
- <span data-ttu-id="a2c48-108">**구성 및 배포** 필요한 Teams 룸 디바이스를 설정하고 연결합니다(자세한 내용은 제조업체의 설명서 참조).</span><span class="sxs-lookup"><span data-stu-id="a2c48-108">**Configuration and deployment** Set up Teams Rooms and connect the peripheral devices you need (see the manufacturer's documentation for details).</span></span>

<span data-ttu-id="a2c48-109">Teams 룸 관리하려면 전역 관리자, 서비스 관리자 Teams 또는 디바이스 Teams 관리해야 합니다. 관리자 역할에 대한 자세한 내용은 [관리자](../using-admin-roles.md)Microsoft Teams 관리자 역할 사용 을 Teams.</span><span class="sxs-lookup"><span data-stu-id="a2c48-109">To manage Teams Rooms, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="a2c48-110">사이트 준비</span><span class="sxs-lookup"><span data-stu-id="a2c48-110">Site readiness</span></span>

<span data-ttu-id="a2c48-111">주문된 디바이스가 조직에 전달되는 동안 네트워킹, 시설 및 시청각 팀과 함께 작업하여 배포 요구 사항이 충족되고 각 사이트와 방이 전원, 네트워킹 및 표시 측면에서 준비되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="a2c48-112">공동 작업 표시줄 사이트에 대한 권장 사항은:</span><span class="sxs-lookup"><span data-stu-id="a2c48-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="a2c48-113">최대 5인실</span><span class="sxs-lookup"><span data-stu-id="a2c48-113">Rooms up to 5 people in size</span></span>
- <span data-ttu-id="a2c48-114">전용 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="a2c48-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="a2c48-115">터치 지원 디스플레이</span><span class="sxs-lookup"><span data-stu-id="a2c48-115">Touch-enabled displays</span></span>
- <span data-ttu-id="a2c48-116">이더넷 케이블링</span><span class="sxs-lookup"><span data-stu-id="a2c48-116">Ethernet cabling</span></span>
- <span data-ttu-id="a2c48-117">네트워크에서 미디어에 대해 사용하도록 설정된 QoS(서비스 품질 Microsoft Teams)</span><span class="sxs-lookup"><span data-stu-id="a2c48-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="a2c48-118">물리적 설치 고려 사항은 제조업체의 설명서를 참조하고, 화면을 설치하고 탑재하고 케이블을 실행하기 전에 시청각 팀의 환경을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="a2c48-119">실시간 트래픽에 [](../prepare-network.md) 대한 대역폭 Teams 네트워크의 적합성을 평가하기 위해 네트워크 준비를 체크 아웃해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="a2c48-120">프록시 서버는 Teams 설치하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="a2c48-121">프록시 서버 및 Teams 대한 자세한 내용은 프록시 서버를 [Teams.](../proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="a2c48-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a2c48-123">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="a2c48-123">Decision points</span></span>|<ul><li><span data-ttu-id="a2c48-124">사이트가 공동 작업 막대에 대한 사이트 준비 요구 사항을 충족하는지 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2c48-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="a2c48-125">각 사이트에 충분한 대역폭을 제공한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a2c48-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2c48-127">Next steps</span></span>|<ul><li><span data-ttu-id="a2c48-128">공동 작업 표시줄 배포 및 구성을 계획하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="a2c48-129">서비스 준비</span><span class="sxs-lookup"><span data-stu-id="a2c48-129">Service readiness</span></span>

<span data-ttu-id="a2c48-130">Teams 룸 배포하기 전에 리소스 계정, 최종 Microsoft 365 둘 다 혼합을 사용할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-130">Before you deploy Teams Rooms, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="a2c48-131">Microsoft 365 리소스 계정은 Teams, 프로젝터 등 특정 리소스에 전용인 사서함 및 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="a2c48-132">이러한 리소스 계정은 사용자가 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="a2c48-133">개인 Teams 룸 특정 개인에 전념하지 않는 한 해당 리소스 계정을 Microsoft 365 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-133">Unless Teams Rooms is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="a2c48-134">리소스 계정 사용</span><span class="sxs-lookup"><span data-stu-id="a2c48-134">Using a resource account</span></span>

<span data-ttu-id="a2c48-135">리소스 계정을 설정하기로 Microsoft 365 경우 해당 리소스에 대한 미팅룸 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="a2c48-136">미팅룸 라이선스에는 조직의 사용자가 모임 또는 모임을 통해 회의실을 예약할 수 있는 리소스 사서함이 Outlook Teams.</span><span class="sxs-lookup"><span data-stu-id="a2c48-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="a2c48-137">또한 이 라이선스를 사용하면 모임 참가자 간 비디오 및 오디오 회의 및 화면 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="a2c48-138">외부 전화 번호로 전화를 걸거나 통화해야 하는 경우 통화 계획 또는 추가 Microsoft 365 Business Voice 라이선스가 필요할 [수 있습니다.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)</span><span class="sxs-lookup"><span data-stu-id="a2c48-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business).</span></span> <span data-ttu-id="a2c48-139">조직에서 직접 라우팅을 사용하도록 설정한 경우 SKU만 미팅룸 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="a2c48-140">리소스 계정을 만들 때 계정에서 모임 요청을 자동으로 수락하거나 거부할지 여부를 선택할 수 있으며, 모임을 다시 허용하고, 리소스를 예약할 수 있는 시간을 미리 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="a2c48-141">리소스 계정에 대한 자세한 Microsoft 365 관리 센터를 사용하여 리소스 [계정 만들기를 Microsoft 365 참조하세요.](resource-account-ui.md)</span><span class="sxs-lookup"><span data-stu-id="a2c48-141">For more information about Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a2c48-143">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="a2c48-143">Decision points</span></span>|<ul><li><span data-ttu-id="a2c48-144">외부 전화 통화를 만들거나 받을지 여부를 결정하고 리소스 계정에 대한 라이선스 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a2c48-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2c48-146">Next steps</span></span>|<ul><li><span data-ttu-id="a2c48-147">리소스 계정을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="a2c48-148">구성 및 배포</span><span class="sxs-lookup"><span data-stu-id="a2c48-148">Configuration and deployment</span></span>

<span data-ttu-id="a2c48-149">구성 및 배포 계획은 다음 주요 영역을 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="a2c48-150">리소스 계정 프로비전</span><span class="sxs-lookup"><span data-stu-id="a2c48-150">Resource account provisioning</span></span>
- <span data-ttu-id="a2c48-151">디바이스 배포</span><span class="sxs-lookup"><span data-stu-id="a2c48-151">Device deployment</span></span>
- <span data-ttu-id="a2c48-152">Teams 룸 및 주변 장치 구성</span><span class="sxs-lookup"><span data-stu-id="a2c48-152">Teams Rooms application and peripheral device configuration</span></span>
- <span data-ttu-id="a2c48-153">테스트</span><span class="sxs-lookup"><span data-stu-id="a2c48-153">Testing</span></span>
- <span data-ttu-id="a2c48-154">자산 관리</span><span class="sxs-lookup"><span data-stu-id="a2c48-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="a2c48-155">계정 프로비전</span><span class="sxs-lookup"><span data-stu-id="a2c48-155">Account provisioning</span></span>

<span data-ttu-id="a2c48-156">Microsoft 365 리소스 계정을 사용하여 사용자가 공동 작업 막대를 예약할 수 [](resource-account-ui.md) 있도록 계획하는 경우 관리 센터를 사용하여 Microsoft 365 계정 만들기의 지침에 Microsoft 365 필요한 각 공동 작업 표시줄에 대한 Microsoft 365 리소스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="a2c48-157">또한 리소스 계정에 미팅룸 라이선스를 추가해야 하고, 외부 전화 번호로 전화를 걸거나 수신하려는 경우 조직에서 직접 라우팅을 사용하지 않는 경우 통화 계획 또는 비즈니스 음성 라이선스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="a2c48-158">개인 사용을 위해 개별 사용자에게 Teams 룸 할당하려는 경우 추가 계정을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-158">If you want to assign Teams Rooms to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="a2c48-159">사용자는 자신의 개인 계정을 사용하여 공동 작업 막대에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="a2c48-160">리소스 계정에 대한 표시 이름을 Microsoft 365 설명하고 쉽게 이해할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="a2c48-161">모임을 검색하고 모임에 추가할 때 사용자가 볼 Teams 룸 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-161">These are the names that users will see when searching for and adding Teams Rooms to meetings.</span></span> <span data-ttu-id="a2c48-162">Site Room Name(최대 회의실 용량)과 같은 규칙을 사용할 수 있으므로 예를 들어 런던의 4인 회의실인 Curie에는 표시 이름 - LON-CURIE(4)가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a2c48-164">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="a2c48-164">Decision points</span></span>|<ul><li><span data-ttu-id="a2c48-165">전용 리소스 계정에 대한 이름 규칙을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="a2c48-166">개별 계정을 만들지 대량 프로비전 스크립트를 사용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a2c48-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2c48-168">Next steps</span></span>|<ul><li><span data-ttu-id="a2c48-169">디바이스 배포를 계획하기 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="a2c48-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="a2c48-170">디바이스 배포</span><span class="sxs-lookup"><span data-stu-id="a2c48-170">Device deployment</span></span>

<span data-ttu-id="a2c48-171">다음으로, 디바이스 및 할당된 주변 장치를 회의실에 배달하기 위한 계획을 만든 다음 설치 및 구성을 진행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a2c48-173">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="a2c48-173">Decision points</span></span>|<ul><li><span data-ttu-id="a2c48-174">사이트당 배포를 관리할 인원을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="a2c48-175">현장에서 Teams 룸 리소스를 식별하고 구성 및 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-175">Identify the resources who will install Teams Rooms on site and undertake the configuration and testing.</span></span></li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a2c48-177">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2c48-177">Next steps</span></span>|<ul><li><span data-ttu-id="a2c48-178">디바이스 테스트를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="a2c48-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="a2c48-179">테스트</span><span class="sxs-lookup"><span data-stu-id="a2c48-179">Testing</span></span>

<span data-ttu-id="a2c48-180">배포한 후 Teams 룸 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-180">After you have deployed Teams Rooms, you should test them.</span></span> <span data-ttu-id="a2c48-181">로그인하여 Teams 룸 기능이 작동하고 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-181">Sign in to Teams Rooms and check that the expected capabilities are working.</span></span> <span data-ttu-id="a2c48-182">관리 센터의 디바이스 탭 아래에 있는  공동 작업 표시  막대 섹션에 Microsoft Teams 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-182">We highly recommend that you verify that they are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="a2c48-183">또한 품질 및 성능을 확인하기 위해 여러 테스트 호출 및 모임을 만드는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="a2c48-184">일반 배포의 일부로 Microsoft Teams CQD(전화 품질 대시보드)에 대한 구성 파일을 구성하고, 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="a2c48-185">자세한 내용은 환경 품질 검토 [가이드 를 참조하세요.](../quality-of-experience-review-guide.md)</span><span class="sxs-lookup"><span data-stu-id="a2c48-185">For more information, see the [Quality of Experience Review Guide](../quality-of-experience-review-guide.md).</span></span>

### <a name="asset-management"></a><span data-ttu-id="a2c48-186">자산 관리</span><span class="sxs-lookup"><span data-stu-id="a2c48-186">Asset management</span></span>

<span data-ttu-id="a2c48-187">배포의 일부로 룸 이름, 로그인된 리소스 계정 및 할당된 주변 장치로 자산 레지스터를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2c48-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2c48-188">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a2c48-188">Related topics</span></span>

[<span data-ttu-id="a2c48-189">관리 센터를 사용하여 Microsoft Teams 룸 계정 Microsoft Teams 구성</span><span class="sxs-lookup"><span data-stu-id="a2c48-189">Configure accounts for Microsoft Teams Rooms using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->