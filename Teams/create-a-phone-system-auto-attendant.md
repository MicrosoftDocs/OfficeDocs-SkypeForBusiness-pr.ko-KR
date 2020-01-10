---
title: 클라우드 자동 전화 교환 설정
ms.author: kenwith
author: kenwith
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Microsoft 팀에 대 한 클라우드 자동 전화 교환을 설정 하 고 테스트 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 5a018b6c3b193d17bfbabdc5178c095a635e65ea
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005198"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="d2d3d-103">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="d2d3d-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="d2d3d-104">자동 전화 교환을 통해 사용자는 조직에 게 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람 또는 교환원에 게 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="d2d3d-105">Microsoft 팀 관리 센터 또는 Powershell을 사용 하 여 조직에 대 한 자동 전화 교환을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with Powershell.</span></span> <span data-ttu-id="d2d3d-106">자동 전화 교환을 만들려면 왼쪽 탐색 창에서 **음성** 으로 이동한 다음 **자동 전화 교환** > **새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-106">To create an auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="d2d3d-107">자동 전화 교환에 대해 자세히 알아보려면 [클라우드 자동 전화 교환 기능](/microsoftteams/what-are-phone-system-auto-attendants) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="d2d3d-108">이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

<span data-ttu-id="d2d3d-109">전화 번호는 자동 전화 교환에 직접 할당 되지 않고 자동 전화 교환에 연결 된 [리소스 계정](manage-resource-accounts.md) 으로 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-109">Phone numbers are not directly assigned to the auto attendant, but rather to a [resource account](manage-resource-accounts.md) that is associated to the auto attendant.</span></span>

<span data-ttu-id="d2d3d-110">자동 전화 교환 구현에는 종종 몇 가지 자동 전화 교환이 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-110">Auto attendant implementations often involve several auto attendants.</span></span> <span data-ttu-id="d2d3d-111">일반적으로 *첫 번째 수준* 자동 전화 교환에는 할당 된 전화 번호를 사용 하는 자원 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-111">A *first-level* auto attendant usually has a resource account with an assigned phone number.</span></span> <span data-ttu-id="d2d3d-112">중첩 된 자동 전화 교환은 *첫 번째 수준* 자동 전화 교환이 호출로 연결 되는 두 번째 수준 메뉴로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-112">A nested auto attendant is used as a second-level menu that the *first-level* auto attendant connects  as call to.</span></span> <span data-ttu-id="d2d3d-113">*중첩* 된 자동 전화 교환은 해당 리소스 계정에 전화 번호를 할당 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-113">A *nested* auto attendant isn't required to  have a phone number assigned to its resource account.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="d2d3d-114">1 단계-시작 하기</span><span class="sxs-lookup"><span data-stu-id="d2d3d-114">Step 1 — Get started</span></span>

- <span data-ttu-id="d2d3d-115">자동 전화 교환은 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-115">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="d2d3d-116">리소스 계정 및 필요한 모든 라이선스에 대 한 자세한 내용은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-116">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span> 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> <span data-ttu-id="d2d3d-117">전화 시스템 라이선스가 있는 온라인 사용자 인 연산자나 메뉴 옵션으로 호출을 리디렉션하려면 엔터프라이즈 음성에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-117">To redirect calls to an operator or a menu option that is an Online user with a Phone System license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="d2d3d-118">[비즈니스용 Skype 라이선스 할당](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) 또는 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="d2d3d-119">Windows PowerShell을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="d2d3d-120">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d2d3d-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-auto-attendants"></a><span data-ttu-id="d2d3d-121">2 단계-자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="d2d3d-121">Step 2 — Create auto attendants</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2d3d-122">모든 자동 전화 교환에는 연결 된 [리소스 계정이](manage-resource-accounts.md)있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="d2d3d-123">먼저 리소스 계정을 만든 다음 자동 전화 교환에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="with-the-microsoft-teams-admin-center"></a><span data-ttu-id="d2d3d-124">Microsoft 팀 관리 센터</span><span class="sxs-lookup"><span data-stu-id="d2d3d-124">With the Microsoft Teams admin center</span></span>

<span data-ttu-id="d2d3d-125">**Microsoft 팀 관리 센터**에서 **음성** > **자동 전화 교환을**클릭 한 다음 **+ 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ Add**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="d2d3d-126">일반 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="d2d3d-126">General info page</span></span>

![내 자동 전화 교환 페이지의 스크린샷](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

<span data-ttu-id="d2d3d-128">![이전 스크린샷](media/teamscallout1.png)
**이름의** 설명선 번호 1의 아이콘은 자동 전화 교환의 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-128">![Icon of the number 1, a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a display name for your auto attendant.</span></span> <span data-ttu-id="d2d3d-129">이름은 필수 이며 공백을 포함 하 여 최대 64 자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-129">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="d2d3d-130">여기에서 지정 하는 **이름은** **자동 전화 교환** 탭의 열에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-130">The **Name** you designate here is listed in a column on the **Auto attendants** tab.</span></span>

<span data-ttu-id="d2d3d-131"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-131"></span></span>

* * *

<span data-ttu-id="d2d3d-132">![이전 스크린샷](media/teamscallout2.png)
 <a name="operator"> </a> 
 **연산자** 의 설명선 인 숫자 2의 아이콘입니다 (권장 사항).</span><span class="sxs-lookup"><span data-stu-id="d2d3d-132">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png)
<a name="operator"> </a>
**Operator** This is optional (but recommended).</span></span> <span data-ttu-id="d2d3d-133">호출자가 메뉴를 차단 하 고 지정 된 사람에 게 말할 수 있도록 **연산자** 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

<span data-ttu-id="d2d3d-134">0 키는 기본적으로 교환원에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-134">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="d2d3d-135">운영자를 설정 하는 경우 **통화 흐름** 페이지의 **편집 메뉴 옵션** 에서 옵션에 대해 전화를 거는 사람에 게 알려 주십시오.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-135">If you set an Operator, tell people who call about the option in **Edit menu options** on the **Call flow** page.</span></span> <span data-ttu-id="d2d3d-136">자동 전화 교환에 운영자를 설정 하는 경우 **호출자가 듣기** 상자에 해당 프롬프트 텍스트를 입력 하거나이 옵션을 포함 하도록 오디오 파일을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-136">If you set an operator on your auto attendant, you enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="d2d3d-137">예를 들어 연산자의 경우 0을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-137">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="d2d3d-138">다음과 같은 여러 가지 방법으로 연산자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-138">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="d2d3d-139">**연산자 없음** "연산자" 및 "0 키" 옵션을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-139">**No operator** disables the "Operator" and "Press 0" options.</span></span> <span data-ttu-id="d2d3d-140">현재 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-140">This is the current default.</span></span>
- <span data-ttu-id="d2d3d-141">**조직의 사용자** 가 Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 계획을 사용 하도록 설정 된 전화 시스템 라이선스를 사용 하는 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-141">**Person in your organization** assigns a person with a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="d2d3d-142">발신자를 보이스 메일로 보내도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-142">You can also set it up so the caller is sent to voicemail.</span></span> <span data-ttu-id="d2d3d-143">전화를 음성 메일로 보내려면 **조직의 사용자** 를 선택 하 고 해당 계정의 설정을 설정 하 여 전화를 음성 메일로 바로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-143">To send a caller to voicemail, select **Person in your organization** and set that account's settings to send calls directly to voicemail.</span></span>

     > [!Note]
     > <span data-ttu-id="d2d3d-144">**조직의** 사용자는 비즈니스용 Skype 서버를 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-144">**Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

- <span data-ttu-id="d2d3d-145">**음성 앱**  이미 만들어진 자동 전화 교환 또는 통화 대기열에 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-145">**Voice app**  Select the name of the resource account linked to an auto attendant or call queue that has already been created.</span></span> <span data-ttu-id="d2d3d-146">연산자를 요청 하는 호출자가이 위치에서 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-146">Callers that request an operator are redirected there.</span></span>  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<span data-ttu-id="d2d3d-147"><a name="timezone"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-147"></span></span>

<span data-ttu-id="d2d3d-148">![숫자 3의 아이콘, 이전 스크린샷](media/teamscallout3.png) **표준 시간대** 의 설명선은 자동 전화 교환의 표준 시간대를 설정 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-148">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Time zone** You are required to set the time zone for your auto attendant.</span></span> <span data-ttu-id="d2d3d-149">설정이 조직에 대해 나열 된 주 주소의 표준 시간대 또는 다른 표준 시간대와 동일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-149">The setting can be the same as the time zone of the main address listed for your organization, or a different time zone.</span></span> <span data-ttu-id="d2d3d-150">각 자동 전화 교환은 다른 표준 시간대를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-150">Each auto attendant can have a different time zone.</span></span> <span data-ttu-id="d2d3d-151">자동 전화 교환에 설정 된 업무 시간에도이 표준 시간대가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-151">The business hours set for the auto attendant also use this time zone.</span></span> <span data-ttu-id="d2d3d-152">일부 지역에서는 일광 절약을 사용 하는 것이 아니기 때문에 비즈니스 시간 불일치를 방지 하기 위해 올바른 표준 시간대를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-152">Make sure to set the right timezone to avoid business-hours discrepancies since not all regions have Daylight Saving.</span></span> 

* * *

<span data-ttu-id="d2d3d-153">![숫자 4의 아이콘으로, 이전 스크린샷](media/teamscallout4.png)
 <a name="language"> </a> 
 **언어** 의 설명선은 자동 전화 교환에 사용할 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-153">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)
<a name="language"> </a>
**Language** Select the language that you want to use for your auto attendant.</span></span> <span data-ttu-id="d2d3d-154">자동 전화 교환은이 언어를 호출자와 함께 사용 하 고 모든 시스템 메시지가이 언어로 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-154">The auto attendant uses that language with callers, and all system prompts are played in this language.</span></span>

 * * *

<span data-ttu-id="d2d3d-155">![숫자 5의 아이콘, 이전 스크린샷](media/teamscallout5.png)
의 설명선 음성 인식 기능을 사용 하는 경우이 옵션을 선택 하면 음성**입력** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-155">![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png)
**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="d2d3d-156">발신자는 [설정한 언어로](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)음성 입력을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-156">Callers can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="d2d3d-157">사용자가 휴대폰 키패드를 사용 하 여 선택 하 게 할 수만 있도록 하려면 음성 인식을 **Off**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-157">If you want to only let people use their phone keypad to make selections, you can leave speech recognition set to **Off**.</span></span>

* * *  

<span data-ttu-id="d2d3d-158">선택이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-158">When you finish with your selections, click **Next**.</span></span>

#### <a name="call-flow"></a><span data-ttu-id="d2d3d-159">통화 흐름</span><span class="sxs-lookup"><span data-stu-id="d2d3d-159">Call flow</span></span>

<span data-ttu-id="d2d3d-160"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-160"></span></span>

> [!TIP]
> <span data-ttu-id="d2d3d-161">업무 시간 중에 다른 통화 흐름 동작을 사용 하 여 사용자 지정 업무 시간 일정을 설정 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-161">You can choose to set up a custom business hours schedule, with different call flow behaviors during and after business hours.</span></span> <span data-ttu-id="d2d3d-162">사용자 지정 일정을 설정 하려면 [이후 시간에 대 한 선택적 통화 흐름](#call-flow-for-after-hours)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-162">To set a custom schedule, set the optional [Call flow for after hours](#call-flow-for-after-hours).</span></span> <span data-ttu-id="d2d3d-163">기본적으로 자동 전화 교환은 업무 시간 호출 흐름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-163">By default, an auto attendant uses business hours call flows.</span></span>

<span data-ttu-id="d2d3d-164">자동 전화 교환에 도달 하면 사용자가 듣는 인사말, 프롬프트 및 메뉴를 사용자 지정 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-164">You can set up customized greetings, prompts, and menus that people hear when they reach your auto attendant.</span></span>

![스크린샷: 통화 처리 페이지 인사말 섹션](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

<span data-ttu-id="d2d3d-166">**먼저 인사말 메시지 재생** 인사말은 선택 사항이 며 **인사말 없음으로**설정 하거나, **오디오 파일을 재생**하거나, **인사말 메시지를 입력할**수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-166">**First play a greeting message** A greeting is optional and can be set to **No greeting**, **Play an audio file**, or **Type a greeting message**.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d3d-167">인사말은 첫 번째 수준 자동 전화 교환에 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-167">A greeting is most valuable for a first-level auto attendant.</span></span> <span data-ttu-id="d2d3d-168">중첩 된 자동 전화 교환에는 인사말이 필요 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-168">A nested auto attendant often doesn't need a greeting.</span></span>

<span data-ttu-id="d2d3d-169">![이전 스크린샷에](media/teamscallout1.png) 표시 된 숫자 1, 설명선의 아이콘 **인사말**을 선택 하지 않으면 나중에 선택한 작업 중 하나에서 통화를 처리 하기 전에 호출자가 메시지 또는 인사말이 들리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-169">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) If you select **No Greeting**, the caller doesn't hear a message or greeting before the call is handled by one of the actions you select later.</span></span> 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

<span data-ttu-id="d2d3d-170">![이전 스크린샷](media/teamscallout2.png) 의 숫자 2, 설명선에서 **오디오 파일 재생** 을 선택한 경우 **파일 업로드** 단추를 사용 하 여 오디오로 저장 된 녹음 된 인사말 메시지를 업로드할 수 있습니다. WAV,. MP3 또는. WMA 형식.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-170">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="d2d3d-171">기록의 크기는 5mb를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-171">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="d2d3d-172">![숫자 3의 아이콘, 이전 스크린샷](media/teamscallout3.png) 의 설명선 **인사말 메시지 입력** 이 옵션을 선택 하는 경우 제공 된 필드에 시스템에서 읽을 텍스트 (최대 1000 자)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-172">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="d2d3d-173">예를 들어 "Contoso 시작 '을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-173">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="d2d3d-174">귀하의 전화는 귀하에 게 중요 합니다. "</span><span class="sxs-lookup"><span data-stu-id="d2d3d-174">Your call is important to us."</span></span> <span data-ttu-id="d2d3d-175">출력은 텍스트 음성 통화 소프트웨어로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-175">Output is created by text-to-voice software.</span></span>

* * *

<span data-ttu-id="d2d3d-176">다음 작업에서 통화 **회람** 섹션의 다음 동작에서 전화를 걸 때 수행할 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-176">You can select what happens next to calls from the following actions in the  **Then route the call** section.</span></span> <span data-ttu-id="d2d3d-177">설정은 **연결 끊기**, **통화 리디렉션**또는 **재생 메뉴 옵션**입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-177">Settings are **Disconnect**, **Redirect call**, or **Play menu options**.</span></span>

<span data-ttu-id="d2d3d-178">**연결 끊기를**선택 하는 경우에는 인사말이 재생 된 후 호출자의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-178">If you select **Disconnect**, the caller is disconnected after the greeting plays.</span></span> 

<span data-ttu-id="d2d3d-179"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-179"></span></span>

<span data-ttu-id="d2d3d-180">![숫자 4의 아이콘, 이전 스크린샷](media/teamscallout4.png) **리디렉션 호출** 의 설명선은 옵션에서 선택 하지 않고 선택한 대상에 호출자를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-180">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png) **Redirect call** sends the caller to the chosen destination without choosing from options.</span></span> <span data-ttu-id="d2d3d-181">다음과 같은 설정이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-181">The possible settings are:</span></span>

  - <span data-ttu-id="d2d3d-182">**조직의 사용자** 선택 하는 계정에는 Enterprise Voice에 사용할 수 있는 전화 시스템 라이선스가 있거나 Office 365에서 통화 요금제를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-182">**Person in organization** The account you choose must have a Phone System license enabled for Enterprise Voice or have an assigned Calling Plan in Office 365.</span></span> <span data-ttu-id="d2d3d-183">발신자에 게 전화를 걸 수 있도록 설정할 수 있습니다: **조직에서 사용자** 를 선택 하 고 해당 계정이 음성 메일로 바로 착신 전환 되도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-183">You can set it up so the caller can be sent to voicemail: select **Person in organization** and set that account to have calls forwarded directly to voicemail.</span></span>

  > [!Note]
  > <span data-ttu-id="d2d3d-184">**조직의** 사용자는 비즈니스용 Skype 서버를 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-184">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

  - <span data-ttu-id="d2d3d-185">**음성 앱** 이미 설정 된 자동 전화 교환 또는 통화 대기열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-185">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="d2d3d-186">서비스와 연결 된 리소스 계정의 이름으로 자동 전화 교환 또는 통화 대기열을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-186">You search for the auto attendant or call queue by the name of the resource account associated with the service.</span></span>
  - <span data-ttu-id="d2d3d-187">보이스 **메일** 이 보이스 메일에 액세스 해야 하는 조직의 사용자를 나타내는 Office 365 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-187">**Voicemail** Select the Office 365 Group representing the users in your organization that need access to this voicemail.</span></span> <span data-ttu-id="d2d3d-188">여기서는 보이스 메일을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-188">This is where you can turn on voicemail transcription too.</span></span> <span data-ttu-id="d2d3d-189">Office 365 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-189">Requires an Office 365 Group.</span></span>

  > [!NOTE]
> <span data-ttu-id="d2d3d-190">이 자동 전화 교환 메일 계정에서 사용자에 게 전송 되는 음성 메시지는 팀에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-190">Voice messages sent to users from this auto attendant voicemail account can't be accessed in Teams.</span></span> <span data-ttu-id="d2d3d-191">전자 메일로 발송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-191">They'll come as an email.</span></span>


<!-- - **Auto attendant** Select the name of an existing auto attendant.
- **Call queue** Select the name of an auto attendant that has already been created.
- **External phone number** routes the caller to a phone number outside your local system.
- **Operator** directs the call to a user you designate as an Operator. If you haven't previously set up an operator, an option to create one now shows up. The 0 key is assigned to Operator by default. Options for setting an Operator are:

  - **No operator** disables the "Operator" and "Press 0" options.
  - **Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server. They must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. Search for the operator in the **Destination for your operator** field.
  - **Auto attendant** lets you choose the name of an existing auto attendant.
  - **Call queue** lets you select an existing call queue.
  - **Group Voicemail** routes the call to a voicemail box that you select. -->

 * * *

![스크린샷: 호출 처리 페이지 작업 섹션](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

<span data-ttu-id="d2d3d-193">![숫자 1, 이전 스크린샷](media/teamscallout1.png) 의 설명선 **메뉴 옵션** 을 선택 하면 오디오 파일을 사용할지 여부를 선택할 수 있습니다. 다이얼 패드 메뉴 옵션을 호출자에 게 제공 하기 위해 텍스트를 음성으로 렌더링 하도록 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-193">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) When you select **Play menu options** You can select whether to use an audio file or enter text that will be rendered as text to speech to give dialpad menu options to callers.</span></span> <span data-ttu-id="d2d3d-194">**호출 리디렉션** 또는 **연결 끊기** 옵션을 대신 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-194">Select this instead of the **Redirect call to** or **Disconnect** options.</span></span>


<span data-ttu-id="d2d3d-195">![숫자 2의 아이콘, 이전 스크린샷](media/teamscallout2.png) 의 설명선에서 **오디오 파일을 재생** 하면 호출자가 선택할 프롬프트 및 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-195">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Play an audio file** lets you set up a prompts and options for the caller to choose.</span></span> 
- <span data-ttu-id="d2d3d-196">**오디오 파일 재생** 을 선택 하는 경우 **파일 업로드** 단추를 사용 하 여 오디오로 저장 된 녹음/녹화 된 인사말 메시지를 업로드할 수 있습니다. WAV,. MP3 또는. WMA 형식.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-196">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="d2d3d-197">기록의 크기는 5mb를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-197">The recording can be no larger than 5 MB.</span></span>

- <span data-ttu-id="d2d3d-198">**인사말 메시지 입력** 이 옵션을 선택 하는 경우 제공 된 필드에 시스템에서 읽을 텍스트 (최대 1000 자)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-198">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="d2d3d-199">예를 들어 "Contoso 시작 '을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-199">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="d2d3d-200">귀하의 전화는 귀하에 게 중요 합니다. "</span><span class="sxs-lookup"><span data-stu-id="d2d3d-200">Your call is important to us."</span></span> <span data-ttu-id="d2d3d-201">출력은 텍스트 음성 통화 소프트웨어로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-201">Output is created by text-to-voice software.</span></span>

<span data-ttu-id="d2d3d-202">**메뉴 옵션 설정** 이 대화 상자에서 전화 키패드 또는 음성 명령을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-202">**Set menu options** Telephone keypad or voice commands can be added or removed in this dialog.</span></span> <span data-ttu-id="d2d3d-203">메뉴 옵션을 삭제 하려면 음성 명령 항목을 제거 하 고 뒤로 **이동을** 다시 **선택**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-203">To delete a menu option, remove the voice command entry and set **Redirect to** back to **Select**.</span></span>

> [!TIP]
> <span data-ttu-id="d2d3d-204">옵션을 제거 하는 경우 메뉴 프롬프트 텍스트를 업데이트 하거나 오디오 메시지를 다시 녹음 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-204">Update menu prompt text or re-record the audio prompts when you remove options.</span></span> <span data-ttu-id="d2d3d-205">호출자에 대해 재생 되는 메뉴 메시지가 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-205">The menu prompt played for callers isn't automatically updated.</span></span>  
>
> <span data-ttu-id="d2d3d-206">모든 메뉴 옵션을 순서에 관계 없이 추가 하 고 제거할 수 있으며 키 매핑도 연속적으로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-206">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="d2d3d-207">예를 들어 옵션에 매핑된 키가 0, 1, 3 인 메뉴를 만들 수 있지만 키 2는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-207">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d3d-208">키 \* (반복)와 \# (뒤로)는 시스템에 예약 되어 있으므로 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-208">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="d2d3d-209">음성 인식 기능을 사용 하는 경우 \*를 누르면 "Repeat"와 #이 "뒤로" 음성 명령에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-209">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="d2d3d-210">![메뉴 옵션을 설정 하기 위한 앞의 스크린샷에](media/teamscallout3.png) 표시 되는 숫자 3의 아이콘에는 **+ 다이얼 키 할당** 을 클릭 하 고 다음 옵션에 대 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-210">![Icon of the number 3, a callout in the previous screenshot](media/teamscallout3.png) To set up a menu option, click on the  **+Assign a dial key** and enter information for the following options:</span></span>

<span data-ttu-id="d2d3d-211">![옵션에 대 한 이전 스크린샷](media/teamscallout4.png)  **음성 명령** 열의 설명선 번호 4는 최대 64 자까지 입력할 수 있으며 "고객 서비스" 또는 "작업 및 Grounds" 등의 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-211">![Icon of the number 4, a callout in the previous screenshot](media/teamscallout4.png)  **Voice command** column for an option can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="d2d3d-212">음성 인식 기능을 사용 하도록 설정 하면 이름이 자동으로 인식 되 고, 발신자는 3을 눌러 "3" 이라고 말 하거나 "고객 서비스" 라고 말하여 키 3에 매핑된 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-212">If speech recognition is enabled, the name is automatically recognized, and the caller is able to press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span> <span data-ttu-id="d2d3d-213">이 텍스트는 "교환원에 게 착신 전환 중" 처럼 서비스 확인 프롬프트에 대 한 텍스트를 음성으로 렌더링 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-213">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to the Operator."</span></span>

<span data-ttu-id="d2d3d-214">![이전 스크린샷](media/teamscallout5.png) 에 있는 숫자 5의 아이콘으로 리디렉션 옵션은 해당 키를 누르거나 음성 인식을 사용 하 여 선택한 옵션 **을** 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-214">![Icon of the number 5, a callout in the previous screenshot](media/teamscallout5.png)  The **Redirect to** option sets where the call goes if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="d2d3d-215">통화는 다음으로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-215">The call can be sent to:</span></span>

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- <span data-ttu-id="d2d3d-216">**연산자** 연산자가 이미 설정 된 경우이 옵션은 키 0에 자동으로 매핑되지만, 삭제 하거나 다른 키에 다시 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-216">**Operator** If an operator is already set up, the option is automatically mapped to key 0, but can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="d2d3d-217">이 옵션을 선택 하는 호출자가 지정 된 운영자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-217">The caller who selects this option is sent to the designated Operator.</span></span> <span data-ttu-id="d2d3d-218">If 연산자가 아무 키로도 설정 되어 있지 않으면 음성 명령 "연산자"를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-218">If Operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 
- <span data-ttu-id="d2d3d-219">**조직의** 사용자는 비즈니스용 Skype 서버를 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-219">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="d2d3d-220">사용자는 Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 전화 시스템 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-220">The user must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="d2d3d-221">**이름으로 검색** 필드에서 해당 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-221">Search for the person in the **Search by name** field.</span></span>

- <span data-ttu-id="d2d3d-222">**음성 앱** 이미 설정 된 자동 전화 교환 또는 통화 대기열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-222">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="d2d3d-223">응용 프로그램과 연결 된 리소스 계정의 이름으로 자동 전화 교환 또는 통화 대기열을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-223">You search for the auto attendant or call queue by the name of the resource account associated with the application.</span></span>

- <span data-ttu-id="d2d3d-224">보이스 **메일** 이 보이스 메일에 액세스 해야 하는 조직의 사용자를 나타내는 Office 365 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-224">**Voicemail** Select the Office 365 Group representing the users in your organization that need access to this voicemail.</span></span> <span data-ttu-id="d2d3d-225">여기서는 보이스 메일을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-225">This is where you can turn on voicemail transcription too.</span></span> <span data-ttu-id="d2d3d-226">Office 365 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-226">Requires an Office 365 Group.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

<span data-ttu-id="d2d3d-227">![이 섹션의 이전 스크린샷](media/teamscallout6.png)  **디렉터리 검색** 에 있는 숫자 6의 아이콘을 사용 하 여 자동 전화 교환에 대 한 **전화 걸기** 및 **내선** 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-227">![Icon of the number 6, a callout in the previous screenshot](media/teamscallout6.png)  **Directory search** In this section, you can enable **Dial by name** and **Dial by Extension** for the auto attendant.</span></span> <span data-ttu-id="d2d3d-228">전화 걸기 범위 (선택 사항) 페이지에서 이러한 서비스에 포함 되지 않는 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-228">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="d2d3d-229">디렉터리 검색은 기본적으로 **없음** 으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-229">Directory search is set to **None** by default.</span></span>

<span data-ttu-id="d2d3d-230">**이름으로 전화 걸기** 이 옵션을 사용 하도록 설정 하는 경우 발신자는 **이름으로 다이얼**을 사용 하 여 조직에서 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-230">**Dial by name** If you enable this option, callers can search for people in your organization using **Dial by name**.</span></span> <span data-ttu-id="d2d3d-231">사용자의 이름과 음성 인식이 사용자에 게 일치 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-231">They say the user's name and voice recognition matches them to a user.</span></span> <span data-ttu-id="d2d3d-232">전화 걸기 범위 (선택 사항) 페이지에서 이러한 서비스에 포함 되지 않는 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-232">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="d2d3d-233">전화 시스템 라이선스가 있는 모든 온라인 사용자 또는 비즈니스용 Skype 서버를 사용 하 여 온-프레미스에 호스팅되는 사용자는 적격 사용자 이며 이름으로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-233">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span>


<span data-ttu-id="d2d3d-234">**내선** 번호 이 옵션을 사용 하도록 설정 하는 경우 발신자는 휴대폰 내선 번호를 입력 하 여 조직의 사용자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-234">**Dial by extension** If you enable this option, callers can connect with users in your organization by entering their phone extension.</span></span> <span data-ttu-id="d2d3d-235">전화 걸기 범위 (선택 사항) 페이지에서 **전화 접속을 통해** 사용할 수 있거나 사용할 수 없음으로 나열 되는 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-235">You can select which users are listed as available or not available for **Dial by extension** in the optional Dial Scope page.</span></span> <span data-ttu-id="d2d3d-236">휴대폰 시스템 라이선스가 있는 모든 온라인 사용자 또는 비즈니스용 Skype를 사용 하 여 온-프레미스에 호스팅되는 모든 사용자는 적격 사용자 이며, 내선 번호로 전화 접속을 통해 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-236">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by extension.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2d3d-237">다음 사항을 준수 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-237">Please observe the following:</span></span>
>- <span data-ttu-id="d2d3d-238">내선 번호로 전화를 걸 수 있도록 하려는 사용자는 내선 번호가 [Microsoft 365 관리 센터](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users)에서 할당 된 전화번호 또는 휴대 전화 번호의 일부로 지정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-238">Users you wish to make available for Dial By Extension need to have an extension specified as part of their phone number or mobile phone number assigned in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users).</span></span>  <span data-ttu-id="d2d3d-239">사용자 전화 번호 필드에 확장명을 입력 하는 데 필요한 형식은 `+<phonenumber>;ext=<extension>` 또는 `x<extension>`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-239">The required format to enter the extension in the user phone number field is is either `+<phonenumber>;ext=<extension>` or `x<extension>`.</span></span>
>- <span data-ttu-id="d2d3d-240">팀 관리 센터에서 확장을 할당 하는 것은 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-240">Assigning an extension in Teams Admin center is not currently supported.</span></span> <span data-ttu-id="d2d3d-241">[Set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) powershell 명령 또는 Microsoft 365 관리 센터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-241">You must either use the [Set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) powershell command or the Microsoft 365 admin center.</span></span>
>- <span data-ttu-id="d2d3d-242">AAD PhoneNumber를 변경 하기 전에 최대 12 시간까지 걸릴 수 있으며 MobilePhone 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-242">It can take up to 12 hours before changes to the AAD PhoneNumber and MobilePhone attributes are available.</span></span>
>- <span data-ttu-id="d2d3d-243">사용자의 LineUri에 대 한 확장을 정의 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-243">Please do NOT define an extension for the LineUri of a user.</span></span> <span data-ttu-id="d2d3d-244">이는 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-244">This is  not supported currently.</span></span>
>- <span data-ttu-id="d2d3d-245">자동 전화 교환은 이름으로 전화 걸기 또는 내선 번호를 통해 전화 접속으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-245">An auto attendant can be configured for either dial by name or dial by extension, but not both.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d3d-246">**전화 걸기 이름** 및 **전화** 걸기 기능을 사용 하는 경우 호출자에 게 사용자의 내선 번호를 알고 있는 경우 메뉴 옵션을 선택 하는 기본 자동 전화 교환 ( **이름으로 전화 걸기**사용 가능)을 만들고이 옵션을 설정 하 여 전화를 다이얼에의 한 자동 전화 교환에 사용할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-246">If you want to use both the **Dial by name** and **Dial by extension** features, you can create  main auto attendant (enabled for **Dial by name**) that prompts callers to choose a menu option if they know the extension of the user, and set that option to transfer the call to an auto attendant enabled for Dial by extension.</span></span>

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

<span data-ttu-id="d2d3d-247">선택이 완료 되 면 **다음** 을 클릭 하 여 고급 설정을 변경 하거나, 다음과 같은 경우에 대 한 기본 설정을 사용 하려면 **제출을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-247">When you are finished with your selections, you can click **Next** if you want to change advanced settings, or click **Submit** if you want to use default settings for things like:</span></span>
- <span data-ttu-id="d2d3d-248">이후 시간에 대 한 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="d2d3d-248">Call flow for after hours</span></span>
- <span data-ttu-id="d2d3d-249">휴일에 대 한 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="d2d3d-249">Call flow for holidays</span></span>
- <span data-ttu-id="d2d3d-250">전화 걸기 범위</span><span class="sxs-lookup"><span data-stu-id="d2d3d-250">Dial Scope</span></span>
- <span data-ttu-id="d2d3d-251">자원 계정</span><span class="sxs-lookup"><span data-stu-id="d2d3d-251">Resource accounts</span></span>

<span data-ttu-id="d2d3d-252">자동 전화 교환은 리소스 계정이 있어야 하기 때문에 **리소스 계정** 페이지로 진행 하 고 이미 구성한 리소스 계정을 연결 하거나 리소스 계정을 만들고 [Microsoft 팀의 자원 계정 관리](manage-resource-accounts.md)에 설명 된 대로 자동 전화 교환에 연결 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-252">Since your auto attendant is required to have a resource account, you have a choice of proceeding to the **Resource account** page and associating a resource account you've already configured, or creating a resource account and associating it to the auto attendant as described in [Manage resource accounts in Microsoft Teams](manage-resource-accounts.md).</span></span> <span data-ttu-id="d2d3d-253">이 자동 전화 교환은 리소스 계정에 연결 될 때까지 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-253">You won't be able to use this auto attendant until it has been associated to a resource account.</span></span> <span data-ttu-id="d2d3d-254">이렇게 하려면 화면 맨 아래에 있는 **다음** 단추를 클릭 한 다음 왼쪽 탐색 모음에서 **리소스 계정을** 클릭 하 여 리소스 계정 페이지로 바로 이동 하 고 자동 전화 교환을 리소스 계정에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-254">to do this, click the **Next** button at the bottom of the screen and then click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="advanced-settings-optional"></a><span data-ttu-id="d2d3d-255">고급 설정 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d2d3d-255">Advanced settings (optional)</span></span>

<span data-ttu-id="d2d3d-256">선택할 때 기본으로 구성 하거나 남겨둘 수 있는 4 개의 추가 화면이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-256">There are four additional screens that you can configure or leave at defaults as you choose.</span></span>

##### <a name="call-flow-for-after-hours"></a><span data-ttu-id="d2d3d-257">이후 시간에 대 한 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="d2d3d-257">Call flow for after hours</span></span>

<span data-ttu-id="d2d3d-258">기본적으로 자동 전화 교환의 업무 시간은 9am-5pm로 설정 되며 월요일 ~ 금요일</span><span class="sxs-lookup"><span data-stu-id="d2d3d-258">By default, an auto attendant's business hours are set to 9am-5pm, Monday to Friday</span></span>  <!--24/7--><span data-ttu-id="d2d3d-259">, 모든 시간이 *업무 시간*으로 간주 되기 때문에 *시간이 지난 후* 통화 흐름 옵션은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-259">, and the call flow options for *after hours* calls are disabled because all hours are considered *business hours*.</span></span> <span data-ttu-id="d2d3d-260">**사용자 지정 비즈니스 시간 설정** 옵션을 선택 하면 시간 이후 자동 전화 교환에 사용 되는 통화 처리 규칙이 **다음 시간 후 호출 흐름 페이지에** 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-260">When you select the **Setup custom business hours** option, the **Call flow for after hours** page configures the call handling rules used by the auto attendant after hours.</span></span> <span data-ttu-id="d2d3d-261">사용할 수 있는 옵션은 서로 다른 메뉴 및 동작에 대 한 일정을 설정할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-261">The options available are the same, the difference is the ability to set a schedule for different menus and behaviors.</span></span>

<span data-ttu-id="d2d3d-262">자동 전화 교환 시스템은 첫 번째 수준 자동 전화 교환에 대 한 시간 통화 처리 동작 이후에 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-262">A system of auto attendants may only need to set after hours call handling behavior for the first-level auto attendant.</span></span> <span data-ttu-id="d2d3d-263">중첩 된 자동 통화는 첫 번째 수준 자동 전화 교환에 의해 호출 되지 않을 수 있지만, 그 외에도 시스템은 사용 하는 각 자동 전화 교환에 대 한 이후 시간 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-263">Nested auto attendants may not even be called by the first-level auto attendant, but alternately the system can define after-hours behavior for each auto attendant it uses.</span></span>

<span data-ttu-id="d2d3d-264">처음에는 업무 시간이 12:00 오전부터 시작 하 여 12:00 pm, 일요일 ~ 토요일에 종료 되도록 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-264">Initially, the business hours are defined to start at 12:00 am and end at 12:00 pm, Sunday through Saturday.</span></span> <span data-ttu-id="d2d3d-265">업무 시간 중에는 하지 않는 모든 시간은 *몇 시간 후*로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-265">All hours that aren't during business hours are considered *after hours*.</span></span>


![지난 시간 통화 흐름 설정 스크린샷](media/aa-afterhour.png)
 * * *

<span data-ttu-id="d2d3d-267">![숫자 1, 이전 스크린샷](media/teamscallout1.png) 의 설명선 **24/7 선택을** 클릭 하 여이 자동 전화 교환에 대 한 업무 시간을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-267">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) You can click **Select 24/7** to make all hours business hours for this auto attendant.</span></span>

<span data-ttu-id="d2d3d-268">![숫자 2의 아이콘, 이전 스크린샷](media/teamscallout2.png) 의 설명선은 일정의 모든 변경 내용을 되돌린 다음 **기본으로 재설정** 옵션을 선택 하 여 오전 9:00에서 5:00 pm 월요일부터 금요일까지 기본 정의 시간으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-268">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) Select the **Reset to default** option to revert all changes in the schedule and return to the default definition of business hours as 9:00 am to 5:00 pm Monday to Friday.</span></span>

<span data-ttu-id="d2d3d-269">![숫자 3의 아이콘, 이전 스크린샷](media/teamscallout3.png) 의 설명선에서는 일정을 완전히 지우는 **모든 시간 지우기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-269">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) Select **Clear all hours** to completely clear the schedule.</span></span> <span data-ttu-id="d2d3d-270">이 옵션을 선택 하 고 설정 해제 한 시간을 유지 하는 것은 권장 되지 않으므로 업무 시간을 완전히 다시 실행 하려는 경우에만이 옵션을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-270">Selecting this and leaving the hours unset is not recommended, so use this option only if you want to completely redo your business hours.</span></span>

<span data-ttu-id="d2d3d-271">![숫자 5의 이전 스크린샷](media/teamscallout4.png)![아이콘에 있는 설명선의 아이콘, 특정 요일의 시작 또는 종료 시간을 사용자 지정 하기 위한 이전](media/teamscallout5.png) 스크린샷의 설명선이 표시 되는 목록에서 **시작** 날짜 또는 **종료** 시간을 클릭 하 고 새 시간을 선택 합니다.  </span><span class="sxs-lookup"><span data-stu-id="d2d3d-271">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)  ![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png) To customize start or end time for a day of the week, click on **Start at** or **End at** time you wish to reset and select the new time from the list that appears.</span></span> <span data-ttu-id="d2d3d-272">이 목록을 사용 하 여 15 분 간격으로 업무 시간을 선택 하 고 여기에서 선택한 업무 시간은 **일반 정보** 페이지에서 설정한 표준 시간대를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-272">The list allows you to select business hours in 15-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span>

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

<span data-ttu-id="d2d3d-273">![숫자 6의 아이콘, 이전에는 나누기를 설정](media/teamscallout6.png) 하는 설명선 (예: 점심 작업)을 선택 하 고 해당 요일에 대해 새 테이블 행을 **추가** 하 여 새 시작 시간 및 종료 시간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-273">![Icon of the number 6,  a callout in the previous screenshot](media/teamscallout6.png)  To set up a break (a lunch break, for example), select **Add new time** for that day of the week to create anew table row, and select new start and end times.</span></span> <span data-ttu-id="d2d3d-274">업무 시간 내에 여러 휴식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-274">You can set multiple breaks within business hours.</span></span>

<span data-ttu-id="d2d3d-275">시간이 지난 후 사용할 수 있는 [통화 흐름](#call-flow) 옵션은 업무 시간 동안 사용할 수 있는 옵션과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-275">The [Call flow](#call-flow) options available after hours are the same as the options available during business hours.</span></span> <span data-ttu-id="d2d3d-276">정보 입력 페이지를 아래로 스크롤하여 시간 호출 흐름 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-276">Scroll down on the information entry page to set after hours call flow options.</span></span>

* * *

<span data-ttu-id="d2d3d-277">선택이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-277">When you are finished with your selections, click **Next**.</span></span> <span data-ttu-id="d2d3d-278">왼쪽 탐색 모음에서 **자원 계정을** 클릭 하 여 리소스 계정 페이지로 바로 이동 하 고 자동 전화 교환을 리소스 계정에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-278">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

##### <a name="call-flow-during-holidays"></a><span data-ttu-id="d2d3d-279">휴일 중 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="d2d3d-279">Call flow during holidays</span></span>

<span data-ttu-id="d2d3d-280"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-280"></span></span>

<span data-ttu-id="d2d3d-281">각 자동 전화 교환에 최대 20 개의 예정 휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-281">You can add up to 20 scheduled holidays to each auto attendant.</span></span> <span data-ttu-id="d2d3d-282">[Microsoft 팀의 휴일 설정](set-up-holidays-in-teams.md)에서 설명한 대로 조직에서 이미 휴일을 정의 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-282">Your organization may already have defined holidays as described in [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="d2d3d-283">그렇지 않으면 다음 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-283">If not you will see the following screen:</span></span> 

![스크린샷: 공휴일이 구성 되지 않음](media/aa-no-holidays.png)

<span data-ttu-id="d2d3d-285">![숫자 1, 위 스크린샷](media/teamscallout1.png) 의 설명선 자동 전화 교환의 명절에 대 한 사용자 지정 통화 흐름을 설정 하는 아이콘을 클릭 하 고 **새 명절 통화 흐름** 보기 화면을 **추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-285">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To set a custom call flow for a holiday on the auto attendant, click **+ Add** the see the **New holiday call flow** screen.</span></span>
> [!TIP]
> <span data-ttu-id="d2d3d-286">휴일을 만들려면 **조직 전체에 걸친 설정** > **명절**의 화면으로 이동 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-286">To create Holidays you can  go to the screen at **Org-wide settings** > **Holidays**.</span></span>  



![스크린샷: 호출 처리기 추가](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

<span data-ttu-id="d2d3d-288">![이전 스크린샷](media/teamscallout1.png) 의 설명선 인 번호 1의 아이콘은 새 통화 흐름의 **이름을** 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-288">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png)  Enter a **Name** for your new call flow.</span></span>

<span data-ttu-id="d2d3d-289">![이전 스크린샷](media/teamscallout2.png) 의 설명선 인 번호 2의 아이콘 이미 공휴일을 만든 경우 **휴일** 풀 다운 메뉴에 표시 되 고 해당 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-289">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you've already created holidays, you'll see them in the **Holiday** pull-down menu and can select them.</span></span> <span data-ttu-id="d2d3d-290">필요에 따라 편집할 수 있는 사용 되지 않는 옵션이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-290">You might see an unused option that you can edit into what you need.</span></span> <span data-ttu-id="d2d3d-291">그렇지 않은 경우 풀 다운 목록의 아래쪽에 있는 **추가** 를 클릭 하 여 새 공휴일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-291">If not, click on **Add** at the bottom of the pull-down list to create a new Holiday.</span></span>  <span data-ttu-id="d2d3d-292">휴일을 만드는 데 사용 되는 단계에 대해서는 [Microsoft 팀에서 휴일 설정을](set-up-holidays-in-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-292">See [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md) for the steps used to create a holiday.</span></span> 

<span data-ttu-id="d2d3d-293">명절 통화 흐름 이름은 최대 64 자까지 사용할 수 있으며, 조직에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-293">A holiday call flow name can be up to 64 characters long and must be unique for the organization.</span></span> <span data-ttu-id="d2d3d-294">예를 들어 같은 조직에서 "추수 감사절" 이라는 두 개의 휴일 통화 흐름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-294">For example, you can't have two holiday call flows named "Thanksgiving" in the same organization.</span></span> <span data-ttu-id="d2d3d-295">자동 전화 교환에는 설정한 각 휴일에 대 한 통화 흐름이 있을 수 있지만, 사용자 지정 된 인사말이 아닌 일반적인 동작 집합을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-295">Your auto attendant can have a call flow for each Holiday you've set up, but you might want to have a common set of behaviors planned other than a customized greeting.</span></span>

<span data-ttu-id="d2d3d-296">![숫자 3의 아이콘, 이전 스크린샷](media/teamscallout3.png) 의 설명선은 휴일 통화 흐름에 사용할 수 있는 [인사말](#call-flow) 옵션은 업무 시간 중에 사용할 수 있는 옵션과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-296">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) The [Greetings](#call-flow) options available for a holiday call flow are the same as the options available during business hours.</span></span> <span data-ttu-id="d2d3d-297">인사말이 재생 된 후 **에 수행할 수 있는 작업은** **연결 끊기** 또는 **리디렉션**만 가능 하 고 **리디렉션 옵션을** 선택 하면 해당 연산자가 사용 가능한 선택 항목 중 하나가 아님을 제외 하 고도 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-297">The **Actions** performed after the greeting plays is also similar, except that the only available actions are to **Disconnect** or **Redirect to**, and when choosing the **Redirect to** option the Operator is not one of the available choices.</span></span> <span data-ttu-id="d2d3d-298">휴일 흐름과 관련 된 메뉴를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-298">You can't set up a menu specific to a Holiday flow.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d3d-299">기본적으로 휴일 기간 중에 수신 되는 모든 통화는 인사말이 끝난 후 **연결을 끊도록** 설정 되므로 사용자 지정 동작을 원하는 경우에는 리디렉션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-299">By default, all calls received during a holiday period are set to **Disconnect** after the greeting (if any), so you must specify a redirect if you want a custom behavior.</span></span>

![공휴일 페이지의 통화 흐름 스크린샷](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

<span data-ttu-id="d2d3d-301">저장을 클릭 하 여 명절 통화 흐름 만들기를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-301">Click on Save to finish creating the Holiday call flow.</span></span> <span data-ttu-id="d2d3d-302">명절 통화 흐름을 만든 후에는 **휴일 화면 중에 통화 흐름** 에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-302">Once you have created a Holiday call flow, it will show up on the **Call Flows during holidays** screen.</span></span>

<span data-ttu-id="d2d3d-303">**다음** 을 클릭 하 여 전화 걸기 범위 설정, **뒤로** 시간 통화 흐름을 변경 하 고 작업을 완료 한 경우에는 **제출** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-303">Click on **Next** to set Dial scope, **Back** to make changes to after hour call flows, and **Submit** if you are finished.</span></span> <span data-ttu-id="d2d3d-304">왼쪽 탐색 모음에서 **자원 계정을** 클릭 하 여 리소스 계정 페이지로 바로 이동 하 고 자동 전화 교환을 리소스 계정에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-304">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="dial-scope"></a><span data-ttu-id="d2d3d-305">전화 걸기 범위</span><span class="sxs-lookup"><span data-stu-id="d2d3d-305">Dial scope</span></span>

<span data-ttu-id="d2d3d-306"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-306"></span></span>

![전화 걸기 범위 페이지를 보여 주는 스크린샷](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

<span data-ttu-id="d2d3d-308">이 페이지에서는 사용자가 조직에 전화를 걸 때 디렉터리에 나열 된 사용자 이름으로 전화를 걸 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-308">On this page, you can set who is listed in your directory and available for Dial by Name when a person calls your organization.</span></span> <span data-ttu-id="d2d3d-309">이전 화면에서 기본적으로 전화 걸기 이름을 **Off** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-309">Dial by name is set to **Off** by default in an earlier screen.</span></span> <span data-ttu-id="d2d3d-310">내선 **번호로 전화 걸기를** 이전에 선택한 경우에는 확장명을 가진 모든 사용자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-310">All users with an extension will be available if **Dial by extension** was selected earlier.</span></span>

<span data-ttu-id="d2d3d-311">![숫자 1의 아이콘, 이전 스크린샷](media/teamscallout1.png) 의 설명선은 **모든 온라인 사용자** 또는 **사용자 지정 사용자 그룹인** 이 섹션의 옵션을 **포함** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-311">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) **Include** The options in this section are either **All online users** or **Custom user groups**</span></span>

<span data-ttu-id="d2d3d-312">**모든 온라인 사용자**를 선택 하면 디렉터리 검색에 모든 적격 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-312">If you select **All online users**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="d2d3d-313">**사용자 지정 사용자 그룹** 이 옵션을 사용 하면 조직에서 이미 만든 Office 365 그룹, 메일 그룹 또는 보안 그룹을 검색 하 고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-313">**Custom user groups** This option lets you search for and select an Office 365 Group, distribution list, or security group already created in your organization.</span></span> <span data-ttu-id="d2d3d-314">사용자가 선택 된 Office 365 그룹, 메일 그룹 또는 보안 그룹과 온라인 사용자이 고, **전화 시스템 라이선스가** 있거나, 비즈니스용 Skype Server를 사용 하 여 온-프레미스에 호스팅되는 경우 해당 디렉터리가 디렉터리에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-314">Users are added to the directory if they are in the chosen Office 365 Group, distribution list, or security group and they are **Online users with a Phone System license** or hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="d2d3d-315">여러 개의 Office 365 그룹, 배포 목록, 보안 그룹을 디렉터리에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-315">You can add multiple Office 365 Groups, distribution lists, and security groups to the directory.</span></span>

<span data-ttu-id="d2d3d-316"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="d2d3d-316"></span></span>

<span data-ttu-id="d2d3d-317">이 페이지에서 조직에 속한 사용자가 디렉터리에 나열 되 고 조직에 전화를 거는 사용자가 이름으로 다이얼을 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-317">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

<span data-ttu-id="d2d3d-318">![숫자 2의 아이콘, 이전 스크린샷](media/teamscallout2.png) 의 설명선이 섹션의 옵션을 **제외** 하면 조직의 디렉터리에서 특정 사용자 또는 사용자 그룹을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-318">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Exclude** The options in this section let you exclude specific users or groups of users from the organization's directory.</span></span>

<span data-ttu-id="d2d3d-319">**없음**을 선택 하면 모든 적합 한 사용자가 디렉터리 검색에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-319">If you select **None**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="d2d3d-320">사용자 **지정 사용자 그룹** 조직에서 만든 Office 365 그룹, 메일 그룹 또는 보안 그룹을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-320">**Custom user group** You can search for an Office 365 Group, distribution list, or security group that has been created in your organization.</span></span> <span data-ttu-id="d2d3d-321">해당 그룹의 사용자는 디렉터리 검색에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-321">Users in that group are excluded from directory search.</span></span> <span data-ttu-id="d2d3d-322">여러 개의 Office 365 그룹, 배포 목록, 보안 그룹을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-322">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>


<span data-ttu-id="d2d3d-323">이름으로 전화 걸기를 사용할 때 설정을 기본값으로 두면 디렉터리 검색에 모든 적격 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-323">If you leave settings at their default when Dial by Name is enabled, all eligible users are included in directory search.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d3d-324">새 사용자가 디렉터리에 이름을 나열 하는 데 최대 36 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-324">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span> <span data-ttu-id="d2d3d-325">다른 사용자가 음성 인식을 사용 하 여 이름으로 전화 걸기를 사용 하는 경우이 기능에 대해 새 계정을 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-325">When someone uses Dial by Name with speech recognition, new accounts may not be available for this feature.</span></span>

<span data-ttu-id="d2d3d-326">필요한 모든 필드를 입력 하 고 통화 처리 메뉴 및 옵션을 설정한 후에 **다음** 을 클릭 하 여 자원 계정 연결을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-326">After you enter all the required fields and set up call handling menus and options, click **Next** to proceed to associating a resource account.</span></span>

#### <a name="resource-accounts"></a><span data-ttu-id="d2d3d-327">자원 계정</span><span class="sxs-lookup"><span data-stu-id="d2d3d-327">Resource accounts</span></span>

<span data-ttu-id="d2d3d-328">모든 자동 전화 교환에는 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-328">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="d2d3d-329">첫 번째 수준 자동 전화 교환에는 연결 된 서비스 번호가 있는 리소스 계정이 하나 이상 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-329">First level auto attendants will definitely need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="d2d3d-330">원하는 경우 자동 전화 교환에 여러 개의 리소스 계정을 할당할 수 있으며, 각각 별도의 서비스 번호를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-330">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="d2d3d-331">자동 전화 교환에 리소스 계정을 아직 구성 하지 않은 경우 다음 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-331">If you haven't already configured a resource account to your auto attendant, you would see the following screen:</span></span> 

![스크린샷: 리소스 계정 관리 (선택 사항)](media/aa-ra-optional.png) 

<span data-ttu-id="d2d3d-333">![1 개 이상의 기존 및 할당 되지 않은 리소스 계정을 자동 전화](media/teamscallout1.png) 교환에 추가 하는 이전 스크린샷의 아이콘 번호 1, **계정 추가** 및 검색을 차례로 클릭 하 고 제공 된 대화 상자에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-333">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add one or more existing and unassigned resource accounts to the auto attendant, click **Add accounts** and search and select them from the provided dialogs.</span></span>

![새 수행자 요약 보기 스크린샷](media/aa-assigned.png)

<span data-ttu-id="d2d3d-335">![숫자 1, 이전 스크린샷에](media/teamscallout1.png) 표시 된 설명선의 아이콘을 선택 하 여 추가 리소스 계정을 추가 하려면 **+ 계정 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-335">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add an additional resource account, click on **+ Add account**.</span></span>

![이전 스크린샷의 설명선 인 숫자 2의 아이콘](media/teamscallout2.png) <span data-ttu-id="d2d3d-337">이 자동 전화 교환에 할당 된 리소스 계정이 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-337">The resource account or accounts assigned to this auto attendant are shown in a list.</span></span>

## <a name="edit-auto-attendants"></a><span data-ttu-id="d2d3d-338">자동 전화 교환 편집</span><span class="sxs-lookup"><span data-stu-id="d2d3d-338">Edit auto attendants</span></span>

<span data-ttu-id="d2d3d-339">새 자동 전화 교환이 저장 되 면 **자동 전화** 교환 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-339">After you save your new auto attendant, it is listed on the **Auto attendants** page.</span></span> <span data-ttu-id="d2d3d-340">해당 페이지를 사용 하면 이름, 연결 된 자원 계정, 언어 및 할당 된 연산자를 포함 하 여 설정한 일부 옵션을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-340">That page allows you to quickly see some of the options that you have set up, including the name, associated resource account, language, and assigned Operator.</span></span>

![전화 교환 목록 스크린샷](media/aa-list.png)

<span data-ttu-id="d2d3d-342">자동 전화 교환 설정을 변경 하려는 경우 자동 전화 교환을 선택 하 고 작업 창에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-342">If you want to change auto attendant settings, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="d2d3d-343">Powershell을 사용 하 여 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="d2d3d-343">Create an auto attendant with Powershell</span></span>

<span data-ttu-id="d2d3d-344">PowerShell을 사용 하 여 자동 전화 교환을 만들고 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-344">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="d2d3d-345">자동 전화 교환을 관리 하는 데 필요한 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-345">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="d2d3d-346">신규-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d2d3d-346">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="d2d3d-347">Set-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d2d3d-347">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="d2d3d-348">Get-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d2d3d-348">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="d2d3d-349">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d2d3d-349">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="d2d3d-350">-CsAutoAttendant 전화 교환 제거</span><span class="sxs-lookup"><span data-stu-id="d2d3d-350">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="d2d3d-351">새로운 CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="d2d3d-351">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="d2d3d-352">새로운 CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="d2d3d-352">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="d2d3d-353">새로운 CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="d2d3d-353">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="d2d3d-354">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d2d3d-354">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="d2d3d-355">새로운 CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="d2d3d-355">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="d2d3d-356">새로운 CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="d2d3d-356">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="d2d3d-357">새로운 CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="d2d3d-357">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="d2d3d-358">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="d2d3d-358">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="d2d3d-359">새로운 CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="d2d3d-359">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="d2d3d-360">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="d2d3d-360">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="d2d3d-361">가져오기-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d2d3d-361">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="d2d3d-362">새로운 CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="d2d3d-362">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="d2d3d-363">Windows PowerShell에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d2d3d-363">More about Windows PowerShell</span></span>

- <span data-ttu-id="d2d3d-364">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-364">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d2d3d-365">Windows PowerShell을 사용 하 여 일상 업무를 단순화할 수 있는 단일 관리 지점에서 Office 365 및 Microsoft 팀을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-365">With Windows PowerShell, you can manage Office 365 and Microsoft Teams from a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="d2d3d-366">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-366">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d2d3d-367">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="d2d3d-367">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="d2d3d-368">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="d2d3d-368">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="d2d3d-369">Windows PowerShell에는 Microsoft 365 관리 센터를 사용 하는 경우 한 번에 여러 사용자의 설정을 변경 하는 것과 같은 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-369">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as making setting changes for many users at once.</span></span> <span data-ttu-id="d2d3d-370">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d2d3d-370">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d2d3d-371">Office 365 PowerShell을 사용 하 여 Office 365 관리</span><span class="sxs-lookup"><span data-stu-id="d2d3d-371">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="d2d3d-372">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="d2d3d-372">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="d2d3d-373">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d2d3d-373">Related topics</span></span>

[<span data-ttu-id="d2d3d-374">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="d2d3d-374">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="d2d3d-375">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="d2d3d-375">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="d2d3d-376">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="d2d3d-376">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="d2d3d-377">새로운 CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d2d3d-377">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="d2d3d-378">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="d2d3d-378">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="d2d3d-379">Small business 예 — 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="d2d3d-379">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
