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
ms.openlocfilehash: 624dcb4f99bc8ae2b83a1b8f62917ac0a5701888
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486773"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="e3f21-103">모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="e3f21-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="e3f21-104">Microsoft Stream을 비즈니스용 OneDrive 및 Microsoft SharePoint for Business에 대 한 변경 내용은 단계적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>


|<span data-ttu-id="e3f21-105">시작일</span><span class="sxs-lookup"><span data-stu-id="e3f21-105">Date</span></span>|<span data-ttu-id="e3f21-106">이벤트</span><span class="sxs-lookup"><span data-stu-id="e3f21-106">Event</span></span>|
|---|-----------------|
|<span data-ttu-id="e3f21-107">초기 Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="e3f21-107">Early Q4 CY20</span></span>|<span data-ttu-id="e3f21-108">**비즈니스용 OneDrive 및 SharePoint에 대 한 팀 모임 녹음/녹화를 옵트인 또는 옵트아웃 (opt out) 할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e3f21-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="e3f21-109">테 넌 트 관리자가 비즈니스용 OneDrive 및 SharePoint에서 옵트인 또는 선택 취소 하 여 PowerShell에서 팀 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e3f21-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="e3f21-110">중급 Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="e3f21-110">Mid Q4 CY20</span></span>|<span data-ttu-id="e3f21-111">**비즈니스용 OneDrive 및 SharePoint에서 팀 모임 녹음/녹화를 옵트아웃 하지 않은 테 넌 트에 대 한 기본값으로 설정**</span><span class="sxs-lookup"><span data-stu-id="e3f21-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="e3f21-112">이는 대부분의 고객에 게 권장 되는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-112">This is the  recommended path for most customers</span></span>|
|<span data-ttu-id="e3f21-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="e3f21-113">Q1 CY21</span></span>|<span data-ttu-id="e3f21-114">**더 이상 허용 되지 않는 클래식 스트림으로 팀 모임 기록 저장**</span><span class="sxs-lookup"><span data-stu-id="e3f21-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="e3f21-115">모든 테 넌 트가 비즈니스용 OneDrive 및 SharePoint에 팀 모임 기록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|


<span data-ttu-id="e3f21-116">Microsoft 팀에는 모임 녹음/녹화를 저장 하는 새로운 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="e3f21-117">이 방법은 기존 Microsoft Stream에서 [새 스트림으로](https://docs.microsoft.com/stream/streamnew/new-stream)전환 하는 첫 번째 단계로, 365 microsoft OneDrive 및 SharePoint에 기록 저장 하 고 다양 한 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="e3f21-118">비즈니스용 OneDrive 및 SharePoint를 사용 하 여 기록을 저장할 때의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="e3f21-119">TMR (팀 모임 기록) 용 보존 정책 (S + C E5 autoretention 레이블)</span><span class="sxs-lookup"><span data-stu-id="e3f21-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="e3f21-120">비즈니스용 OneDrive 및 SharePoint 정보 관리 혜택</span><span class="sxs-lookup"><span data-stu-id="e3f21-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="e3f21-121">손쉬운 사용 권한 및 공유 설정</span><span class="sxs-lookup"><span data-stu-id="e3f21-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="e3f21-122">명시적 공유로만 게스트 (외부 사용자)와 녹음/녹화 공유</span><span class="sxs-lookup"><span data-stu-id="e3f21-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="e3f21-123">액세스 흐름 요청</span><span class="sxs-lookup"><span data-stu-id="e3f21-123">Request access flow</span></span>
- <span data-ttu-id="e3f21-124">비즈니스용 OneDrive 및 SharePoint 공유 링크 제공</span><span class="sxs-lookup"><span data-stu-id="e3f21-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="e3f21-125">할당량 증가</span><span class="sxs-lookup"><span data-stu-id="e3f21-125">Increased quota</span></span>
- <span data-ttu-id="e3f21-126">모임 녹음/녹화 속도 향상</span><span class="sxs-lookup"><span data-stu-id="e3f21-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="e3f21-127">**로컬** 테 넌 트 이동 지원</span><span class="sxs-lookup"><span data-stu-id="e3f21-127">**Go local** tenant support</span></span>
- <span data-ttu-id="e3f21-128">다중 지역 지원 – 녹음/녹화가 해당 사용자와 관련 된 지역에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="e3f21-129">자체 키 (BYOK) 지원</span><span class="sxs-lookup"><span data-stu-id="e3f21-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="e3f21-130">향상 된 성적 품질 및 강연자 특성</span><span class="sxs-lookup"><span data-stu-id="e3f21-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="e3f21-131">다음과 같은 몇 가지 제한 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="e3f21-132">영어 전용 자막 및 성적 증명서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="e3f21-133">본 대화 내용 또는 해당 콘텐츠는 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="e3f21-134">성적 증명서는 편집할 수 없지만, 캡션을 설정/해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="e3f21-135">녹음/녹화를 공유한 사람을 제어할 수 있지만, 공유 액세스 권한이 있는 사용자는 녹음/녹화를 다운로드 하지 못하도록 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="e3f21-136">녹음/녹화가 완료 되 면 전자 메일을 받을 수 없지만, 완료 되 면 녹음 내용이 모임 채팅에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="e3f21-137">이는 이전에 스트림에서 했던 것 보다 훨씬 더 빠르게 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="e3f21-138">자세한 내용은 "모임 녹음/녹화"를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f21-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="e3f21-139">비즈니스용 OneDrive 및 SharePoint에 대 한 모임 녹음/녹화 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="e3f21-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="e3f21-140">비즈니스용 Skype Online PowerShell 관리 콘솔을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="e3f21-141">a.</span><span class="sxs-lookup"><span data-stu-id="e3f21-141">a.</span></span> <span data-ttu-id="e3f21-142">[비즈니스용 Skype Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f21-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="e3f21-143">b.</span><span class="sxs-lookup"><span data-stu-id="e3f21-143">b.</span></span> <span data-ttu-id="e3f21-144">화면의 지시에 따라 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="e3f21-145">c.</span><span class="sxs-lookup"><span data-stu-id="e3f21-145">c.</span></span> <span data-ttu-id="e3f21-146">컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-146">Restart your machine.</span></span>

2. <span data-ttu-id="e3f21-147">관리자로 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="e3f21-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="e3f21-148">SkypeOnline 커넥터를 가져오고 팀 관리자로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="e3f21-149">[Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 를 사용 하 여 스트림 저장소에서 odsp로 전환 하도록 팀 모임 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="e3f21-150">비즈니스용 OneDrive 및 SharePoint에서 스트림을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="e3f21-151">정책이 **Stream**으로 설정 되어 있는 경우에도 설정 되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="e3f21-152">일반적으로 정책이 설정 되어 있지 않으면 기본 설정은 **스트림**입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="e3f21-153">그러나이 새로운 변경으로 인해 SharePoint 또는 OneDrive 사용을 옵트아웃 하려면 정책을 **스트림으로** 다시 설정 하 여 해당 설정이 기본값 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a><span data-ttu-id="e3f21-154">사용 권한 또는 역할 기반 액세스</span><span class="sxs-lookup"><span data-stu-id="e3f21-154">Permissions or role-based access</span></span>


|<span data-ttu-id="e3f21-155">모임 유형</span><span class="sxs-lookup"><span data-stu-id="e3f21-155">Meeting type</span></span>                               | <span data-ttu-id="e3f21-156">누가 레코드를 클릭 했습니까?</span><span class="sxs-lookup"><span data-stu-id="e3f21-156">Who clicked on Record?</span></span>| <span data-ttu-id="e3f21-157">녹화가 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="e3f21-157">Where does the recording land?</span></span>                               |<span data-ttu-id="e3f21-158">누가 액세스 권한이 있나요?</span><span class="sxs-lookup"><span data-stu-id="e3f21-158">Who has access?</span></span> <span data-ttu-id="e3f21-159">R/W, R 또는 공유</span><span class="sxs-lookup"><span data-stu-id="e3f21-159">R/W, R or sharing</span></span>                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="e3f21-160">내부 파티와의 1:1 통화</span><span class="sxs-lookup"><span data-stu-id="e3f21-160">1:1 call with internal parties</span></span>             |<span data-ttu-id="e3f21-161">호출인</span><span class="sxs-lookup"><span data-stu-id="e3f21-161">Caller</span></span>                 |<span data-ttu-id="e3f21-162">발신자의 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="e3f21-162">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="e3f21-163">-호출자가 소유자이 고 전체 권한 (동일한 테 넌 트)에 읽기 전용 액세스 권한이 있는 경우 공유 액세스-피호출자 (다른 테 넌 트에 있는 경우)는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-163">- Caller is owner, has full rights  - Callee (if in the same tenant) has read only access, no sharing access -  Callee (if in different tenant) has no access.</span></span> <span data-ttu-id="e3f21-164">호출자는이를 피호출자와 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-164">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="e3f21-165">내부 파티와의 1:1 통화</span><span class="sxs-lookup"><span data-stu-id="e3f21-165">1:1 call with internal parties</span></span>             |<span data-ttu-id="e3f21-166">피호출자</span><span class="sxs-lookup"><span data-stu-id="e3f21-166">Callee</span></span>                 |<span data-ttu-id="e3f21-167">피호출자의 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="e3f21-167">Callee’s OneDrive for Business account</span></span>                        |<span data-ttu-id="e3f21-168">-피호출자는 소유자 이며, 모든 권한 호출자 (동일한 테 넌 트에 읽기 전용 액세스 권한이 있는 경우, 공유 액세스 호출자 없음 (다른 테 넌 트에 있는 경우)에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-168">- Callee is owner, has full rights - Caller (if in the same tenant has read only access, no sharing access - Caller (if in different tenant) has no access.</span></span> <span data-ttu-id="e3f21-169">피호출자가이를 피호출자와 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-169">Callee must share it to the Callee</span></span>|
|<span data-ttu-id="e3f21-170">1:1 통화 (외부 통화 포함)</span><span class="sxs-lookup"><span data-stu-id="e3f21-170">1:1 call with an external call</span></span>             |<span data-ttu-id="e3f21-171">호출인</span><span class="sxs-lookup"><span data-stu-id="e3f21-171">Caller</span></span>                 |<span data-ttu-id="e3f21-172">발신자의 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="e3f21-172">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="e3f21-173">-호출자가 소유자이 고 전체 권한이 있는 경우 호출 수신자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-173">- Caller is owner, has full rights - Callee has no access.</span></span> <span data-ttu-id="e3f21-174">호출자는이를 피호출자와 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-174">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="e3f21-175">1:1 통화 (외부 통화 포함)</span><span class="sxs-lookup"><span data-stu-id="e3f21-175">1:1 call with an external call</span></span>             |<span data-ttu-id="e3f21-176">피호출자</span><span class="sxs-lookup"><span data-stu-id="e3f21-176">Callee</span></span>                 |<span data-ttu-id="e3f21-177">발신자의 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="e3f21-177">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="e3f21-178">-피호출자는 소유자 이며, 모든 권한이 있는 호출자는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-178">- Callee is owner, has full rights - Caller has no access.</span></span> <span data-ttu-id="e3f21-179">피호출자가이를 호출자에 게 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-179">Callee must share it to the Caller</span></span>|
|<span data-ttu-id="e3f21-180">그룹 통화</span><span class="sxs-lookup"><span data-stu-id="e3f21-180">Group call</span></span>                                 |<span data-ttu-id="e3f21-181">통화의 모든 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-181">Any member of the call</span></span> |<span data-ttu-id="e3f21-182">Record의 비즈니스용 OneDrive 계정에서 클릭 한 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-182">Member who clicked on Record’s OneDrive for Business account</span></span>  |<span data-ttu-id="e3f21-183">-레코드를 클릭 한 구성원에 게 모든 권한이 있는 경우-동일한 테 넌 트의 다른 구성원에 게 읽기 권한이 있습니다. 다른 구성원에 대 한 권한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-183">- Member who clicked on Record has full rights - Other members from the same tenant have Read rights - Other members for different have no rights to it.</span></span>|
|<span data-ttu-id="e3f21-184">임시/예약 된 모임</span><span class="sxs-lookup"><span data-stu-id="e3f21-184">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="e3f21-185">구성 도우미</span><span class="sxs-lookup"><span data-stu-id="e3f21-185">Organizer</span></span>              |<span data-ttu-id="e3f21-186">조직자의 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="e3f21-186">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="e3f21-187">-이끌이는 모든 녹음/녹화에 대 한 모든 권한을 가집니다-모임의 다른 모든 구성원은 읽기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-187">- Organizer has full rights to the recording - All other members of the meeting have read access</span></span>|
|<span data-ttu-id="e3f21-188">임시/예약 된 모임</span><span class="sxs-lookup"><span data-stu-id="e3f21-188">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="e3f21-189">다른 모임 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-189">Other meeting member</span></span>   |<span data-ttu-id="e3f21-190">레코드를 클릭 한 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-190">Member who clicked on Record</span></span>                                  |<span data-ttu-id="e3f21-191">-레코드를 클릭 한 구성원에 게 녹음/녹화 구성 도우미에 대 한 모든 권한이 있는 경우 모든 구성원에 게 편집 권한이 있고 공유할 수 있음-다른 모든 구성원이 읽기 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-191">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members have read access</span></span>|
|<span data-ttu-id="e3f21-192">외부 사용자와의 임시/예약 된 모임</span><span class="sxs-lookup"><span data-stu-id="e3f21-192">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="e3f21-193">구성 도우미</span><span class="sxs-lookup"><span data-stu-id="e3f21-193">Organizer</span></span>              |<span data-ttu-id="e3f21-194">조직자의 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="e3f21-194">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="e3f21-195">이끌이는 읽기 권한이 있으므로-organizer에는 같은 테 넌 트의 모든 다른 구성원의 기록에 대 한 모든 권한이 있습니다. 다른 모든 외부 구성원은 액세스 권한이 없으며 이끌이는이를 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-195">- Organizer has full rights to the recording - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="e3f21-196">외부 사용자와의 임시/예약 된 모임</span><span class="sxs-lookup"><span data-stu-id="e3f21-196">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="e3f21-197">다른 모임 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-197">Other meeting member</span></span>   |<span data-ttu-id="e3f21-198">레코드를 클릭 한 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-198">Member who clicked on Record</span></span>                                  |<span data-ttu-id="e3f21-199">-레코드를 클릭 한 구성원에 게 녹음/녹화 구성 도우미에 대 한 모든 권한이 있는 경우 이끌이는 읽기 권한이 있고, 다른 모든 외부 구성원은 액세스할 수 없으며, 이끌이는이를 공유 해야 하는 경우에는 같은 테 넌 트에서 모임의 모든 구성원을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-199">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="e3f21-200">채널 모임</span><span class="sxs-lookup"><span data-stu-id="e3f21-200">Channel meeting</span></span>                            |<span data-ttu-id="e3f21-201">채널 구성원</span><span class="sxs-lookup"><span data-stu-id="e3f21-201">Channel Member</span></span>         |<span data-ttu-id="e3f21-202">해당 채널에 대 한 팀의 SharePoint 위치</span><span class="sxs-lookup"><span data-stu-id="e3f21-202">Teams' SharePoint location for that channel</span></span>                   |<span data-ttu-id="e3f21-203">-레코드를 클릭 한 구성원에 게 녹음/녹화에 대 한 편집 권한이 있는 경우-다른 모든 구성원의 권한은 채널의 SharePoint 사용 권한에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-203">- Member who clicked on Record has edit rights to the recording  - Every other member’s permissions are based off of the Channel SharePoint permissions</span></span>|


## <a name="frequently-asked-questions"></a><span data-ttu-id="e3f21-204">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="e3f21-204">Frequently asked questions</span></span>

<span data-ttu-id="e3f21-205">**모임 녹화가 저장 되는 위치**</span><span class="sxs-lookup"><span data-stu-id="e3f21-205">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="e3f21-206">채널이 아닌 모임의 경우 녹음/녹화는 모임 녹음/녹화를 시작한 사람에 속한 OneDrive의 상위 수준 **에 있는 기록** 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-206">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="e3f21-207">예</span><span class="sxs-lookup"><span data-stu-id="e3f21-207">Example:</span></span>

  <span data-ttu-id="e3f21-208"><i>레코더의 비즈니스용 OneDrive</i> / **기록**</span><span class="sxs-lookup"><span data-stu-id="e3f21-208"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="e3f21-209">채널 모임의 **경우 기록은 기록 이라는 폴더**의 팀 사이트 문서 라이브러리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-209">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="e3f21-210">예</span><span class="sxs-lookup"><span data-stu-id="e3f21-210">Example:</span></span>

  <span data-ttu-id="e3f21-211"><i>팀 이름-채널 이름</i> / **문서** / **기록**</span><span class="sxs-lookup"><span data-stu-id="e3f21-211"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="e3f21-212">**이전 직원의 녹음/녹화를 처리 하려면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e3f21-212">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="e3f21-213">비디오는 OneDrive 및 SharePoint의 다른 파일과 유사 하므로 직원을 떠난 후 소유권 및 보존을 처리 하는 것은 일반 [OneDrive 및 sharepoint 프로세스]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-213">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="e3f21-214">**모임 녹음/녹화를 볼 수 있는 권한이 있는 사람은 누구 인가요?**</span><span class="sxs-lookup"><span data-stu-id="e3f21-214">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="e3f21-215">채널이 아닌 모임의 경우 외부 사용자를 제외한 모든 모임 초대 대 상자가 개인 공유 링크를 자동으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-215">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="e3f21-216">외부 사용자는 모임 이끌이 또는 모임 녹음/녹화를 시작한 사용자가 공유 목록에 명시적으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-216">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="e3f21-217">채널 모임의 경우 사용 권한은 채널의 소유자 및 구성원 목록에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-217">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="e3f21-218">**어떻게 하면 증명서를 관리할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e3f21-218">**How can I manage transcripts?**</span></span>

<span data-ttu-id="e3f21-219">이 미리 보기를 사용 하는 고객에 게는 OneDrive 및 SharePoint로 마이그레이션된 팀 모임 녹음/녹화에 대 한 폐쇄 캡션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-219">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="e3f21-220">여기서는 영어에서 선택 자막으로 시작 하 여 2020 년 10 월에 모임 녹음/녹화에 캡션을 추가 하는 작업을 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-220">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="e3f21-221">[팀 구름 기록](cloud-recording.md) 에 설명 된 대로 기록을 허용 하도록 옵트인 된 고객의 경우 선택 자막을 팀 모임 기록에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-221">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="e3f21-222">캡션은 모든 기능을 보는 사람을 위해 포괄 콘텐츠를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-222">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="e3f21-223">소유자는 팀에서 캡션을 삭제 하지 않는 한 팀에서 성적을 사용할 수 있지만, 캡션을 숨길 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-223">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="e3f21-224">[모임 녹음/녹화를 설정 하거나 해제 하는 방법](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) 보기</span><span class="sxs-lookup"><span data-stu-id="e3f21-224">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="e3f21-225">폐쇄 캡션은 모임이 기록 될 때 60 일간의 팀 모임 기록에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-225">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="e3f21-226">**내 저장소 할당량에 영향을 주는 방법**</span><span class="sxs-lookup"><span data-stu-id="e3f21-226">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="e3f21-227">비즈니스용 OneDrive 및 SharePoint에 파일을 기록 하는 팀 모임에는 해당 서비스의 할당량에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-227">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="e3f21-228">[SharePoint 할당량](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 및 [비즈니스용 OneDrive 할당량] ()을 참조 하세요 https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="e3f21-228">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="e3f21-229">**팀 모임 녹음/녹화를 재생 하려면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e3f21-229">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="e3f21-230">파일에 액세스 하는 위치에 따라 비즈니스용 OneDrive 또는 SharePoint의 비디오 플레이어에서 비디오가 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-230">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="e3f21-231">**Deprecating 추가를 계획 하는 경우 기존 비디오는 그대로 유지 되 고 얼마 동안 지속 되나요?**</span><span class="sxs-lookup"><span data-stu-id="e3f21-231">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="e3f21-232">플랫폼으로 스트림은 가까운 장래에 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-232">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="e3f21-233">현재 스트림에 살고 있는 비디오는 마이그레이션을 시작할 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-233">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="e3f21-234">마이그레이션에 따라 이러한 비디오는 ODSP로도 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f21-234">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="e3f21-235">자세한 내용은 [여기](https://docs.microsoft.com/stream/streamnew/classic-migration) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f21-235">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
