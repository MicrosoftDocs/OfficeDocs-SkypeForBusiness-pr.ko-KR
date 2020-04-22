---
title: 인사말 및 전자 메일의 기본 언어 변경
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 비즈니스용 Skype를 설정 하 여 조직의 기본 음성 메일 인사말에 다른 언어를 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 1fb9a97c31e973d6a56da65d301324b1d9d34b90
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43752345"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="bf2e7-103">인사말 및 전자 메일의 기본 언어 변경</span><span class="sxs-lookup"><span data-stu-id="bf2e7-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="bf2e7-104">[Office 365 전역 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)인 경우 비즈니스용 Skype를 설정 하 여 다른 언어로 기본 음성 메일 인사말을 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="bf2e7-105">기본 시스템 인사말은 "John Smith에 게 메시지를 남기기 주십시오." 라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="bf2e7-106">발신음을 확인 한 후 메시지를 기록 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-106">After the tone, please record your message.</span></span> <span data-ttu-id="bf2e7-107">녹화를 완료 하거나, 전화를 끊거나, 더 많은 옵션을 보려면 파운드 키를 누릅니다. "</span><span class="sxs-lookup"><span data-stu-id="bf2e7-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="bf2e7-108">**먼저 다음과 같은 중요 한 정보를 읽어 보세요.**</span><span class="sxs-lookup"><span data-stu-id="bf2e7-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="bf2e7-109">**사용할 수 있는 언어는 조직의 위치에 따라 결정 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="bf2e7-110">예를 들어 미국에 거주 하는 조직의 경우 기본 언어를 영어 또는 스페인어로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="bf2e7-111">조직이 캐나다에 거주 하는 경우에는 영어와 프랑스어 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="bf2e7-112">지원 되는 언어 목록은 [비즈니스용 Skype에서 음성 메일 인사말 및 메시지에 대 한 언어](languages-for-voicemail-greetings-and-messages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="bf2e7-113">**조직의 한 사용자만 시스템 언어를 변경할 수 있는 방법은 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="bf2e7-113">**There's no way to change the system language for only one person in your organization.**</span></span> <span data-ttu-id="bf2e7-114">조직의 모든 사용자에 대 한 인사말만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-114">You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bf2e7-115">사용자는 로그인 한 후 설정을 통해 자신의 인사말 언어를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="bf2e7-116">**보내는 보이스 메일 메시지를 녹음 하 고 싶으신가요?**</span><span class="sxs-lookup"><span data-stu-id="bf2e7-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="bf2e7-117">[비즈니스용 Skype 음성 메일 및 옵션 확인](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="bf2e7-118">Microsoft 팀의 경우-사용자가 [팀 데스크톱 클라이언트 설정](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) 에서 보이스 메일 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="bf2e7-119">**보이스 메일 메시지의 언어를 변경 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="bf2e7-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="bf2e7-120">비즈니스용 Skype [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) For **Prompt 언어**아래에서 새 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="bf2e7-121">Microsoft 팀의 경우-사용자가 [팀 데스크톱 클라이언트 설정](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) 에서 보이스 메일 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="bf2e7-122">조직의 모든 사용자에 대 한 시스템 언어 변경</span><span class="sxs-lookup"><span data-stu-id="bf2e7-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="bf2e7-123">에서 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) [Office 365 전역 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-123">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="bf2e7-124">Microsoft 365 관리 센터에서 **설정** > **설정** > **조직 프로필**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-124">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![설정 선택 및 조직 프로필을 보여 주는 스크린샷](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="bf2e7-126">**편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-126">Choose **Edit**.</span></span>
    
    ![편집 옵션을 보여 주는 스크린샷](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="bf2e7-128">조직의 모든 사용자에 대 한 **기본 설정 언어** 목록에서 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="bf2e7-129">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2e7-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="bf2e7-130">관리자를 위한 관련 문서</span><span class="sxs-lookup"><span data-stu-id="bf2e7-130">Related articles for the admin</span></span>

- [<span data-ttu-id="bf2e7-131">전화 시스템 및 통화 플랜</span><span class="sxs-lookup"><span data-stu-id="bf2e7-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="bf2e7-132">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="bf2e7-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="bf2e7-133">비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 Office 365의 전화 시스템 계획</span><span class="sxs-lookup"><span data-stu-id="bf2e7-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="bf2e7-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bf2e7-134">Related topics</span></span>

- [<span data-ttu-id="bf2e7-135">비즈니스용 Office 365에서 표시 언어 및 표준 시간대 변경</span><span class="sxs-lookup"><span data-stu-id="bf2e7-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="bf2e7-136">[Office 2010 이상에서 언어 추가 또는 언어 기본 설정 지정](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="bf2e7-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="bf2e7-137">키보드 레이아웃 언어 사용 또는 변경</span><span class="sxs-lookup"><span data-stu-id="bf2e7-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
