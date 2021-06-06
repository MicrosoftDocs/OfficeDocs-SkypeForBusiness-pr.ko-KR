#### <a name="video-demonstration"></a><span data-ttu-id="fef7e-101">비디오 데모</span><span class="sxs-lookup"><span data-stu-id="fef7e-101">Video demonstration</span></span>

<span data-ttu-id="fef7e-102">이 비디오에서는 자동 참석자 를 만드는 방법에 대한 기본 예제를 Teams.</span><span class="sxs-lookup"><span data-stu-id="fef7e-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="fef7e-103">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="fef7e-103">Before you begin</span></span>

<span data-ttu-id="fef7e-104">조직 외부에서 직접 전화를 걸면 액세스할 수 있는 자동 참석자에 필요한 서비스 번호(서비스 번호는 자동 참석자가 사용하는 특수한 전화 번호)를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="fef7e-105">여기에는 다른 [공급자의](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 번호 전송 또는 새 서비스 번호 [요청이 포함됩니다.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="fef7e-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="fef7e-106">각 자동 참석자를 가상 사용자 전화 시스템 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="fef7e-107">Business Voice를 구입한 경우 가상 사용자 전화 시스템 여러 개가 수신되어 더 많은 요청을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="fef7e-108">그러나 향후 더 많은 것이 필요한 경우 가상 사용자 라이선스 의 지침에 따라 전화 시스템 [수 있습니다.](../teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="fef7e-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="fef7e-109">공휴일에는 자동 출석 경로 호출을 다르게 설정하려는 경우 자동 참석자 만들기 전에 사용할 공휴일을 만드길 수 있습니다. [](../set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fef7e-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="fef7e-110">다음 단계에 따라 자동 수행자 설정</span><span class="sxs-lookup"><span data-stu-id="fef7e-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="fef7e-111">1단계 전화 <br> 번호</span><span class="sxs-lookup"><span data-stu-id="fef7e-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="fef7e-112">처음으로 비즈니스 음성을 설정하는 단계를 따르고 있는 경우 **6단계:** 회사의 주 전화 번호에 대한 자동 수행자 설정이 있는 경우 이 탭의 단계를 이미 완료했습니다. 다음 탭으로 이동: [자동 참석자 일반 정보 입니다.](?tabs=general-info#steps)</span><span class="sxs-lookup"><span data-stu-id="fef7e-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="fef7e-113">만드는 각 자동 참석자에는 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="fef7e-114">이는 계정이 사용자 대신 자동 참석자 또는 통화 큐와 연결되어 있는 것을 제외하고 사용자 계정과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="fef7e-115">이 단계에서는 계정을 만들고 가상 사용자 *Microsoft 365 전화 시스템 할당한* 다음 서비스 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="fef7e-116">리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="fef7e-116">Create a resource account</span></span>

<span data-ttu-id="fef7e-117">관리 센터에서 리소스 계정을 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="fef7e-118">Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 리소스 계정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="fef7e-119">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-119">Click **Add**.</span></span>

3. <span data-ttu-id="fef7e-120">리소스 계정 **추가** 창에서 표시 **이름,** 사용자 이름 **및** 리소스 계정 유형에 대한 **자동** 참석자를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add.png)

4. <span data-ttu-id="fef7e-122">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-122">Click **Save**.</span></span>

    <span data-ttu-id="fef7e-123">새 계정이 계정 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-123">The new account will appear in the list of accounts.</span></span>

    ![리소스 계정 목록 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="fef7e-125">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="fef7e-125">Assign a license</span></span>

<span data-ttu-id="fef7e-126">리소스 계정에 Microsoft 365 전화 시스템 *가상* 사용자 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="fef7e-127">관리 Microsoft 365 관리 센터에서 라이선스를 할당할 리소스 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="fef7e-128">라이선스 **및** 앱 탭의 라이선스에서 가상 **Microsoft 365 전화 시스템 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="fef7e-129">변경 **내용 저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-129">Click **Save changes**.</span></span>

    ![관리 센터에서 라이선스 사용자 인터페이스 할당 Microsoft 365 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="fef7e-131">서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="fef7e-131">Assign a service number</span></span>

<span data-ttu-id="fef7e-132">전화 번호로 이 자동 참석자를 연결해야 하는 경우 해당 번호를 리소스 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="fef7e-133">관리 Teams 관리 센터의 **리소스** 계정 페이지에서 서비스 번호를 할당할 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="fef7e-134">숫자 **전화** 드롭다운에서 사용할 숫자 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="fef7e-135">할당된 전화 번호 **상자에서** 사용할 번호를 검색하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![서비스 번호 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="fef7e-137">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7e-138">2단계 - 자동 참석자 일반 정보 ></span><span class="sxs-lookup"><span data-stu-id="fef7e-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="fef7e-139">2단계 <br> 참석자 일반 정보</span><span class="sxs-lookup"><span data-stu-id="fef7e-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="fef7e-140">자동 참석자 설정</span><span class="sxs-lookup"><span data-stu-id="fef7e-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="fef7e-141">관리 Teams 센터에서 **음성을** 확장하고 자동 참석자 를 **클릭한** 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="fef7e-142">맨 위에 있는 상자에 자동 참석자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="fef7e-143">연산자를 지정하려는 경우 연산자에 대한 호출에 대한 대상을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="fef7e-144">선택 사항입니다(하지만 권장).</span><span class="sxs-lookup"><span data-stu-id="fef7e-144">This is optional (but recommended).</span></span> <span data-ttu-id="fef7e-145">발신자가  메뉴에서 끊어지고 지정된 사용자와 통화할 수 있도록 연산자 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="fef7e-146">이 자동 참석자에 대한 표준 시간대를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="fef7e-147">표준 시간대는 시간 이후에 별도의 통화 흐름을 만드는 경우 업무 시간을 계산하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="fef7e-148">이 자동 [참석자에](../create-a-phone-system-auto-attendant-languages.md) 대해 지원되는 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-148">Specify a [supported language](../create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="fef7e-149">시스템 생성 음성 프롬프트에 사용되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-149">This is the language that will be used for system-generated voice prompts.</span></span> 

6. <span data-ttu-id="fef7e-150">음성 입력을 사용하도록 설정할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="fef7e-151">이 옵션을 사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="fef7e-152">예를 들어 발신자는 "One"이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택하거나 "Sales"라고 말하여 "Sales"라는 메뉴 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![이름, 연산자, 표준 시간대, 언어 및 음성 입력에 대한 자동 참석자 설정 스크린샷](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="fef7e-154">다음 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7e-155">3단계 - 통화 흐름 ></span><span class="sxs-lookup"><span data-stu-id="fef7e-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="fef7e-156">3단계 <br> 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="fef7e-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="fef7e-157">통화 흐름 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="fef7e-157">Choose your call flow options</span></span>

1. <span data-ttu-id="fef7e-158">자동 참석자가 통화에 응답할 때 인사말을 재생할지 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="fef7e-159">오디오 파일 **재생을** 선택하면 파일 업로드 단추를 사용하여 에서 오디오로 저장된 기록된 **인사말** 메시지를 업로드할 수 있습니다. WAV, .MP3 또는 . WMA 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="fef7e-160">기록은 5MB보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="fef7e-161">인사말  메시지 입력을 선택하면 자동 참석자가 통화에 응답할 때 입력한 텍스트(최대 1000자)를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![인사말 메시지 설정 스크린샷](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="fef7e-163">호출을 라우팅할 방법을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="fef7e-164">연결 **끊기를 선택하면** 자동 참석자가 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="fef7e-165">리디렉션 **호출을 선택하면** 통화 라우팅 대상 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="fef7e-166">메뉴 재생 옵션을 선택하는 경우 오디오  파일 재생  또는 인사말 메시지에 입력을 선택한 다음 메뉴 옵션과 디렉터리 검색 사이에서 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="fef7e-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![통화 라우팅 설정 스크린샷](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="fef7e-168">발신자에서 다이얼 키를 사용하여 탐색하려는 경우 메뉴 설정 옵션에서 발신자 다이얼 키를 누를 때 어떤 일이 일어날지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="fef7e-169">(이 자동 참석을 회사 디렉터리로 만드는 경우 다이얼 키 옵션을 비워 두십시오.)</span><span class="sxs-lookup"><span data-stu-id="fef7e-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="fef7e-170">다이얼 키를 다음 대상으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="fef7e-171">**조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="fef7e-172">**음성 앱** - 다른 자동 참석자 또는 통화 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="fef7e-173">**외부 전화 번호** - 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="fef7e-174">이 형식 사용: +[국가 코드][지역 코드][전화 번호]</span><span class="sxs-lookup"><span data-stu-id="fef7e-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="fef7e-175">**Voicemail** - 지정한 그룹과 Microsoft 365 음성 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span> <span data-ttu-id="fef7e-176">음성 메일 전사와 "음색 후에 메시지를 남겨 주세요."를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-176">You can choose if you want voicemail transcriptions and the "Please leave a message after the tone."</span></span> <span data-ttu-id="fef7e-177">시스템 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-177">system prompt.</span></span>
    - <span data-ttu-id="fef7e-178">**연산자** - 자동 참석자에 대해 정의된 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-178">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="fef7e-179">연산자 정의는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-179">Defining an operator is optional.</span></span> <span data-ttu-id="fef7e-180">연산자는 이 목록의 다른 대상 중 하나로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-180">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="fef7e-181">연산자에 0 키를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-181">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="fef7e-182">각 메뉴 옵션에 대해 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-182">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="fef7e-183">**다이얼 키** - 이 옵션에 액세스하기 위한 전화 키 패드의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-183">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="fef7e-184">**음성 명령** - 음성 입력이 활성화되어 있는 경우 발신자에게 이 옵션에 액세스하기 위해 부여할 수 있는 음성 명령을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-184">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="fef7e-185">"고객 서비스" 또는 "작업 및 근거" 같은 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-185">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="fef7e-186">**리디렉션** - 호출자에서 이 옵션을 선택할 때 호출이 이동하려는 위치로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-186">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="fef7e-187">자동 참석자 또는 호출 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="fef7e-187">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![다이얼 키 옵션 스크린샷](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="fef7e-189">이 자동 참석을 회사 디렉터리로 사용하려는 경우 디렉터리 검색에서 이름으로 **전화 걸기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-189">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="fef7e-190">이 옵션을 사용하도록 설정하면 호출자는 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-190">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="fef7e-191">라이선스가 전화 시스템 모든 온라인 사용자는 적격 사용자로 전화 걸기 이름으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-191">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="fef7e-192">(확장으로 **전화 걸기를** 선택할 수 있습니다. 하지만 확장은 Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="fef7e-192">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="fef7e-193">디렉터리 검색 옵션을 **선택한** 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-193">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7e-194">4단계 - 시간 후 통화 흐름 ></span><span class="sxs-lookup"><span data-stu-id="fef7e-194">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="fef7e-195">4단계 <br> 후 시간</span><span class="sxs-lookup"><span data-stu-id="fef7e-195">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="fef7e-196">각 자동 참석자에 대해 업무 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-196">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="fef7e-197">업무 시간이 설정되지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 하루의 모든 일 및 모든 시간은 영업 시간으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-197">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="fef7e-198">업무 시간은 낮 동안의 휴식 시간으로 설정할 수 있으며, 영업 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-198">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="fef7e-199">시간 이후의 다른 수신 통화 처리 옵션 및 인사말을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-199">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="fef7e-200">자동 참석자 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 참석자에 대한 시간 후 통화 라우팅만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-200">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="fef7e-201">시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 매일 업무 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-201">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="fef7e-202">새 **시간** 추가를 클릭하여 특정 날짜에 대해 여러 시간 집합을 지정합니다(예: 점심 시간 지정).</span><span class="sxs-lookup"><span data-stu-id="fef7e-202">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![시간 및 시간 설정 후 스크린샷](../media/auto-attendant-business-hours.png)

<span data-ttu-id="fef7e-204">업무 시간을 지정한 후 시간 후 통화 라우팅 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-204">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="fef7e-205">3단계 - 통화 흐름 에서 지정한 업무 시간 호출 라우팅과 동일한 **옵션을 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-205">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="fef7e-206">완료되면  다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-206">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7e-207">5단계 - 휴일 통화 흐름 ></span><span class="sxs-lookup"><span data-stu-id="fef7e-207">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="fef7e-208">5단계 <br> 공휴일</span><span class="sxs-lookup"><span data-stu-id="fef7e-208">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="fef7e-209">공휴일에는 다른 날과 다르게 자동 참석자에 대한 호출이 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-209">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="fef7e-210">(휴일에 대해 다른 통화 흐름을 원하지 않는 경우 이 단계를 건너뛸 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="fef7e-210">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="fef7e-211">자동 참석자가 설정한 각 휴일에 대한 통화 흐름을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-211">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="fef7e-212">각 자동 참석자에 최대 20일의 예약된 공휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-212">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="fef7e-213">휴일 통화 설정 페이지에서 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-213">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="fef7e-214">이 휴일 설정의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-214">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="fef7e-215">휴일 **드롭다운에서** 사용할 공휴일을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-215">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="fef7e-216">사용할 인사말 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-216">Choose the type of greeting that you want to use.</span></span>

    ![휴일 및 휴일 인사말 설정 스크린샷](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="fef7e-218">통화 연결을 **끊거나** **리디렉션할지** 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-218">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="fef7e-219">리디렉션을 선택한 경우 통화에 대한 통화 라우팅 대상을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="fef7e-219">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![휴일 통화 작업 설정 스크린샷](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="fef7e-221">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-221">Click **Save**.</span></span>

    <span data-ttu-id="fef7e-222">추가 휴일마다 필요에 따라 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-222">Repeat the procedure as needed for each additional holiday.</span></span>

    ![공휴일이 나열된 휴일 설정 스크린샷](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="fef7e-224">모든 공휴일을 추가한 경우 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-224">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7e-225">6단계 - 디렉터리에 있는 사용자 선택 ></span><span class="sxs-lookup"><span data-stu-id="fef7e-225">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="fef7e-226">6단계 <br> 디렉터리 구성원</span><span class="sxs-lookup"><span data-stu-id="fef7e-226">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="fef7e-227">전화 *걸기 범위는* 발신자에서 전화 접속 또는 전화 걸기 확장을 사용할 때 디렉터리에서 사용할 수 있는 사용자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-227">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="fef7e-228">모든 온라인 사용자의 **기본값은** 라이선스가 있는 Online 사용자인 조직의 모든 전화 시스템 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-228">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="fef7e-229">포함 또는 제외에서 사용자 지정 사용자 그룹을  선택하고  하나 이상의 그룹, 메일 그룹 또는 Microsoft 365 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="fef7e-229">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="fef7e-230">예를 들어 조직의 임원을 전화 걸기 디렉터리에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-230">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="fef7e-231">(사용자가 두 목록에 있는 경우 디렉터리에서 제외됩니다.)</span><span class="sxs-lookup"><span data-stu-id="fef7e-231">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![다이얼 범위의 스크린샷에는 옵션이 포함 및 제외됩니다.](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="fef7e-233">새 사용자가 디렉터리에 자신의 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-233">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="fef7e-234">다이얼 범위를 설정하면 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-234">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7e-235">7단계 - 리소스 계정 할당 ></span><span class="sxs-lookup"><span data-stu-id="fef7e-235">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="fef7e-236">7단계 <br> 리소스 계정</span><span class="sxs-lookup"><span data-stu-id="fef7e-236">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="fef7e-237">모든 자동 참석자는 연결된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="fef7e-238">첫 번째 수준 자동 참석자는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-238">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="fef7e-239">원하는 경우 별도의 서비스 번호가 있는 자동 참석자에 여러 리소스 계정을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="fef7e-240">리소스 계정을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="fef7e-240">To add a resource account</span></span>

1. <span data-ttu-id="fef7e-241">**추가를** 클릭하고 추가할 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-241">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="fef7e-242">**추가를** 클릭한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-242">Click **Add**, and then click **Add**.</span></span>

    ![리소스 계정 추가 계정 패널 스크린샷](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="fef7e-244">서비스 계정 추가가 완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fef7e-244">When you have finished adding service accounts, click **Submit**.</span></span>

    ![할당된 서비스 번호가 있는 리소스 계정을 보여주는 리소스 계정 목록 스크린샷](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="fef7e-246">이렇게 하여 자동 참석자 구성이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef7e-246">This completes the auto attendant configuration.</span></span>

---
