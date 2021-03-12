---
title: 시작 마법사를 사용하여 Business Voice 설정하기
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
- m365initiative-voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a3a5162f46631e00e6ffc22c19654908b4cb78b
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726239"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="0344f-102">시작 마법사를 사용하여 Business Voice 설정하기</span><span class="sxs-lookup"><span data-stu-id="0344f-102">Use the Getting Started wizard to set up Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0344f-103">이 문서의 정보는 통화 플랜이 **포함된** Business Voice에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="0344f-104">통화 플랜이 포함된 Business Voice는 선택된 국가 및 지역에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="0344f-105">이 문서를 읽기 전에 [Business Voice의 국가 및 지역 가용성](country-region-availability.md)을 확인하여 해당 국가 또는 지역에서 통화 플랜이 포함된 Business Voice를 지원하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0344f-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="0344f-106">테넌트가 통화 플랜을 포함한 Business Voice를 지원하지 않는 국가 또는 지역에 있는 경우 [Microsoft 리셀러 또는 파트너에게 도움 받기](reseller-partner-support.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0344f-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="0344f-107">Microsoft 365 Business Voice용 시작 마법사를 사용하면 Microsoft Teams에서 전화를 걸고 받도록 빠르게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-107">The Getting Started wizard for Microsoft 365 Business Voice gets you set up quickly to make and receive phone calls in Microsoft Teams.</span></span> <span data-ttu-id="0344f-108">갓 시작한 중소기업에서는 마법사를 사용해 몇 분 안에 전화번호, 통화 메뉴, 인사말 등을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-108">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="0344f-109">전화 통신 솔루션을 구축한 대기업의 경우 모든 사용자를 위해 Business Service를 설정하기 전에 마법사를 통해 파일럿을 설정하여 일부 사용자가 먼저 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-109">If you're a larger business with an established telephony solution, the wizard can help you set up a pilot so a few users can try Business Voice before you roll it out for everyone.</span></span> <span data-ttu-id="0344f-110">두 경우 모두 마법사가 완료되면 Business Voice 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-110">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="0344f-111">마법사를 시작하기 전에 이 문서를 읽는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-111">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="0344f-112">마법사를 실행할 준비가 되면 [Microsoft 365 Business Voice 시작](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) 페이지에서 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-112">When you're ready to run the wizard, select **Get started** on the [Get started with Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) page.</span></span> <span data-ttu-id="0344f-113">구독을 만들 때 사용한 계정 또는 전역 관리자인 다른 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-113">Sign in by using the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0344f-114">Microsoft Teams와 Business Voice는 사용자의 사서함이 Microsoft 365에 있는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-114">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="0344f-115">온-프레미스 Exchange 서버의 사서함은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-115">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="0344f-116">시작 마법사에서는 비즈니스용 Skype 하이브리드 배포를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-116">The Getting Started Wizard doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="0344f-117">비즈니스용 Skype 하이브리드 배포가 있고 비즈니스 음성을 설정하려는 경우 [조직에서 전화 시스템 설정](../setting-up-your-phone-system.md)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0344f-117">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

<span data-ttu-id="0344f-118">지금 바로 사용자 정의할 것이 없는 경우, 설정이 완료되었습니다!</span><span class="sxs-lookup"><span data-stu-id="0344f-118">If you don't want to customize anything immediately, you're done!</span></span> <span data-ttu-id="0344f-119">Business Voice를 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-119">You can start using Business Voice right away.</span></span>

## <a name="emergency-services-location"></a><span data-ttu-id="0344f-120">긴급 서비스 위치</span><span class="sxs-lookup"><span data-stu-id="0344f-120">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="0344f-121">긴급 주소를 변경하려면 <b>편집</b>을 클릭하고 새 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-121">If you want to change the emergency address, click <b>Edit</b>, and then enter a new address.</span></span> <span data-ttu-id="0344f-122">입력하는 주소는 긴급 대응 서비스에 적절하며 형식이 올바른지 확인을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-122">The address that you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="0344f-123">그런 다음 이 주소는 다음 단계에서 번호를 할당한 모든 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-123">This address is then assigned to all users that you assign a number to in the next step.</span></span> <span data-ttu-id="0344f-124">둘 이상의 위치에 직원이 있는 경우 시작 마법사를 준비한 후 더 많은 긴급 주소를 추가하고 할당하려면 <a href="./customize-business-voice.md">Business Voice 디자인 사용자 지정</a>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0344f-124">If you have employees in more than one location, see <a href="./customize-business-voice.md">Business Voice design customization</a> to add and assign more emergency addresses after you prepare the Getting Started wizard.</span></span></td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400" alt="wizard choose number"></td></tr>
</table>

<span data-ttu-id="0344f-125">자세한 내용은 [긴급 위치, 주소 및 통화 라우팅이 무엇인가요?](../what-are-emergency-locations-addresses-and-call-routing.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0344f-125">For more information, see [What are emergency locations, addresses, and call routing](../what-are-emergency-locations-addresses-and-call-routing.md)?</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="0344f-126">회사 전화번호</span><span class="sxs-lookup"><span data-stu-id="0344f-126">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="0344f-127">새 현지 전화번호 외에도 무료 전화 번호를 구입하거나 기존 번호를 Microsoft 365로 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-127">In addition to a new local phone number, you can purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="0344f-128">무료 전화 번호를 설정하려면 커뮤니케이션 크레딧을 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-128">To set up a toll-free number, you need to purchase Communications Credits.</span></span> <span data-ttu-id="0344f-129">하나 이상의 번호를 Microsoft 365로 이식하려면 마법사가 완료된 후 <a href="https://admin.teams.microsoft.com">팀 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-129">To port one or more numbers to Microsoft 365, go to the <a href="https://admin.teams.microsoft.com">Teams admin center</a> after the wizard finishes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400" alt="choose number">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="0344f-130">기존 전화번호를 Microsoft 365로 이식하도록 선택해도 마법사에 임시 전화번호가 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-130">If you port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="0344f-131">예상된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-131">This is expected.</span></span> <span data-ttu-id="0344f-132">마법사와 이식 절차를 완료하면 임시 전화 번호가 기존 번호로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-132">After you complete the wizard and the porting process, the temporary phone number will be replaced by the pre-existing number.</span></span>

## <a name="user-licenses"></a><span data-ttu-id="0344f-133">사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="0344f-133">User licenses</span></span>

<table>
    <tr>
        <td><span data-ttu-id="0344f-134">사용자 라이선스를 할당하려면 Teams 외부와 통화(예: 공급업체에 전화)가 필요한 조직의 일원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-134">To assign user licenses, select the people in your organization who need to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="0344f-135">사용 가능한 만큼의 Business Voices 라이선스만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-135">You can only assign as many Business Voices licenses as you have available.</span></span> <span data-ttu-id="0344f-136">라이선스가 더 필요한 경우 마법사가 완료된 후 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-136">If you need more, you can buy additional licenses after the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400" alt="get numbers">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="0344f-137">마법사가 완료된 후 기존 전화 번호를 Microsoft 365로 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-137">You can port existing phone numbers to Microsoft 365 after the wizard is finished.</span></span> <span data-ttu-id="0344f-138">이식 절차를 완료하면 마법사가 제공한 임시 전화번호가 이식된 전화번호로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-138">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers that the wizard provided.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="0344f-139">수신 전화 인사말</span><span class="sxs-lookup"><span data-stu-id="0344f-139">Incoming-call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="0344f-140">5MB 이하의 음성 파일(MP3 또는 WAV)을 업로드해 전화 인사말로 사용할 수 있습니다. 또는 인사말을 텍스트로 입력하면 Microsoft 365가 TTS 기능을 사용해 발신자에게 읽어줍니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-140">You can upload a sound file (MP3 or WAV) of up to 5 Megabytes (MB) to use as a call greeting, or you can type your greeting, and Microsoft 365 will use text-to-speech to read it to the caller.</span></span> <span data-ttu-id="0344f-141">인사말은 발신자가 회사 전화번호로 전화를 걸었을 때 처음 듣게 되는 소리입니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-141">The greeting will be the first thing callers hear when they call your company phone number.</span></span> <span data-ttu-id="0344f-142">TTS(텍스트 음성 변환)의 경우 발음을 정확히 하기 위해 표음식 철자를 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-142">For text-to-speech, you might need to use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400" alt="greeting">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="0344f-143">통화 메뉴 및 착신 전환</span><span class="sxs-lookup"><span data-stu-id="0344f-143">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="0344f-144">모든 통화를 특정 사용자에게 착신 전환하거나, 발신자가 옵션을 선택할 수 있도록 메뉴를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-144">You can forward all calls to a specific user, or you can set up a menu that the caller can choose options from.</span></span> <span data-ttu-id="0344f-145">통화 메뉴를 만드는 경우 발신자가 음성 또는 전화 키패드의 번호를 눌러 선택할 수 있는 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-145">If you create a call menu, you specify options that the caller can select by voice or by pressing a number on a phone's keypad.</span></span> <span data-ttu-id="0344f-146">각 메뉴 옵션은 특정 사용자에게 착신 전활할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-146">Each menu option can forward calls to a specific user.</span></span><br><br>
        <span data-ttu-id="0344f-147">발신자에게 지침을 제공하는 5MB 이하의 음성 파일(MP3 또는 WAV)을 업로드하거나 지침을 텍스트로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-147">You can upload a sound file (MP3 or WAV) of up to 5 MB that gives instructions to the caller, or you can type the instructions.</span></span> <span data-ttu-id="0344f-148">Microsoft 365는 텍스트 음성 변환을 사용하여 발신자에게 지침을 읽어줍니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-148">Microsoft 365 will use text-to-speech to read them to the caller.</span></span> <span data-ttu-id="0344f-149">발음을 정확히 하기 위해 발음에 맞는 철자를 입력해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-149">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400" alt="call forwarding">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="0344f-150">시작 마법사를 사용하면 빠르게 실행할 수 있는 간단한 통화 메뉴를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-150">The Getting Started wizard helps you set up a simple call menu to get you up and running quickly.</span></span> <span data-ttu-id="0344f-151">통화 메뉴를 설정하려는 번호가 여러 개인 경우나 좀 더 복잡한 통화 메뉴(자동 전화 교환)를 설정하려는 경우는 마법사를 완료한 후 [클라우드 자동 전화 교환 설정](set-up-auto-attendants.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0344f-151">If you have multiple phone numbers that you want to set up call menus for or you want to set up more complex call menus (also called auto attendants), see [Set up a Cloud auto attendant](set-up-auto-attendants.md) after you finish the wizard.</span></span>

<table>
    <tr>
        <td> <p><span data-ttu-id="0344f-152">시작 마법사는 입력한 정보를 사용하여 Business Voice를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-152">The Getting Started wizard takes the information that you enter and sets up Business Voice.</span></span> <span data-ttu-id="0344f-153"><b>개요</b> 페이지에서 사용자에게 할당되는 전화번호를 확인하고, 통화 메뉴를 살펴보고, 인사말을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-153">On the <b>Overview</b> page, you can see what phone numbers are assigned to your users, look at your call menu, listen to your greeting, and more.</span></span></p>
             <p><span data-ttu-id="0344f-154">설치하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-154">Setup takes several minutes.</span></span> <span data-ttu-id="0344f-155"><b>완료</b>를 선택하면 백그라운드에서 Business Voice가 계속 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-155">If you select <b>Done</b>, we'll continue to set up Business Voice in the background.</span></span> <span data-ttu-id="0344f-156">또는 설치가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0344f-156">Or just wait until setup is finished.</span></span> <span data-ttu-id="0344f-157">설정이 완료되면 <a href="https://admin.teams.microsoft.com" target="_blank">Teams 관리 센터</a>에서 <b>음성</b>으로 이동하여 더 많은 Business Voice 기능을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="0344f-157">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400" alt="finish page">
        </td>
    </tr>
</table>
