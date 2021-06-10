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
ms.openlocfilehash: 8d25f37f94a514b83bd37e44d1b022bac064a839
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739658"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="a51a7-103">라이브 이벤트 기록 정책은 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a51a7-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="a51a7-104">라이브 이벤트를 기록하기 위한 몇 가지 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="a51a7-105">기록 옵션은 기록 정책을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="a51a7-106">이 문서에서는 다양한 설정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-106">This article describes the various settings.</span></span>

<span data-ttu-id="a51a7-107">기록 옵션은 PowerShell 명령 [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)를 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="a51a7-108">설정 및 옵션 동작</span><span class="sxs-lookup"><span data-stu-id="a51a7-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="a51a7-109">라이브 이벤트 녹화를 진행하는 동안 두 가지 이끌이 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="a51a7-110">생산자 및 발표자에 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="a51a7-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="a51a7-111">녹음 파일: 이벤트가 끝났을 때 생산자 및 발표자가 다운로드할 수 있는 녹음 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="a51a7-112">참석자에 사용할 수 있는 기록</span><span class="sxs-lookup"><span data-stu-id="a51a7-112">Recording available for attendees</span></span>

  - <span data-ttu-id="a51a7-113">DVR: DVR(디지털 비디오 레코더)을 사용하면 참석자들이 이벤트 중에 되감기 및 일시 중지를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="a51a7-114">VOD: VOD(VoD) 비디오로 참석자들이 이벤트가 끝났을 때 시청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="a51a7-115">브로드캐스트 녹화 정책 설정</span><span class="sxs-lookup"><span data-stu-id="a51a7-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="a51a7-116">브로드캐스트 정책의 일부로 라이브 이벤트에 대해 녹화를 켜거나 끄기 위해 전환할 수 있는 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="a51a7-117">생산자 및 발표자에 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="a51a7-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="a51a7-118">참석자에 사용할 수 있는 기록</span><span class="sxs-lookup"><span data-stu-id="a51a7-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="a51a7-119">항상 레코드</span><span class="sxs-lookup"><span data-stu-id="a51a7-119">Always record</span></span>               | <span data-ttu-id="a51a7-120">사용하지 않도록 설정되어 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-120">Disabled and selected</span></span>                                | <span data-ttu-id="a51a7-121">사용 및 선택</span><span class="sxs-lookup"><span data-stu-id="a51a7-121">Enabled and selected</span></span>         |
| <span data-ttu-id="a51a7-122">이끌이가 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-122">Organizer can record or not</span></span> | <span data-ttu-id="a51a7-123">기본적으로 사용 및 선택</span><span class="sxs-lookup"><span data-stu-id="a51a7-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="a51a7-124">기본적으로 사용 및 선택</span><span class="sxs-lookup"><span data-stu-id="a51a7-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="a51a7-125">기록 안 합니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-125">Never record</span></span>               | <span data-ttu-id="a51a7-126">사용하지 않도록 설정되어 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-126">Disabled and not selected</span></span>                            | <span data-ttu-id="a51a7-127">사용하지 않도록 설정되어 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="a51a7-128">Storage 및 지속성 동작</span><span class="sxs-lookup"><span data-stu-id="a51a7-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="a51a7-129">옵션</span><span class="sxs-lookup"><span data-stu-id="a51a7-129">Option</span></span>                                       | <span data-ttu-id="a51a7-130">상태</span><span class="sxs-lookup"><span data-stu-id="a51a7-130">State</span></span>   | <span data-ttu-id="a51a7-131">DVR</span><span class="sxs-lookup"><span data-stu-id="a51a7-131">DVR</span></span>                                                   | <span data-ttu-id="a51a7-132">VOD</span><span class="sxs-lookup"><span data-stu-id="a51a7-132">VOD</span></span>                                                     | <span data-ttu-id="a51a7-133">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="a51a7-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="a51a7-134">참석자에 사용할 수 있는 기록</span><span class="sxs-lookup"><span data-stu-id="a51a7-134">Recording available for attendees</span></span> | <span data-ttu-id="a51a7-135">선택된</span><span class="sxs-lookup"><span data-stu-id="a51a7-135">Selected</span></span>     | <span data-ttu-id="a51a7-136">DVR을 사용할 수 있으며 AMS(Azure Media Services) 자산은 180일 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="a51a7-137">참석자 는 이벤트에 액세스하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="a51a7-138">선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-138">Not Selected</span></span> | <span data-ttu-id="a51a7-139">DVR을 사용할 수 있으며 AMS 자산은 180일 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="a51a7-140">참석자들은 이벤트가 끝났을 때 이벤트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="a51a7-141">사용하지 않도록 설정(선택되지 않았습니다)</span><span class="sxs-lookup"><span data-stu-id="a51a7-141">Disabled (Not selected)</span></span>|<span data-ttu-id="a51a7-142">DVR을 사용할 수 있으며 이벤트 후 AMS 자산이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="a51a7-143">참석자들은 이벤트가 끝났을 때 이벤트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="a51a7-144">생산자 및 발표자가 사용할 수 있는 녹화</span><span class="sxs-lookup"><span data-stu-id="a51a7-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="a51a7-145">선택된</span><span class="sxs-lookup"><span data-stu-id="a51a7-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="a51a7-146">MP4가 만들어지며 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="a51a7-147">선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="a51a7-148">파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a51a7-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="a51a7-149">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a51a7-149">Related topics</span></span>

- [<span data-ttu-id="a51a7-150">Teams 라이브 이벤트란?</span><span class="sxs-lookup"><span data-stu-id="a51a7-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="a51a7-151">Teams 라이브 이벤트 계획</span><span class="sxs-lookup"><span data-stu-id="a51a7-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="a51a7-152">Teams에서 라이브 이벤트 설정 구성하기</span><span class="sxs-lookup"><span data-stu-id="a51a7-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="a51a7-153">Teams 클라우드 모임 녹화</span><span class="sxs-lookup"><span data-stu-id="a51a7-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
