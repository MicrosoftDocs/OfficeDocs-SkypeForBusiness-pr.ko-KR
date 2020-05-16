---
title: Microsoft 팀을 위한 공동 작업 표시줄 배포
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
description: Microsoft 팀의 공동 작업 모음 배포에 대해 자세히 알아보려면이 문서를 참조 하세요.
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268057"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a><span data-ttu-id="25d01-103">Microsoft 팀을 위한 공동 작업 표시줄 배포</span><span class="sxs-lookup"><span data-stu-id="25d01-103">Deploy collaboration bars for Microsoft Teams</span></span>

<span data-ttu-id="25d01-104">Microsoft 팀에 대 한 공동 작업 표시줄 배포는 다음 단계로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-104">Deployment of collaboration bars for Microsoft Teams can be broken down into the following phases:</span></span>

- <span data-ttu-id="25d01-105">**사이트 준비** 배포 위치 (회의실)가 배포 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="25d01-106">**서비스 준비** 리소스 계정을 만들고 장치에 할당 합니다 ([Microsoft 365 관리 센터를 사용 하 여 리소스 계정 만들기 참조](resource-account-ui.md)).</span><span class="sxs-lookup"><span data-stu-id="25d01-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="25d01-107">전용 회의실 라이선스를 사용 하는 것이 좋지만, 적절 한 라이선스 최종 사용자 계정이 공동 작업 모음에 로그인 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to collaboration bars.</span></span>
- <span data-ttu-id="25d01-108">**구성 및 배포** 회의실에서 공동 작업 모음을 설정 하 고 필요한 주변 기기를 연결 하세요 (공동 작업 표시줄에 대 한 제조업체 설명서 참조).</span><span class="sxs-lookup"><span data-stu-id="25d01-108">**Configuration and deployment** Set up collaboration bars in rooms and connect the peripheral devices you need (see the manufacturer's documentation for your collaboration bars).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="25d01-109">사이트 준비</span><span class="sxs-lookup"><span data-stu-id="25d01-109">Site readiness</span></span>

<span data-ttu-id="25d01-110">순서가 지정 된 디바이스는 조직에 게 전달 되는 반면, 네트워킹, 시설 및 오디오-시각적 팀과 협력 하 여 배포 요구 사항이 충족 되 고 각 사이트와 채팅방이 전원, 네트워킹, 디스플레이 측면에서 준비 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-110">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="25d01-111">공동 작업 모음 사이트에 대 한 권장 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-111">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="25d01-112">크기가 최대 4 명까지 회의실</span><span class="sxs-lookup"><span data-stu-id="25d01-112">Rooms up to 4 people in size</span></span>
- <span data-ttu-id="25d01-113">전용 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="25d01-113">Dedicated resource accounts</span></span>
- <span data-ttu-id="25d01-114">터치 가능 디스플레이</span><span class="sxs-lookup"><span data-stu-id="25d01-114">Touch-enabled displays</span></span>
- <span data-ttu-id="25d01-115">이더넷 케이블 연결</span><span class="sxs-lookup"><span data-stu-id="25d01-115">Ethernet cabling</span></span>
- <span data-ttu-id="25d01-116">Microsoft 팀 미디어의 네트워크에서 사용할 수 있는 QoS (서비스 품질)</span><span class="sxs-lookup"><span data-stu-id="25d01-116">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="25d01-117">물리적 설치 고려 사항은 제조업체의 설명서를 참조 하 고, 화면을 설치 및 탑재 하 고 케이블링을 실행 하기 전에 오디오-시각적 팀의 경험을 활용 하세요.</span><span class="sxs-lookup"><span data-stu-id="25d01-117">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="25d01-118">대역폭 계획 및 네트워크의 실제 시간 트래픽에 대 한 평가에 대 한 [팀 네트워크 준비](../prepare-network.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25d01-118">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="25d01-119">팀 장치와 인터넷 간에 프록시 서버를 배치 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-119">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="25d01-120">프록시 서버와 팀에 대 한 자세한 내용은 [팀에 대 한 프록시 서버](../proxy-servers-for-skype-for-business-online.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25d01-120">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="25d01-122">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="25d01-122">Decision points</span></span>|<ul><li><span data-ttu-id="25d01-123">사이트가 Microsoft 팀의 공동 작업 모음에 대 한 사이트 준비 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-123">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="25d01-124">각 사이트에 충분 한 대역폭을 제공 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-124">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="25d01-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25d01-126">Next steps</span></span>|<ul><li><span data-ttu-id="25d01-127">공동 작업 모음 배포 및 구성 계획을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-127">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="25d01-128">서비스 준비</span><span class="sxs-lookup"><span data-stu-id="25d01-128">Service readiness</span></span>

<span data-ttu-id="25d01-129">공동 작업 모음을 배포 하기 전에 Microsoft 365 리소스 계정, 최종 사용자 계정 또는 두 가지 모두를 함께 사용할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-129">Before you deploy your collaboration bars, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="25d01-130">Microsoft 365 리소스 계정은 특정 리소스 (예: 회의실, 프로젝터 등)를 전담 하는 사서함 및 팀 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-130">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="25d01-131">이러한 리소스 계정은 생성 될 때 사용자가 정의한 규칙을 사용 하 여 모임 초대에 자동으로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-131">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="25d01-132">개인 사용을 위해 공동 작업 모음이 특정 개인에 게 전담 되지 않는 경우에는 Microsoft 365 리소스 계정을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-132">Unless a collaboration bar is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="25d01-133">자원 계정 사용</span><span class="sxs-lookup"><span data-stu-id="25d01-133">Using a resource account</span></span>

<span data-ttu-id="25d01-134">Microsoft 365 리소스 계정을 설정 하기로 결정 한 경우에는이에 대 한 회의실 라이선스를 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-134">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="25d01-135">회의실 라이선스에는 조직의 사용자가 Outlook 또는 팀을 통해 회의실을 예약할 수 있도록 하는 리소스 사서함이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-135">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="25d01-136">또한 라이선스는 모임 참가자 간에 영상 및 오디오 회의와 화면 공유를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-136">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="25d01-137">외부 전화 번호로 전화를 걸거나 받아야 하는 경우 Microsoft 365 전화 시스템 또는 Microsoft 365 Business 음성 라이선스도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-137">If you need to receive or make calls to or from an external telephone number, you'll also need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="25d01-138">자원 계정을 만들 때 계정에서 모임 요청을 자동으로 수락 하거나 거절 하 고, 되풀이 모임을 허용 하 고, 사용자가 리소스를 예약할 수 있는 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-138">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="25d01-139">Microsoft 365 리소스 계정의 공동 작업 표시줄에 대 한 자세한 내용은 [microsoft 365 관리 센터를 사용 하 여 자원 계정 만들기](resource-account-ui.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25d01-139">For more information about collaboration bars for Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="25d01-141">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="25d01-141">Decision points</span></span>|<ul><li><span data-ttu-id="25d01-142">외부 전화를 걸거나 받을 수 있으며 리소스 계정에 대 한 라이선스 요구 사항을 확인할 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-142">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="25d01-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25d01-144">Next steps</span></span>|<ul><li><span data-ttu-id="25d01-145">리소스 계정 준비</span><span class="sxs-lookup"><span data-stu-id="25d01-145">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="25d01-146">구성 및 배포</span><span class="sxs-lookup"><span data-stu-id="25d01-146">Configuration and deployment</span></span>

<span data-ttu-id="25d01-147">구성 및 배포 계획에는 다음 주요 영역이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-147">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="25d01-148">리소스 계정 프로 비전</span><span class="sxs-lookup"><span data-stu-id="25d01-148">Resource account provisioning</span></span>
- <span data-ttu-id="25d01-149">장치 배포</span><span class="sxs-lookup"><span data-stu-id="25d01-149">Device deployment</span></span>
- <span data-ttu-id="25d01-150">Microsoft 팀 응용 프로그램 및 주변 장치 구성에 대 한 공동 작업 모음</span><span class="sxs-lookup"><span data-stu-id="25d01-150">Collaboration bars for Microsoft Teams application and peripheral device configuration</span></span>
- <span data-ttu-id="25d01-151">테스트가</span><span class="sxs-lookup"><span data-stu-id="25d01-151">Testing</span></span>
- <span data-ttu-id="25d01-152">자산 관리</span><span class="sxs-lookup"><span data-stu-id="25d01-152">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="25d01-153">계정 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="25d01-153">Account provisioning</span></span>

<span data-ttu-id="25d01-154">Microsoft 365 리소스 계정을 사용 하 여 사용자를 예약할 계획 이라면 [microsoft 365 관리 센터를 사용 하 여 자원 계정 만들기](resource-account-ui.md) 의 지침에 따라 필요한 각 공동 작업 표시줄에 대 한 microsoft 365 리소스 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-154">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="25d01-155">또한 사용자는 리소스 계정에 회의실 라이선스를 추가 하 고 외부 전화 번호, 전화 시스템 또는 비즈니스 음성 라이선스에 대 한 통화를 보내거나 받으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-155">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Phone System or Business Voice license.</span></span>

<span data-ttu-id="25d01-156">개인 사용을 위해 개별 사용자에 게 공동 작업 막대를 할당 하려는 경우에는 추가 계정을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-156">If you want to assign collaboration bars to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="25d01-157">사용자는 개인 계정을 사용 하 여 공동 작업 모음에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-157">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="25d01-158">Microsoft 365 리소스 계정의 표시 이름을 설명 하 고 이해 하기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-158">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="25d01-159">Microsoft 팀의 공동 작업 막대를 검색 하 고 모임에 추가할 때 사용자에 게 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-159">These are the names that users will see when searching for and adding collaboration bars for Microsoft Teams to meetings.</span></span> <span data-ttu-id="25d01-160">*사이트* - *공간 이름*(*최대 회의실 용량*)과 같은 규칙을 사용할 수 있기 때문에, 예를 들어, London의 4 인칭 모임 채팅방에 표시 이름 LON-curie (4)가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-160">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="25d01-162">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="25d01-162">Decision points</span></span>|<ul><li><span data-ttu-id="25d01-163">전용 리소스 계정에 대 한 명명 규칙을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-163">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="25d01-164">개별 계정을 만들지 아니면 대량 프로 비전 스크립트를 사용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-164">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="25d01-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25d01-166">Next steps</span></span>|<ul><li><span data-ttu-id="25d01-167">장치 배포 계획을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-167">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="25d01-168">장치 배포</span><span class="sxs-lookup"><span data-stu-id="25d01-168">Device deployment</span></span>

<span data-ttu-id="25d01-169">다음으로, 장치 및 할당 된 주변 기기 장치를 채팅방에 전달 하는 계획을 만든 다음 설치 및 구성을 진행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-169">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="25d01-171">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="25d01-171">Decision points</span></span>|<ul><li><span data-ttu-id="25d01-172">사이트별 배포를 관리할 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-172">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="25d01-173">사이트에서 Microsoft 팀에 대 한 공동 작업 모음을 설치할 리소스를 식별 하 고 구성 및 테스트를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-173">Identify the resources who will install the collaboration bars for Microsoft Teams on site and undertake the configuration and testing.</span></span></li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="25d01-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25d01-175">Next steps</span></span>|<ul><li><span data-ttu-id="25d01-176">장치 테스트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-176">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="25d01-177">테스트가</span><span class="sxs-lookup"><span data-stu-id="25d01-177">Testing</span></span>

<span data-ttu-id="25d01-178">Microsoft 팀의 공동 작업 모음을 배포한 후에는 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-178">After the collaboration bars for Microsoft Teams have been deployed, you should test them.</span></span> <span data-ttu-id="25d01-179">장치에 로그인 하 고 예상 되는 기능이 배포 된 장치에서 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-179">Sign in to the device and check that the expected capabilities are working on the deployed device.</span></span> <span data-ttu-id="25d01-180">Microsoft 팀 관리 센터의 **장치** 탭에 있는 **공동 작업 모음** 섹션에 장치가 표시 되는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-180">We highly recommend that you verify that the devices are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="25d01-181">품질과 성능을 확인 하기 위해 다양 한 테스트 통화와 모임을 수행 하는 것도 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-181">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="25d01-182">일반 Microsoft 팀을 출시 하는 동안, 통화 품질 대시보드 (CQD)에 대 한 빌드 파일을 구성 하 고, 품질 추세를 모니터링 하 고, 경력의 품질 검토 프로세스에 참여 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-182">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="25d01-183">자세한 내용은 [경험 치 리뷰 가이드](https://aka.ms/qerguide)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25d01-183">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="25d01-184">자산 관리</span><span class="sxs-lookup"><span data-stu-id="25d01-184">Asset management</span></span>

<span data-ttu-id="25d01-185">배포의 일환으로, 자산 이름, 로그인 한 리소스 계정 및 할당 된 주변 기기 장치를 사용 하 여 자산 등록기를 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25d01-185">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25d01-186">관련 항목</span><span class="sxs-lookup"><span data-stu-id="25d01-186">Related topics</span></span>

[<span data-ttu-id="25d01-187">Microsoft 팀 관리 센터를 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 계정 구성</span><span class="sxs-lookup"><span data-stu-id="25d01-187">Configure accounts for collaboration bars for Microsoft Teams using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
