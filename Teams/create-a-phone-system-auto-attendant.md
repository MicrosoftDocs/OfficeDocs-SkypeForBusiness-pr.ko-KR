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
description: Microsoft Teams에 대한 자동 참석자 설정 및 테스트 방법에 대해 자세히 알아보고 있습니다.
ms.openlocfilehash: deb9bf013136bb8efd9171e5562de5e2ba1b631f
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347869"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="01631-103">자동 참석자 설정</span><span class="sxs-lookup"><span data-stu-id="01631-103">Set up an auto attendant</span></span>

<span data-ttu-id="01631-104">자동 참석자는 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서에 문의하고 큐, 사람 또는 운영자에게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="01631-105">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 조직에 대한 자동 참석자 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="01631-106">Teams 자동 참석자 계획을 읽고 큐를 호출하고 이 [](plan-auto-attendant-call-queue.md#getting-started) 문서의 절차를 따르기 전에 시작 단계를 수행해야 합니다. [](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="01631-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="01631-107">자동 참석자는 발신자 입력에 따라 다음 대상 중 하나에 전화를 걸 수 있습니다. <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="01631-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="01631-108">**연산자** - 자동 참석자에 대해 정의된 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="01631-109">연산자 정의는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-109">Defining an operator is optional.</span></span> <span data-ttu-id="01631-110">연산자는 이 목록의 다른 대상 중 하나로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="01631-111">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="01631-112">비즈니스용 Skype 서버를 사용하여 온라인 사용자 또는 사내에서 호스팅되는 사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-112">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="01631-113">**음성 앱** - 다른 자동 참석자 또는 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="01631-114">(이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)</span><span class="sxs-lookup"><span data-stu-id="01631-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="01631-115">**Voicemail** - 지정한 Microsoft 365 그룹과 연결된 음성 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="01631-116">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="01631-117">(외부 [전송 기술 세부 정보 참조).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="01631-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="01631-118">**공지** - 오디오 파일을 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-118">**Announcement** - Play an audio file.</span></span> <span data-ttu-id="01631-119">업로드한 기록된 공지 메시지는 에서 오디오로 저장됩니다. WAV, . MP3 또는 . WMA 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="01631-120">기록은 5MB보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="01631-121">시스템에서 공지 사항을 재생한 다음 자동 참석 메뉴로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="01631-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="01631-122">**공지** - 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-122">**Announcement** - Type in a message.</span></span> <span data-ttu-id="01631-123">시스템을 읽을 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-123">Text you want the system to read.</span></span> <span data-ttu-id="01631-124">최대 1000자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="01631-125">시스템에서 공지 사항을 재생한 다음 자동 참석 메뉴로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="01631-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="01631-126">자동 참석자 설정 시 다양한 단계에서 이러한 옵션 중 하나를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="01631-127">자동 참석을 설정하려면 Teams 관리 센터에서 음성을 확장하고 **자동** 참석자 선택 **및** **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-127">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="01631-128">일반 정보</span><span class="sxs-lookup"><span data-stu-id="01631-128">General info</span></span>

![이름, 연산자, 표준 시간대, 언어 및 음성 입력에 대한 자동 참석자 설정 스크린샷](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="01631-130">맨 위에 있는 상자에 자동 참석자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-130">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="01631-131">연산자를 지정하려는 경우 연산자에 대한 호출에 대한 대상을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-131">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="01631-132">선택 사항입니다(하지만 권장).</span><span class="sxs-lookup"><span data-stu-id="01631-132">This is optional (but recommended).</span></span> <span data-ttu-id="01631-133">발신자가  메뉴에서 끊어지고 지정된 사용자와 통화할 수 있도록 연산자 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="01631-134">이 자동 참석자에 대한 표준 시간대를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-134">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="01631-135">표준 시간대는 시간 후 별도 통화 흐름을 만드는 경우 업무 시간을 계산하는 [데 사용됩니다.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="01631-135">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="01631-136">이 자동 [참석자에](create-a-phone-system-auto-attendant-languages.md) 대해 지원되는 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-136">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="01631-137">시스템 생성 음성 프롬프트에 사용되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-137">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="01631-138">음성 입력을 사용하도록 설정할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-138">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="01631-139">이 옵션을 사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-139">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="01631-140">예를 들어 발신자는 "One"이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택하거나 "Sales"라고 말하여 "Sales"라는 메뉴 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-140">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="01631-141">음성 입력을 지원하지 않는 4단계에서 언어를 선택하면 이 옵션이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-141">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="01631-142">다음 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-142">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="01631-143">통화 흐름</span><span class="sxs-lookup"><span data-stu-id="01631-143">Call flow</span></span>

![인사말 메시지 설정 스크린샷](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="01631-145">자동 참석자가 통화에 응답할 때 인사말을 재생할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-145">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="01631-146">오디오 파일 재생을 **선택하면** 파일  업로드 단추를 사용하여 오디오로 저장된 녹음된 인사말 메시지를 업로드할 수 있습니다. WAV, . MP3 또는 . WMA 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-146">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="01631-147">기록은 5MB보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-147">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="01631-148">인사말  메시지 입력을 선택하면 자동 참석자가 통화에 응답할 때 입력한 텍스트(최대 1000자)를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-148">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![통화 라우팅 설정 스크린샷](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="01631-150">호출을 라우팅할 방법을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-150">Choose how you want to route the call.</span></span>

<span data-ttu-id="01631-151">연결 **끊기를 선택하면** 자동 참석자가 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-151">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="01631-152">리디렉션 **호출을 선택하면** 통화 라우팅 대상 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-152">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="01631-153">메뉴 재생 옵션을 선택하는 경우 오디오  파일 재생  또는 인사말 메시지에 입력을 선택한 다음 메뉴 옵션과 디렉터리 검색 사이에서 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="01631-153">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="01631-154">메뉴 옵션</span><span class="sxs-lookup"><span data-stu-id="01631-154">Menu options</span></span>

![다이얼 키 옵션 스크린샷](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="01631-156">전화 걸기 옵션의 경우 전화 키패드의 0-9 키를 통화 라우팅 대상 중 하나에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-156">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="01631-157">(키 \* (반복) 및 (뒤로)는 시스템에서 예약되어 있으며 다시할 \# 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="01631-157">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="01631-158">키 매핑은 연속적일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-158">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="01631-159">예를 들어 키 0, 1 및 3이 옵션에 매핑된 메뉴를 만들 수 있으며, 두 키는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-159">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the two key isn't used.</span></span>

<span data-ttu-id="01631-160">0 키를 구성한 경우 연산자에 매핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-160">We recommend mapping the zero key to the operator if you have configured one.</span></span> <span data-ttu-id="01631-161">연산자가 키로 설정되지 않은 경우 음성 명령 "Operator"도 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-161">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="01631-162">각 메뉴 옵션에 대해 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-162">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="01631-163">**다이얼 키** - 이 옵션에 액세스하기 위한 전화 키 패드의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-163">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="01631-164">음성 입력을 사용할 수 있는 경우 호출자는 이 숫자를 말하여 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-164">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="01631-165">**음성 명령** - 음성 입력이 활성화되어 있는 경우 발신자에게 이 옵션에 액세스하기 위해 부여할 수 있는 음성 명령을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-165">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="01631-166">"고객 서비스" 또는 "작업 및 근거" 같은 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-166">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="01631-167">예를 들어 호출자에서 2 키를 누르거나 "2"라고 말하거나 "Sales"라고 말하여 두 키에 매핑된 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-167">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two key.</span></span> <span data-ttu-id="01631-168">이 텍스트는 서비스 확인 프롬프트에 대해 음성으로 텍스트로 렌더링됩니다. "판매로 전화 전송" 같은 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-168">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="01631-169">**리디렉션** - 호출자에서 이 옵션을 선택할 때 사용되는 호출 라우팅 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-169">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="01631-170">자동 참석자 또는 호출 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="01631-170">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="01631-171">디렉터리 검색</span><span class="sxs-lookup"><span data-stu-id="01631-171">Directory search</span></span>

<span data-ttu-id="01631-172">대상에 다이얼 키를 할당하는 경우 디렉터리 검색에 대해 **없음을** **선택하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-172">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="01631-173">발신자는 특정 대상에 할당된 키를 사용하여 이름 또는 확장에 전화를 걸고자 하는 경우 이름 또는 확장 입력을 완료하기 전에 예기치 않게 대상에 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-173">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="01631-174">디렉터리 검색을 위해 별도의 자동 참석자 를 만들고 다이얼 키를 통해 기본 자동 참석자 링크가 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-174">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="01631-175">다이얼 키를 할당하지 않은 경우 디렉터리 검색 옵션을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-175">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="01631-176">**전화 걸기** - 이 옵션을 사용하도록 설정하면 발신자는 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-176">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="01631-177">비즈니스용 Skype Server를 사용하여 온라인 사용자 또는 모든 온라인 사용자가 호스팅되는 모든 사용자는 적격 사용자로 이름에 따라 다이얼을 사용하여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-177">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="01631-178">(전화 걸기 범위 페이지의 디렉터리에 포함되지 않은 대상을 설정할 [수](#dial-scope) 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="01631-178">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="01631-179">**확장으로 전화** 걸기 - 이 옵션을 사용하도록 설정하면 발신자는 해당 전화 확장에 전화를 걸고 조직 내 사용자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-179">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="01631-180">비즈니스용 Skype Server를 사용하여 온라인 사용자 또는 모든 온라인 사용자가 호스팅되는 모든 사용자는 적격 사용자로, 다이얼 by 확장 을 **사용하여 찾을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-180">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="01631-181">(전화 걸기 범위 페이지의 디렉터리에 포함되지 않은 대상을 설정할 [수](#dial-scope) 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="01631-181">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="01631-182">다이얼로 확장에 사용할 수 있도록 설정하려면 Active Directory 또는 Azure Active Directory에 정의된 다음 휴대폰 특성 중 [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 일부로 확장이 지정되어야 합니다(자세한 내용은 사용자 추가를 개별적으로 또는 일괄 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="01631-182">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="01631-183">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="01631-183">OfficePhone</span></span>
- <span data-ttu-id="01631-184">HomePhone</span><span class="sxs-lookup"><span data-stu-id="01631-184">HomePhone</span></span>
- <span data-ttu-id="01631-185">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="01631-185">Mobile/MobilePhone</span></span>
- <span data-ttu-id="01631-186">PhoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="01631-186">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="01631-187">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="01631-187">OtherTelephone</span></span>

<span data-ttu-id="01631-188">사용자 전화 번호 필드에 확장을 입력하는 데 필요한 형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-188">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="01631-189">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="01631-189">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="01631-190">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="01631-190">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="01631-191">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="01631-191">*x\<extension>*</span></span>

- <span data-ttu-id="01631-192">예제 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+155555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="01631-192">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="01631-193">예제 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+155555678x5678"</span><span class="sxs-lookup"><span data-stu-id="01631-193">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="01631-194">예제 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="01631-194">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="01631-195">[Microsoft 365](https://admin.microsoft.com/) 관리 센터 또는 Azure Active Directory 관리 센터에서 확장을 [설정할 수 있습니다.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="01631-195">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="01631-196">자동 참석자 및 통화 큐에서 변경 내용을 사용할 수 있는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-196">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="01631-197">전화 걸기 이름  및 확장  기능 모두를 사용하려는 경우 기본 자동 전화 접속에 다이얼 키를 할당하여 이름에 따라 다이얼을 사용하도록 설정된 자동 참석자에 도달할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-197">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="01631-198">해당 자동 참석자 내에서 1개 키(해당 키와 연결된 문자가 없는)를 할당하여 확장 자동 전화 걸기 전화 접속에 도달할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="01631-198">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="01631-199">디렉터리 검색 옵션을 **선택한** 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-199">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="01631-200">시간 후의 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="01631-200">Call flow for after hours</span></span>

![시간 및 시간 설정 후 스크린샷](media/auto-attendant-business-hours.png)

<span data-ttu-id="01631-202">각 자동 참석자에 대해 업무 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-202">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="01631-203">업무 시간이 설정되지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 하루의 모든 일 및 모든 시간은 영업 시간으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-203">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="01631-204">업무 시간은 낮 동안의 휴식 시간으로 설정할 수 있으며, 영업 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-204">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="01631-205">시간 이후의 다른 수신 통화 처리 옵션 및 인사말을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-205">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="01631-206">자동 참석자 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 참석자에 대한 시간 후 통화 라우팅만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-206">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="01631-207">시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 매일 업무 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-207">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="01631-208">새 **시간** 추가를 선택하여 특정 날짜에 대해 여러 시간 집합을 지정합니다(예: 점심 시간 지정).</span><span class="sxs-lookup"><span data-stu-id="01631-208">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="01631-209">업무 시간을 지정한 후 시간 후 통화 라우팅 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-209">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="01631-210">위에서 지정한 업무 시간 호출 라우팅과 동일한 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-210">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="01631-211">완료되면  다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-211">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="01631-212">공휴일 동안 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="01631-212">Call flows during holidays</span></span>

![휴일 및 휴일 인사말 설정 스크린샷](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="01631-214">자동 참석자가 설정한 각 휴일에 대한 통화 [흐름을 설정할 수 있습니다.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="01631-214">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="01631-215">각 자동 참석자에 최대 20일의 예약된 공휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-215">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="01631-216">휴일 통화 설정 페이지에서 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-216">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="01631-217">이 휴일 설정의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-217">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="01631-218">휴일 **드롭다운에서** 사용할 공휴일을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-218">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="01631-219">사용할 인사말 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-219">Choose the type of greeting that you want to use.</span></span>

    ![휴일 통화 작업 설정 스크린샷](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="01631-221">통화 연결을 **끊거나** **리디렉션할지** 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-221">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="01631-222">리디렉션을 선택한 경우 통화에 대한 통화 라우팅 대상을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="01631-222">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="01631-223">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-223">Select **Save**.</span></span>

![공휴일이 나열된 휴일 설정 스크린샷](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="01631-225">추가 휴일마다 필요에 따라 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-225">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="01631-226">모든 공휴일을 추가한 경우 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-226">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="01631-227">전화 걸기 범위</span><span class="sxs-lookup"><span data-stu-id="01631-227">Dial scope</span></span>

![다이얼 범위의 스크린샷에는 옵션이 포함 및 제외됩니다.](media/auto-attendant-dial-scope.png)

<span data-ttu-id="01631-229">전화 *걸기 범위는* 발신자에서 전화 접속 또는 전화 걸기 확장을 사용할 때 디렉터리에서 사용할 수 있는 사용자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-229">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="01631-230">모든 온라인 사용자의 **기본값은** 비즈니스용 Skype 서버를 사용하여 온라인 사용자 또는 호스팅되는 조직 내 모든 사용자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-230">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="01631-231">포함 또는 제외에서 사용자 지정 사용자 그룹을  선택하고  하나 이상의 Microsoft 365 그룹, 메일 그룹 또는 보안 그룹을 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="01631-231">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="01631-232">예를 들어 조직의 임원을 전화 걸기 디렉터리에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-232">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="01631-233">(사용자가 두 목록에 있는 경우 디렉터리에서 제외됩니다.)</span><span class="sxs-lookup"><span data-stu-id="01631-233">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="01631-234">새 사용자가 디렉터리에 자신의 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-234">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="01631-235">다이얼 범위를 설정하면 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-235">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="01631-236">리소스 계정</span><span class="sxs-lookup"><span data-stu-id="01631-236">Resource accounts</span></span>

<span data-ttu-id="01631-237">모든 자동 참석자는 연결된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="01631-238">첫 번째 수준 자동 참석자는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-238">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="01631-239">원하는 경우 별도의 서비스 번호가 있는 자동 참석자에 여러 리소스 계정을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![리소스 계정 추가 계정 패널 스크린샷](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="01631-241">리소스 계정을 추가하려면 계정 추가를 **선택하고** 추가할 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-241">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="01631-242">추가 **를** 선택한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01631-242">Select **Add**, and then select **Add**.</span></span>

![할당된 서비스 번호가 있는 리소스 계정을 보여주는 리소스 계정 목록 스크린샷](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="01631-244">서비스 계정 추가를 완료한  경우 제출을 선택하여 자동 참석자 구성을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-244">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="01631-245">외부 전화 번호 전송 - 기술 세부 정보</span><span class="sxs-lookup"><span data-stu-id="01631-245">External phone number transfers - technical details</span></span>

<span data-ttu-id="01631-246">자동 참석자가 외부에서 호출을 전송할 수 있도록 허용하기 위해 전제 구성표를 참조합니다. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="01631-246">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="01631-247">또한:</span><span class="sxs-lookup"><span data-stu-id="01631-247">In addition:</span></span>

- <span data-ttu-id="01631-248">통화 계획 번호가 [](calling-plans-for-office-365.md) 있는 리소스 계정의 경우 외부 전송 전화 번호를 E.164 형식으로 입력해야 합니다(+[국가 코드][지역 코드][전화 번호]).</span><span class="sxs-lookup"><span data-stu-id="01631-248">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="01631-249">직접 라우팅 번호가 있는 리소스 계정의 경우 외부 전송 전화 번호 형식은 [SBC(세션](direct-routing-connect-the-sbc.md) 테두리 컨트롤러) 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="01631-249">For a resource account with a Direct Routing number, the external transfer phone number format is dependent on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="01631-250">표시되는 아웃바운드 전화 번호는 다음과 같이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-250">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="01631-251">통화 계획 번호의 경우 원래 발신자 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-251">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="01631-252">직접 라우팅 번호의 경우 보낸 숫자는 다음과 같이 SBC의 P-Asserted-Identity(PAI) 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-252">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="01631-253">사용 안 으로 설정하면 원래 발신자 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-253">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="01631-254">이 설정은 기본 설정 및 권장 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-254">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="01631-255">사용하도록 설정하면 리소스 계정 전화 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01631-255">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="01631-256">비즈니스용 Skype 하이브리드 환경에서 PSTN에 자동 참석자 호출을 전송하기 위해 PSTN 번호로 통화 전달 집합을 사용하여 새 On-프레미스 사용자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-256">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="01631-257">사용자가 사용자에 대해 사용하도록 설정해야 Enterprise Voice 음성 정책이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01631-257">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="01631-258">자세한 내용은 [PSTN으로 자동 전화 전송을 참조합니다.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="01631-258">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="01631-259">PowerShell을 사용하여 자동 참석자 만들기</span><span class="sxs-lookup"><span data-stu-id="01631-259">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="01631-260">PowerShell을 사용하여 자동 참석자 만들기 및 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-260">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="01631-261">자동 참석자 관리에 필요한 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01631-261">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="01631-262">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="01631-262">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="01631-263">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="01631-263">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="01631-264">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="01631-264">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="01631-265">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="01631-265">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="01631-266">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="01631-266">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="01631-267">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="01631-267">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="01631-268">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="01631-268">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="01631-269">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="01631-269">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="01631-270">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="01631-270">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="01631-271">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="01631-271">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="01631-272">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="01631-272">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="01631-273">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="01631-273">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="01631-274">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="01631-274">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="01631-275">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="01631-275">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="01631-276">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="01631-276">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="01631-277">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="01631-277">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="01631-278">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="01631-278">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="01631-279">관련 주제</span><span class="sxs-lookup"><span data-stu-id="01631-279">Related topics</span></span>

[<span data-ttu-id="01631-280">다음은 통화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="01631-280">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="01631-281">서비스 통화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="01631-281">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="01631-282">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="01631-282">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="01631-283">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="01631-283">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
