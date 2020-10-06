---
title: 모임 녹음/녹화에 OneDrive 및 SharePoint 사용
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 스트림을 비즈니스용 OneDrive 및 SharePoint 모임 기록 저장소로 전환 하는 방법을 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b31972ed662b6752286fa2ff33b80150496cfb0f
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361338"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="1ec63-103">모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="1ec63-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="1ec63-104">Microsoft Stream에서 모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint로의 변경은 단계별로 접근합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="1ec63-105">시작 시 테 넌 트 관리자는 지금이 새 워크플로 옵션을 선택할 수 있으며, 2020 년 10 월부터 비즈니스용 OneDrive 및 SharePoint에 대 한 녹음/녹화 자동 업로드를 표시 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="1ec63-106">11 월에는 스트림을 계속 사용 하기 위해 옵트아웃 해야 하며, 초기 2021에는 모든 고객이 비즈니스용 OneDrive 및 SharePoint를 사용 하 여 새 모임 녹화가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="1ec63-107">Microsoft 팀에는 모임 녹음/녹화를 저장 하는 새로운 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="1ec63-108">Stream에서 출발 하는 경우이 메서드는 Microsoft 365에서 Microsoft OneDrive 및 SharePoint를 사용 하 고 다양 한 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="1ec63-109">비즈니스용 OneDrive 및 SharePoint를 사용 하 여 기록을 저장할 때의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="1ec63-110">TMR (팀 모임 기록) 용 보존 정책 (S + C E5 autoretention 레이블)</span><span class="sxs-lookup"><span data-stu-id="1ec63-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="1ec63-111">비즈니스용 OneDrive 및 SharePoint 정보 관리 혜택</span><span class="sxs-lookup"><span data-stu-id="1ec63-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="1ec63-112">손쉬운 사용 권한 및 공유 설정</span><span class="sxs-lookup"><span data-stu-id="1ec63-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="1ec63-113">명시적 공유로만 게스트 (외부 사용자)와 녹음/녹화 공유</span><span class="sxs-lookup"><span data-stu-id="1ec63-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="1ec63-114">액세스 흐름 요청</span><span class="sxs-lookup"><span data-stu-id="1ec63-114">Request access flow</span></span>
- <span data-ttu-id="1ec63-115">비즈니스용 OneDrive 및 SharePoint 공유 링크 제공</span><span class="sxs-lookup"><span data-stu-id="1ec63-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="1ec63-116">할당량 증가</span><span class="sxs-lookup"><span data-stu-id="1ec63-116">Increased quota</span></span>
- <span data-ttu-id="1ec63-117">모임 녹음/녹화 속도 향상</span><span class="sxs-lookup"><span data-stu-id="1ec63-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="1ec63-118">**로컬** 테 넌 트 이동 지원</span><span class="sxs-lookup"><span data-stu-id="1ec63-118">**Go local** tenant support</span></span>
- <span data-ttu-id="1ec63-119">다중 지역 지원 – 녹음/녹화가 해당 사용자와 관련 된 지역에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="1ec63-120">자체 키 (BYOK) 지원</span><span class="sxs-lookup"><span data-stu-id="1ec63-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="1ec63-121">향상 된 성적 품질 및 강연자 특성</span><span class="sxs-lookup"><span data-stu-id="1ec63-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="1ec63-122">다음과 같은 몇 가지 제한 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="1ec63-123">영어 전용 자막 및 성적 증명서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="1ec63-124">본 대화 내용 또는 해당 콘텐츠는 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="1ec63-125">성적 증명서는 편집할 수 없지만, 캡션을 설정/해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="1ec63-126">녹음/녹화를 공유한 사람을 제어할 수 있지만, 공유 액세스 권한이 있는 사용자는 녹음/녹화를 다운로드 하지 못하도록 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="1ec63-127">녹음/녹화가 완료 되 면 전자 메일을 받을 수 없지만, 완료 되 면 녹음 내용이 모임 채팅에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="1ec63-128">이는 이전에 스트림에서 했던 것 보다 훨씬 더 빠르게 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="1ec63-129">자세한 내용은 "모임 녹음/녹화"를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec63-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="1ec63-130">비즈니스용 OneDrive 및 SharePoint에 대 한 모임 녹음/녹화 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="1ec63-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="1ec63-131">비즈니스용 Skype Online PowerShell 관리 콘솔을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="1ec63-132">a.</span><span class="sxs-lookup"><span data-stu-id="1ec63-132">a.</span></span> <span data-ttu-id="1ec63-133">[비즈니스용 Skype Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec63-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="1ec63-134">b.</span><span class="sxs-lookup"><span data-stu-id="1ec63-134">b.</span></span> <span data-ttu-id="1ec63-135">화면의 지시에 따라 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="1ec63-136">c.</span><span class="sxs-lookup"><span data-stu-id="1ec63-136">c.</span></span> <span data-ttu-id="1ec63-137">컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-137">Restart your machine.</span></span>

2. <span data-ttu-id="1ec63-138">관리자로 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="1ec63-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="1ec63-139">SkypeOnline 커넥터를 가져오고 팀 관리자로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="1ec63-140">[Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 를 사용 하 여 스트림 저장소에서 odsp로 전환 하도록 팀 모임 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="1ec63-141">비즈니스용 OneDrive 및 SharePoint에서 스트림을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="1ec63-142">정책이 **Stream**으로 설정 되어 있는 경우에도 설정 되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="1ec63-143">일반적으로 정책이 설정 되어 있지 않으면 기본 설정은 **스트림**입니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="1ec63-144">그러나이 새로운 변경으로 인해 SharePoint 또는 OneDrive 사용을 옵트아웃 하려면 정책을 **스트림으로** 다시 설정 하 여 해당 설정이 기본값 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="1ec63-145">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="1ec63-145">Frequently asked questions</span></span>

<span data-ttu-id="1ec63-146">**모임 녹화가 저장 되는 위치**</span><span class="sxs-lookup"><span data-stu-id="1ec63-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="1ec63-147">채널이 아닌 모임의 경우 기록은 이라는 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-147">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="1ec63-148">기록 \* \* 모임 녹음/녹화를 시작한 사람에 속한 OneDrive의 최상위 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-148">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="1ec63-149">예</span><span class="sxs-lookup"><span data-stu-id="1ec63-149">Example:</span></span>

  <span data-ttu-id="1ec63-150"><i>레코더의 비즈니스용 OneDrive</i> / **기록**</span><span class="sxs-lookup"><span data-stu-id="1ec63-150"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="1ec63-151">채널 모임의 **경우 기록은 기록 이라는 폴더**의 팀 사이트 문서 라이브러리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-151">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="1ec63-152">예</span><span class="sxs-lookup"><span data-stu-id="1ec63-152">Example:</span></span>

  <span data-ttu-id="1ec63-153"><i>팀 이름-채널 이름</i> / **문서** / **기록**</span><span class="sxs-lookup"><span data-stu-id="1ec63-153"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="1ec63-154">**모임 녹음/녹화를 볼 수 있는 권한이 있는 사람은 누구 인가요?**</span><span class="sxs-lookup"><span data-stu-id="1ec63-154">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="1ec63-155">채널이 아닌 모임의 경우 외부 사용자를 제외한 모든 모임 초대 대 상자가 개인 공유 링크를 자동으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-155">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="1ec63-156">외부 사용자는 모임 이끌이 또는 모임 녹음/녹화를 시작한 사용자가 공유 목록에 명시적으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-156">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="1ec63-157">채널 모임의 경우 사용 권한은 채널의 소유자 및 구성원 목록에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-157">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="1ec63-158">**어떻게 하면 증명서를 관리할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1ec63-158">**How can I manage transcripts?**</span></span>

<span data-ttu-id="1ec63-159">이 미리 보기를 사용 하는 고객에 게는 OneDrive 및 SharePoint로 마이그레이션된 팀 모임 녹음/녹화에 대 한 폐쇄 캡션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-159">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="1ec63-160">여기서는 영어에서 선택 자막으로 시작 하 여 2020 년 10 월에 모임 녹음/녹화에 캡션을 추가 하는 작업을 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-160">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="1ec63-161">[팀 구름 기록](cloud-recording.md) 에 설명 된 대로 기록을 허용 하도록 옵트인 된 고객의 경우 선택 자막을 팀 모임 기록에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-161">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="1ec63-162">캡션은 모든 기능을 보는 사람을 위해 포괄 콘텐츠를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-162">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="1ec63-163">소유자는 팀에서 캡션을 삭제 하지 않는 한 팀에서 성적을 사용할 수 있지만, 캡션을 숨길 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-163">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="1ec63-164">[모임 녹음/녹화를 설정 하거나 해제 하는 방법](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) 보기</span><span class="sxs-lookup"><span data-stu-id="1ec63-164">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="1ec63-165">폐쇄 캡션은 모임이 기록 될 때 60 일간의 팀 모임 기록에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-165">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="1ec63-166">**내 저장소 할당량에 영향을 주는 방법**</span><span class="sxs-lookup"><span data-stu-id="1ec63-166">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="1ec63-167">비즈니스용 OneDrive 및 SharePoint에 파일을 기록 하는 팀 모임에는 해당 서비스의 할당량에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-167">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="1ec63-168">[SharePoint 할당량](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 [비즈니스용 OneDrive 할당량] ()을 참조 하세요 https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="1ec63-168">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="1ec63-169">**팀 모임 녹음/녹화를 재생 하려면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="1ec63-169">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="1ec63-170">파일에 액세스 하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-170">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="1ec63-171">**Deprecating 추가를 계획 하는 경우 기존 비디오는 그대로 유지 되 고 얼마 동안 지속 되나요?**</span><span class="sxs-lookup"><span data-stu-id="1ec63-171">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="1ec63-172">플랫폼으로 스트림은 가까운 장래에 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-172">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="1ec63-173">현재 스트림에 살고 있는 비디오는 마이그레이션을 시작할 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-173">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="1ec63-174">마이그레이션에 따라 이러한 비디오는 ODSP로도 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec63-174">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="1ec63-175">자세한 내용은 [여기](https://docs.microsoft.com/stream/streamnew/classic-migration) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec63-175">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
