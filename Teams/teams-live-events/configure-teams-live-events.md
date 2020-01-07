---
title: Microsoft 팀에서 실시간 이벤트 설정 구성
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 조직에 보유 된 팀의 live 이벤트에 대 한 설정을 관리 하는 방법에 대해 알아봅니다.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ad9d97c6d4dd6b7eb370bda026dbee3e33f2a32
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952841"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="e11c4-103">Microsoft 팀에서 실시간 이벤트 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e11c4-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="e11c4-104">팀 라이브 이벤트 설정을 사용 하 여 조직에 보유 된 라이브 이벤트에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="e11c4-105">지원 URL을 설정 하 고 타사 영상 배포 공급자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="e11c4-106">이러한 설정은 조직에서 만든 모든 라이브 이벤트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="e11c4-107">Microsoft 팀 관리 센터에서 이러한 설정을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e11c4-108">왼쪽 탐색 창에서 **모임** > **라이브 이벤트 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="e11c4-109">![팀의 라이브 이벤트 설정 스크린샷](../media/teams-live-events-settings.png "Microsoft 팀 관리 센터에서 구성할 수 있는 팀 live 이벤트 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="e11c4-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="e11c4-110">이벤트 지원 URL 설정</span><span class="sxs-lookup"><span data-stu-id="e11c4-110">Set up event support URL</span></span>

<span data-ttu-id="e11c4-111">이 URL은 live 이벤트 참석자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="e11c4-112">라이브 이벤트 중에 참석자에 게 고객 지원에 연락할 수 있는 방법을 제공 하는 조직의 지원 URL을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Microsoft 팀 로고를 표시 하는 아이콘](../media/teams-logo-30x30.png) <span data-ttu-id="e11c4-114">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="e11c4-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e11c4-115">왼쪽 탐색 창에서 **모임** > **라이브 이벤트 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="e11c4-116">**지원 url**에서 조직의 지원 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="e11c4-117">![관리 센터에서 라이브 이벤트에 대 한 URL 설정 지원](../media/teams-live-events-settings-supporturl.png "팀 라이브 이벤트에 대 한 지원 URL 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="e11c4-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="e11c4-118">Windows PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="e11c4-118">Using Windows PowerShell</span></span>
<span data-ttu-id="e11c4-119">다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-119">Run the following:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="e11c4-120">자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e11c4-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="e11c4-121">타사 영상 배포 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="e11c4-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="e11c4-122">Microsoft 비디오 배달 파트너를 통해 SDN (소프트웨어 정의 네트워크) 솔루션 또는 eCDN (enterprise content delivery network) 솔루션을 구입한 경우 팀에서 실시간 이벤트에 대 한 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Microsoft 팀 로고를 표시 하는 아이콘](../media/teams-logo-30x30.png) <span data-ttu-id="e11c4-124">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="e11c4-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e11c4-125">왼쪽 탐색 창에서 **모임** > **라이브 이벤트 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="e11c4-126">**타사 비디오 배포 공급자**아래에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="e11c4-127">![관리 센터의 타사 영상 배포 공급자 설정](../media/teams-live-events-settings-distribution-provider.png "라이브 이벤트의 타사 비디오 배포 공급자 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="e11c4-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="e11c4-128">**타사 배포 공급자 사용** 타사 비디오 배포 공급자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="e11c4-129">**SDN 공급자 이름** 사용 중인 공급자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="e11c4-130">**공급자 라이선스 키** 공급자 연락처에서 받은 라이선스 ID를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="e11c4-131">**SDN API 서식 파일 URL** 공급자 연락처에서 받은 API 서식 파일 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="e11c4-132">Windows PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="e11c4-132">Using Windows PowerShell</span></span>
<span data-ttu-id="e11c4-133">공급자 연락처에서 라이선스 ID 또는 API 토큰과 API 서식 파일을 가져온 후 사용 중인 공급자에 따라 다음 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="e11c4-134">**벌**</span><span class="sxs-lookup"><span data-stu-id="e11c4-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="e11c4-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="e11c4-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="e11c4-136">자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e11c4-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="e11c4-137">외부 앱 또는 장치를 사용 하 여 라이브 이벤트를 만들려는 경우 Microsoft Stream을 사용 하 여 [eCDN 공급자도 구성](https://docs.microsoft.com/stream/network-caching)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e11c4-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="e11c4-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e11c4-138">Related topics</span></span>
- [<span data-ttu-id="e11c4-139">Teams 라이브 이벤트란?</span><span class="sxs-lookup"><span data-stu-id="e11c4-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="e11c4-140">Teams 라이브 이벤트 계획</span><span class="sxs-lookup"><span data-stu-id="e11c4-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="e11c4-141">Teams 라이브 이벤트 설정</span><span class="sxs-lookup"><span data-stu-id="e11c4-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)