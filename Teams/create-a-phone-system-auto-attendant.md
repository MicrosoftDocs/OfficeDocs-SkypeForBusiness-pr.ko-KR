---
title: Microsoft Teams에 대한 자동 참석자 설정
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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft Teams에 대한 자동 참석을 설정하고 테스트하는 방법을 배워야 합니다.
ms.openlocfilehash: bffe66fc59dfeb2f7028f2d5520b45930d753d07
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196632"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="da50a-103">자동 참석자 설정</span><span class="sxs-lookup"><span data-stu-id="da50a-103">Set up an auto attendant</span></span>

<span data-ttu-id="da50a-104">자동 전화 회의를 통해 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서, 통화 큐, 사람 또는 운영자에게 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="da50a-105">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 조직의 자동 참석자용 자동 참석을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="da50a-106">이 문서의 절차를 수행하기 전에 [Teams](plan-auto-attendant-call-queue.md) 자동 전화 회의 [](plan-auto-attendant-call-queue.md#getting-started) 및 통화 큐에 대한 계획을 읽고 시작 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="da50a-107">자동 전화 회의는 발신자 입력에 따라 다음 목적지 중 하나에 전화를 걸 수 있습니다. <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="da50a-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="da50a-108">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="da50a-109">비즈니스용 Skype Server를 사용하여 온라인 사용자 또는 온라인에서 호스팅되는 사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="da50a-110">**음성 앱** - 다른 자동 전화 걸기 또는 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="da50a-111">(이 대상을 선택할 때 자동 전화 연결 또는 통화 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="da50a-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="da50a-112">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="da50a-113">(외부 [전송 기술 세부 정보 참조).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="da50a-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="da50a-114">**음성 메일** - 지정한 Microsoft 365 그룹과 연결된 음성 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="da50a-115">**연산자** - 자동 attendant에 대해 정의된 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="da50a-116">연산자 정의는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-116">Defining an operator is optional.</span></span> <span data-ttu-id="da50a-117">연산자는 이 목록의 다른 대상 중 하나로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="da50a-118">자동 참석을 설정할 때 다양한 단계에서 이러한 옵션 중 하나를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="da50a-119">자동 참석을 설정하려면 Teams 관리 센터에서 음성을 확장하고 **자동** 참석을 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="da50a-120">일반 정보</span><span class="sxs-lookup"><span data-stu-id="da50a-120">General info</span></span>

![이름, 연산자, 표준 시간대, 언어 및 음성 입력에 대한 자동 Attendant 설정 스크린샷](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="da50a-122">맨 위에 있는 상자에 자동 참석자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="da50a-123">연산자를 지정하려는 경우 연산자에 대한 호출 대상을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="da50a-124">이는 선택 사항입니다(하지만 권장).</span><span class="sxs-lookup"><span data-stu-id="da50a-124">This is optional (but recommended).</span></span> <span data-ttu-id="da50a-125">발신자가  메뉴에서 나서 지정된 담당자에게 말하도록 연산자 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="da50a-126">이 자동 참석자에 대한 표준 시간대를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="da50a-127">표준 시간대는 시간 후 별도의 호출 흐름을 만드는 경우 업무 시간을 [계산하는 데 사용됩니다.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="da50a-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="da50a-128">이 자동 [참석자에](create-a-phone-system-auto-attendant-languages.md) 대해 지원되는 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-128">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="da50a-129">시스템 생성 음성 프롬프트에 사용되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-129">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="da50a-130">음성 입력을 사용하도록 설정할지 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="da50a-131">사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="da50a-132">예를 들어 발신자는 키 1에 매핑된 메뉴 옵션을 선택하기 위해 "One"이라고 말하거나 "판매"라고 말하여 "판매"라는 메뉴 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="da50a-133">4단계에서 음성 입력을 지원하지 않는 언어를 선택하면 이 옵션이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-133">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="da50a-134">다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-134">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="da50a-135">호출 흐름</span><span class="sxs-lookup"><span data-stu-id="da50a-135">Call flow</span></span>

![인사말 메시지 설정 스크린샷](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="da50a-137">자동 전화 문의가 통화에 응답할 때 인사말을 재생할지 선택</span><span class="sxs-lookup"><span data-stu-id="da50a-137">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="da50a-138">오디오 파일 **재생을** 선택하면 파일  업로드 단추를 사용하여 오디오로 저장된 녹화된 인사말 메시지를 업로드할 수 있습니다. WAV, . MP3 또는 . WMA 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-138">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="da50a-139">기록은 5MB보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-139">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="da50a-140">인사말  메시지 입력을 선택하면 자동 전화 문의가 전화를 걸 때 입력한 텍스트(최대 1,000자)를 시스템에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-140">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![통화 라우팅 설정 스크린샷](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="da50a-142">통화를 라우팅할 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-142">Choose how you want to route the call.</span></span>

<span data-ttu-id="da50a-143">연결 **끊기를 선택하면** 자동 전화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-143">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="da50a-144">리디렉션 **호출을 선택하는** 경우 통화 라우팅 대상 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-144">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="da50a-145">재생 **메뉴** 옵션을 선택하는 경우 인사말 메시지에서  오디오 파일 또는 입력을 재생한 다음 메뉴 옵션과 디렉터리 검색을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="da50a-145">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="da50a-146">메뉴 옵션</span><span class="sxs-lookup"><span data-stu-id="da50a-146">Menu options</span></span>

![다이얼 키 옵션 스크린샷](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="da50a-148">전화 걸기 옵션의 경우 전화 키패드의 0-9 키를 통화 라우팅 대상 중 하나에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-148">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="da50a-149">(키 \* (반복) 및 (뒤로)는 시스템에서 예약되어 있으며 다시 배정할 \# 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="da50a-149">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="da50a-150">키 매핑은 연속적이지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-150">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="da50a-151">예를 들어 키 0, 1 및 3이 옵션에 매핑된 메뉴를 만들 수 있으며 2개 키는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-151">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="da50a-152">0 키를 구성한 경우 연산자에 매핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-152">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="da50a-153">연산자가 키로 설정되지 않은 경우 음성 명령 "연산자"도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-153">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="da50a-154">각 메뉴 옵션에 대해 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-154">For each menu option, specify the following:</span></span>

- <span data-ttu-id="da50a-155">**전화기 키** - 이 옵션에 액세스하기 위한 전화 키패드의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-155">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="da50a-156">음성 입력을 사용할 수 있는 경우 발신자는 이 숫자를 말하여 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-156">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="da50a-157">**음성 명령** - 음성 입력이 활성화된 경우 발신자에서 이 옵션에 액세스하기 위해 부여할 수 있는 음성 명령을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-157">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="da50a-158">"고객 서비스" 또는 "작업 및 근거"과 같은 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-158">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="da50a-159">예를 들어 호출자에서 "2"라고 말하거나 "판매"라고 말하여 2 키에 매핑된 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-159">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="da50a-160">또한 이 텍스트는 서비스 확인 프롬프트에 대한 텍스트 음성으로 렌더링됩니다. "판매에 대한 호출 전송"일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-160">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="da50a-161">**리디렉션 -** 호출자에서 이 옵션을 선택할 때 사용되는 호출 라우팅 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-161">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="da50a-162">자동 전화 연결 또는 통화 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="da50a-162">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="da50a-163">디렉터리 검색</span><span class="sxs-lookup"><span data-stu-id="da50a-163">Directory search</span></span>

<span data-ttu-id="da50a-164">대상에 다이얼 키를 할당하는 경우 디렉터리 검색에 **대해 없음을** **선택하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-164">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="da50a-165">호출자는 특정 대상에 할당된 키를 사용하여 이름 또는 확장에 전화를 걸고 시도하는 경우 이름 또는 확장 입력을 완료하기 전에 예기치 않게 대상에 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-165">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="da50a-166">디렉터리 검색을 위해 별도의 자동 전화 접속을 만들고 다이얼 키를 통해 기본 자동 전화 접속 링크를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-166">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="da50a-167">다이얼 키를 할당하지 않은 경우 디렉터리 검색 옵션을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-167">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="da50a-168">**이름별로** 전화 걸기 - 이 옵션을 사용하도록 설정하면 발신자는 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-168">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="da50a-169">비즈니스용 Skype Server를 사용하여 온라인 사용자 또는 모든 온라인 사용자가 적격 사용자로, 전화 접속 이름으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-169">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="da50a-170">(전화 범위 페이지의 디렉터리에 포함되지 않은 사용자와 포함되지 않은 대상을 설정할 [수](#dial-scope) 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="da50a-170">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="da50a-171">**내선 번호로 전화** 걸기 - 이 옵션을 사용하도록 설정하면 발신자는 전화 내선 번호로 전화를 걸면 조직의 사용자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-171">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="da50a-172">비즈니스용 Skype Server를 사용하여 모든 온라인 사용자 또는 모든 사용자가 적격 사용자로 전화 걸기 확장명을 사용하여 찾을 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-172">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="da50a-173">(전화 범위 페이지의 디렉터리에 포함되지 않은 사용자와 포함되지 않은 대상을 설정할 [수](#dial-scope) 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="da50a-173">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="da50a-174">Dial By Extension을 사용할 수 있도록 설정하려면 Active Directory 또는 Azure Active Directory에 정의된 다음 전화 특성 [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 중 일부로 확장을 지정해야 합니다(자세한 내용은 개별적으로 또는 대량으로 사용자 추가 참조).</span><span class="sxs-lookup"><span data-stu-id="da50a-174">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="da50a-175">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="da50a-175">OfficePhone</span></span>
- <span data-ttu-id="da50a-176">HomePhone</span><span class="sxs-lookup"><span data-stu-id="da50a-176">HomePhone</span></span>
- <span data-ttu-id="da50a-177">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="da50a-177">Mobile/MobilePhone</span></span>
- <span data-ttu-id="da50a-178">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="da50a-178">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="da50a-179">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="da50a-179">OtherTelephone</span></span>

<span data-ttu-id="da50a-180">사용자 전화 번호 필드에 내선 번호를 입력하는 데 필요한 형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-180">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="da50a-181">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="da50a-181">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="da50a-182">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="da50a-182">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="da50a-183">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="da50a-183">*x\<extension>*</span></span>

- <span data-ttu-id="da50a-184">예제 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="da50a-184">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="da50a-185">예제 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="da50a-185">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="da50a-186">예제 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="da50a-186">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="da50a-187">[Microsoft 365](https://admin.microsoft.com/) 관리 센터 또는 Azure Active Directory 관리 센터에서 확장을 [설정할 수 있습니다.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="da50a-187">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="da50a-188">자동 전화 회의 및 통화 큐에서 변경 내용을 사용할 수 있는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-188">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="da50a-189">전화 걸기 이름  및 내선  번호로 전화 걸기 기능을 모두 사용하려는 경우 기본 자동 전화 번호에서 다이얼 키를 할당하여 전화로 전화 걸기를 사용하도록 설정된 자동 전화 번호에 **도달할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-189">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="da50a-190">해당 자동 전화 접속자 내에서 1개 키(문자와 연결된 문자가 없는)를 할당하여 **내선** 번호 자동 전화 접속 전화 걸기에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-190">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="da50a-191">디렉터리 검색 옵션을 선택한 **후** 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="da50a-192">시간 후의 호출 흐름</span><span class="sxs-lookup"><span data-stu-id="da50a-192">Call flow for after hours</span></span>

![시간 후 및 시간 설정 스크린샷](media/auto-attendant-business-hours.png)

<span data-ttu-id="da50a-194">각 자동 참석자에 대해 업무 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="da50a-195">업무 시간을 설정하지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 해당 날의 모든 일 및 모든 시간은 업무 시간으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="da50a-196">업무 시간은 하루 중 시간의 시간으로 설정할 수 있으며, 근무 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="da50a-197">다른 수신 호출 처리 옵션과 인사말을 시간 후의 인사말로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="da50a-198">자동 전화 회의 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 전화 참석에 대한 시간 후 통화 라우팅만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="da50a-199">시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 각 날짜의 업무 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="da50a-200">예를 **들어 새 시간 추가를** 클릭하여 특정 날짜에 대해 여러 시간 집합을 지정하여 점심 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="da50a-201">업무 시간을 지정한 후 시간 후 통화 라우팅 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-201">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="da50a-202">위에서 지정한 업무 시간 통화 라우팅과 동일한 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-202">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="da50a-203">완료되면 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-203">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="da50a-204">공휴일 동안 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="da50a-204">Call flows during holidays</span></span>

![휴일 및 휴일 인사말 설정 스크린샷](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="da50a-206">자동 전화 걸기에는 설정한 각 휴일에 대한 통화 [흐름이 있습니다.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="da50a-206">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="da50a-207">각 자동 참석자에 최대 20회의 예정된 공휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-207">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="da50a-208">휴일 통화 설정 페이지에서 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-208">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="da50a-209">이 휴일 설정의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-209">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="da50a-210">휴일 **드롭다운에서** 사용할 공휴일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-210">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="da50a-211">사용할 인사말 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-211">Choose the type of greeting that you want to use.</span></span>

    ![휴일 통화 작업 설정 스크린샷](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="da50a-213">통화 연결을 끊거나 **리디렉션할지** 선택 합니다. </span><span class="sxs-lookup"><span data-stu-id="da50a-213">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="da50a-214">리디렉션을 선택한 경우 통화에 대한 통화 라우팅 대상을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="da50a-214">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="da50a-215">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-215">Click **Save**.</span></span>

![공휴일이 나열된 휴일 설정 스크린샷](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="da50a-217">추가 공휴일마다 필요에 따라 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-217">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="da50a-218">모든 공휴일을 추가한 경우 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-218">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="da50a-219">다이얼 범위</span><span class="sxs-lookup"><span data-stu-id="da50a-219">Dial scope</span></span>

![다이얼 범위 포함 및 제외 옵션 스크린샷](media/auto-attendant-dial-scope.png)

<span data-ttu-id="da50a-221">다이얼 *범위는* 발신자에서 전화 접속 이름 또는 다이얼로 확장을 사용할 때 디렉터리에서 사용할 수 있는 사용자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-221">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="da50a-222">모든 온라인 사용자의 **기본값에는** 비즈니스용 Skype 서버를 사용하여 온라인 사용자 또는 호스팅되는 조직의 모든 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-222">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="da50a-223">포함 또는 제외에서 사용자 지정 사용자 그룹을  선택하고  하나 이상의 Microsoft 365 그룹, 메일 그룹 또는 보안 그룹을 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="da50a-223">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="da50a-224">예를 들어 조직의 임원을 전화 걸기 디렉터리에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-224">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="da50a-225">(사용자가 두 목록에 모두 있는 경우 디렉터리에서 제외됩니다.)</span><span class="sxs-lookup"><span data-stu-id="da50a-225">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="da50a-226">새 사용자가 디렉터리에 자신의 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-226">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="da50a-227">다이얼 범위 설정을 완료하면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-227">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="da50a-228">리소스 계정</span><span class="sxs-lookup"><span data-stu-id="da50a-228">Resource accounts</span></span>

<span data-ttu-id="da50a-229">모든 자동 참석자에는 연결된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-229">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="da50a-230">첫 번째 수준 자동 전화 회의에는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-230">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="da50a-231">원하는 경우 각각 별도의 서비스 번호가 있는 자동 전화 회의에 여러 리소스 계정을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-231">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![리소스 계정 계정 추가 패널의 스크린샷](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="da50a-233">리소스 계정을 추가하려면 **계정** 추가를 클릭하고 추가할 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-233">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="da50a-234">**추가를** 클릭한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-234">Click **Add**, and then click **Add**.</span></span>

![서비스 번호가 할당된 리소스 계정을 보여주는 리소스 계정 목록의 스크린샷](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="da50a-236">서비스 계정 추가를 마쳤을 때 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da50a-236">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="da50a-237">이렇게 하여 자동 attendant 구성이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-237">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="da50a-238">외부 전화 번호 전송 - 기술 세부 정보</span><span class="sxs-lookup"><span data-stu-id="da50a-238">External phone number transfers - technical details</span></span>

<span data-ttu-id="da50a-239">자동 전화가 [](plan-auto-attendant-call-queue.md#prerequisites) 외부로 통화를 전송할 수 있도록 허용하기 위해 전제 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-239">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="da50a-240">또한:</span><span class="sxs-lookup"><span data-stu-id="da50a-240">In addition:</span></span>

- <span data-ttu-id="da50a-241">통화 계획 번호가 [](calling-plans-for-office-365.md) 있는 리소스 계정의 경우 외부 전송 전화 번호는 E.164 형식(+[국가 코드][지역 번호][전화 번호])으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-241">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="da50a-242">직접 라우팅 번호가 있는 리소스 계정의 경우 외부 전송 전화 번호 형식은 [SBC(세션](direct-routing-connect-the-sbc.md) 테두리 컨트롤러) 설정에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-242">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="da50a-243">표시되는 아웃바운드 전화 번호는 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-243">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="da50a-244">통화 요금제 번호의 경우 원래 발신자 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-244">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="da50a-245">직접 라우팅 번호의 경우 전송되는 번호는 다음과 같이 SBC의 PAI(P-Asserted-Identity) 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-245">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="da50a-246">사용 안 으로 설정하면 원래 발신자 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-246">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="da50a-247">이 설정은 기본 설정으로 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-247">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="da50a-248">사용으로 설정하면 리소스 계정 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-248">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="da50a-249">비즈니스용 Skype 하이브리드 환경에서 자동 전화 걸기 통화를 PSTN으로 전송하기 위해 PSTN 번호로 설정된 통화 전달 기능을 사용하여 새 On-프레미스 사용자를 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-249">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="da50a-250">사용자가 사용자에 대해 사용하도록 Enterprise Voice 음성 정책이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-250">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="da50a-251">자세한 내용은 PSTN으로 자동 전화 [걸기 전송을 참조합니다.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="da50a-251">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="da50a-252">PowerShell을 사용하여 자동 참석자 만들기</span><span class="sxs-lookup"><span data-stu-id="da50a-252">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="da50a-253">PowerShell을 사용하여 자동 Attendants를 만들고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-253">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="da50a-254">자동 참석자 관리에 필요한 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-254">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="da50a-255">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="da50a-255">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="da50a-256">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="da50a-256">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="da50a-257">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="da50a-257">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="da50a-258">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="da50a-258">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="da50a-259">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="da50a-259">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="da50a-260">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="da50a-260">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="da50a-261">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="da50a-261">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="da50a-262">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="da50a-262">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="da50a-263">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="da50a-263">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="da50a-264">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="da50a-264">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="da50a-265">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="da50a-265">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="da50a-266">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="da50a-266">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="da50a-267">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="da50a-267">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="da50a-268">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="da50a-268">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="da50a-269">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="da50a-269">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="da50a-270">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="da50a-270">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="da50a-271">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="da50a-271">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="da50a-272">관련 주제</span><span class="sxs-lookup"><span data-stu-id="da50a-272">Related topics</span></span>

[<span data-ttu-id="da50a-273">다음은 통화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="da50a-273">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="da50a-274">서비스 통화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="da50a-274">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="da50a-275">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="da50a-275">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="da50a-276">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="da50a-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
