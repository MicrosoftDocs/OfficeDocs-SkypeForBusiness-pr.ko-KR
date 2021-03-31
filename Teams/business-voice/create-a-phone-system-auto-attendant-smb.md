---
title: Microsoft Teams에 대한 자동 참석자 설정 - 중소기업 자습서
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
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
description: Microsoft 365 Business Voice에 대한 자동 참석자 설정 및 테스트 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: fef89971ad99dff15332905d6f9b98a343af6ffd
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439723"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="99a61-103">자동 참석자 설정 - 중소기업 자습서</span><span class="sxs-lookup"><span data-stu-id="99a61-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="99a61-104">자동 참석자는 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서에 문의하고 큐, 사람 또는 운영자에게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="99a61-105">Microsoft Teams 관리 센터를 사용하여 조직에 대한 자동 참석자 를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="99a61-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="99a61-106">Before you begin</span></span>

<span data-ttu-id="99a61-107">조직 외부에서 직접 전화를 걸면 액세스할 수 있는 자동 참석자에 필요한 서비스 번호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="99a61-108">여기에는 다른 [공급자의](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 번호 전송 또는 새 서비스 번호 [요청이 포함됩니다.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="99a61-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="99a61-109">전화 시스템 [- 만들](../teams-add-on-licensing/virtual-user.md) 계획인 각 자동 참석자에 대한 가상 사용자 라이선스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="99a61-110">이러한 라이선스는 무료이기 때문에 향후 설정을 변경하기로 결정한 경우 몇 가지 추가를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="99a61-111">공휴일에는 자동 출석 경로 호출을 다르게 설정하려는 경우 자동 참석자 만들기 전에 사용할 공휴일을 만드길 수 있습니다. [](../set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="99a61-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="99a61-112">다음 단계에 따라 자동 수행자 설정</span><span class="sxs-lookup"><span data-stu-id="99a61-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="99a61-113">1단계 <br> 전화 번호</span><span class="sxs-lookup"><span data-stu-id="99a61-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="99a61-114">만드는 각 자동 참석자에는 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="99a61-115">이는 계정이 사용자 대신 자동 참석자 또는 통화 큐와 연결되어 있는 것을 제외하고 사용자 계정과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="99a61-116">이 단계에서는 계정을 만들고 *Microsoft 365 Phone System - Virtual User* 라이선스를 할당한 다음 서비스 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="99a61-117">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="99a61-117">Create a resource account</span></span>

<span data-ttu-id="99a61-118">Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="99a61-119">Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 **리소스 계정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="99a61-120">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-120">Click **Add**.</span></span>

3. <span data-ttu-id="99a61-121">리소스 계정 **추가** 창에서 표시 **이름,** 사용자 이름 **및** 리소스 계정 유형에 대한 **자동** 참석자를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add.png)

4. <span data-ttu-id="99a61-123">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-123">Click **Save**.</span></span>

<span data-ttu-id="99a61-124">새 계정이 계정 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-124">The new account will appear in the list of accounts.</span></span>

![리소스 계정 목록 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="99a61-126">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="99a61-126">Assign a license</span></span>

<span data-ttu-id="99a61-127">*Microsoft 365 Phone System - 가상 사용자* 라이선스를 리소스 계정에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="99a61-128">Microsoft 365 관리 센터에서 라이선스를 할당할 리소스 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="99a61-129">라이선스 **및** 앱 탭의 라이선스 **아래에서** **Microsoft 365 Phone System - Virtual User 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="99a61-130">변경 **내용 저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-130">Click **Save changes**.</span></span>

    ![Microsoft 365 관리 센터에서 라이선스 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="99a61-132">서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="99a61-132">Assign a service number</span></span>

<span data-ttu-id="99a61-133">전화 번호로 이 자동 참석자를 연결해야 하는 경우 해당 번호를 리소스 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="99a61-134">Teams 관리 센터의 리소스  계정 페이지에서 서비스 번호를 할당할 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="99a61-135">전화 번호 **유형 드롭다운에서** 사용할 번호 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="99a61-136">할당된 전화 번호 **상자에서** 사용할 번호를 검색하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![서비스 번호 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="99a61-138">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99a61-139">2단계 - 자동 참석자 일반 정보 ></span><span class="sxs-lookup"><span data-stu-id="99a61-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="99a61-140">2단계 <br> 참석자 일반 정보</span><span class="sxs-lookup"><span data-stu-id="99a61-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="99a61-141">자동 참석자 설정</span><span class="sxs-lookup"><span data-stu-id="99a61-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="99a61-142">Teams 관리 센터에서 **음성을** 확장하고 자동 참석자 **를** 클릭한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="99a61-143">맨 위에 있는 상자에 자동 참석자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="99a61-144">연산자를 지정하려는 경우 연산자에 대한 호출에 대한 대상을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="99a61-145">선택 사항입니다(하지만 권장).</span><span class="sxs-lookup"><span data-stu-id="99a61-145">This is optional (but recommended).</span></span> <span data-ttu-id="99a61-146">발신자가  메뉴에서 끊어지고 지정된 사용자와 통화할 수 있도록 연산자 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="99a61-147">이 자동 참석자에 대한 표준 시간대를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="99a61-148">표준 시간대는 시간 이후에 별도의 통화 흐름을 만드는 경우 업무 시간을 계산하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="99a61-149">이 자동 참석자에 대한 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="99a61-150">시스템 생성 음성 프롬프트에 사용되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="99a61-151">음성 입력을 사용하도록 설정할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="99a61-152">이 옵션을 사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="99a61-153">예를 들어 발신자는 "One"이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택하거나 "Sales"라고 말하여 "Sales"라는 메뉴 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![이름, 연산자, 표준 시간대, 언어 및 음성 입력에 대한 자동 참석자 설정 스크린샷](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="99a61-155">다음 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99a61-156">3단계 - 통화 흐름 ></span><span class="sxs-lookup"><span data-stu-id="99a61-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="99a61-157">3단계 <br> 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="99a61-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="99a61-158">통화 흐름 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="99a61-158">Choose your call flow options</span></span>

1. <span data-ttu-id="99a61-159">자동 참석자가 통화에 응답할 때 인사말을 재생할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="99a61-160">오디오 파일 **재생을** 선택하면 파일  업로드 단추를 사용하여 오디오로 저장된 녹음된 인사말 메시지를 업로드할 수 있습니다. WAV, . MP3 또는 . WMA 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="99a61-161">기록은 5MB보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="99a61-162">인사말  메시지 입력을 선택하면 자동 참석자가 통화에 응답할 때 입력한 텍스트(최대 1000자)를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![인사말 메시지 설정 스크린샷](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="99a61-164">호출을 라우팅할 방법을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="99a61-165">연결 **끊기를 선택하면** 자동 참석자가 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="99a61-166">리디렉션 **호출을 선택하면** 통화 라우팅 대상 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="99a61-167">메뉴 재생 옵션을 선택하는 경우 오디오  파일 재생  또는 인사말 메시지에 입력을 선택한 다음 메뉴 옵션과 디렉터리 검색 사이에서 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="99a61-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![통화 라우팅 설정 스크린샷](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="99a61-169">발신자에서 다이얼 키를 사용하여 탐색하려는 경우 메뉴 설정 옵션에서 발신자 다이얼 키를 누를 때 어떤 일이 일어날지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="99a61-170">(이 자동 참석을 회사 디렉터리로 만드는 경우 다이얼 키 옵션을 비워 두십시오.)</span><span class="sxs-lookup"><span data-stu-id="99a61-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="99a61-171">다이얼 키를 다음 대상으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="99a61-172">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="99a61-173">**음성 앱** - 다른 자동 참석자 또는 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="99a61-174">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="99a61-175">이 형식 사용: +[국가 코드][지역 코드][전화 번호]</span><span class="sxs-lookup"><span data-stu-id="99a61-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="99a61-176">**Voicemail** - 지정한 Microsoft 365 그룹과 연결된 음성 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="99a61-177">**연산자** - 자동 참석자에 대해 정의된 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="99a61-178">연산자 정의는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-178">Defining an operator is optional.</span></span> <span data-ttu-id="99a61-179">연산자는 이 목록의 다른 대상 중 하나로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="99a61-180">연산자에 0 키를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="99a61-181">각 메뉴 옵션에 대해 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="99a61-182">**다이얼 키** - 이 옵션에 액세스하기 위한 전화 키 패드의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="99a61-183">**음성 명령** - 음성 입력이 활성화되어 있는 경우 발신자에게 이 옵션에 액세스하기 위해 부여할 수 있는 음성 명령을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="99a61-184">"고객 서비스" 또는 "작업 및 근거" 같은 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="99a61-185">**리디렉션** - 호출자에서 이 옵션을 선택할 때 호출이 이동하려는 위치로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="99a61-186">자동 참석자 또는 호출 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="99a61-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![다이얼 키 옵션 스크린샷](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="99a61-188">이 자동 참석을 회사 디렉터리로 사용하려는 경우 디렉터리 검색에서 이름으로 **전화 걸기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="99a61-189">이 옵션을 사용하도록 설정하면 호출자는 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="99a61-190">전화 시스템 라이선스가 있는 모든 온라인 사용자는 적격 사용자로 전화 걸기 이름으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="99a61-191">(확장으로 **전화 걸기를 선택할 수 있습니다.** 하지만 확장은 Azure Active Directory에서 구성해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="99a61-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="99a61-192">디렉터리 검색 옵션을 **선택한** 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99a61-193">4단계 - 시간 후 통화 흐름 ></span><span class="sxs-lookup"><span data-stu-id="99a61-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="99a61-194">4단계 <br> 후 시간</span><span class="sxs-lookup"><span data-stu-id="99a61-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="99a61-195">각 자동 참석자에 대해 업무 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="99a61-196">업무 시간이 설정되지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 하루의 모든 일 및 모든 시간은 영업 시간으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="99a61-197">업무 시간은 낮 동안의 휴식 시간으로 설정할 수 있으며, 영업 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="99a61-198">시간 이후의 다른 수신 통화 처리 옵션 및 인사말을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="99a61-199">자동 참석자 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 참석자에 대한 시간 후 통화 라우팅만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="99a61-200">시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 매일 업무 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="99a61-201">새 **시간** 추가를 클릭하여 특정 날짜에 대해 여러 시간 집합을 지정합니다(예: 점심 시간 지정).</span><span class="sxs-lookup"><span data-stu-id="99a61-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![시간 및 시간 설정 후 스크린샷](../media/auto-attendant-business-hours.png)

<span data-ttu-id="99a61-203">업무 시간을 지정한 후 시간 후 통화 라우팅 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="99a61-204">3단계 - 통화 흐름 에서 지정한 업무 시간 호출 라우팅과 동일한 **옵션을 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="99a61-205">완료되면  다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99a61-206">5단계 - 휴일 통화 흐름 ></span><span class="sxs-lookup"><span data-stu-id="99a61-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="99a61-207">5단계 <br> 공휴일</span><span class="sxs-lookup"><span data-stu-id="99a61-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="99a61-208">공휴일에는 다른 날과 다르게 자동 참석자에 대한 호출이 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="99a61-209">(휴일에 대해 다른 통화 흐름을 원하지 않는 경우 이 단계를 건너뛸 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="99a61-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="99a61-210">자동 참석자가 설정한 각 휴일에 대한 통화 흐름을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="99a61-211">각 자동 참석자에 최대 20일의 예약된 공휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="99a61-212">휴일 통화 설정 페이지에서 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="99a61-213">이 휴일 설정의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="99a61-214">휴일 **드롭다운에서** 사용할 공휴일을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="99a61-215">사용할 인사말 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-215">Choose the type of greeting that you want to use.</span></span>

    ![휴일 및 휴일 인사말 설정 스크린샷](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="99a61-217">통화 연결을 **끊거나** **리디렉션할지** 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="99a61-218">리디렉션을 선택한 경우 통화에 대한 통화 라우팅 대상을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="99a61-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![휴일 통화 작업 설정 스크린샷](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="99a61-220">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-220">Click **Save**.</span></span>

<span data-ttu-id="99a61-221">추가 휴일마다 필요에 따라 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-221">Repeat the procedure as needed for each additional holiday.</span></span>

![공휴일이 나열된 휴일 설정 스크린샷](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="99a61-223">모든 공휴일을 추가한 경우 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99a61-224">6단계 - 디렉터리에 있는 사용자 선택 ></span><span class="sxs-lookup"><span data-stu-id="99a61-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="99a61-225">6단계 <br> 디렉터리 구성원</span><span class="sxs-lookup"><span data-stu-id="99a61-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="99a61-226">전화 *걸기 범위는* 발신자에서 전화 접속 또는 전화 걸기 확장을 사용할 때 디렉터리에서 사용할 수 있는 사용자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="99a61-227">모든 온라인 사용자의 **기본값에는** 전화 시스템 라이선스가 있는 Online 사용자인 조직의 모든 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="99a61-228">포함 또는 제외에서 사용자 지정 사용자 그룹을  선택하고  하나 이상의 Microsoft 365 그룹, 메일 그룹 또는 보안 그룹을 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="99a61-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="99a61-229">예를 들어 조직의 임원을 전화 걸기 디렉터리에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="99a61-230">(사용자가 두 목록에 있는 경우 디렉터리에서 제외됩니다.)</span><span class="sxs-lookup"><span data-stu-id="99a61-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![다이얼 범위의 스크린샷에는 옵션이 포함 및 제외됩니다.](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="99a61-232">새 사용자가 디렉터리에 자신의 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="99a61-233">다이얼 범위를 설정하면 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99a61-234">7단계 - 리소스 계정 할당 ></span><span class="sxs-lookup"><span data-stu-id="99a61-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="99a61-235">7단계 <br> 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="99a61-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="99a61-236">모든 자동 참석자는 연결된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="99a61-237">첫 번째 수준 자동 참석자는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="99a61-238">원하는 경우 별도의 서비스 번호가 있는 자동 참석자에 여러 리소스 계정을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="99a61-239">리소스 계정을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="99a61-239">To add a resource account</span></span>

1. <span data-ttu-id="99a61-240">계정 **추가를** 클릭하고 추가할 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="99a61-241">**추가를** 클릭한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-241">Click **Add**, and then click **Add**.</span></span>

    ![리소스 계정 추가 계정 패널 스크린샷](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="99a61-243">서비스 계정 추가가 완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99a61-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![할당된 서비스 번호가 있는 리소스 계정을 보여주는 리소스 계정 목록 스크린샷](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="99a61-245">이렇게 하여 자동 참석자 구성이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="99a61-245">This completes the auto attendant configuration.</span></span>

---


