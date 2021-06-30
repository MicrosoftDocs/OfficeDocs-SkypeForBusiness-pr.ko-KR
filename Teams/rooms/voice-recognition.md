---
title: 음성 인식(음성 프로필)에 대한 테넌트 관리 Teams 룸
author: cichur
ms.author: v-cichur
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 회의실에서 음성 인식(음성 프로필)에 대한 테넌트 Teams 알아보세요.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96f82b398ff75cdaf651eb841c412c502c5108d4
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203587"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a><span data-ttu-id="a3af6-103">지능형 스피커에 대한 음성 인식 기술 컨트롤 관리</span><span class="sxs-lookup"><span data-stu-id="a3af6-103">Manage voice recognition technology controls for an Intelligent Speaker</span></span>

<span data-ttu-id="a3af6-104">지능형 스피커는 음성 프로필 정보를 사용하여 라이브 전사에서 누구를 말한지 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-104">An Intelligent Speaker uses voice profile information to recognize who said what in live transcription.</span></span> <span data-ttu-id="a3af6-105">회의실에 Microsoft Teams 룸 Windows 지능형 스피커가 장착되어 있는 경우 모임 중에 라이브 전사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-105">When a Microsoft Teams Rooms for Windows meeting room is equipped with an Intelligent Speaker, live transcription can be used during the meeting.</span></span> <span data-ttu-id="a3af6-106">이 문서에서는 테넌트 관리자인 사용자가 음성 인식에 사용되는 음성 프로파일링을 제어하여 라이브 전사 생성 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-106">This article explains how you, a tenant admin, control the voice profiling that's used for voice recognition to generate live transcription.</span></span> <span data-ttu-id="a3af6-107">조직에서 음성 인식 및 다음 기능을 사용하는 정도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-107">You can control to what degree the organization is using voice recognition and the following features:</span></span>

- <span data-ttu-id="a3af6-108">전사에서 발표자 이름을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-108">Edit the speaker's name in transcripts.</span></span>
- <span data-ttu-id="a3af6-109">대본에서 단일 발화의 발언을 변경하거나 대본의 모든 발화에서 스피커를 변경합니다(하지만 향후 대본에는 제공되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="a3af6-109">Change the speaker of a single utterance in the transcript or change the speaker in all the utterances in the transcript (but not on future transcripts).</span></span>
- <span data-ttu-id="a3af6-110">모임에 나열된 사용자에 대한 발표자 ID를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-110">Change the speaker identification for the people who are listed in the meeting.</span></span>
- <span data-ttu-id="a3af6-111">모든 대본에서 해당 스피커로 식별된 하나 이상의 발언의 식별을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-111">Remove the identification of one or more utterances identified as that speaker, on every transcript.</span></span>

## <a name="review-intelligent-speaker-requirements"></a><span data-ttu-id="a3af6-112">지능형 스피커 요구 사항 검토</span><span class="sxs-lookup"><span data-stu-id="a3af6-112">Review Intelligent Speaker requirements</span></span>

<span data-ttu-id="a3af6-113">지능형 스피커에는 특수 7개 마이크 배열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-113">An Intelligent Speaker includes a special seven-microphone array.</span></span> <span data-ttu-id="a3af6-114">시스템은 음성 프로필 정보를 사용하여 회의실에서 최대 10명까지의 음성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-114">The system uses voice profile information to identify voices of up to 10 people in meeting rooms.</span></span>

<span data-ttu-id="a3af6-115">다음 항목은 지능형 스피커 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-115">The following items are Intelligent Speaker requirements:</span></span>

- <span data-ttu-id="a3af6-116">고객 테넌트는 미국(북아메리카)에 있어야 합니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a3af6-116">The customer tenant must be located in the U.S. (North America).<sup>1</sup></span></span>
- <span data-ttu-id="a3af6-117">회의실에 최대 10명이 참석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-117">The meeting room should have a maximum of 10 people present in person.</span></span>
- <span data-ttu-id="a3af6-118">회의실에 최소 7Mbps의 업로드 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-118">The meeting room has an upload link of minimum 7 Mbps.</span></span>

 <span data-ttu-id="a3af6-119"><sup>1</sup> 지능형 스피커 및 관련 음성 프로필 및 사용량은 EN-US 언어 및 미국(NA-미국 지역) 테넌트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-119"><sup>1</sup> An Intelligent Speaker and associated voice profile and usage will only be available in EN-US language and for US (NA-US region) tenants.</span></span> <span data-ttu-id="a3af6-120">테넌트 사용자가 특성 전사에 지능형 스피커를 등록하고 사용하는 경우 두 조건 모두 true가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-120">Both conditions must be true for a tenant user to enroll and use an Intelligent Speaker for attributed transcription.</span></span>

## <a name="set-up-an-intelligent-speaker"></a><span data-ttu-id="a3af6-121">지능형 스피커 설정</span><span class="sxs-lookup"><span data-stu-id="a3af6-121">Set up an Intelligent Speaker</span></span>

<span data-ttu-id="a3af6-122">지능형 스피커는 USB를 사용하여 본체에 Teams 룸 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-122">An Intelligent Speaker connects directly using USB to the Teams Rooms console.</span></span> <span data-ttu-id="a3af6-123">최상의 결과를 얻기 위해 Yealink 브랜드 지능형 스피커를 Yealink 브랜드 콘솔과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-123">For best results, a Yealink brand Intelligent Speaker should be used with a Yealink brand console.</span></span>

> [!NOTE]
> <span data-ttu-id="a3af6-124">Yealink 지능형 **스피커는** Yealink 콘솔과 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-124">A Yealink Intelligent Speaker **must** be used with a Yealink console.</span></span>

> [!NOTE]
> <span data-ttu-id="a3af6-125">Logitech에 연결된 지능형 스피커는 지원하지 Surface Pro Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="a3af6-125">We don't support an Intelligent Speaker connected to Logitech Surface Pro Microsoft Teams Rooms.</span></span> <span data-ttu-id="a3af6-126">도크를 통해 지능형 Teams 룸 인식할 수 없는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-126">There is a known issue that Teams Rooms can't recognize the Intelligent Speaker through the dock.</span></span>

<span data-ttu-id="a3af6-127">지능형 스피커는 벽과 노트북과 같은 큰 개체에서 8인치(20cm) 이상 떨어져 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-127">An Intelligent Speaker should be placed at least 8 inches (20 cm) away from walls and large objects, such as laptops.</span></span> <span data-ttu-id="a3af6-128">지능형 스피커 USB 케이블이 설치에 충분하지 않은 경우 케이블 확장 장치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-128">If the Intelligent Speaker USB cable isn't long enough for your setup, use cable extenders.</span></span>

1. <span data-ttu-id="a3af6-129">관리자 권한으로 본체에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-129">Sign in to the console as administrator.</span></span>
2. <span data-ttu-id="a3af6-130">지능형 Teams 마이크 및 스피커와 일치하게 디바이스 설정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-130">Set the Teams device settings to match the Intelligent Speaker microphone and speaker.</span></span>
   <span data-ttu-id="a3af6-131">또한 룸 콘솔 대신 TAC 포털을 통해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-131">You can also do this through the TAC portal instead of at the room console.</span></span>

   <span data-ttu-id="a3af6-132">이 다이어그램은 디바이스에 데이터 상자가 있는 경우 지능형 스피커가 디바이스에 연결된 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-132">The diagram shows how the Intelligent Speaker is connected to the device if the device includes a data box.</span></span>

   ![<span data-ttu-id="a3af6-133">스피커, 전원 및 데이터 상자가 있는 지능형 스피커 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-133">The Intelligent Speaker setup with the speaker, the power and data box.</span></span> <span data-ttu-id="a3af6-134">한 줄은 본체의 USB 포트로 이동하고 다른 줄은 전원이 공급됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-134">One line goes to the USB port of the console, and the other line goes to power.</span></span> ](../media/intelligent-speakers1.png)

   <span data-ttu-id="a3af6-135">이 다이어그램은 디바이스에 데이터 상자가 없는 경우 지능형 스피커가 디바이스에 연결되는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-135">The diagram shows how the Intelligent Speaker is connected to the device if the device doesn't include a data box.</span></span>

   ![<span data-ttu-id="a3af6-136">스피커가 본체에 직접 연결된 지능형 스피커 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-136">The Intelligent Speaker setup with the speaker connecting directly to the console.</span></span> ](../media/intelligent-speakers2.png)

> [!Note]
> <span data-ttu-id="a3af6-137">EPOS 및 Yealink 디바이스에는 "EPOS" 또는 "Yealink" UAC2_RENDER 마이크 이름에 "UAC2_TEAMS"가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-137">EPOS and Yealink devices should have "EPOS" or "Yealink" prefix and contain "UAC2_RENDER" in the speaker name and "UAC2_TEAMS" in the microphone name.</span></span> <span data-ttu-id="a3af6-138">드롭다운 메뉴에서 이러한 마이크 및 스피커 이름을 찾을 수 없는 경우 Intelligent Speaker 디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-138">If you don't find these microphone and speaker names in the dropdown menu, restart the Intelligent Speaker device.</span></span>

## <a name="enable-an-intelligent-speaker-user-recognition"></a><span data-ttu-id="a3af6-139">지능형 스피커 사용자 인식 사용</span><span class="sxs-lookup"><span data-stu-id="a3af6-139">Enable an Intelligent Speaker user recognition</span></span>

<span data-ttu-id="a3af6-140">지능형 스피커가 있는 모든 모임에서 음성 프로필 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-140">Voice profile data can be used in any meeting with an Intelligent Speaker.</span></span> <span data-ttu-id="a3af6-141">모임 [Teams](../meeting-policies-in-teams.md#allow-transcription) 정책 및 [PowerShell 모임 cmdlet을](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3af6-141">See [Teams meetings policies](../meeting-policies-in-teams.md#allow-transcription) and the [PowerShell meeting cmdlets](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) for information on the meeting settings.</span></span>

<span data-ttu-id="a3af6-142">사용자의 음성 프로필 데이터는 정책이 구분하도록 설정되거나 모임이 아닌 초대자를 모임 중에 볼 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-142">The voice profile data of the user is created when the policy is set to distinguish or a non-meeting invitee walks in during the meeting.</span></span> <span data-ttu-id="a3af6-143">모임이 끝날 때 음성 프로필 데이터가 비우기됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-143">The voice profile data is dismissed at the end of the meeting.</span></span>

<span data-ttu-id="a3af6-144">다음은 지능형 스피커 및 사용자 인식을 설정하는 데 필요한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-144">The following are the required policies to set an Intelligent Speaker and user recognition.</span></span>

|<span data-ttu-id="a3af6-145">정책</span><span class="sxs-lookup"><span data-stu-id="a3af6-145">Policy</span></span>|<span data-ttu-id="a3af6-146">설명</span><span class="sxs-lookup"><span data-stu-id="a3af6-146">Description</span></span>|<span data-ttu-id="a3af6-147">값 및 동작</span><span class="sxs-lookup"><span data-stu-id="a3af6-147">Values and Behavior</span></span>|
|-|-|-|
|<span data-ttu-id="a3af6-148">enrollUserOverride</span><span class="sxs-lookup"><span data-stu-id="a3af6-148">enrollUserOverride</span></span>|<span data-ttu-id="a3af6-149">테넌트에 대한 음성 프로필 캡처 또는 Teams 설정에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-149">Use to set voice profile capture, or enrollment, in Teams settings for a tenant.</span></span> |<span data-ttu-id="a3af6-150">**사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="a3af6-150">**Disabled**</span></span><br><ul><li> <span data-ttu-id="a3af6-151">등록하지 않은 사용자는 보기, 등록 또는 다시 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-151">Users who have never enrolled can't view, enroll, or re-enroll.</span></span><li><span data-ttu-id="a3af6-152">등록 흐름에 대한 진입점은 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-152">The entry point to the enrollment flow will be hidden.</span></span><li><span data-ttu-id="a3af6-153">사용자가 등록 페이지에 대한 링크를 선택하면 해당 조직에서 이 기능을 사용하도록 설정하지 않았다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-153">If users select a link to the enrollment page, they'll see a message that states this feature isn't enabled for their organization.</span></span>  <li><span data-ttu-id="a3af6-154">등록한 사용자는 설정에서 음성 프로필을 보고 제거할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-154">Users who have enrolled can view and remove their voice profile in the Teams settings.</span></span> <span data-ttu-id="a3af6-155">음성 프로필을 제거하면 등록 흐름을 보고, 액세스하거나, 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-155">Once they remove their voice profile, they won't be able to view, access, or complete the enrollment flow.</span></span></li></ul><br><span data-ttu-id="a3af6-156">**사용 가능**</span><span class="sxs-lookup"><span data-stu-id="a3af6-156">**Enabled**</span></span><br><ul><li> <span data-ttu-id="a3af6-157">사용자는 등록 흐름을 보고, 액세스하고, 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-157">Users can view, access, and complete the enrollment flow.</span></span><li><span data-ttu-id="a3af6-158">진입점은 인식 탭의 Teams 설정 페이지에 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a3af6-158">The entry point will show on Teams settings page under the **Recognition** tab.</span></span></li></ul>|
|<span data-ttu-id="a3af6-159">roomAttributeUserOverride</span><span class="sxs-lookup"><span data-stu-id="a3af6-159">roomAttributeUserOverride</span></span>|<span data-ttu-id="a3af6-160">회의실에서 음성 기반 사용자 ID를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-160">Control the voice-based user identification in meeting rooms.</span></span> <span data-ttu-id="a3af6-161">이 설정은 계정의 Teams 룸 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-161">This setting is required for Teams Rooms accounts.</span></span>| <span data-ttu-id="a3af6-162">**해제**</span><span class="sxs-lookup"><span data-stu-id="a3af6-162">**Off**</span></span><br><ul><li><span data-ttu-id="a3af6-163">Teams 룸 디바이스는 방에서 오디오 스트림 저장 대역폭을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-163">The Teams Rooms device won't send audio stream-saving bandwidth from the room.</span></span> <li><span data-ttu-id="a3af6-164">회의실 사용자는 기인하거나 구분되지 않습니다. 음성 서명은 검색되거나 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-164">Meeting room users won't be attributed or distinguished, and their voice signatures won't be retrieved or used at all.</span></span><li><span data-ttu-id="a3af6-165">회의실 사용자는 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-165">Meeting room users are unknown.</span></span></li></ul> <br><span data-ttu-id="a3af6-166">**특성**</span><span class="sxs-lookup"><span data-stu-id="a3af6-166">**Attribute**</span></span><br><ul><li><span data-ttu-id="a3af6-167">룸 사용자는 등록 상태에 따라 기인됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-167">Rooms users will be attributed based on their enrollment status.</span></span><li><span data-ttu-id="a3af6-168">등록된 사용자는 전사에 해당 이름과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-168">Users who are enrolled are shown with their name in the transcription.</span></span>  <li><span data-ttu-id="a3af6-169">등록되지 않은 사용자는 스피커 n으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-169">Users who aren't enrolled show as Speaker n.</span></span><li><span data-ttu-id="a3af6-170">Teams 룸 디바이스는 방에서 7개의 오디오 스트림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-170">The Teams Rooms device will send seven audio streams from the room.</span></span></ul> <br><span data-ttu-id="a3af6-171">**구분**</span><span class="sxs-lookup"><span data-stu-id="a3af6-171">**Distinguish**</span></span><br> <span data-ttu-id="a3af6-172">*이 설정은 나중에 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="a3af6-172">*This setting will be available at a later date.*</span></span>|
|<span data-ttu-id="a3af6-173">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="a3af6-173">AllowTranscription</span></span>|<span data-ttu-id="a3af6-174">사용자 및 Teams 계정에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-174">Required for user and Teams rooms accounts.</span></span>|<span data-ttu-id="a3af6-175">**True** 및 **False**</span><span class="sxs-lookup"><span data-stu-id="a3af6-175">**True** and **False**</span></span>|
||||

<span data-ttu-id="a3af6-176">관리 Teams 관리 센터에서 전사 허용 정책을 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3af6-176">In the Teams admin center, set the **Allow transcription** policy.</span></span> <span data-ttu-id="a3af6-177">설정 **기본적으로 꺼집니다.**</span><span class="sxs-lookup"><span data-stu-id="a3af6-177">Settings are **Off** by default.</span></span>

![모임 정책을 강조 표시하고 전사 허용이 선택된 관리 센터](../media/allow-transcription1.png)

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="a3af6-179">자주 묻는 질문 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="a3af6-179">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="a3af6-180">**음성 프로필 데이터는 어디에 저장하나요?**</span><span class="sxs-lookup"><span data-stu-id="a3af6-180">**Where is the voice profile data stored?**</span></span>

<span data-ttu-id="a3af6-181">음성 프로필 데이터는 사용자 Office 365 클라우드에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-181">Voice profile data is stored in Office 365 cloud with user content.</span></span>

<span data-ttu-id="a3af6-182">**보존 시간 표시 막대 및 정책이란?**</span><span class="sxs-lookup"><span data-stu-id="a3af6-182">**What is the retention timeline and policy?**</span></span>

<span data-ttu-id="a3af6-183">일반 보존 정책은 데이터 보존 개요 [에 설명되어 있습니다.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="a3af6-183">General retention policy is stated in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span> <span data-ttu-id="a3af6-184">또한 사용자가 해당 3년 기간 내에 지능형 스피커를 사용하여 모임에 초대되지 않은 경우 사용자의 음성 프로필 데이터가 3년 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-184">In addition, a user's voice profile data will be deleted after 3 years  if the user isn't invited to any meetings with an Intelligent Speaker within that 3-year period.</span></span> <span data-ttu-id="a3af6-185">기존 직원의 모임에는 데이터가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-185">Data isn't used in any meetings for existing employees.</span></span> <span data-ttu-id="a3af6-186">직원이 회사를 떠났을 경우 음성 프로필 데이터는 사용자 콘텐츠로 간주되어 데이터 보존 개요에 Office 365 데이터 보존 정책에 따라 [처리됩니다.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="a3af6-186">If an employee has left the company, voice profile data is considered user content and is treated as such per Office 365 data retention policy described in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="a3af6-187">**음성 프로필 데이터가 전체 사용자에 Microsoft 서비스?**</span><span class="sxs-lookup"><span data-stu-id="a3af6-187">**Is voice profile data used across Microsoft services?**</span></span>

<span data-ttu-id="a3af6-188">아니요, 음성 프로필 데이터는 사용자가 동의를 제공한 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-188">No, voice profile data is only used for the purpose for which the user has provided consent.</span></span> <span data-ttu-id="a3af6-189">Microsoft는 음성 인식 시나리오 내에서는 음성 프로필 Teams 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-189">Microsoft will not use the voice profile data except within Teams voice recognition scenarios.</span></span>

<span data-ttu-id="a3af6-190">예를 들어 Microsoft는 다음 상황에서 데이터를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-190">For example, Microsoft won't use the data in the following situations:</span></span>

<span data-ttu-id="a3af6-191">**다른 조직에서 모임에 참가할 때 내 음성 프로필 데이터가 사용하나요?**</span><span class="sxs-lookup"><span data-stu-id="a3af6-191">**Is my voice profile data used when I join a meeting in another organization?**</span></span>

<span data-ttu-id="a3af6-192">조직의 사용자가 조직한 모임에만 해당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-192">No only in meetings organized by a user in your organization.</span></span>

<span data-ttu-id="a3af6-193">**내 음성 프로필을 내보낼 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="a3af6-193">**How can I export my voice profile?**</span></span>

<span data-ttu-id="a3af6-194">IT 관리자는 오디오 데이터를 수시로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3af6-194">Your IT admin can export your audio data at any time.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3af6-195">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a3af6-195">Related topics</span></span>

[<span data-ttu-id="a3af6-196">지원 문서: 지능형 스피커를 사용하여 객실 내 참가자 식별 </span><span class="sxs-lookup"><span data-stu-id="a3af6-196">Support article: Use Intelligent Speakers to Identify in-room participants </span></span>](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
