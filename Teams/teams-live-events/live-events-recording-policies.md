---
title: 라이브 이벤트 기록 정책
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 라이브 이벤트 기록 정책에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cd54bc123b852ff34da9353dd7e250924931420d
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262660"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="d1f50-103">Microsoft Teams의 라이브 이벤트 기록 정책</span><span class="sxs-lookup"><span data-stu-id="d1f50-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="d1f50-104">Microsoft Teams 라이브 이벤트를 기록하기 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="d1f50-105">기록 옵션은 기록 정책을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="d1f50-106">이 문서에서는 다양한 설정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-106">This article describes the various settings.</span></span>

<span data-ttu-id="d1f50-107">PowerShell 명령 [Set-CsTeamsMeetingBroadcastPolicy를](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps) 사용하여 녹음 옵션이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="d1f50-108">설정 및 옵션 동작</span><span class="sxs-lookup"><span data-stu-id="d1f50-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="d1f50-109">라이브 이벤트 녹화를 진행하는 동안 두 가지 이끌이 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="d1f50-110">생산자 및 발표자에 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="d1f50-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="d1f50-111">녹음 파일: 이벤트가 끝났을 때 생산자 및 발표자가 다운로드할 수 있는 녹음 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="d1f50-112">참석자에 사용할 수 있는 기록</span><span class="sxs-lookup"><span data-stu-id="d1f50-112">Recording available for attendees</span></span>

  - <span data-ttu-id="d1f50-113">DVR: DVR(디지털 비디오 레코더)을 사용하면 참석자들이 이벤트 중에 되감기 및 일시 중지를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="d1f50-114">VOD: VOD(VoD) 비디오로 참석자들이 이벤트가 끝났을 때 시청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="d1f50-115">브로드캐스트 녹화 정책 설정</span><span class="sxs-lookup"><span data-stu-id="d1f50-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="d1f50-116">브로드캐스트 정책의 일부로 라이브 이벤트에 대해 녹화를 켜거나 끄기 위해 전환할 수 있는 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="d1f50-117">생산자 및 발표자에 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="d1f50-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="d1f50-118">참석자에 사용할 수 있는 기록</span><span class="sxs-lookup"><span data-stu-id="d1f50-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="d1f50-119">항상 레코드</span><span class="sxs-lookup"><span data-stu-id="d1f50-119">Always record</span></span>               | <span data-ttu-id="d1f50-120">사용하지 않도록 설정되어 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-120">Disabled and selected</span></span>                                | <span data-ttu-id="d1f50-121">사용 및 선택</span><span class="sxs-lookup"><span data-stu-id="d1f50-121">Enabled and selected</span></span>         |
| <span data-ttu-id="d1f50-122">이끌이가 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-122">Organizer can record or not</span></span> | <span data-ttu-id="d1f50-123">기본적으로 사용 및 선택</span><span class="sxs-lookup"><span data-stu-id="d1f50-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="d1f50-124">기본적으로 사용 및 선택</span><span class="sxs-lookup"><span data-stu-id="d1f50-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="d1f50-125">기록 안 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-125">Never record</span></span>               | <span data-ttu-id="d1f50-126">사용하지 않도록 설정되어 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-126">Disabled and not selected</span></span>                            | <span data-ttu-id="d1f50-127">사용하도록 설정되어 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-127">Enabled and not selected</span></span>      |

<span data-ttu-id="d1f50-128">정책이 **Always record로** 설정되면 정책 페이지에는 다음과 같은 옵션이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="d1f50-129">![라이브 이벤트 정책 설정](../media/live-event-recording-policy.png "Microsoft Teams 관리 센터의 라이브 이벤트 정책 설정 스크린샷입니다.")</span><span class="sxs-lookup"><span data-stu-id="d1f50-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="d1f50-130">저장소 및 지속성 동작</span><span class="sxs-lookup"><span data-stu-id="d1f50-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="d1f50-131">옵션</span><span class="sxs-lookup"><span data-stu-id="d1f50-131">Option</span></span>                                       | <span data-ttu-id="d1f50-132">상태</span><span class="sxs-lookup"><span data-stu-id="d1f50-132">State</span></span>   | <span data-ttu-id="d1f50-133">DVR</span><span class="sxs-lookup"><span data-stu-id="d1f50-133">DVR</span></span>                                                   | <span data-ttu-id="d1f50-134">VOD</span><span class="sxs-lookup"><span data-stu-id="d1f50-134">VOD</span></span>                                                     | <span data-ttu-id="d1f50-135">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="d1f50-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="d1f50-136">생산자 및 발표자가 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="d1f50-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="d1f50-137">선택된</span><span class="sxs-lookup"><span data-stu-id="d1f50-137">Selected</span></span>     | <span data-ttu-id="d1f50-138">DVR을 사용할 수 있으며 AMS(Azure Media Services) 자산은 180일 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="d1f50-139">참석자 는 이벤트에 액세스하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="d1f50-140">선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-140">Not Selected</span></span> | <span data-ttu-id="d1f50-141">DVR을 사용할 수 있으며 AMS 자산은 180일 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="d1f50-142">참석자들은 이벤트가 끝났을 때 이벤트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="d1f50-143">사용하지 않도록 설정(선택되지 않았습니다)</span><span class="sxs-lookup"><span data-stu-id="d1f50-143">Disabled (Not selected)</span></span>|<span data-ttu-id="d1f50-144">DVR을 사용할 수 있으며 이벤트 후 AMS 자산이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="d1f50-145">참석자들은 이벤트가 끝났을 때 이벤트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="d1f50-146">생산자 및 발표자가 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="d1f50-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="d1f50-147">선택된</span><span class="sxs-lookup"><span data-stu-id="d1f50-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="d1f50-148">MP4가 만들어지며 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="d1f50-149">선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="d1f50-150">파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f50-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="d1f50-151">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d1f50-151">Related topics</span></span>

- [<span data-ttu-id="d1f50-152">Teams 라이브 이벤트란?</span><span class="sxs-lookup"><span data-stu-id="d1f50-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="d1f50-153">Teams 라이브 이벤트 계획</span><span class="sxs-lookup"><span data-stu-id="d1f50-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="d1f50-154">Teams에서 라이브 이벤트 설정 구성하기</span><span class="sxs-lookup"><span data-stu-id="d1f50-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="d1f50-155">Teams 클라우드 모임 녹화</span><span class="sxs-lookup"><span data-stu-id="d1f50-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)