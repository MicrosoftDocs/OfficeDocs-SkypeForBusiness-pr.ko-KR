---
title: Microsoft 팀에 대 한 자동 전화 교환 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
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
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft 팀에 대 한 자동 전화 교환을 설정 하 고 테스트 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bda0772f26e0adf996461f838b5f0978341d0e82
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48840418"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="519d4-103">자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="519d4-103">Set up an auto attendant</span></span>

<span data-ttu-id="519d4-104">자동 전화 교환을 통해 사용자는 조직에 게 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람 또는 교환원에 게 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="519d4-105">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 조직에 대 한 자동 전화 교환을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="519d4-106">이 문서의 절차를 따르기 전에 [팀 자동 전화 교환 및 통화 대기열에 대 한 요금제](plan-auto-attendant-call-queue.md) 를 확인 하 고 [시작 단계](plan-auto-attendant-call-queue.md#getting-started) 를 팔 로우 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="519d4-107">자동 전화 교환의 경우 발신자의 입력에 따라 다음 중 한 가지 대상에 게 전화를 걸 수 있습니다. <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="519d4-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="519d4-108">**조직 내 사람** -음성 통화를 받을 수 있는 조직의 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="519d4-109">이는 비즈니스용 Skype 서버를 사용 하 여 온-프레미스 사용자 또는 온라인 사용자 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="519d4-110">**음성 앱** -다른 자동 전화 교환 또는 통화 대기열.</span><span class="sxs-lookup"><span data-stu-id="519d4-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="519d4-111">(이 대상을 선택할 때 자동 전화 교환 또는 통화 대기열과 연결 된 리소스 계정을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="519d4-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="519d4-112">**외부 전화 번호** -전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="519d4-113">( [외부 이전 기술 정보](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="519d4-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="519d4-114">보이스 **메일** -사용자가 지정 하는 Microsoft 365 그룹과 연결 된 음성 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="519d4-115">**Operator** -자동 전화 교환에 대해 정의 된 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="519d4-116">연산자 정의는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-116">Defining an operator is optional.</span></span> <span data-ttu-id="519d4-117">이 연산자는이 목록의 다른 대상 중 하에 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="519d4-118">자동 전화 교환을 설정 하는 다양 한 단계에서 이러한 옵션 중 하나를 선택 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="519d4-119">자동 전화 교환을 설정 하려면 팀 관리 센터에서 **음성을** 확장 하 고 **자동 전화 교환을** 클릭 한 다음 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-119">To set up an auto attendant, in the Teams admin center, expand **Voice** , click **Auto attendants** , and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="519d4-120">일반 정보</span><span class="sxs-lookup"><span data-stu-id="519d4-120">General info</span></span>

![이름, 운영자, 표준 시간대, 언어 및 음성 입력에 대 한 자동 전화 교환 설정 스크린샷](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="519d4-122">맨 위의 상자에 자동 전화 교환 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="519d4-123">연산자를 지정 하려는 경우 연산자에 대 한 호출 대상을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="519d4-124">선택 사항입니다 (권장).</span><span class="sxs-lookup"><span data-stu-id="519d4-124">This is optional (but recommended).</span></span> <span data-ttu-id="519d4-125">호출자가 메뉴를 차단 하 고 지정 된 사람에 게 말할 수 있도록 **연산자** 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="519d4-126">이 자동 전화 교환의 표준 시간대를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="519d4-127">표준 시간대는 근무 시간 동안 [별도의 통화 흐름을 만든](#call-flow-for-after-hours)경우 업무 시간을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="519d4-128">이 자동 전화 교환의 언어를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="519d4-129">시스템 생성 음성 메시지에 사용 되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="519d4-130">음성 입력을 사용할 것인지 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="519d4-131">이 설정을 사용 하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="519d4-132">예를 들어 발신자는 "One" 이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택 하거나 "Sales" 라고 말하여 "Sales" 라는 메뉴 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="519d4-133">**다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="519d4-134">통화 흐름</span><span class="sxs-lookup"><span data-stu-id="519d4-134">Call flow</span></span>

![인사말 메시지 설정 스크린샷](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="519d4-136">자동 전화 교환에서 전화를 걸 때 인사말을 재생할 것인지 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="519d4-137">**오디오 파일 재생** 을 선택 하는 경우 **파일 업로드** 단추를 사용 하 여 오디오로 저장 된 녹음/녹화 된 인사말 메시지를 업로드할 수 있습니다. WAV,. MP3 또는. WMA 형식.</span><span class="sxs-lookup"><span data-stu-id="519d4-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="519d4-138">기록의 크기는 5mb를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="519d4-139">**인사말 메시지 입력** 을 선택 하면 시스템에서 자동 전화 교환이 전화를 받을 때 입력 한 텍스트 (최대 1000 자) 텍스트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![통화 라우팅 설정 스크린샷](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="519d4-141">통화를 회람할 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="519d4-142">**연결 끊기를** 선택 하면 자동 전화 교환이 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-142">If you select **Disconnect** , the auto attendant will hang up the call.</span></span>

<span data-ttu-id="519d4-143">**통화 리디렉션을** 선택한 경우에는 호출 라우팅 대상 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-143">If you select **Redirect call** , you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="519d4-144">**재생 메뉴 옵션** 을 선택한 경우 **오디오 파일 재생** 또는 **인사말 메시지 입력** 을 선택 하 고 메뉴 옵션 및 디렉터리 검색 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-144">If you select **Play menu options** , you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="519d4-145">메뉴 옵션</span><span class="sxs-lookup"><span data-stu-id="519d4-145">Menu options</span></span>

![전화 걸기 키 옵션 스크린샷](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="519d4-147">전화 걸기 옵션의 경우 전화 키패드의 0-9 키를 호출 라우팅 대상 중 하나에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="519d4-148">(키 \* (Repeat) \# 는 시스템에 의해 예약 되며 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="519d4-149">키 매핑은 연속적으로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="519d4-150">예를 들어 옵션에 매핑된 키가 0, 1, 3 인 메뉴를 만들 수 있지만, 2 개의 키는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="519d4-151">1을 구성한 경우 연산자에 0 키를 매핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="519d4-152">연산자가 아무 키로도 설정 되지 않은 경우 음성 명령 "연산자"를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="519d4-153">각 메뉴 옵션에 대해 다음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="519d4-154">**Dial 키** -이 옵션에 액세스 하려면 전화 키패드에서 키를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="519d4-155">음성 입력을 사용할 수 있는 경우 발신자는이 번호를 발음 하 여 옵션에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="519d4-156">**음성 명령** -음성 입력이 활성화 된 경우이 옵션에 액세스 하기 위해 발신자가 지정할 수 있는 음성 명령을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="519d4-157">"고객 서비스" 또는 "작업 및 Grounds"과 같은 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="519d4-158">예를 들어 발신자는 2를 누르거나 "2" 라고 말하고 "Sales" 라고 말하여 2 개의 키에 매핑된 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="519d4-159">이 텍스트는 "영업에 대 한 통화 전환 중" 처럼 서비스 확인 프롬프트에 대해 텍스트를 음성으로 렌더링 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="519d4-160">**이동:** 발신자가이 옵션을 선택할 때 사용 되는 호출 라우팅 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="519d4-161">자동 전화 교환 또는 통화 대기열로 리디렉션하는 경우에는 연결 된 리소스 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="519d4-162">디렉터리 검색</span><span class="sxs-lookup"><span data-stu-id="519d4-162">Directory search</span></span>

<span data-ttu-id="519d4-163">대상에 전화 걸기 키를 지정 하는 경우 **디렉터리 검색** 에 대해 **없음** 을 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="519d4-164">발신자가 특정 대상에 지정 된 키를 사용 하 여 이름 또는 내선 번호를 다이얼 하려고 하면 이름 또는 내선 번호 입력을 마치기 전에 예기치 않게 대상에 경로를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="519d4-165">디렉터리 검색을 위해 별도의 자동 전화 교환을 만들고 전화 접속 키를 통해 해당 사용자에 게 기본 자동 전화 교환을 연결 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="519d4-166">다이얼 키를 지정 하지 않은 경우에는 **디렉터리 검색** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="519d4-167">**이름으로 전화 걸기** -이 옵션을 사용 하도록 설정 하는 경우 발신자는 사용자의 이름을 말할 수 있고 전화 키패드에서 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="519d4-168">전화 시스템 라이선스가 있는 모든 온라인 사용자 또는 비즈니스용 Skype 서버를 사용 하 여 온-프레미스에 호스팅되는 사용자는 적격 사용자 이며 이름으로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="519d4-169">( [전화 범위](#dial-scope) 페이지의 디렉터리에 포함 되지 않은 사용자를 설정할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="519d4-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="519d4-170">**내선 번호로 전화 걸기** -이 옵션을 사용 하도록 설정 하는 경우 발신자는 휴대폰 내선 번호로 전화를 걸어 조직의 사용자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="519d4-171">휴대폰 시스템 라이선스가 있는 모든 온라인 사용자 또는 비즈니스용 Skype를 사용 하 여 온-프레미스에 호스팅되는 모든 사용자는 적격 사용자 이며, **내선 번호로 전화 접속** 을 통해 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="519d4-172">( [전화 범위](#dial-scope) 페이지의 디렉터리에 포함 되지 않은 사용자를 설정할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="519d4-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="519d4-173">내선 번호로 전화 접속을 사용할 수 있도록 하려는 사용자는 Active Directory 또는 Azure Active Directory에 정의 된 다음 phone 특성 중 하나의 일부로 확장명을 지정 해야 합니다 (자세한 내용은 추가 정보를 보려면 [사용자를 개별적으로 추가 또는 대량 입력](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 참조).</span><span class="sxs-lookup"><span data-stu-id="519d4-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="519d4-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="519d4-174">OfficePhone</span></span>
- <span data-ttu-id="519d4-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="519d4-175">HomePhone</span></span>
- <span data-ttu-id="519d4-176">모바일/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="519d4-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="519d4-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="519d4-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="519d4-178">기타 전화</span><span class="sxs-lookup"><span data-stu-id="519d4-178">OtherTelephone</span></span>

<span data-ttu-id="519d4-179">사용자 전화 번호 필드에 확장명을 입력 하는 데 필요한 형식은 *+ <phone number> ext = <extension>* 또는 *+ <phone number> x <extension>* 입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-179">The required format to enter the extension in the user phone number field is either *+<phone number>ext=<extension>* or *+<phone number>x<extension>*.</span></span>

<span data-ttu-id="519d4-180">[Microsoft 365 관리 센터](https://admin.microsoft.com/) 또는 [Azure Active Directory 관리 센터](https://aad.portal.azure.com)에서 확장을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-180">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="519d4-181">자동 전화 교환 및 통화 대기열에서 변경 사항을 사용할 수 있으려면 최대 12 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-181">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="519d4-182">**이름으로 전화 걸기** 및 **내선** 번호를 사용 하 여 전화를 걸 때, 기본 자동 전화 교환에 다이얼 키를 할당 하 여 **전화를 걸** 수 있는 자동 전화 교환에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-182">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="519d4-183">해당 자동 전화 교환 내에서 **전화를 걸 때 내선** 번호 자동 전화 교환에 도달 하는 1 개의 키 (이에는 연결 된 문자가 없음)를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-183">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="519d4-184">**디렉터리 검색** 옵션을 선택한 후 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-184">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="519d4-185">이후 시간에 대 한 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="519d4-185">Call flow for after hours</span></span>

![시간 및 시간 설정 후의 스크린샷](media/auto-attendant-business-hours.png)

<span data-ttu-id="519d4-187">각 자동 전화 교환에 대해 업무 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-187">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="519d4-188">비즈니스 시간이 설정 되어 있지 않으면 24/7 일정이 기본적으로 설정 되어 있으므로 일의 모든 일과 모든 시간이 시간으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-188">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="519d4-189">업무 시간에는 하루에 휴식 시간을 설정할 수 있으며 업무 시간으로 설정 되지 않은 모든 시간은 근무 시간 이후로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-189">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="519d4-190">한 시간 내에 다른 수신 통화 처리 옵션과 인사말을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-190">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="519d4-191">자동 전화 교환 및 통화 대기열을 구성한 방법에 따라 직접 전화 번호를 사용 하 여 자동 전화 교환에 대 한 다음 시간 후 통화 라우팅을 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-191">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="519d4-192">시간 단위 호출자에 대해 별도의 통화 라우팅이 필요한 경우 각 날짜별로 업무 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-192">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="519d4-193">지정 된 날짜에 여러 시간 집합을 지정 하려면 **새 시간 추가** 를 클릭 합니다 (예: 점심 약속 중단을 지정).</span><span class="sxs-lookup"><span data-stu-id="519d4-193">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="519d4-194">업무 시간을 지정한 후에는 시간이 지난 후 통화 회람 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-194">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="519d4-195">위에서 지정한 업무 시간 통화 라우팅과 동일한 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-195">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="519d4-196">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-196">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="519d4-197">휴일 중 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="519d4-197">Call flows during holidays</span></span>

![명절 및 명절 인사말 설정 스크린샷](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="519d4-199">자동 전화 교환에는 [설정한 각 휴일](set-up-holidays-in-teams.md)에 대 한 통화 흐름이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-199">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="519d4-200">각 자동 전화 교환에 최대 20 개의 예정 휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-200">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="519d4-201">명절 통화 설정 페이지에서 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-201">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="519d4-202">이 공휴일 설정의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-202">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="519d4-203">**휴일** 드롭다운에서 사용 하려는 휴일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-203">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="519d4-204">사용할 인사말 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-204">Choose the type of greeting that you want to use.</span></span>

    ![명절 통화 동작 설정 스크린샷](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="519d4-206">**연결을 끊거나** 통화를 **리디렉션할지** 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-206">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="519d4-207">리디렉션을 선택한 경우 통화 회람 대상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-207">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="519d4-208">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-208">Click **Save**.</span></span>

![공휴일이 나열 된 휴일 설정 스크린샷](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="519d4-210">각 휴일에 대해 필요에 따라이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-210">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="519d4-211">모든 공휴일을 추가 했으면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-211">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="519d4-212">전화 걸기 범위</span><span class="sxs-lookup"><span data-stu-id="519d4-212">Dial scope</span></span>

![다이얼 범위 스크린샷 포함 및 제외 옵션](media/auto-attendant-dial-scope.png)

<span data-ttu-id="519d4-214">*전화 걸기 범위* 는 발신자가 이름 또는 내선 번호를 사용 하 여 전화를 걸 때 디렉터리에서 사용할 수 있는 사용자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-214">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="519d4-215">**모든 온라인 사용자** 의 기본값에는 비즈니스용 Skype 서버를 사용 하 여 온라인 사용자가 전화 시스템 라이선스 또는 온-프레미스에 호스팅되는 조직의 모든 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-215">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="519d4-216">**포함** 또는 **제외** 에서 **사용자 지정 사용자 그룹** 을 선택 하 고 하나 이상의 Microsoft 365 그룹, 배포 목록 또는 보안 그룹을 선택 하 여 특정 사용자를 포함 하거나 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-216">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="519d4-217">예를 들어, 전화 접속 디렉터리에서 조직의 임원을 제외 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-217">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="519d4-218">(사용자가 두 목록에 모두 있는 경우 해당 디렉터리에서 제외 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="519d4-218">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="519d4-219">새 사용자가 디렉터리에 이름을 나열 하는 데 최대 36 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-219">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="519d4-220">전화 걸기 범위 설정을 마쳤으면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-220">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="519d4-221">자원 계정</span><span class="sxs-lookup"><span data-stu-id="519d4-221">Resource accounts</span></span>

<span data-ttu-id="519d4-222">모든 자동 전화 교환에는 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-222">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="519d4-223">첫 번째 수준 자동 전화 교환에는 연결 된 서비스 번호가 있는 리소스 계정이 하나 이상 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-223">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="519d4-224">원하는 경우 자동 전화 교환에 여러 개의 리소스 계정을 할당할 수 있으며, 각각 별도의 서비스 번호를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-224">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![리소스 계정, 계정 추가 패널 스크린샷](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="519d4-226">리소스 계정을 추가 하려면 **계정 추가** 를 클릭 하 고 추가 하려는 계정을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-226">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="519d4-227">**추가** 를 클릭 한 다음 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-227">Click **Add** , and then click **Add**.</span></span>

![배정 된 서비스 번호가 있는 자원 계정이 표시 된 자원 계정 목록의 스크린샷](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="519d4-229">서비스 계정 추가를 마쳤으면 **제출을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-229">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="519d4-230">자동 전화 교환 구성이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-230">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="519d4-231">외부 전화 번호 전송-기술 세부 정보</span><span class="sxs-lookup"><span data-stu-id="519d4-231">External phone number transfers - technical details</span></span>

<span data-ttu-id="519d4-232">외부 전화 번호로 통화를 전송할 때 자동 전화 교환 또는 통화 대기열과 연결 된 리소스 계정에는 전화 번호와 Microsoft 365 전화 시스템-가상 사용자 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-232">When transferring calls to an external phone number, the resource account associated with the auto attendant or call queue must have a phone number and a Microsoft 365 Phone System - Virtual User license.</span></span> <span data-ttu-id="519d4-233">업데이트로</span><span class="sxs-lookup"><span data-stu-id="519d4-233">Additionally:</span></span>

- <span data-ttu-id="519d4-234">통화 요금제 번호가 있는 자원 계정의 경우, [통화 요금제](calling-plans-for-office-365.md) 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-234">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
  - <span data-ttu-id="519d4-235">외부 전송 전화 번호는 E-164 형식으로 입력 해야 합니다 (+ CC + phone_number).</span><span class="sxs-lookup"><span data-stu-id="519d4-235">The external transfer phone number must be entered in E.164 format (+CC+phone_number).</span></span>

- <span data-ttu-id="519d4-236">직접 라우팅 번호가 있는 리소스 계정의 경우 [온라인 음성 라우팅 정책을](manage-voice-routing-policies.md)할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-236">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
  - <span data-ttu-id="519d4-237">외부 전송 전화 번호 형식은 [SBC (세션 경계 컨트롤러)](https://docs.microsoft.com/microsoftteams/direct-routing-connect-the-sbc) 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-237">The external transfer phone number format is dependant on your [Session Border Controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-connect-the-sbc) settings.</span></span>

<span data-ttu-id="519d4-238">표시 되는 아웃 바운드 전화 번호는 다음과 같이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-238">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="519d4-239">통화 요금제 번호의 경우 최초 발신자의 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-239">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="519d4-240">직접 라우팅 번호의 경우 전송 되는 숫자는 다음과 같이 SBC에 대 한 P-어설션된-Identity (PAI) 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-240">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="519d4-241">사용 안 함으로 설정 하면 최초 발신자의 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-241">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="519d4-242">이 설정이 기본값 이며 권장 되는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-242">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="519d4-243">사용으로 설정 하면 리소스 계정 전화 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-243">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="519d4-244">통화 요금제 trunks와 다이렉트 라우팅 trunks 간에 전송이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-244">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

<span data-ttu-id="519d4-245">하이브리드 환경에서 비즈니스용 Skype PSTN 통합을 통해 PSTN으로 자동 전화 교환 통화를 전송 하려면 통화 전달을 PSTN 번호로 설정한 상태로 새 온-프레미스 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-245">In a hybrid environment, to transfer an auto attendant call to the PSTN via Skype for Business PSTN integration, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="519d4-246">사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 하 고 음성 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-246">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="519d4-247">자세한 내용은 [PSTN으로 자동 전화 교환 통화 전송을](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="519d4-247">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="519d4-248">PowerShell을 사용 하 여 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="519d4-248">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="519d4-249">PowerShell을 사용 하 여 자동 전화 교환을 만들고 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-249">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="519d4-250">자동 전화 교환을 관리 하는 데 필요한 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-250">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="519d4-251">신규-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="519d4-251">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="519d4-252">Set-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="519d4-252">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="519d4-253">Get-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="519d4-253">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="519d4-254">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="519d4-254">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="519d4-255">-CsAutoAttendant 전화 교환 제거</span><span class="sxs-lookup"><span data-stu-id="519d4-255">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="519d4-256">새로운 CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="519d4-256">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="519d4-257">새로운 CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="519d4-257">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="519d4-258">새로운 CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="519d4-258">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="519d4-259">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="519d4-259">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="519d4-260">새로운 CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="519d4-260">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="519d4-261">새로운 CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="519d4-261">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="519d4-262">새로운 CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="519d4-262">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="519d4-263">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="519d4-263">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="519d4-264">새로운 CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="519d4-264">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="519d4-265">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="519d4-265">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="519d4-266">가져오기-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="519d4-266">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="519d4-267">새로운 CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="519d4-267">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a><span data-ttu-id="519d4-268">관련 항목</span><span class="sxs-lookup"><span data-stu-id="519d4-268">Related topics</span></span>

[<span data-ttu-id="519d4-269">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="519d4-269">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="519d4-270">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="519d4-270">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="519d4-271">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="519d4-271">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="519d4-272">Small business 예 — 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="519d4-272">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="519d4-273">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="519d4-273">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
