---
title: Microsoft Teams에서 라이브 이벤트 설정 구성
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
- enabler-strategic
description: 조직에 있는 Teams 라이브 이벤트에 대한 설정을 관리하는 방법을 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831198"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="ed8e7-103">Microsoft Teams에서 라이브 이벤트 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ed8e7-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="ed8e7-104">Teams 라이브 이벤트 설정을 사용하여 조직에 있는 라이브 이벤트에 대한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="ed8e7-105">지원 URL을 설정하고 타사 비디오 배포 공급자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="ed8e7-106">이러한 설정은 조직에서 만든 모든 라이브 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="ed8e7-107">Microsoft Teams 관리 센터에서 이러한 설정을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ed8e7-108">왼쪽 탐색 모음에서 **모임** 라이브 이벤트  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed8e7-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="ed8e7-109">![Teams 라이브 이벤트 설정 스크린샷](../media/teams-live-events-settings.png "Microsoft Teams 관리 센터에서 구성할 수 있는 Teams 라이브 이벤트 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="ed8e7-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="ed8e7-110">이벤트 지원 URL 설정</span><span class="sxs-lookup"><span data-stu-id="ed8e7-110">Set up event support URL</span></span>

<span data-ttu-id="ed8e7-111">이 URL은 라이브 이벤트 참석자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="ed8e7-112">조직의 지원 URL을 추가하여 라이브 이벤트 중에 참석자 지원에 문의할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](../media/teams-logo-30x30.png) <span data-ttu-id="ed8e7-114">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ed8e7-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ed8e7-115">왼쪽 탐색 모음에서 **모임** 라이브 이벤트  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed8e7-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="ed8e7-116">지원 **URL 아래에서** 조직의 지원 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="ed8e7-117">![관리 센터의 라이브 이벤트에 대한 지원 URL 설정](../media/teams-live-events-settings-supporturl.png "Teams 라이브 이벤트에 대한 지원 URL 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="ed8e7-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="ed8e7-118">다음 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed8e7-118">Using Windows PowerShell</span></span>

<span data-ttu-id="ed8e7-119">다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="ed8e7-120">자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration을 참조하세요.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ed8e7-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="ed8e7-121">타사 비디오 배포 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="ed8e7-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="ed8e7-122">Microsoft 비디오 배달 파트너를 통해 SDN(소프트웨어 정의 네트워크) 솔루션 또는 eCDN(엔터프라이즈 콘텐츠 배달 네트워크) 솔루션을 구입하고 설정한 경우 Teams에서 라이브 이벤트에 대한 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](../media/teams-logo-30x30.png) <span data-ttu-id="ed8e7-124">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="ed8e7-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ed8e7-125">왼쪽 탐색 모음에서 **모임** 라이브 이벤트  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed8e7-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="ed8e7-126">타사 **비디오 배포 공급자에서** 다음을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="ed8e7-127">![관리 센터의 타사 비디오 배포 공급자 설정](../media/teams-live-events-settings-distribution-provider.png "라이브 이벤트에 대한 타사 비디오 배포 공급자 설정 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="ed8e7-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="ed8e7-128">**타사 배포 공급자 사용** 타사 비디오 배포 공급자를 사용하도록 설정하려면 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="ed8e7-129">**SDN 공급자 이름** 사용 하는 공급자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="ed8e7-130">**공급자 라이선스 키** 공급자 연락처에서 받은 라이선스 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="ed8e7-131">**SDN API 템플릿 URL** 공급자 연락처에서 제공한 API 템플릿 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="ed8e7-132">다음 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed8e7-132">Using Windows PowerShell</span></span>
<span data-ttu-id="ed8e7-133">공급자 연락처에서 라이선스 ID 또는 API 토큰 및 API 템플릿을 받은 다음 사용 하는 공급자에 따라 다음 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="ed8e7-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="ed8e7-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="ed8e7-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="ed8e7-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="ed8e7-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="ed8e7-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="ed8e7-137">자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration을 참조하세요.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ed8e7-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="ed8e7-138">외부 앱 또는 디바이스를 사용하여 라이브 이벤트를 만들 계획인 경우 Microsoft Stream을 사용하여 [eCDN 공급자를 구성해야 합니다.](https://docs.microsoft.com/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="ed8e7-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="ed8e7-p104">Microsoft Stream의 사용에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](../tmr-meeting-recording-change.md)로의 변경은 단계별 접근 방식을 사용합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우, 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8e7-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="related-topics"></a><span data-ttu-id="ed8e7-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ed8e7-141">Related topics</span></span>
- [<span data-ttu-id="ed8e7-142">Teams 라이브 이벤트란?</span><span class="sxs-lookup"><span data-stu-id="ed8e7-142">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="ed8e7-143">Teams 라이브 이벤트 계획</span><span class="sxs-lookup"><span data-stu-id="ed8e7-143">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="ed8e7-144">Teams 라이브 이벤트 설정</span><span class="sxs-lookup"><span data-stu-id="ed8e7-144">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
