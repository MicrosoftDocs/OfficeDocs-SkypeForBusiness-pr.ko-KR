---
title: 클라우드 자동 전화 교환 설정
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
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
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375712"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="9ca3e-103">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="9ca3e-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="9ca3e-104">자동 전화 교환을 통해 조직에 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람, 교환원에 게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="9ca3e-105">Microsoft 팀 관리 센터를 사용 하 여 조직의 자동 전화 교환을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="9ca3e-106">새 자동 전화 교환을 만들려면 왼쪽 탐색 창에서 **음성** 으로 이동한 다음 **자동 전화 교환** > **새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="9ca3e-107">자동 전화 교환에 대해 자세히 알아보려면 [클라우드 자동 전화 교환 기능](/microsoftteams/what-are-phone-system-auto-attendants) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="9ca3e-108">이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="9ca3e-109">1 단계-시작 하기</span><span class="sxs-lookup"><span data-stu-id="9ca3e-109">Step 1 — Get started</span></span>

- <span data-ttu-id="9ca3e-110">자동 전화 교환은 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="9ca3e-111">리소스 계정 및 필요한 모든 라이선스에 대 한 자세한 내용은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="9ca3e-112">**전화 시스템** 라이선스가 있는 온라인 사용자 인 연산자나 메뉴 옵션으로 호출을 리디렉션하려면 엔터프라이즈 음성에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="9ca3e-113">[비즈니스용 Skype 라이선스 할당](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) 또는 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="9ca3e-114">Windows PowerShell을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="9ca3e-115">예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="9ca3e-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="9ca3e-116">2 단계-새 자동 전화 교환 만들기</span><span class="sxs-lookup"><span data-stu-id="9ca3e-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ca3e-117">모든 자동 전화 교환에는 연결 된 [리소스 계정이](manage-resource-accounts.md)있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="9ca3e-118">먼저 리소스 계정을 만든 다음 자동 전화 교환에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9ca3e-119">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9ca3e-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9ca3e-120">**Microsoft 팀 관리 센터**에서 **음성** > **자동 전화 교환을**클릭 한 다음 **+ 새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="9ca3e-121">일반 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="9ca3e-121">General info page</span></span>

![내 자동 전화 교환 페이지의 스크린샷](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="9ca3e-124">**이름** 자동 전화 교환에 대 한 설명 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="9ca3e-125">이름은 필수 이며 공백을 포함 하 여 최대 64 자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="9ca3e-126">**자동 전화 교환** 탭의 **이름** 열에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="9ca3e-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca3e-128"></span></span>

<span data-ttu-id="9ca3e-129">**자원 계정** 하나 이상의 리소스 계정을 선택 하 여 새 자동 전화 교환에 연결 하려면이 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="9ca3e-130">모든 자동 전화 교환에는 연결 된 리소스 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="9ca3e-131">리소스 계정은 계정에 연결 된 전화 번호를 가질 수 있지만 전화 번호는 요구 사항이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="9ca3e-132">일반적으로 최상위 자동 전화 교환에는 할당 된 전화 번호가 있는 리소스 계정이 있지만, 중첩 된 자동 전화 교환 (첫 번째 수준 자동 전화 교환에 연결 되는 수준 2 메뉴로 사용)에는 해당 리소스 계정에 할당 된 전화 번호가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="9ca3e-133">![앞의 스크린샷은](media/sfbcallout3.png)
 <a name="timezone"> </a> 설명선을 참조 하는 숫자 3의 아이콘</span><span class="sxs-lookup"><span data-stu-id="9ca3e-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="9ca3e-134">**표준 시간대** 자동 전화 교환에 대 한 표준 시간대를 설정 해야 하지만 조직에 대해 나열 된 기본 주소의 표준 시간대에 해당 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="9ca3e-135">각 자동 전화 교환은 다른 표준 시간대를 가질 수 있으며 자동 전화 교환에 설정 된 업무 시간은 여기서 선택한 표준 시간대에 따라 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

<span data-ttu-id="9ca3e-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca3e-137"></span></span>

<span data-ttu-id="9ca3e-138">**언어가** 나열 된 사용 가능한 언어 중에서 자동 전화 교환에 사용할 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="9ca3e-139">여기서 설정한 언어는 자동 전화 교환이이 자동 전화 교환에 연결 하는 사람들과 상호 작용 하는 데 사용 하는 언어 이며, 모든 시스템 메시지가이 언어로 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 5의 아이콘](media/sfbcallout5.png)

<span data-ttu-id="9ca3e-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca3e-141"></span></span>

<span data-ttu-id="9ca3e-142">**연산자** 선택 사항 이지만 호출자가 메뉴를 차단 하 고 사용자에 게 말할 수 있도록 **연산자** 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="9ca3e-143">0 키는 기본적으로 교환원에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="9ca3e-144">운영자를 설정 하는 경우 **비즈니스 시간 통화 처리** 페이지의 **편집 메뉴 옵션** 에서 해당 옵션에 대해 누가 전화를 하는지도 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="9ca3e-145">자동 전화 교환에 운영자를 설정 하는 경우 **호출자가 듣기** 상자에 해당 프롬프트 텍스트를 입력 하거나이 옵션을 포함 하도록 오디오 파일을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="9ca3e-146">예를 들어 연산자의 경우 0을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="9ca3e-147">다음과 같은 여러 가지 방법으로 연산자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="9ca3e-148">Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 **전화 시스템** 라이선스가 있는 **회사의 사람** 입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="9ca3e-149">**회사** 사용자는 비즈니스용 Skype 서버 2015 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="9ca3e-150">**음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="9ca3e-151">전화를 걸 사람을 음성 메일로 전송 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="9ca3e-152">이렇게 하려면 **회사에서 사람** 을 선택 하 고이 사용자의 통화가 바로 보이스 메일로 착신 전환 되도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 6 번의 아이콘](media/sfbcallout6.png)

<span data-ttu-id="9ca3e-154">**음성 입력 사용** 이 옵션을 선택 하는 경우 음성 인식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="9ca3e-155">통화를 하는 사람들은 사용자가 [설정한 언어로](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)음성 입력을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="9ca3e-156">다른 사용자만 전화 키패드를 사용할 수 있도록 하려면 음성 인식을 끄려면 (꺼짐)으로 설정 하 여 해제 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="9ca3e-157">선택이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="9ca3e-158">업무 시간 페이지</span><span class="sxs-lookup"><span data-stu-id="9ca3e-158">Business hours page</span></span>

<span data-ttu-id="9ca3e-159">기본적으로 업무 시간은 월요일 ~ 금요일, 오전 9:00-5:00 pm으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="9ca3e-160">업무 시간에 포함 되지 않은 모든 시간은 업무 시간 후로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="9ca3e-161">**24/7 선택을** 클릭 하 여 업무 시간을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="9ca3e-162">**24/7 선택** 옵션을 선택 하지 않는 한, **이후 시간 통화 설정** 페이지는 자동 전화 교환에 대 한 업무 시간 후에 통화 처리 규칙을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![업무 시간 페이지 스크린샷](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="9ca3e-165">기본적으로 업무 시간은 월요일 ~ 금요일, 오전 9:00-5:00 pm으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="9ca3e-166">**모든 시간 지우기** 옵션을 선택 하 여 일정에서 모든 시간의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="9ca3e-167">**기본값으로 재설정**을 선택 하면 업무 시간이 월요일에서 금요일, 오전 9:00은 5:00 pm으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="9ca3e-169">업무 시간을 변경 하려면 일정에서 설정 하려는 업무 시간을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="9ca3e-170">달력을 사용 하면 30 분 간격으로 업무 시간을 선택 하 고 여기에서 선택한 업무 시간은 **일반 정보** 페이지에서 설정한 표준 시간대를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="9ca3e-171">나누기를 설정 하려면 (예: 점심 작업 나누기) 일정에서 시간을 선택 취소 하거나 끌어서 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="9ca3e-172">업무 시간 내에 여러 휴식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="9ca3e-173">선택이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="9ca3e-174">업무 시간 통화 설정</span><span class="sxs-lookup"><span data-stu-id="9ca3e-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="9ca3e-175">사용자 지정 업무 시간 일정을 사용 하는 경우에는 업무 시간 통화 **처리** 페이지를 사용 하 여 근무 시간 후에도 통화 연결을 설정 해야 하며,이 경우 **업무 시간 통화 설정과**동일한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="9ca3e-176">업무 시간 중 조직의 자동 전화 교환에 연결 된 전화 번호로 전화할 때 들리는 인사말, 메시지 및 메뉴를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="9ca3e-177">![비즈니스 시간 통화 처리](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![페이지 업무 시간 호출 처리 페이지 동작 섹션 스크린샷의 스크린샷](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="9ca3e-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="9ca3e-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca3e-179"></span></span>

<span data-ttu-id="9ca3e-180">**인사말이** 업무 시간 인사말은 선택 사항이 며 **인사말 없음으로**설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="9ca3e-181">이 경우 호출자는 사용자가 선택한 작업 중 하나에서 호출을 처리 하기 전에 메시지 또는 인사말이 들리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="9ca3e-182">오디오 파일 (.wav, mp3 또는 .wma 형식)을 업로드 하거나 텍스트 읽어주기를 사용 하 여 사용자 지정 인사말을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="9ca3e-183">**오디오 파일 업로드** 이를 선택 하는 경우 인사말을 녹음 한 다음 오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="9ca3e-184">**인사말 메시지 입력** 이 옵션을 선택 하는 경우 시스템에서 읽을 텍스트를 입력 합니다 (최대 1000 자).</span><span class="sxs-lookup"><span data-stu-id="9ca3e-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="9ca3e-185">예를 들어 "Contoso 시작 '을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="9ca3e-186">귀하의 전화는 귀하에 게 중요 합니다. "</span><span class="sxs-lookup"><span data-stu-id="9ca3e-186">Your call is important to us."</span></span> <span data-ttu-id="9ca3e-187">**발신자가 들립니다** 상자를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-187">in the **Callers will hear** box.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="9ca3e-189">업무 시간 동안 도착 하는 전화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="9ca3e-190">다음 작업 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-190">You can chose from the following actions:</span></span>

<span data-ttu-id="9ca3e-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca3e-191"></span></span>

- <span data-ttu-id="9ca3e-192">**연결 해제** 이를 선택 하면 업무 시간 인사말이 들릴 때 전화를 거는 사용자의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="9ca3e-193">**통화 리디렉션** 이를 사용 하 여 자동으로 통화를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="9ca3e-194">Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 **전화 시스템** 라이선스가 있는 **회사의 사람** 입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="9ca3e-195">전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="9ca3e-196">이렇게 하려면 **회사에서 사람** 을 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="9ca3e-197">**회사 사용자** 는 비즈니스용 Skype 서버 2015 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="9ca3e-198">다른 **자동 전화 교환**</span><span class="sxs-lookup"><span data-stu-id="9ca3e-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="9ca3e-199">기존 자동 전화 교환을 사용 하 여 하위 메뉴를 포함 하는 두 번째 수준의 메뉴 옵션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="9ca3e-200">이를 중첩 된 자동 전화 교환 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-200">These are called nested auto attendants.</span></span> <span data-ttu-id="9ca3e-201">중첩 된 자동 전화 교환으로 통화를 보내려면 **회사에서 사용자** 를 선택 하 고 이미 연결 된 자동 전화 교환이 있는 리소스 계정이 나이 자동 전화 교환 만들기가 완료 되 면 자동 전화 교환에 연결 되도록 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="9ca3e-202">**재생 메뉴 옵션** 을 사용 하 여 재생 하려는 메시지를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![앞의 스크린샷은 설명선을 참조 하는 숫자 3의 아이콘](media/sfbcallout3.png)

<span data-ttu-id="9ca3e-204">**메뉴 프롬프트** 주 메뉴 프롬프트를 만들려면 텍스트 음성 변환 또는 오디오 파일 업로드 (.wav,. mp3 또는 .wma)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="9ca3e-205">**호출자의 메뉴 탐색 설정** 상자에 프롬프트를 입력 하거나 오디오 파일을 녹음/녹화할 수 있습니다 (예: "판매를 위해").</span><span class="sxs-lookup"><span data-stu-id="9ca3e-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="9ca3e-206">서비스의 경우 2를 누르거나 말을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-206">For Services, press or say 2.</span></span> <span data-ttu-id="9ca3e-207">고객 지원이 필요한 경우에는 3을 누르거나 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="9ca3e-208">연산자의 경우 0을 누르거나 말을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-208">For the operator, press or say 0.</span></span> <span data-ttu-id="9ca3e-209">이 메뉴를 다시 들으려면 star 키를 누르거나 "반복" 이라고 말 하세요. "</span><span class="sxs-lookup"><span data-stu-id="9ca3e-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="9ca3e-210">**인사말 메시지 입력** 이를 선택한 경우에는 시스템에서 읽을 텍스트 (최대 1000 자)를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="9ca3e-211">**오디오 파일 업로드** 이를 선택한 경우에는 인사말을 녹음 한 다음 오디오 파일 (.wav, mp3 또는 .wma 형식)을 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

<span data-ttu-id="9ca3e-213">**메뉴 옵션 설정** 키패드의 키 단추를 사용 하 여 메뉴 옵션을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="9ca3e-214">메뉴 옵션을 추가 하려면 **+ 다이얼 키 할당**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="9ca3e-215">해당 하는 옵션 행이 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="9ca3e-216">메뉴 옵션을 삭제 하려면 키패드 컨트롤에서 해당 키의 왼쪽을 클릭 하 고 위의 삭제 아이콘을 클릭 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="9ca3e-217">키 매핑 행이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="9ca3e-218">기존 메뉴 프롬프트에 대해 자동으로 수행 되지 않으므로 제거 옵션에 추가 하는 경우 메뉴 프롬프트 텍스트를 업데이트 하거나 오디오를 개별적으로 다시 기록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="9ca3e-219">모든 메뉴 옵션을 순서에 관계 없이 추가 하 고 제거할 수 있으며 키 매핑도 연속적으로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="9ca3e-220">예를 들어 옵션에 매핑된 키가 0, 1, 3 인 메뉴를 만들 수 있지만 키 2는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="9ca3e-221">키 \* (반복)와 \# (뒤로)는 시스템에 예약 되어 있으므로 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="9ca3e-222">음성 인식 기능을 사용 하는 경우 \*를 누르면 "Repeat"와 #이 "뒤로" 음성 명령에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="9ca3e-223">메뉴 옵션을 설정 하려면 다이얼 키를 선택한 후 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="9ca3e-224">옵션의 **음성 명령을** 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="9ca3e-225">이는 최대 64 자를 입력할 수 있으며 "고객 서비스" 또는 "작업 및 Grounds" 같은 여러 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="9ca3e-226">음성 인식 기능을 사용 하는 경우 자동으로 이름이 인식 되 고, 통화를 하는 사용자는 3을 눌러 "3" 이라고 말할 수 있으며, "고객 서비스" 라고 말할 때 키 3에 매핑된 옵션을 선택 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="9ca3e-227">해당 키를 누르거나 음성 인식을 사용 하 여 옵션을 선택한 경우 통화를 보낼 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="9ca3e-228">통화는 다음으로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-228">The call can be sent to:</span></span>

  - <span data-ttu-id="9ca3e-229">**연산자** If 연산자가 이미 설정 되어 있으면 키 0에 자동으로 매핑되지만, 삭제 하거나 다른 키에 다시 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="9ca3e-230">If 연산자를 아무 키로 설정 하지 않으면 음성 명령 "교환원"도 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="9ca3e-231">**회사에서** 엔터프라이즈 음성에 대해 사용 하도록 설정 되거나 Office 365에서 호출 계획을 할당 한 **전화 시스템** 라이선스가 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="9ca3e-232">전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="9ca3e-233">이렇게 하려면 **회사에서 사람** 을 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="9ca3e-234">**회사** 사용자는 비즈니스용 Skype 서버 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>

  - <span data-ttu-id="9ca3e-235">다른 **자동 전화 교환**</span><span class="sxs-lookup"><span data-stu-id="9ca3e-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="9ca3e-236">기존 자동 전화 교환을 사용 하 여 하위 메뉴를 포함 하는 두 번째 수준의 메뉴 옵션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="9ca3e-237">이를 중첩 된 자동 전화 교환 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-237">These are called nested auto attendants.</span></span> <span data-ttu-id="9ca3e-238">중첩 된 자동 전화 교환으로 통화를 보내려면 **회사에서 사용자** 를 선택 하 고 이미 연결 된 자동 전화 교환이 있는 리소스 계정이 나이 자동 전화 교환 만들기가 완료 되 면 자동 전화 교환에 연결 되도록 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - <span data-ttu-id="9ca3e-239">**음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-239">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 5의 아이콘](media/sfbcallout5.png)

<span data-ttu-id="9ca3e-241">**이름으로 전화 걸기** 이 옵션을 선택 하면에서 전화를 거는 사용자가 디렉터리 검색을 사용 하 여 조직 내 사용자를 검색할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-241">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="9ca3e-242">**전화 걸기 범위** 페이지에서 해당 옵션을 설정 하 여 전화를 걸 수 있거나 이름으로 사용할 수 없는 사람을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-242">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="9ca3e-243">**전화 시스템** 라이선스가 있는 모든 온라인 사용자 또는 비즈니스용 Skype 서버 또는 Lync server 2013을 사용 하 여 온-프레미스에 호스팅되는 사용자는 이름으로 전화 걸기를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-243">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="9ca3e-244">선택이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-244">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="9ca3e-245">명절 통화 설정</span><span class="sxs-lookup"><span data-stu-id="9ca3e-245">Holiday call settings</span></span>

<span data-ttu-id="9ca3e-246"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca3e-246"></span></span>

<span data-ttu-id="9ca3e-247">각 자동 전화 교환에 최대 20 개의 예정 휴일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="9ca3e-248">**조직도** > 에서 화면을**진행 하 여 공휴일을 만들거나** 새 통화 처리기를 만드는 과정에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![명절 통화 설정 페이지 스크린샷](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="9ca3e-251">이미 자동 전화 교환을 만든 경우에는이 목록에서 필요한 항목을 사용 하거나 편집할 수 있는 옵션이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="9ca3e-252">그렇지 않은 경우 새 통화 처리기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="9ca3e-253">새 호출 처리기를 추가 하려면 **+ 새 통화 처리기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![새 호출 처리기 추가를 보여 주는 스크린샷](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

<span data-ttu-id="9ca3e-256">새 창에서 화면 맨 위에 새 통화 처리기의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="9ca3e-258">명절의 이름이 **휴일** 풀 다운 목록에 이미 있는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="9ca3e-259">필요한 휴일 이름이 없는 경우에는 풀 다운 목록에서 **새 공휴일 만들기** 를 선택 하 고 새 공휴일이 표시 되는 새 명절에 대 한 이름과 날짜를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="9ca3e-260">준비가 되 면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="9ca3e-261">공휴일 이름은 최대 64 자로 구성 될 수 있으며 동일한 자동 전화 교환에 대해 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="9ca3e-262">예를 들어 같은 자동 전화 교환에서 "추수 감사절" 이라는 두 개의 공휴일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![앞의 스크린샷은 설명선을 참조 하는 숫자 3의 아이콘](media/sfbcallout3.png)

<span data-ttu-id="9ca3e-264">**인사말이** 인사말은 선택 사항이 며 **인사말 없음으로**설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="9ca3e-265">이 경우 발신자는 사용자가 선택 하는 옵션 중 하나에서 통화를 처리 하기 전에 메시지나 인사말이 들리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="9ca3e-266">오디오 파일 (.wav, mp3 또는 .wma 형식)을 업로드 하거나 텍스트 읽어주기를 사용 하 여 사용자 지정 인사말을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="9ca3e-267">**인사말 없음** 다른 사용자가 자동 전화 교환 전화 번호로 전화를 걸 때 인사말이 재생 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="9ca3e-268">**오디오 파일 업로드** 이를 선택 하는 경우 명절 인사말을 기록 하 고 오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="9ca3e-269">**인사말 메시지 입력** 이 옵션을 선택 하는 경우 시스템에서 읽을 텍스트를 입력 합니다 (최대 1000 자).</span><span class="sxs-lookup"><span data-stu-id="9ca3e-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="9ca3e-270">예를 들어 "새 해 아침에 행복!"를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="9ca3e-271">현재 사무실이 닫혔습니다. "</span><span class="sxs-lookup"><span data-stu-id="9ca3e-271">Our offices are currently closed."</span></span> <span data-ttu-id="9ca3e-272">**인사말 메시지 입력** 상자에</span><span class="sxs-lookup"><span data-stu-id="9ca3e-272">in the **Type a greeting message** box.</span></span>

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

<span data-ttu-id="9ca3e-274">**작업** 이 휴일 동안 도착 하는 통화에 대 한 진행 상황을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="9ca3e-275">다음 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-275">You can chose from the following options:</span></span>

- <span data-ttu-id="9ca3e-276">**연결 해제** 명절 인사말이 들릴 때 전화를 거는 사람이 연결 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="9ca3e-277">**통화 리디렉션** 이를 사용 하 여 자동으로 통화를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="9ca3e-278">Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 **전화 시스템** 라이선스가 있는 **회사의 사람** 입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="9ca3e-279">전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="9ca3e-280">이렇게 하려면 **회사에서 사람**을 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="9ca3e-281">**회사** 사용자는 비즈니스용 Skype 서버 2015 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="9ca3e-282">**음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="9ca3e-283">기본적으로 휴일 기간 중에 도착 하는 모든 통화는 인사말 이후 연결 해제로 설정 되므로 다른 동작이 필요 하면 리디렉션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a><span data-ttu-id="9ca3e-284">전화 걸기 범위 페이지 선택</span><span class="sxs-lookup"><span data-stu-id="9ca3e-284">Select dial scope page</span></span>

<span data-ttu-id="9ca3e-285">이 페이지에서 조직에 속한 사용자가 디렉터리에 나열 되 고 조직에 전화를 거는 사용자가 이름으로 다이얼을 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![전화 걸기 범위 페이지를 보여 주는 스크린샷](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="9ca3e-287">![](media/sfbcallout1.png) **포함** 옵션을 사용 하 여 이전 화면의 설명선을 참조 하는 숫자 1의 아이콘은 다음 두 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="9ca3e-288">**모든 온라인 사용자** 이 옵션을 사용 하면 조직 내 모든 사용자가 디렉터리 검색에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="9ca3e-289">**휴대폰 시스템** 라이선스가 있는 모든 온라인 사용자는 물론 비즈니스용 Skype를 사용 하 여 온-프레미스를 호스트 하는 사용자와 Office 365에서 호출 계획이 있는 Lync server 2013이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="9ca3e-290">사용자 **지정 사용자 그룹** 이 옵션을 사용 하는 경우 조직에서 만든 Office 365 그룹, 메일 그룹 또는 보안 그룹을 검색 하 고,이 Office 365 그룹, 메일 그룹 또는 사용자가 추가 된 온라인 사용자를 포함 하는 개인을 검색할 수 있습니다. \*\* \*\*Skype server 2015 또는 Lync server 2013를 사용 하 여 온-프레미스로 전화 시스템 라이선스 또는 호스팅</span><span class="sxs-lookup"><span data-stu-id="9ca3e-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="9ca3e-291">여러 개의 Office 365 그룹, 배포 목록, 보안 그룹을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

<span data-ttu-id="9ca3e-293">**Exclude** 옵션을 사용 하 여 다음 두 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="9ca3e-294">**없음** 이 옵션을 사용 하면 디렉터리 검색에서 온라인 사용자가 제외 됨이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="9ca3e-295">사용자 **지정 사용자 그룹** 이 옵션을 사용 하는 경우 조직에서 만든 Office 365 그룹, 메일 그룹 또는 보안 그룹을 검색할 수 있으며,이 Office 365 그룹, 메일 그룹 또는 보안 그룹에 추가 된 모든 사용자는 디렉터리 검색에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="9ca3e-296">여러 개의 Office 365 그룹, 배포 목록, 보안 그룹을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="9ca3e-297">사용자가 음성 인식을 사용 하 여 이름으로 전화 걸기를 사용할 때 새 사용자가 디렉터리에 이름을 나열 하는 데 최대 36 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="9ca3e-298">필요한 모든 필드를 입력 하 고 통화 처리 메뉴 및 옵션을 설정한 후 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="9ca3e-299">자동 전화 교환 편집 및 테스트</span><span class="sxs-lookup"><span data-stu-id="9ca3e-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="9ca3e-300">자동 전화 교환을 저장 하면 **자동 전화 교환** 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="9ca3e-301">이렇게 하면 이름, 전화 번호, 언어, 상태 등 설정한 일부 옵션을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="9ca3e-302">자동 전화 교환을 변경 하려는 경우 자동 전화 교환을 선택 하 고 작업 창에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="9ca3e-303">또한 작업 창의 **테스트** 단추를 사용 하 여 자동 전화 교환에 테스트 통화를 빠르게 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="9ca3e-304">자동 전화 교환 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9ca3e-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="9ca3e-305">Windows PowerShell을 사용 하 여 자동 전화 교환을 만들고 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="9ca3e-306">자동 전화 교환을 관리 하는 데 필요한 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="9ca3e-307">신규-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="9ca3e-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="9ca3e-308">Set-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="9ca3e-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9ca3e-309">Get-CsAutoAttendant 전화 교환</span><span class="sxs-lookup"><span data-stu-id="9ca3e-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9ca3e-310">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="9ca3e-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9ca3e-311">-CsAutoAttendant 전화 교환 제거</span><span class="sxs-lookup"><span data-stu-id="9ca3e-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9ca3e-312">새로운 CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="9ca3e-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="9ca3e-313">새로운 CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="9ca3e-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="9ca3e-314">새로운 CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="9ca3e-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="9ca3e-315">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="9ca3e-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9ca3e-316">새로운 CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="9ca3e-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="9ca3e-317">새로운 CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="9ca3e-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="9ca3e-318">새로운 CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="9ca3e-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="9ca3e-319">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="9ca3e-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="9ca3e-320">새로운 CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="9ca3e-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="9ca3e-321">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="9ca3e-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="9ca3e-322">가져오기-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="9ca3e-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9ca3e-323">새로운 CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="9ca3e-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="9ca3e-324">Windows PowerShell에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9ca3e-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="9ca3e-325">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9ca3e-326">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 Microsoft 팀을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9ca3e-327">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9ca3e-328">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="9ca3e-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="9ca3e-329">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9ca3e-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="9ca3e-330">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9ca3e-331">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9ca3e-332">Office 365 PowerShell을 사용 하 여 Office 365 관리</span><span class="sxs-lookup"><span data-stu-id="9ca3e-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="9ca3e-333">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="9ca3e-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="9ca3e-334">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9ca3e-334">Related topics</span></span>

[<span data-ttu-id="9ca3e-335">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="9ca3e-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="9ca3e-336">서비스 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="9ca3e-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="9ca3e-337">오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능 여부</span><span class="sxs-lookup"><span data-stu-id="9ca3e-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="9ca3e-338">새로운 CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9ca3e-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="9ca3e-339">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="9ca3e-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="9ca3e-340">Small business 예-자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="9ca3e-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
